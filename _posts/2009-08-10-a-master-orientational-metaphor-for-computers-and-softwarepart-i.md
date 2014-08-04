---
layout: post
title: A Master Orientational Metaphor for Computers and Software(Part I)
tags: [metaphors, computers]
---
The purpose of this article is to introduce my views and theories regarding general orientational metaphors and their influence over our understanding of computers.  Since the English language dominates computer discourse and most machine languages are written from an English perspective special attention is given to orientational metaphors derived from the English language.  The reader is expected to have a basic understanding of computer organization.  While more detailed knowledge of software artifacts and the methods associated with managing their complexity may also be useful.

### An Orientational Metaphor Primer

Orientational metaphors are those metaphors that use orientational language to provide coherence in a conceptual system. Or as Kovecses says in “Metaphor: A Practical Introduction” on page 36.  
<br/>

**“[Orientational metaphor’s] cognitive job is to make a set of target concepts coherent in our conceptual system. The name ‘orientational metaphor’ derives from the fact that most metaphors which serve this function have to do with basic human spatial orientations, such as up-down, center periphery, etc.**  
<br/>

The most commonly given example of an orientational metaphor is: Happy is Up; Sad is Down. ‘I’m feeling up today’ or ‘I’ve been feeling down lately’ are common examples of this metaphor most likely grounded in the human trait of walking and standing upright. People who are physically dejected or depressed can literally appear more down with their head hanging while those who are happy can literally walk more upright with their chest out. In general, orientational metaphors referring to ‘up’ carry a positive connotation while those referring to ‘down’ carry a negative connotation. This positive or negative connotation is grounded in our shared human experience.  From Lakoff and Johnson’s “Metaphors We Live By” page 58:  
<br/>

**“Since there are systematic correlates between our emotions (like happiness) and our sensory-motor experiences (like erect posture), these form the basis of orientational metaphorical concepts (like Happy Is Up). Such metaphors allow us to conceptualize our emotions in more sharply defined terms and also to relate them to other concepts having to do with general well-being (e.g., Heath, Life, Control, etc).”**  
<br/>

Another orientational metaphor interesting for this article is ‘The Inside Man’. ‘The Inside Man’ doesn’t use up or down but is still an orientational metaphor since 'inside' is an orientational descriptor.  One of the most famous ‘inside men’ ever was Deep Throat. Deep Throat was able to provide valuable information on Nixon’s Plumbers in the Watergate scandal. Even though he turned out not to be a member of Nixon’s Plumbers nor of the Nixon administration, Deep Throat's metaphorical proximity to proprietary information made him invaluable to Woodward and Bernstein in their investigation and eventual exposure of the Watergate scandal.  
<br/>

Not all conceptual metaphors are pan-linguistic or pan-cultural. Some metaphors only ‘work’ in one language or culture even though they still might be based on some shared human experience. Our shared human experience is still coupled to cultural and linguistic traditions and assumptions.Take the difference between the Dutch and English when conceptualizing music volume for example.  When an English speaker wants to increase or decrease music volume he 'turns it up' or 'turns it down'.  While a Dutch speaker 'makes it harder' or 'makes it softer'.  An English speaker might say ‘Please make the music softer’. But he could not say ‘Please make the music harder’. ‘Hard music’ or making music ‘harder’ in English has a different meaning that is not related to volume intensity.  So whereas in English more volume is up and less volume is down.  In Dutch this is clearly not the case.  

### Our Master Orientational Metaphor

A master metaphor is a metaphor that acts as a root for other metaphors in the same problem space or subject matter.  It is atomic and primitive enough so that it cannot be broken into more base metaphors that provide a more thourough conceptual mapping. I posit that the following orientational metaphor is the master metaphor for our conceptual understanding of computer and software organization.  

 - **Inside and down is arcane, complex and approaching the hardware.**
 - **Up and outside is general, abstract and approaching the user.**

Some obvious examples of this metaphor are:

 - I will need to dig into the code to fix that bug.
 - This function passes a value up to its calling process.
 - We need to get this code released soon.

It is also frequently seen in computing terms and definitions:

 - Bottom-up programming
 - Top-down programming
 - High-level language
 - Low-level language
 - Operating system kernel
 - ISO/OSI 7 layer model

### Operating Systems: Organized and Powerful

“The 8th Edition of Operating System Concepts” by Silberschatz, Galvin and Gagne defines an operating system as:  
<br/>

**“A program that acts as an intermediary between a user of a computer and the computer hardware.”**  
<br/>

An operating system is the software that intermediates between the users and the hardware. So it’s not surprising that we’ve adopted a metaphor for discussing software and operating systems that places it between hardware and users. But this doesn’t explain why we’ve adopted a metaphor that has users above the operating system and the operating system above hardware. Why do we talk about operating systems as beneath the user and as being above the hardware?  
<br/>

To understand this added facet of our master metaphor we will need to introduce another aspect of this metaphor’s experiential grounding, control. Not only does the operating system sit in between users and hardware, but users control the operating system and through it the hardware. It may not always seem like it to many users. But computers do not take initiative of their own. And something that is in control of something else is usually above it in metaphorical terms. There is a reason why thrones and those who sit on them are the highest places in throne rooms and why judges look down at us in courtrooms. Being on top denotes control and power. We do not exert control under something.  We exert control over something. This changes our concept of users, the operating system and hardware and provides up/down orientation to a 3 layer model with hardware at the bottom, users at the top and the operating system in the middle.  
<br/>

Witness the surreptitious use of this orientation in advertising with the relatively recent rise of virtualization software such as VMWare and Xen. From http://www.xen.org/about/.  
<br/>

**“With Xen virtualization, a thin software layer known as the Xen hypervisor is inserted between the server’s hardware and the operating system. This provides an abstraction layer that allows each physical server to run one or more “virtual servers”, effectively decoupling the operating system and its applications from the underlying physical server.“**  
<br/>

This quote is expected to resonate with prospective users of the Xen virtualization engine precisely because it plays so well with our orientational metaphor. It implicitly reinforces it by making use of a shared conceptualization of hardware, operating systems and users to market Xen software. Not only does it clearly delineate operating system and hardware.  But it also places the operating system above the hardware while wedging the Xen hypervisor in between them both.  If both author and reader didn’t share this conceptualization then this wouldn’t be an effective advertisement and the reader would be left with a disjointed feeling that Xen just doesn't get it.  
<br/>

### Popcorn, Cakes and Interfaces

Before computerese infected English with technical terms most people only used the word kernel when they were talking about popcorn.  Rarely did the  average English speaking human equate kernel with non-food stuff.  They still don't.  But for the computer literate the word kernel can have an entirely different meaning. The American Heritage Dictionary defines kernel as:  
<br/>

**“The most material and central part of something; the core.”**  
<br/>

But the word kernel in operating system parlance specifically refers to the smallest possible part of the operating system that directly interacts with the hardware. “The 8th Edition of Operating System Concepts” by Silberschatz, Galvin and Gagne defines a kernel as  
<br/>

**“The one program running at all times on the computer.” The job of the kernel is “..to implement the lowest-level abstraction layer.”**  
<br/>

If the kernel isn’t running then no other software can run. Because the kernel’s primary function, besides interacting with hardware, is to implement the lowest level of abstraction for software. So the kernel is the lowest and deepest piece of software running on a computer.  
<br/>

The term ‘lowest-level of abstraction’ is interesting because it denotes a conceptual border between two layers. A layer of abstraction, more commonly called an interface, designates where one conceptual layer meets another. Software development is largely a process of managing complexity, any method by which complex concepts can be broken up into more manageable chunks and dealt with piece meal provides advantage to programmers. Since there are limits to how much 1 person can think about at once. The most common way this advantage is realized is by breaking up large concepts into smaller ones and then designating interfaces between them.  
<br/>

Top-down programming and bottom-up programming are two approaches to programming a piece of software which contains interfaces.  In bottom-up programming the lowest level abstraction is conceived of and created first. In this way bottom-up programming deals with the most specific and arcane problems first. While in top-down programming the opposite is true. Top-down programming focuses on capturing abstract user centric concepts first. And then focusing on arcane details later. Both approaches treat interfaces as central to program conception and both recognize the unique power that interfaces provide for conceptualizing and managing complexity. They also both place users at the top and hardware at the bottom with software somewhere in the middle. Most adherents of top-down programming would emphasize the need to create a user interface first. And then move on to writing the guts and inner workings of the program second.  While a bottom-up approach to programming would have the user interface written last.  
<br/>

Conceptualizing and compartmentalizing software through the use of interfaces provides us with a sort of layered cake outlook on computer organization. The lowest level of our software cake is the kernel. Followed by increasingly abstract and user focused levels until we finally reach our human. An obvious example of our layered-cake software metaphor would be the 7 layer ISO/OSI model for networking. This model lays out 7 layers for communication with hardware at the bottom and the user at the top. From layer 1(physical layer) up to layer 7(application layer) each step up the model moves from specific to general and from hardware to user.  
<br/>

If we use Ethernet and IP as our example technology we can define the layers as such. Layer 1 is cables and connectors. Layer 2 is MAC addresses and vlans. Layer 3 is IP addresses and the IP header. Layer 4 is the payload of the IP packet, typically TCP or UDP.  
<br/>

After Layer 4 we start having problems. Our grounding becomes more vague and we begin having trouble applying our model to reality. Is layer 5 the port number of the TCP or UDP packet? What about protocols that have no port like ICMP? Very rarely is the ISO/OSI model used for communicating about networks after layer 4. In fact, in my 12 years of professional networking experience I have never heard someone use the term layer 5 or layer 6. While I frequently hear mention of layers 1-4. If someone did tell me a device was operating on layer 5 or layer 6 I would have to ask what they meant because it would be unclear to me exactly what that layer represents. As we move away from the hardware and towards the user concepts become more vague and removed from their physical grounding. It's not until layer 7 that we again feel comfortable using the ISO/OSI model to describe networking traffic. If someone says to me that a device operates on layer 7 it means that the device can operate on anything within the packet. Layer 7 takes on the role of the entire packet. It is essentially the whole cake and not just another layer.  
<br/>

### Conclusion

We conceptualize software, hardware and users in a complex multi-level orientational metaphor that is based on grounding in the physical world. Hardware is at the bottom, the operating system and software is in the middle and users are at the top. In addition hardware is in the middle of a series of concentric circles, surrounded first by the operating system or software and finally by users. This metaphor reveals itself through our common use of language surrounding computers, software and hardware. As we move up or outward we are approaching users and abstraction. As we move down or inside we are approaching the hardware and arcane complexity. Power and not only architectural necessity plays a role in this as well. With users being placed above software and hardware because of their control over both. The implications of this orientational metaphor and what it means to users and creators of software artifacts will have to wait for the followup article.
