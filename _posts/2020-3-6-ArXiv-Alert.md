---
layout: post
title: ArXiv Alert
---

ArXiv is an incredible tool to get access to research papers, but it has one drawback for me: there are too much papers in it! I want to filter new ArXiv based on my research interests, so here is how I created an ArXiv Alert.

<br/>

# A Python script to create an ArXiv Alert

In fact, as a researcher in Machine Learning (and working on Adversarial Examples), I usually use ArXiv to know and read new papers related to my research areas. Obviously, I can go on the website and search for papers manually, but it is easier and nicer to have an alert browsing for me on ArXiv and feeding me with relevant papers only.

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

![_config.yml]({{ site.baseurl }}/images/arxiv_alert.png){:height="1000%" width="1000%"}

And that's it! The whole thing is quite easy to do, and you obtain a nice ArXiv alert based on keywords :)