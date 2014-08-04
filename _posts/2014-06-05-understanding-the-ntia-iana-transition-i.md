---
layout: post
title: Understanding the NTIA IANA Transition - Part 1
tags: [politics, computers]
---

On March 14, 2014, The National Telecommunications and Information Administration(NTIA) announced its, "intent to transition key Internet domain name functions to the global multistakeholder community."[^1] This transition is more commonly referred to as the transition of the Internet Assigned Numbers Authority(IANA) functions contract, or sometimes just the IANA contract. This series of three posts will attempt to unwrap exactly what the transition of the IANA contract means, and why it matters to the Internet at large. In the process these posts will investigate what the IANA contract is, its history, the people and policy makers influencing it, and an informed recommendation for its transference.  
<br/>

In this first of three posts on the NTIA IANA transition we'll examine what coordinated naming entails, and the history of the IANA and the Internet.  

#### Conventions and Prerequisites
This series makes use of many acronyms. The first time an acronym is mentioned it will be proceeded by its definition. Each successive mention of this acronym will be in all capitals without any definition.  
<br/>

These posts assume the reader has a basic understanding of computer networking. The reader needs to know what an IP address and DNS domain are. Beyond that no expectation of knowledge is required.  

## Coordinated Naming

 **"There are only two hard things in Computer Science: cache invalidation and naming things."**  
Phil Karlton  
<br/>

The IANA contract is the historical zero cost contract that has determined which party controls the naming and numbering of resources on the Internet. It can be thought of as a baton that has passed between various individuals and organizations. When an entity holds this contract they coordinate the naming and numbering of Internet resources. They do not have any authority other than to coordinate names and numbers, nor do they have any means to enforce their will. The power of the IANA contract is in its coordinating ability and historical precedent. Without a central naming and numbering authority the Internet could not function, computers could not communicate with one another if Internet users chose their own IP addresses or DNS names.  
<br/>

Imagine if there was no coordination for naming and numbering of city streets. If everyone got to choose their own street name and number, the international postage network would break down. Having a coordinated naming facility, even if it is distributed across sovereign boundaries, allows us to send letters across the planet. Simply having mostly agreed upon names for countries allows us to address and send letters to them.  
<br/>

If tomorrow the entire Internet decided to rename and renumber every computer on the Internet, the holder of the IANA contract could not stop them. However, the Internet would cease to function.  Packets, just like postal packages, would be undeliverable.

## History of the IANA Contract
Attempts to coordinate resource naming or numbering date back to the earliest days of Arpanet, the precursor of the Internet. Researching the early days of the Internet can be difficult and contentious. Therefore, I would like to apologize in advance for any omissions, mischaracterizations, or inaccuracies I might have made in compiling the following.  
<br/>

Requests for Comments(RFCs) are the technical documents of the Internet, and early RFCs can provide a window into past efforts at numbering coordination. RFCs are incrementally numbered documents, with each new RFC just getting the next number. RFC 1 was published in 1969, and as of June 2014, the latest RFC is 7279.  
<br/>

The first example of numbering coordination in an RFC is the first sentence of RFC 25 published in 1969. It states, "Because it may be desirable to reserve one or more link numbers for instrumentation purposes, and because 256 link numbers are many more than are needed, we suggest that no link number over 63 be used." There are hardcoded numbered resources mentioned in RFCs prior to this, but this was the earliest attempt at numbering coordination mentioned in RFCs. Eventually these ad-hoc attempts at coordination were assigned to the Internet's Network Information Center(NIC). The first mention of which was in RFC 115, published in 1971. The NIC, sometimes called InterNIC, "was the information hub of the early Internet."[^2] Located at Stanford Research Institute(SRI), the NIC was the first organization responsible for maintaining the host file for Arpanet.[^3] The Arpanet host file was a simplified precursor to the Domain Name System(DNS) we use today. It registered the names of computers on the Internet. The NIC worked in coordination with the Information Sciences Institute located at the University of Southern California(USC-ISI), which coordinated the assignment of IP addresses on Arpanet.  
<br/>

Jon Postel was an early employee of the NIC who played an important role in Arpanet and Internet numbering and naming. He even named himself 'czar' of protocol numbering coordination with RFC 349 in 1972. Postel moved from SRI and NIC to USC-ISI in 1977, where he formalized his position as RFC editor.[^4] In 1983 the NIC changed its name to the Defense Data Network Network Information Center(DDN-NIC) as the Department of Defense's(DOD) Defense Communication Agency(DCA) assumed the operations of the Arpanet.[^5] However, the term NIC continued to be used colloquially to refer to the new DDN-NIC organization. In 1987 Arpanet, now more commonly being called the ARPA Internet, or just Internet, transitioned from host files to the DNS. The need for which was spelled out plainly in RFC 882, "Currently hosts in the ARPA Internet are registered with the Network Information Center (NIC) and listed in a global table [..] The size of this table, and especially the frequency of updates to the table are near the limit of manageability." DDN-NIC developed the DNS Top Level Domain(TLD) system we still use today. With recognizable TLDs such as .mil, .gov, .edu, .org, and .com.[^6]  
<br/>

The first mention of the acronym IANA came with RFC 1060, published in 1990. RFC 1060 is a historical RFC and primarily meant to codify many informal arrangements concerning naming and numbering. Whether the term IANA was used prior to 1990 may be known by the surviving luminaries of the early Internet, but it does not appear in texts prior to RFC 1060.  
<br/>

Published slightly later in 1990, RFC 1174 was the first attempt at distributing naming and numbering to multiple institutions, and an important historical milestone in Internet history. It starts with this sentence, "Throughout its entire history, the Internet system has employed a central Internet Assigned Numbers Authority (IANA) for the allocation and assignment of various numeric identifiers needed for the operation of the Internet." Then continues with another bold claim, "With the demise of the ARPANET and the growth of a global Internet, the administration and registration of Internet network numbers has outgrown its initially conceived client base[..]." RFC 1174 recommends a multi-step process for IP address assignment whereby a centralized authority would disseminate large blocks of IPs to localized authorities, who would then disseminate them to individual organizations. It mentions no principles or organizations by name, but lays the groundwork for, and predicts the relationship between, future organizations the Internet Corporation for Assigned Names and Numbers(ICANN), and the Regional Internet Registries(RIR)s.  
<br/>

As a result of the recommendations put forth in RFC 1174, in 1991 the Defense Information Systems Agency(DISA) awarded the role of NIC to a company called GSI, which then subcontracted out to a small company called Network Solutions.[^7] The job of NIC had been at SRI, and located in Menlo Park, for 22 years. With the transfer of the NIC to Network Solutions the headquarters moved to Herndon, Virginia. It would stay there until 1997, when everything changed again.  
<br/>

In 1997, in accordance with an NSF request, Network Solutions transferred the responsibility of IP addressing to The American Registry for Internet Numbers(ARIN), also located in northern Virginia.[^8] Continuing in the spirit of RFC 1174, ARIN was established so that the organizations using IP addresses could be more involved in their assignment. ARIN was actually the third RIR to be founded. Réseaux IP Européens Network Coordination Centre(RIPE-NCC), the organization that would eventually become the RIR for Europe, as well as the first RIR, was established in the same month as RFC 1174 was published.[^9] Later, in 1993 the Asia Pacific Network Information Centre(APNIC) was established for the Asia Pacific region. However, it wasn't until the formation of ARIN in 1997, that the role of RIPE-NCC and APNIC in Internet numbering became clear. RIPE-NCC became the RIR for Europe, and APNIC became the RIR for Asia Pacific.  
<br/>

A famous controversy best illustrates the ad-hoc state of Internet naming in the late 1990's. On January 28, 1998 Jon Postel emailed operators from six of the twelve DNS root servers and asked that they point their servers to his server at USC. While having no actual operational effect, this act transferred half of the DNS root authority away from Network Solutions, and directly to Postel's server.[^10] Postel claimed he did it as an experiment, but the US government was not amused, and senior advisor to President Clinton, Ira Magaziner, told Postel, "You'll never work on the Internet again".[^11]  
<br/>

This event is interesting because it not only shows how much respect key operators had for Postel, but also demonstrates the fragility of Internet naming. The only way to get these operators to revert their changes was to have Postel personally mail them and ask them. As one of the server operators put it bluntly to the Washington Post, "If Jon asks us to point somewhere else, we'll do it. He is the authority here."[^12]  
<br/>

Later that year Postel died due to complications with his heart, he was just 55 years old. That same year ICANN was formed to handle almost everything related to naming and numbering on the Internet. Since then not much has changed. There have been disputes and minor changes to delegation of authority, but the IANA functions themselves still primarily rest with ICANN.  
<br/>

The history of Internet naming and numbering is a history of ad-hoc rules becoming progressively more codified through time and organizational influence. It's a history of scrambling to find scalable, consensus based solutions to an ever growing number of computers that need names and numbers. A history that started in Jon Postel's notebook and which now occupies the attention of thousands of individuals and dozens of institutions.  
<br/>

In the [next post in this series](/understanding-the-ntia-iana-transition-ii) we will break down the constituent parts of Internet naming and numbering, and the IANA contract. After that we will discuss the organizations that play a role in Internet naming and numbering, what they are responsible for, and how they interact with one another to get the job done.

 [^1]: [http://www.ntia.doc.gov/press-release/2014/ntia-announces-intent-transition-key-internet-domain-name-functions](http://www.ntia.doc.gov/press-release/2014/ntia-announces-intent-transition-key-internet-domain-name-functions)
 [^2]: Feinler, Elizabeth, ["The Network Information Center and its Archives,"](http://muse.jhu.edu/login?auth=0&type=summary&url=/journals/ieee_annals_of_the_history_of_computing/v032/32.3.feinler.html) IEEE Annals of the History of Computing 32, no. 3 (2010), 83-89 
 [^3]: <i>id.</i>
 [^4]: <i>id.</i>
 [^5]: Fritz E. Froehlich and Allen Kent, ARPANET, the Defense Data Network, and Internet: The Froehlich/Kent Encyclopedia of Telecommunications (CRC Press, 1990), 341–375.
 [^6]: Feinler, Elizabeth, ["The Network Information Center and its Archives,"](http://muse.jhu.edu/login?auth=0&type=summary&url=/journals/ieee_annals_of_the_history_of_computing/v032/32.3.feinler.html) IEEE Annals of the History of Computing 32, no. 3 (2010), 83-89 
 [^7]: [http://www.sri.com/about/alumni/alumni-hall-fame-2000#Feinler](http://www.sri.com/about/alumni/alumni-hall-fame-2000#Feinler)
 [^8]: [http://archive.icann.org/en/nsi/coopagmt-amend7-03dec97.htm](http://archive.icann.org/en/nsi/coopagmt-amend7-03dec97.htm)
 [^9]: [http://www.cisco.com/web/about/ac123/ac147/archived_issues/ipj_4-4/regional_internet_registries.html](http://www.cisco.com/web/about/ac123/ac147/archived_issues/ipj_4-4/regional_internet_registries.html)
 [^10]: [https://web.archive.org/web/20131020214030/http://songbird.com/pab/mail/0472.html](https://web.archive.org/web/20131020214030/http://songbird.com/pab/mail/0472.html)
 [^11]: [http://www.salon.com/2002/07/02/gilmore_2/](http://www.salon.com/2002/07/02/gilmore_2/)
 [^12]: [https://web.archive.org/web/20131020214030/http://songbird.com/pab/mail/0472.html](https://web.archive.org/web/20131020214030/http://songbird.com/pab/mail/0472.html)
