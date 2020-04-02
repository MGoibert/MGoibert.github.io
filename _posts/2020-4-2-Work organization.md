---
layout: post
title: Working Organization for PdH Student
---

Like many other PhD student before, I have been facing some challenging issues regarding organization of my work since the beginning of my PhD. I have asked advice from collegues or other PhD students, and researched on the internet any tip that could be useful.

I think there is not one way to work efficiently that can fit everyone, and in fact I mixed all the tips I received to find my own way of working. In any case, here is my take on how to manage my bibliography, take notes on research papers, organize my ideas and so on.

<br/>

# Bibliography

In my opinion, there are two challenges I have to face regarding bibliography. The first one is to keep track of research papers I need to read or work on, and organizing these papers (by topic for example). The second one is to easily generate a bibliography that could be included in my own publications (as a researcher in Maths, I work with LaTeX so I need .bib files).

There are two main reference manager software that are designed to tackle these two issues : Mendeley and Zotero. I am not a fantastic expert on all the differences between these two softwares or all the tools they provide. I used Mendeley before, and I use Zotero now mainly for synchronization reasons, but I think both of them do the job.
Mendeley and Zotero enables you to save references (and both of them have add-ons you can download for your browser to very easily add a new reference to you library), to organize them with folders for exemple, and generate bibliography quite easily, so they perfectly meet my expectations

<br/>

# Take notes on papers

I am the kind of person who loves paper and pen, way more than numerical readers and annotation tools. The way I was working before was just to have a notebook, pens, and printed version of the papers I wanted to work on and that's it.
I took notes on my printed papers, as well as on my notebook when I needed to have more space, and since I was quite organized, I had folder to store py printed papers by topic, with the title and the authors of each paper in the folder written on the cover. Each time I wrote on my notebook something related to a paper, I added the date and a few keyworks at the begining of the page.
Honestly, it was ok for me. It was not really handy all of the times, because you can't move all you folders/papers from one location to another (let's be honest, when I wanted to work from home, I just have to take 3 or 4 papers I mostly worked on at that moment and that's it, I never had to really move everything), or you can't search automatically a keywork in your notes (we all dreamt of being able to do that with our handwritten courses at school no ?), and so on. But it worked fine for me.

In fact, the main reason I changed my organization is because I live in France, and we have the Coronavirus problem right now, and we have been in containment for several weeks now. So you can see this coming: my papers and one of my notebooks stayed at the office, and I'm stucked at home. Anyway, I wanted to be able to use nice features that come with numerical tools for quite some time, so that was an opportunity for change.

Now, I have and Ipad with an Apple pencil to take notes. I tried to look at different tablets and also other solutions such as special notebooks and/or pen that allows you to take handwritten notes on paper but that synchronize what you're writting in numerical format, but in the hand I chose a tablet because I think that for now, the technologies for taking notes are more mature than on other type of devices, and I choose an Ipad because it that's the best tablet for note taking purposes.

To take notes on pdf papers (as well as notes related to papers but for which I need more space), I use Flexcil. It's quite a recent app compared to Notability, GoodNotes or PDF Expert, but I really like one of its feature: you can add on top of your pdf pdf paper a notebook page you can move freely on the screen to take more notes (I put a screenshot of what I mean by that just below).
In addition to that, there are a lot of gestures that are really nice to have, like being able to select part of the pdf (like an image), copy-pasting it to the notebook note, and having a hyperef link automatically added to find the reference.
Flexcil can also import and export from a variety of cloud services, and I use Google Drive, so it's working fine with it.

![Screenshot Flexcil 1]({{ site.baseurl }}/images/screenshot1.png) ![Screenshot Flexcil 2]({{ site.baseurl }}/images/screenshot2.png)

<br/>

# Take notes for courses

For notes not related to any pdf paper (like courses for example, but also for ideas I want to write somewhere), I use another app called Nebo. The main advantage of Nebo is that it has a really really good handwrtitten recorgnition system embedded in it, so you can very easily transform what you're writting with the pen in a text format.
On top of that, the app is well designed to easily correct mistakes, skip lines to add stuff, and so on. You can even write a little bit of maths in it so it is recognized as maths caracters.

Like Flexcil, you can export to Google Drive so no problem with synchronization.

<br/>

# Synchronizing everything

I have several different tools to work with, but the main idea was also to have a fluid workflow so that it is easy to switch from my laptop to my tablet, from a laptop to another computer, and even (why not ?) to my phone.

I was able to do that thanks to this very useful tutorial on how to synchronize Zotero with a Cloud storage [here](https://www.researchgate.net/publication/325828616_Tutorial_The_Best_Reference_Manager_Setup_Zotero_ZotFile_Cloud_Storage "Zotero to Cloud storage tutorial"){:target="_blank"}.

Thus, my workflow feels like this:
1) On my laptop: I find files related to my research areas thanks to the ArXiv alert I created [(see here)](https://mgoibert.github.io/ArXiv-Alert/ "ArXiv Alert post"){:target="_blank"}.
2) On my laptop: I open the pdf and save if to my Zotero library thanks to the Zotero Connector add-on.
3) On my laptop: the new paper is synchronize automatically in a folder on my laptop, which is also synchronize with Google Drive. The paper is thus automatically added to my Google Drive account.
4) On my tablet: I import the paper as pdf in Flexcil and take all the notes I want.
5) On my tablet: when I'm finished, I export the annotated pdf (and any other notes I want) to Google Drive
6) On my phone: I can reread my notes while commuting.


<br/>
<br/>

On the whole, I find this new organization very efficient. Using a tablet and a pen to write feels mostly great (we can't say it's like writting on paper, but I was surprised to find it quite nice after all). While working from home, I find it essential since I don't have a printer and I can work more easily on my sofa too (eventhough it is far more better to work on my desk !).

So here is how I work with Zotero: when I have a new reference I want to keep (like a paper I have to read), I open its pdf version on ArXiv generally. My browser is Google Chrome, and I have the add-on Zotero Connector connected to it, so while on the pdf of my reference, I just have to click on the add-on. I allows me to save my reference, and to choose where I want to save it, so I just select the convenient folder where I want to see my reference, and it is added to my library of papers.




<br/>

You can go on the website and follow their instructions to get an alert based on authors only, but it was not completely what I was looking for. I prefered having an alert based on keywords. I did not found any way to do that via ArXiv website, so I created a Python script that can filter papers based on keywords found in the title or abstract. I also added the possibility to add specific categories (since a keyword can be used in a totally different area than the ones I am interested in) and specific authors if you want to restrict even more your query.

<br/>

The script is based on what Alex Breitweiser did and posted [here](https://academia.stackexchange.com/questions/76020/subscribe-to-cross-listings-on-arxiv "Alex Breitweiser post"){:target="_blank"} and [ArXiv API](https://arxiv.org/help/api/index "ArXiv API"){:target="_blank"}.

This script outputs a html file with the list of papers, and open it automatically in a new page of your browser.
There are four different parameters you can tune to personalize your alert: categories (e.g. ["stat.ml, "cs.cv"]) should be a list of all ArXiv research areas you are interested in. Keywords (e.g. ["adversarial", "robustness"]) is also a list and contain keywords you want to find in the title or in the abstract. Authors is again a list in the same format, which allows to search for papers authored by specific researchers. Finally, max_results is a integer number tuning how many papers you want to see at most.

It is not a parameter, but do not forget to change the path! I put an absolute path, not a relative one in my code (sorry!). You just have to change the variable "my_path" (line 120).

<br/>

You can download the script [here]({{ site.url }}/downloads/arxiv_alert_script.py){:target="_blank"}.


<br/>

# Run you script automatically every week

Next, to run this script automatically every week, I use a nice feature of Mac: crontab. It is very easy, you just have to open your Temrinal, and run the following commands:

{% highlight r %}
crontab -e
{% endhighlight %}

which opens a document where you can lists all the scripts you want to run on a timely basis. In my case, I wanted my code to run every Monday morning at 10 am. The relevant code line is then:

{% highlight r %}
0 10 * * 1 /Your/python3.7 /The/Relevant/Path/arxiv_alert_script.py
{% endhighlight %}

You can find a nice explanation on how to use crontab [here](https://www.google.com/search?q=use+crontab+mac&rlz=1C5CHFA_enFR880FR880&oq=use+crontab+mac&aqs=chrome..69i57j0l7.2654j0j7&sourceid=chrome&ie=UTF-8#kpvalbx=_szxiXpb9FZadjLsPr9qL6AE31 "Crontab explanation"){:target="_blank"}.


The final HTML file looks like this:

![_config.yml]({{ site.baseurl }}/images/arxiv_alert.png)

And that's it! The whole thing is quite easy to do, and you obtain a nice ArXiv alert based on keywords :)
