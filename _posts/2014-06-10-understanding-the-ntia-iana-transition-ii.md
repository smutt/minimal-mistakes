---
layout: post
title: Understanding the NTIA IANA Transition - Part 2
tags: [politics, computers]
---
On March 14, 2014, The National Telecommunications and Information Administration(NTIA) announced its, "intent to transition key Internet domain name functions to the global multistakeholder community."[^1] This transition is more commonly referred to as the transition of the Internet Assigned Numbers Authority(IANA) functions contract, or sometimes just the IANA contract. This series of three posts will attempt to unwrap exactly what the transition of the IANA contract means, and why it matters to the Internet at large. In the process these posts will investigate what the IANA contract is, its history, the people and policy makers influencing it, and an informed recommendation for its transference.  
<br/>

In this second of three posts on the NTIA IANA transition we'll examine the IANA contract itself.  Then we'll look into some of the organizations behind coordinated numbering and naming in the Internet.  If you haven't already, check out the [first](/understanding-the-ntia-iana-transition-i/)  post in the series before reading further. 

## Atomizing the IANA Contract
To atomize means to break something down into its smallest, indivisible parts. This section will atomize the IANA contract. We will then explain what each function is, and who is responsible for coordinating it. Unless otherwise noted, the information in this section originates from the IANA functions contract[^2] between ICANN and the NTIA awarded on October 1, 2012.  
<br/>

The current IANA contract covers the period of October 1, 2012 until September 30, 2015. The government retains an option to extend the contract in two year increments until september 30, 2019. The contract lists ten distinct duties of the IANA contract holder. Officially numbered sections C.2.9.1, C.2.9.2a, C.2.9.2b, C.2.9.2c, C.2.9.2d, C.2.9.2e, C.2.9.2f, C.2.9.2g, C.2.9.3, and C.2.9.4.  
<br/>

#### C.2.9.1 Protocol Parameters and ARPA TLD
The assignment of protocol parameters is an effort co-evolved with the IETF. Often times when the IETF defines a new protocol via an RFC, the protocol requires numbered resources. For example, Hypertext Transfer Protocol(HTTP) uses Transmission Control Protocol(TCP) port 80. Different protocols that use TCP each use their own port number, which must be unique, and universally recognized. Another protocol cannot use TCP port 80 as it is taken. If another protocol did use TCP port 80 an application listening on that port would incorrectly assume the traffic was HTTP, when in fact it was not.  
<br/>

The ARPA DNS TLD is a historical leftover. There are no computers actually running with a .arpa TLD. However, it's used for reverse DNS translation, which is when a computer needs to translate an IP address to a DNS hostname. As opposed to normal DNS translation, which is a translation from a DNS name to an IP address. This means that the .arpa TLD must be reserved, and cannot be used for anything else.  
<br/>

It's not clear why the NTIA decided to group these two distinct functions together, as they share almost nothing in common.  

#### C.2.9.2a Root Zone Change Management
All functions starting with C.2.9.2 concern administrative functions of DNS. C.2.9.2a specifically concerns change requests made to the DNS root zone file. This change management function is probably the most important element of DNS management in the IANA contract.  
<br/>

When new TLDs are issued, the root zone file must be updated with the authoritative DNS hosts for those TLDs. TLD registries are organizations that control and manage individual TLDs. They typically contract out to DNS registrars, who then resell individual domain names. Registries control entire TLDs, then contract to registrars who resell to individuals and organizations.  
<br/>

DNS names are translated to IP addresses from right to left. For example, if someone wanted to reserve example.com they would reserve it with a registrar, who would then inform the .com registry of the reservation. To translate www.example.com to an IP address, a computer would first ask one of the DNS root servers for the IP address of the .com registry. Then the computer would ask the .com registry for the IP address of the example.com DNS server. Lastly, the computer would ask the example.com DNS server for the IP address of www.example.com.  
<br/>

The root zone of the DNS hierarchy is literally a list of every TLD and its associated DNS server. It's officially the first place a computer should start when translating any DNS name to an IP address on the Internet. In actuality though, subordinate DNS servers save previous lookups for a period of time through a process called caching. This helps alleviate the strain on the root zone servers, and increases redundancy.  

#### C.2.9.2b WHOIS Database Management
The WHOIS database is a distributed database containing information on every registered DNS name. Every time a new DNS domain name is reserved through a registrar an entry is placed in the distributed WHOIS database. The WHOIS database contains information such as contact, address, and the name of the domain name owner. It's an important tool for dealing with abuse, and the default option for getting in touch with an actual human behind a domain name. WHOIS is not an acronym, instead the name originates from the first UNIX command to provide this service, which is still called whois.  
<br/>

This function specifically concerns the management of the root WHOIS database. Which only contains information on DNS TLD registries. This top-level WHOIS database is used to find the subordinate WHOIS databases for each TLD, in a hierarchical manner similar to how DNS itself is organized.  

#### C.2.9.2c Country Code Top Level Domains(ccTLDs)
Country Code Top Level Domains(ccTLDs) are special TLDs such as .uk, .ru or .jp. The registries for these TLDS are sovereign states. Unlike generic Top Level Domains(gTLDs) such as .com, .edu, or .info, ccTLD registry function duty cannot be transferred. When new gTLDs are issued any organization can become their registry. This is not the case with ccTLDs as their functional duty remains fixed with the country they represent. This function concerns management of the ccTLD namespace, which includes dealing with any regulatory issues which might emerge in any jurisdiction.  

#### C.2.9.2d Generic Top Level Domains(gTLDs)
This function concerns management of the gTLD namespace. Generic TLDs are the most common TLDs on the Internet. Besides the common ones like .com, .edu, or .net, there are many more that rarely see use. In 2014 ICANN started the introduction of over 1,300 new gTLDs such as .food, .berlin, and .hyundai.[^3] As well as introducing unicode gTLDs, which support non-latin character sets.  

#### C.2.9.2e Root Zone Automation
This function concerns the development of automation tools for root zone management. It will most likely alter in future IANA contracts as either the work is already finished, or only maintenance is required.  

#### C.2.9.2f DNSSEC Key Management
Domain Name System Security Extensions(DNSSEC) are extensions to the DNS protocol that make it more secure. The primary purpose of DNSSEC is to prevent bad actors from hijacking DNS names and thereby tricking unsuspecting Internet users into visiting the wrong site. Since DNS translates human readable names into IP addresses, it's very important that DNS always translate a given name into the correct IP address.  
<br/>

DNSSEC attaches to the hierarchical nature of DNS, by having subordinate DNS servers implicitly trust their immediately superior DNS server. DNSSEC is still relatively new, and is currently still undergoing deployment. However, it has emerged as a very important technology and will become increasingly more relevant in the future. This function concerns the trust-anchor at the top of the hierarchy that all other DNS servers are subordinate to. This trust-anchor is quite literally the root of all trust in the DNSSEC hierarchy.  

#### C.2.9.2g Customer Service
This function concerns establishing a procedure for complaints and handling customer support claims related to the rest of the functions.  

#### C.2.9.3 IP Addressing and AS Numbers
This function concerns the management of IP addresses and Autonomous System(AS) numbers. As well as the management of special purpose reserved IP addresses or AS numbers not to be used for normal Internet addressing. This function only relates to the delegation of large blocks of IP addresses and AS numbers to RIRs. Who then break up the large blocks into smaller blocks and delegate those to individual organizations.  
<br/>

An AS number is a unique identifier given to each organization on the Internet. Each administrative entity on the Internet should have its own AS number, but sometimes organizations may have more than one due to entity consolidation. Recently IANA ran out of AS numbers as they were limited to 16 bits, or roughly 64,000 addresses. These were exhausted around 2008, therefore RFC 4893 introduced 32 bit AS numbers. This allows roughly 4 billion addresses.  
<br/>

IP addresses are the core numbering system on the Internet. Every computer on the Internet is assigned an IP address. IP version 4(IPv4) dates from 1981 and RFC 791. IANA exhausted large blocks of IPv4 addresses in 2013. In preparation for this exhaustion, IP version 6(IPv6) was introduced in 1995 with RFC 1752. While many operators have been slow to adopt IPv6, the continued growth of the Internet depends on it.  
<br/>
 
This function concerns the allocation of 32 bit AS numbers and IPv6 addresses. To a lesser extent it also concerns any future reservation of special purpose IPs and AS numbers.  

#### C.2.9.4 INT TLD
The .int TLD is a special TLD because it is neither a gTLD nor a ccTLD. It stands for international, so while it is not affiliated with a sovereign entity it is also not transferable. This function concerns being the registry for the .int TLD.  

### Additional Functions
In addition to the IANA functions enumerated in the 2012 IANA functions contract there are other functions which are often considered IANA functions.  

#### Timezone database
The timezone database is a database of all timezones in the world and their offset from Greenwich Mean Time(GMT). It can be downloaded as a single compressed file from iana.org, and its management is documented in IETF Best Current Practice(BCP) 175. On October 14, 2011 ICANN took over management of the timezone database.[^4] This was in response to a suit filed against the volunteer maintainers of the timezone database by astrology software publisher Astrolabe. The suit claimed copyright infringement.[^5] The Electronic Frontier Foundation(EFF) represented the defendants and was able to get Astrolabe to dismiss the suit and agree to never sue again.[^6]  
<br/>

This function concerns the management of both the human and machine readable timezone database.  

#### IDN Tables
Some domain names contain non-latin characters. These are commonly referred to as Internationalized Domain Names(IDNs) and use the unicode format for representation standardized by The International Standards Organization(ISO). Just like there are latin characters which cannot appear in domain names, there are also non-latin characters which cannot appear in domain names. This function concerns the maintenance of the permitted lists of characters for every non-latin character set.  
<br/>

The IANA contract contains many diverse functions and has encompassed steadily more since the word IANA was first used in an RFC in 1990. When the NTIA announced its intent to transition key Internet "name functions"[^7] it sounds very simple. However, as we have just seen, the IANA contract encompasses far more than just naming. In the next section we look at the organizations and institutions involved in Internet naming and numbering.  

## Organizations and Institutions
We have looked at some of the organizations involved in Internet naming and numbering already. This section will delve more deeply into these organizations and others that coordinate to organize the Internet.  

#### NTIA
The National Telecommunications and Information Administration(NTIA), an agency of the US Department of Commerce, issues the no charge IANA Function contract. They are mentioned here because, regardless of how this transition resolves, they will exit from their role as contractee. Their intention is to terminate their involvement in the IANA functions contract entirely.  

#### ICANN
The Internet Corporation for Assigned Names and Numbers(ICANN) is the most important organization involved in Internet naming and numbering. ICANN is the current holder of the IANA contract. Other organizations carrying out aspects of the IANA contract do so as sub-contractors to ICANN. ICANN was founded in 1998 in Los Angeles. The location of Los Angeles was chosen because Jon Postel lived there, and Postel was chosen to be ICANN's first CEO. Unfortunately Postel died immediately prior to ICANN's founding. ICANN is a not-for-profit public-benefit corporation registered in the state of California.  

#### RIRs
Regional Internet Registries(RIR) are the local presence of Internet naming and numbering throughout the world. They are; the African Network Information Centre(AFRINIC), Latin America and Caribbean Network Information Centre(LACNIC), and the aforementioned RIPE, APNIC, and ARIN. RIRs receive large blocks of IP addresses and AS numbers from ICANN and then divvy them out to individual organizations. They also play an important role in establishing operator communities in their respective regions, and sometimes perform measuring and statistics generation for their regional, and global Internet community.  

#### IETF
The Internet Engineering Task Force(IETF) is the chief standards making body of the Internet. Their primary purpose is to, "produc[e] high quality, relevant technical documents that influence the way people design, use, and manage the Internet."[^8] Often times the IETF will create a new protocol and then ask the IANA function contract holder to reserve specific protocol parameters for that protocol. For example, when IPv6 was introduced it was first called IPng. It was only after the number '6' was reserved through IANA that the IETF, and everyone else, started referring to IPng as IPv6. Specifically this is IANA function C.2.9.1.  

#### ISOC
The Internet Society(ISOC) was established in 1991 as the more formal, parent organization to the IETF. The IETF does not have any formal legal instantiation, such as corporation or sovereign power. ISOC was formed to help provide the IETF with a corporate structure, and to provide policy oversight for the Internet and the IETF. Their mission statement is, "To promote the open development, evolution, and use of the Internet for the benefit of all people throughout the world."[^9] Most of their activities can be broken down into the three categories of education, technology development, and standards facilitation. Another important role of ISOC is to hold the copyright for all IETF documents.  

#### Verisign
Verisign is a US based corporation originally founded in 1995. Since that time they have operated, or been involved with, various Internet naming and numbering operational activities. Currently Verisign operates two of the thirteen DNS root servers, and is responsible for generating the DNS root zone file. Verisign's role in the root zone file is strictly operational. ICANN has policy control of the root zone file. Verisign also has numerous other DNS operational duties including being the registry for .com and .net, and managing the encryption keys for the root of DNSSEC. Specifically, Verisign is operationally responsible for the 2012 IANA functions contract subsections C.2.9.2a, and C.2.9.2f. Verisign is a public for-profit corporation located in Virginia, and listed on the NASDAQ exchange under VRSN.  

#### Peripheral Standards Organizations
Besides the IETF, there are many other standards making bodies in the world that influence the functioning of the Internet. These include, but are not limited to; The International Telecommunication's Union(ITU), Institute of Electrical and Electronics Engineers(IEEE), World Wide Web Consortium(W3C), Metro Ethernet Forum(MEF), American National Standards Institute(ANSI) and the aforementioned ISO. These bodies will often define a standard which will later be referenced in an IETF RFC, since the nature of standards bodies is to promote already existing standards where applicable and relevant.  

####  Network Operator Groups
Network Operator Groups(NOGs) contain the important user base of Internet network operators. Since the Internet is just a collection of interconnected networks, NOGs provide the operators of these networks with fora to discuss operational and policy issues. The North American Network Operators Group(NANOG) is probably the most famous, and the most vocal of these groups. There are many more, with some of the larger ones being; Latin American and Caribbean Region Network Operators Group(LACNOG), Asia Pacific Regional Internet Conference on Operational Technologies(APRICOT), the Middle East Network Operators Group(MENOG), and RIPE, a European network operator group associated with RIPE-NCC.  
<br/>

In the [next post of this series](/understanding-the-ntia-iana-transition-iii) we will look at some of the proposals for the IANA transition. Then we will outline what is at stake here, define the problem, and propose our own transition plan for the IANA function.  

 [^1]: [http://www.ntia.doc.gov/press-release/2014/ntia-announces-intent-transition-key-internet-domain-name-functions](http://www.ntia.doc.gov/press-release/2014/ntia-announces-intent-transition-key-internet-domain-name-functions)
 [^2]: [http://www.ntia.doc.gov/files/ntia/publications/sf_26_pg_1-2-final_award_and_sacs.pdf](http://www.ntia.doc.gov/files/ntia/publications/sf_26_pg_1-2-final_award_and_sacs.pdf)
 [^3]: [https://www.youtube.com/watch?v=1kFcxf8KAjg](https://www.youtube.com/watch?v=1kFcxf8KAjg)
 [^4]: [http://mm.icann.org/pipermail/tz/2011-October/008090.html](http://mm.icann.org/pipermail/tz/2011-October/008090.html)
 [^5]: [http://www.scribd.com/doc/67760407/ASTROLABE-INC-Vs-ARTHUR-DAVID-OLSON-and-PAUL-EGGERT-Complaint](http://www.scribd.com/doc/67760407/ASTROLABE-INC-Vs-ARTHUR-DAVID-OLSON-and-PAUL-EGGERT-Complaint)
 [^6]: [https://www.eff.org/press/releases/eff-wins-protection-time-zone-database](https://www.eff.org/press/releases/eff-wins-protection-time-zone-database)
 [^7]: [http://www.ntia.doc.gov/press-release/2014/ntia-announces-intent-transition-key-internet-domain-name-functions](http://www.ntia.doc.gov/press-release/2014/ntia-announces-intent-transition-key-internet-domain-name-functions)
 [^8]: [http://ietf.org/index.html](http://ietf.org/index.html)
 [^9]: [http://www.internetsociety.org/who-we-are/mission](http://www.internetsociety.org/who-we-are/mission)
