---
layout: post
title: Net Neutrality:Beyond the FCC's 2010 Open Internet Order
tags: [politics, computers]
---

**For the purposes of this post I will use the term ISP to mean last mile residential ISPs.  Business ISPs, non-residential last mile ISPs, IXPs and Tier-1 providers, are not included in this definition.**

## Introduction 

In 2010 the FCC established 3 rules for ISPs regarding the Open Internet and network neutrality.  These rules are called the FCC's Open Internet Order 2010.  The first rule is transparency.  ISPs must disclose their bandwidth management practices and performance characteristics.  The second rule is no blocking.  ISPs must not block traffic based on source, destination or application.  The third rule is no discrimination.  ISPs must not bias certain traffic based on source, destination or application.  These rules exclude 'reasonable network management practices', thereby allowing ISPs to take reasonable measures to insure continued service and protect against abuse.  
<br/>

On January 14, 2014 the U.S. Court of Appeals for the D.C. Circuit vacated rules two and three.  Ruling that the FCC did not have authority to regulate broadband providers in this manner.  For the purposes of this post, we're going to assume this court case was found in favor of the FCC, and that all three rules survived the court's scrutiny.  
<br/>

The question then becomes; what kinds of other tricks will ISPs play in order to bias or block traffic, and what can consumers do about it?   
<br/>

ISPs have an interest in biasing traffic, through price discrimination they can not only raise their margins, but also force competitors out of other markets.  As the ISP market in the United States has consolidated, many ISPs have become more vertically integrated, and are now in markets other than providing Internet access.  This puts American ISPs in the unique position of being able to interfere with how an application competitor reaches their customers.  ISPs can charge rents to application providers who require access to the last mile, and leverage their monopoly of the last mile for other business units in the now vertically integrated ISP.  This is exactly what the Comcast Netflix conflict is about.  Comcast can extract rents from Netflix as an application provider, and Comcast can degrade Netflix's service thereby promoting Comcast's own video on demand service and cable TV.  
<br/>

The easiest way for an ISP to bias traffic without breaking any of the FCC's three rules is to simply drop it due to bandwidth constraints.  If an ISP wants to favor traffic to network X and punish traffic to network Y, they just make more bandwidth available to X.  Traffic destined for X will be dropped once the pipe to X is filled.  Nothing in the FCC's three rules prevents this blatantly discriminatory behavior.  Attempting to regulate this kind of bad behavior by delving into the complexities of BGP and Internet peering would not only fail, but fuel further resentment against regulatory intervention.  Attaining this idealized platform behavior requires examining the problem from the perspective of the consumer.  If we want to ensure consumers receive unbiased connectivity, we need to define a way to measure that connectivity for individual subscribers.  Then boil it down to a single simple rating.  
<br/>

Therefore this post does not propose additional regulation, or additional rules by which the FCC could regulate ISPs.  Instead this post introduces a peer-produced method for measuring and communicating a generalized neutrality rating for ISPs.  We borrow concepts from the Nielsen Ratings system and bandwidth economics to craft a simple rating that non-technical consumers can use to determine how neutral their ISP is behaving.  We also rely on two current efforts to measure Internet traffic, Project Bismark[^1] and mLab[^2].  
<br/>

This post will begin with an explanation on determining consumer common bandwidth usage.  Then explain how we can performance test the ISP with regards to this usage.  Finally, we explain how to express the ISP's neutrality using the Gini coefficient.  

## Measuring

Central to determining how well an Internet connection works for common subscribers is determining what a common subscriber is.  Borrowing heavily from the methodology of the established Nielsen ratings system, our proposal would position network probes at a statistically significant number of subscribers of our target ISP.  We call these probes Customer Premise Equipment(CPE) monitors.  Project Bismark, an open source measuring toolkit based on OpenWRT, can be used for the probe.  
<br/>

These probes would monitor bandwidth usage in a time independent aggregate form, both ingressing and egressing a given subscriber's CPE.  The purpose of these measurements is to determine the bandwidth utilization of the target ISP's boundaries in relation to one another.  A boundary is where the ISP's administrative domain ends, and another begins.  It is typically a point-to-point link to a transit provider, or a switch port in an IXP.  Given that many ISPs contain multiple BGP AS's this may, or may not, correspond with a BGP AS boundary.  
<br/>

An ISP subscriber generally communicates with multiple Internet services through multiple boundaries.  The probe would measure download and upload bandwidth to each service, then combine services using the same boundary, where boundary per service is determined via traceroute.  The bandwidth for each boundary is then divided by the total bandwidth used, yielding a percentage for each boundary.  By combinining the ratios of (boundary bandwidth / total bandwidth) from a statistically significant number of subscriber probes, a generalizated utilization per-boundary can be inferred for our ISP.  Bandwidth measured corresponds with demand, so we call this our demand distribution, where each item represents (boundary demand / total demand).  
<br/>

This is relevant because this is how our target ISP should be provisioning bandwidth.  For example, assume our target ISP has three boundaries with relative utilzation of 25%, 25% and 50%, respectively.  They should be provisioning bandwidth for each of these boundaries as close to 25%, 25% and 50% as possible.  Otherwise they're most likely engaging in bad behavior.  Keep in mind these measurements are relative to total bandwidth utilization and do not take into account absolute overall bandwidth.  This would only ensure a similar level of service for each boundary.  It would not ensure any absolute level of service.  

## Testing

Now that we have which boundaries our subscribers use to reach their services, we must now determine how much bnadwidth our target ISP provisions for each boundary.  
<br/>

In addition to the probes measuring bandwidth usage, we deploy traffic generators which periodically generate packets to mLab servers directly behind each boundary.  These can be the same devices as the CPE monitors.  The goal is to measure throughput between each traffic generator and each boundary.  Ideally each mLab server would be directly outside the target ISP's administrative domain, a single hop away from the boundary, or as close as possible in the adjacent network.  This traffic generation would happen at random times of the day since Internet traffic is heavily time of day dependent, and would encompass both sending and receiving traffic.  
<br/>

The amount of traffic each generator generates will correspond with the ratio of boundary bandwidth to total bandwidth that we determined by measuring usage patterns with our CPE monitors.  Traffic generated will match aggregate demand.  For example, assume boundaries X, Y, and Z are reachable from this CPE generator, and those represent 5%, 10%, and 10% of the ISPs aggregate bandwidth demand, respectively.  Our generator will then generate and receive 20% of its packets from X, 40% from Y, and 40% from Z.  We record the percentage of lost packets per boundary, and combine the scores for each boundary from all generators into an average for each boundary.  This gives us an average level of service per-boundary that's based on actual subscriber demand.  We call this our bandwidth shortage distribution, since it represents where demand was not met with supply.  
<br/>

Taken in the aggregate, these percentages should be roughly equal.  If our target ISP is delivering service irrespective of its own interests it should be dropping a similar amount of packets at all boundaries.  If a majority of packets sent to one boundary are being dropped, while a majority of packets sent to another boundary are not dropped, then the ISP is probably engaging in bad behavior.  Since the amount of packets we're sending through a given boundary directly corresponds to the amount of packets consumers are sending in aggregate, if the ISP is remaining neutral, we should have somewhat equal amounts of packet drops between all boundaries.  
<br/>

An obvious question at this point might be; What if our aggregate of users are being throughput limited to a popular service, won't we then only measure that limited throughput on our monitor probes?  If our target ISP limits bandwidth to a popular service we will only measure that limited usage on our probes, so we might then incorrectly assume that this service is less popular based on bandwidth usage.  In actuality, users want more of this service, but due to constant packet drops the probe only measures their limited bandwidth.  One could argue that all an ISP need do is keep every upstream link completely saturated all the time.  Thereby causing our CPE monitors to measure constrained demand and mistake it for actual demand.  
<br/>

This is not a problem, and again highlights our focus on relative measurements, and relative packet generation.  Internet traffic is bursty, and largely time dependent.  There are specific times when users are busy, and times when they are not.  However, ISPs buy bandwidth using what's called the 95% rule[^3].  Bandwidth usage is sampled on a continual basis, and in a given billing cycle an ISP is not charged for their busiest 5% of samples.  They are instead charged at the 95% mark.  This encourages purchasers of Internet transit to not have their upstream links saturated all the time, since then the 95% mark would be the same as the 100% mark, and they would not receive the discount offered by their upstream provider for burstiness.  Therefore, besides the indiscriminately terrible customer experience it would ensure, we can assume ISPs will not game the system by saturating all of their upstream links due to the 95% rule governing Internet transit bandwidth pricing.  

## Communicating

Now that we have determined how much traffic subscribers demand at each boundary, and how well our target ISP meets that demand, we need to communicate this knowledge in a clear manner to consumers.  We do this by calculating the Gini coefficient over the bandwidth shortage distribution.  
<br/>

Although usually used for determining inequality of wealth distributions, the Gini coefficient is effective at distilling inequality in any distribution.  Low Gini values indicate equality while high values indicate inequality.  We are only concerned with the relative equality delivered by an ISP's boundary connections.  Therefore, by calculating the Gini coefficient across our shortage distribution we can determine if a given ISP boundary is unequally dropping packets, as compared to all other ISP boundaries.  
<br/>

This Gini coefficient can then be communicated as a single quantifier for consumers to gauge a target ISP's neutrality.  Consumers can come to understand that a high number is bad, while a low number is good.  No further understanding of networking, or math, is required on the part of consumers.

### Clarifications and Limitations

This post plays rather loose with definitions of bandwidth and throughput.  These words have specific definitions which may or may not be interchangable, but unfortunately a full discussion of these terms falls outside this post's scope.  This post also completely ignores issues of latency, jitter and implications of possible ISP action on real-time applications.  This also falls outside the scope of this post.  However, it should be noted that both latency and jitter improve as bandwidth increases.  Improved jitter can be directly correlated with improved latency, and improved latency can be directly correlated with faster link speeds.  Since increasing bandwidth generally requires increasing link speeds, and not just aggregating links, this post focuses on bandwidth as the greatest determinant of service level.

### Conclusion

I have presented a method for determining neutrality of ISPs.  This method does not prescribe new regulations, or any centralized state action, but instead manifests as a peer produced bandwidth monitoring and measuring system.  Its purpose is to not to punish ISPs who behave badly, but instead to provide relevant information to consumers and policy makers concerning the neutrality of ISP interconnection.

[^1]: [Project Bismark](http://projectbismark.net/)
[^2]: [mLab](http://www.measurementlab.net/)
[^3]: Norton, William B. The Internet Peering Playbook:Connecting to the Core of the Internet. Palo Alto: DrPeering Press, 2011. Print
