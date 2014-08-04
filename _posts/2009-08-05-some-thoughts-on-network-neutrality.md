---
layout: post
title: Some Thoughts on Network Neutrality
tags: [politics, computers]
---
There is a new debate brewing over net neutrality and I thought it time I offered up some of my opinions on this subject.  As both a consumer of ISP services and a frequent consultant to ISPs I can hopefully provide a nuanced perspective on this debate. My experience is global so the scope of this article is global. I will start by identifying the actors in this debate and their interests. Then I will provide reasons why I believe transparency and competition can negate most of this debate. I will then end with some suggestions for legislators and an acronym filled look into the future. 

### The Providers

Internet Service Providers(ISPs) are the companies that deliver our internet connectivity. Their existence as well as what they provide us are being increasing viewed as public infrastructure akin to energy or waste disposal. Most ISPs service both business and residential customers and the services they provide vary greatly by cost as well as delivered bandwidth. It's not unusual for a business customer of an ISP to receive money back when they experience an outage. Whereas it's practically unheard of for a residential subscriber to ever receive money back for anything. In this way almost all ISPs exist in two distinct markets simultaneously. They have residential customers who pay little and might occasionally lose connectivity or be disrupted, and they have business customers who pay significantly more and have very little patience for downtime or disruption. In the ISP world, as in other service industries, you get what you pay for.  
<br/>

An ISPs wants to minimize investment and maximize returns. So ISPs want to buy new equipment and lay or lease new connections only when absolutely necessary and only when they can be guaranteed a return on investment. All ISP networks are oversubscribed for residential customers. What this means is that the ISP that sells you 10Mb/s downstream is not actually selling you a leased line of 10Mb/s from their internet peering point to your doorstep. The line you have running from your house to the first device the ISP owns might be capable of 10mb/s. But from then on your traffic is mixed with the traffic of all the other residential customers from that ISP. When your traffic eventually leaves the ISP it is most likely squeezed down even further since fat pipes to internet peering points are expensive. The ratio of oversubscription might be 2:1. Which means that customers can create twice as much traffic as the ISPs network can handle. Or to put it another way if every customer were to use all of their available bandwidth at the same time half of it would be dropped. Typically oversubscription ratios are much higher than 2:1 and might range as high as 20:1.  An ISPs oversubscription rate is its margin. If an ISP that can support 10,000 subscribers on its network doesn't want to buy more hardware and leased lines to support 20,000 subscribers it just doubles its oversubscription rate.  
<br/>

Oversubscription isn't all bad. When I was a student at university I remember learning and being amazed by the fact that my university could only deliver 26 dial tones at any given instant. The university had around 20,000 landlines it was supplying and I was amazed that it could only handle 26 of those landlines going [off-hook](http://en.wikipedia.org/wiki/Off-hook) at the exact same time. But everyone always had a dial tone when they picked up a phone since no more than 26 people would ever need dial tone at the exact same instant. I wouldn't even consider 26 dial tones for 20,000 people an oversubscribed voice network. This was just the agreed upon dial tone capacity for 20,000 landlines at a university. And voice networks are regulated much more heavily than data networks because if I need to call an ambulance or the police I better have dial tone when I pick up the phone.  
<br/>

Studies have shown that bandwidth usage for residential data customers varies greatly with time of day. Most internet usage in western countries peaks between 7-10pm local time. Since most people's 'internet time' is after dinner and before going to bed. It simply doesn't make economic sense for an ISP to build a 1:1 subscribed network for its residential users since most residential users don't use all of their bandwidth all of the time.

### Residential ISP Subscribers

There is no average residential ISP subscriber. The range of applications that people use on the internet has increased greatly in the last decade and will continue to increase. But all internet applications can basically be broken down into two distinct groups;bandwidth bound applications and latency bound applications. Bandwidth bound applications are those that require large amounts of bandwidth but that are not bothered by high latency. Latency bound applications are those that require low latency but that do not need high bandwidth. Don't get confused with the terms 'high' and 'low'. High bandwidth is good, while low latency is good. The most common example of a bandwidth bound application is file-sharing or ftp downloads. While the most common example of a low latency bounded application is Voice over IP(VoIP) or its most common brandnomer Skype. Something like streaming HD video across the public internet would be both bandwidth and latency bound. But once you buffer it at the destination it is no longer latency bound. For a more complete technical discussion about bandwidth and latency try [here](http://compnetworking.about.com/od/speedtests/a/network-speed.htm)  
<br/>

Residential internet consumers don't purchase internet connectivity based on guarantees of latency. All a typical residential internet consumer sees when they purchase an internet connection is a marketed bandwidth value like 10Mb/s. This value may or may not have any actual bearing on reality since ISPs typically exaggerate these values. ISPs don't even bother mentioning to their customers anything concerning latency.  If they did most consumers wouldn't know how to interpret it or how it relates to their internet application experience. Some subscribers are going to be using bandwidth bound applications while others are going to be using latency bound applications. Some subscribers are going to be using both and others are going to be using neither. The interests of each group are going to be different and its a practical impossibility to please all groups.

### Net Neutrality Folks

As far as I can tell the people pushing for net neutrality want 2 things.
1.They don't want any biasing of traffic based on destination site. Given [advances in technology](http://arstechnica.com/tech-policy/news/2009/08/network-neutrality-dead-in-practice-as-most-isps-throttle.ars) concerning deep-packet-inspection(DPI) ISPs might be able to strike deals with specific internet sites to positively or negatively bias traffic going there. This would have the net effect of an ISPs subscribers having a better experience at one internet site versus another. Maybe the Google search page loads faster than the Yahoo search page because Google paid this ISP to make it so.  
<br/>

2.They don't want any biasing of traffic based on application. Their argument is that ISPs are strictly dumb transport and they have no right to bias traffic based on application. Even insuring that latency bound applications don't get squeezed out by bandwidth hungry applications is bad. Any kind of traffic prioritization based on application need is bad.  
<br/>

I completely agree with position 1 taken by the net neutrality folks. Biasing traffic based on destination will lead to fragmentation of the public internet and back room dealing between large content providers and large ISPs. It is only in the best interests of large established content providers and large established ISPs to bias traffic based on destination. Any ISP that engages in this behavior should be charged under anti-monopoly laws in the countries they operate. This behavior is dangerous to the public good and the continued development of the public internet. It's akin to Standard Oil offering increased rail rates to transport the oil of competitors for which they were ruled a monopoly. The scariest part about it is its opaque nature. There is no way for a subscriber to know if their ISP is favoring traffic to one destination or another.  
<br/>

I do not completely agree with position 2 taken by the net neutrality folks. Given what we already know about the economics of ISPs they must bias traffic based upon application in order to turn a profit. It's unrealistic to expect ISPs to treat all traffic equally. It's also unrealistic for ISPs to build out their networks in such a way to avoid oversubscription. If ISPs were to stop biasing traffic based on application than customers running latency bound applications would suffer. And if we expect ISPs to build out their networks to 1:1 subscription levels we must be willing to pay for it as consumers. Why should an ISP invest money in new equipment and links if they are only saturated at peak times? And why should an ISP invest money in new equipment and links if only a small percentage of their user base is going to need it? Forcing ISPs to do this through regulation will have the net effect of forcing regular users to subsidize power users. Since the costs incurred by the ISP to upgrade its infrastructure will be spread among all users.

### Transparency

What ISP subscribers and the public need more than anything else is complete honesty and transparency in what ISPs are actually doing with their traffic. Business users have service level agreements(SLA) with their ISP to insure that they receive the level of service that they pay for. Residential subscribers need something similar to that only with less hassle and at a much lower level of service. Currently there is no way for a residential subscriber to know what actual service the ISP is giving them. The marketed bandwidth values that ISPs use to entice new customers are approximations at best and entirely arbitrary at worst. Consumers must rely on anecdotal evidence from forums and friends to find out what upload and download rates they can honestly achieve.   
<br/>

My suggestions for what ISPs should disclose are the following:

 1. Actual speed of the last-mile. This is usually the marketed bit rate that ISPs use to entice us into their service but it doesn't necessarily have to be. Subscribers have a right to know exactly how much traffic their last mile can handle.
 2. Oversubscription ratio. Right now ISPs are scared to publish this kind of information. So the only fair way to handle it would be to make all ISPs in a given market publish it at the same time.
 3. The how and why of traffic shaping the ISP is engaged in. How is the ISP shaping traffic and why is it doing so?

If all ISPs in a given market were forced to be as honest to their residential subscribers as they typically are to their business subscribers a few good things would happen.

 1. Consumers would be able to make decisions based on actual facts. Always a good thing.
 2. Different tiers of residential subscriber would be created for power users and regular users. Right now the only tiers we have are based on the marketed bandwidth values. But power subscribers currently have no reason to believe that their traffic won't get throttled back more or less than regular users.
 3. Specific ISPs might take it upon themselves to cater to power users or regular users only. Specialization and diversity would most likely create more choice in the marketplace.

### Competition

I've paid for bandwidth and worked at ISPs in many countries and one constant I've found is that increased competition directly translates into cheap bandwidth. In too many countries there is still not enough competition among ISPs. In the United States the number of ISPs a consumer may select further dwindled in the past decade.  
<br/>

All over the world you can see the same pattern. Countries with lots of competition among ISPs enjoy the cheapest and best internet service. The countries that are the worst off are the countries where 1 company controls all internet access. That was the case when I lived in India in 1998. Since then India opened itself up to competition and internet usage skyrocketed while bandwidth costs plummeted. Now India is basically on par with the USA for bandwidth costs. Much of Africa is still suffering under government controlled ISPs. The relatively modern country of South Africa has overpriced bandwidth for exactly this reason.  
<br/>

Might it be relevant that net-neutrality enters the American discourse at a time when American consumers have the least amount of choice since [1983?](http://www.ieee.org/portal/cms_docs_iportals/iportals/aboutus/history_center/yurcik.pdf)


### Legislators

[H.R. 3458](http://markey.house.gov/images/PDFs/netneutralitybill.pdf) put forth by US Representative Ed Markey of Massachusetts on July 30, 2009 echoes both goals of the net neutrality folks. While I'm glad that problem 1 is being addressed. I don't believe it's in the best interests of the citizens of the United States to argue for point 2. I'm specifically taking issue with the following(page 6 lines 16-23).  
<br/>

**“With respect to any Internet access service offered to the public, each Internet access service provider shall have the duty to not block, interfere with, discriminate against, impair, or degrade the ability of any person to use an Internet access service to access, use, send, post, receive, or offer any lawful content, application, or service through the Internet.”**  
<br/>

This sounds great in principle but it's effect will be chilling to ISPs already using DPI to insure bit torrent users don't overrun Skype users. The bill doesn't even make mention of the fact that different applications have different needs. Instead they specifically state that ISPs may not 'discriminate against' users by application. This is short sighted and unrealistic.   
<br/>

The bill does nothing to promote increased competition except to point out there isn't much of it(page 3 lines 12-15).  
<br/>

**“The overwhelming majority of residential consumers subscribe to Internet access service from 1 of only 2 wireline providers: the cable operator or the telephone company.”**  
<br/>

If the United States had better competition among ISPs they might not even need this legislation.


### The Future

(This section was obfuscatingly written at an intentionally higher technical level than the rest of this article.)
People of Earth! You must figure out a way to administratively handle different types of applications on the public internet openly and transparently. Already many ISPs offer latency bounded applications within their own network such as television or VoIP services. But the television feeds don't come from the public internet and if you want to be able to reach emergency services on your ISP provided VoIP phone you better hope your call isn't routed over the public internet.  
<br/>

If we are to move forward with the next batch of 'not yet conceived applications' we will need to develop an honest framework for current application interoperability on our public networks. At some point we will want to start actually routing multicast traffic across the public internet and not just pretending like we do now. We will want to replace the Public Switched Telephony Network(PSTN) entirely with the public internet and stop using 0-9 as people identifiers. We will want to replace all existing metaphors for communication with their internet equivalents at some point. And then we will develop new metaphors for communicating that only work with the public internet like we did with email and IM.  
<br/>

The protocols and technologies are in place. The IETF and IEEE have done their jobs providing us the offsets to mark precedence. The hardware vendors have done their jobs providing devices for DPI and fast forwarding engines that honor precedence. Now it's up to the legislators and the public to provide an administrative framework that brings it all together in the public interest.
