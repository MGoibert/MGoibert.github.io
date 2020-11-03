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

Next, to run this script automatically every week, there are two solutions on Mac.

The first, crontab, one is easier to use, but not recommended, and you can go through permission errors when using it on a recent OS version (Mojave or Catalina). Still, here is how to run your arxiv alert script: you just have to open your Temrinal, and run the following commands:

{% highlight r %}
crontab -e
{% endhighlight %}

which opens a document where you can lists all the scripts you want to run on a timely basis. In my case, I wanted my code to run every Monday morning at 10 am. The relevant code line is then:

{% highlight r %}
0 10 * * 1 /Your/python3.7 /The/Relevant/Path/arxiv_alert_script.py
{% endhighlight %}

You can find a nice explanation on how to use crontab [here](https://www.google.com/search?q=use+crontab+mac&rlz=1C5CHFA_enFR880FR880&oq=use+crontab+mac&aqs=chrome..69i57j0l7.2654j0j7&sourceid=chrome&ie=UTF-8#kpvalbx=_szxiXpb9FZadjLsPr9qL6AE31 "Crontab explanation"){:target="_blank"}.



The second option is to use launchd (see [here](https://killtheyak.com/schedule-jobs-launchd/ "Launchd explanation"){:target="_blank"} for a nice introduction to launchd), which does more or less the same thing as crontab (there are some slight differences), and is the recommended way to schedule scripts on a Mac.
To use launchd, you have to create a .plist file which specify all the required information for your script to run. This .plist file should be located in your `~/Library/LaunchAgents/` folder. Mine is called `com.arxiv_alert.daemon.plist`.

This file contains the following lines (you should adapt the text in capital letters), that will make my arxiv alert script execute every monday at 9 am:

```html
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple Computer//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
        <key>Label</key>
        <string>MY_PLIST_FILENAME.plist</string>
        <key>ProgramArguments</key>
        <array>
                <string>/YOUR/PYTHON/PATH</string>
                <string>arxiv_alert_script.py</string>
        </array>
        <key>StartCalendarInterval</key>
        <dict>
                <key>Hour</key>
                <integer>9</integer>
                <key>Minute</key>
                <integer>0</integer>
                <key>Weekday</key>
                <integer>1</integer>
        </dict>
        <key>UserName</key>
        <string>YOUR USER NAME</string>
        <key>WorkingDirectory</key>
        <string>THE/FOLDER/WHERE/IS/LOCATED/THE/ARXIV_ALERT/SCRIPT</string>
</dict>
</plist>
```

Then, all you have to is to load what we have just done so that your scheduled process is taken into account: `launchctl load ~/Library/LaunchAgents/MY_PLIST_FILENAME.plist`.

<br/>

# Rendered output

The final HTML file looks like this:

<div class="resized_img">
  <img width="725" height="725" src="{{ site.baseurl }}/images/arxiv_alert.png">
</div>

And that's it! The whole thing is quite easy to do, and you obtain a nice ArXiv alert based on keywords :)