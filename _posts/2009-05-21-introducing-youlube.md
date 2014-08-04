---
layout: post
title: Introducing YouLube
tags: [computers, monkey-typists]
---
I used to work as a college radio DJ in a small town in Appalachia.  I was a hip-hop and electronica DJ but I loved the adverts the metal department would produce every week. They would produce these listings to be played during the metal shows that quickly ran down all the metal shows playing in the area for that month. And I would play the recording on my show because it was so funny to listen to.  
<br/>

If you've never heard someone say the names of 50 metal bands in tight succession with a completely monotone voice you have never truly laughed. Thinking back to that experience inspired me to make my own automagic metal word mashup generator. But why make just a heavy metal toy when you can make a general purpose toy?  
<br/>

Introducing YouLube. YouLube is a little program I whipped up in a couple of coding frenzies. Input a link to a YouTube video into YouLube and he will use Text To Speech(TTS) to read the names of the first 20 related videos. He will then pick one of the related videos and read its related videos' names. Ad infinitum or until you tell him to stop. YouLube can also substitute commonly occurring words with filthy words from an accompanying list of filthy words. But he won't substitute any of the 100 most commonly occurring words. A full listing of available options is available by just typing YouLube from the cli.  
<br/>

So what does this all mean? It means that entering a link to a Cannibal Corpse video into YouLube ends up sounding like Satan reading slam poetry. Eventually he wanders off into something innocuous like Britney Spears videos or dog walking but he still manages to stay filthy because of the substituting of filthy words. I've been listening to it prattle on now for a couple of days as I built it and I think I must be proper mad now. Good times.  
<br/>

YouLube requires Mac OSX with php installed. I got it to work under Linux quite easily but both Festival TTS and espeak just sound like shit compared to what comes with OSX. YouLube is licensed under the GPL so go have some fun with it.[^1]  
<br/>

 [^1]: Updated on Jun 1, 2014, YouLube is dead.
