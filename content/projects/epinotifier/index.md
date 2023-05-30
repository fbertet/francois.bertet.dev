---
title: EpiNotifier
date: 2016-10-01
weight: 30
tags: [android]
---

<img style="float: right;width:10%" src="epinotifier_icon.png">

{{< lead >}}
An Android app to consult and get notified about EPITA newsgroups.
{{< /lead >}}


## Project Genesis

During the first year of EPITA engineering cycle, EPITA students are mentored and assisted by final-year students to realize one C/C++/Java/... project per week.

All the communication like questions/answers, requirements updates, ... is done through [Usenet newsgroups](https://en.wikipedia.org/wiki/Usenet_newsgroup), an old fashion way of messaging based on NNTP (Network News Transfer Protocol) from before the advent of World Wide Web and discussion forums.

To navigate through news, we used the usenet client SLRN.

![SLRN](slrn.png "SLRN, example of Usenet client.")

**Problems:**
- There is no native way to get notified about activity while not being aware of project requirements updates can cause significant time loss. Students were forced to frequently and manually check newsgroups.
- Most of usenet clients are terminal based and not really user friendly → See above SLRN screenshot 😬.

From this came the idea of **EpiNotifier**, a Mobile application allowing to navigate through EPITA newsgroups easily and to subscribe to some of them to receive notifications in case of activity.

Like [EpiRoom](/projects/epiroom), this project has been developed during my studies as a side project. It took almost one year from the initial idea to the release of the project.


## EpiNotifier Android App

### Overview

![EpiNotifier overview](epinotifier.png "EpiNotifier Homescreen / Newsgroup screen / News screen")

EpiNotifier main features:
- Navigate in the news through a nice interface.
- Subscribe to newsgroups to receive notified in case of activity.
- Do advanced searches.
- Bookmark news to retrieve them easily.

![Example of notifications](epinotifier_notification.png "Example of notifications")

On the design side, EpiNotifier is following Material design guidelines.
To make the application look alive, many animations have been implemented like the bell that seems to ring when the user subscribes to a newsgroup.

On the technical side, EpiNotifier has been developed in Java following the MVC (Model–view–controller) software architecture pattern.

It embeds some well known libraries:
- [Retrofit](https://github.com/square/retrofit): A type-safe HTTP client for Android and Java.
- [Butterknife](https://github.com/JakeWharton/butterknife): Field and method binding for Android views using annotations.
- [EventBus](https://github.com/greenrobot/EventBus): A publish/subscribe event bus for Android.
- [Crashlytics](https://firebase.google.com/products/crashlytics): A crash reporting tool.
- [Google Analytics](https://analytics.google.com/analytics/web/): A web/mobile analytics service offered by Google.
- ...

Because of the fragmentation of android versions on the market, the choice was made not to use the latest features of standard libraries to make the application compatible with `Android 4.0 Ice Cream Sandwich`.


### Adoption & support

EpiNotifier has been released on the Google Playstore the 21 September 2016.

![Google Analytics](google_analytics.png "Google Analytics - First days")

In order to ensure the support of the product, two tools have been setup:
- Google Analytics: To track the application usage, number of users, ...
- Crashlytics: To get data about crashes.


## EpiNotifier Backend

Although we designed the RESTful API together, the Backend part of this project has been developed by a friend of mine, [Julien Dubiel](https://www.linkedin.com/in/juliendubiel) as part of *NGNotifier*, a web equivalent of EpiNotifier.

This Backend part was especially needed to handle notifications. It also made the development of EpiNotifier easier by adding an abstraction layer on the NNTP protocol.
