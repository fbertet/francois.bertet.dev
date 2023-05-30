---
title: EpiRoom
date: 2016-06-21
weight: 40
tags: [android, python]
---

<img style="float: right;width:10%" src="epiroom_icon.png">

{{< lead >}}
An Android app and its Backend to get information about EPITA classrooms availability.
{{< /lead >}}


## Project Genesis

At EPITA students can rely on *EpiLife*, a Mobile application (Android \& iOS) to get information about their timetables.

![EpiLife Android app](epilife.png "EpiLife Android app")

But timetables are not always full, so during inter-course we were frequently going to unused classrooms to work on school projects / prepare our exams.

**Problem:** To do so, the only solution was to manually check every classroom to find an available one. Then, it often happened that 30 minutes after settling in, a teacher arrived and took over the room 🥹.

From this came the idea of **EpiRoom**, a Mobile application allowing to see which classrooms are available and for how long (Based on all classes timetables).


## EpiRoom Python Backend

![EpiRoom Backend illustration image](backend.jpg)

For this project, a custom Backend in Python using Flask and PonyORM (Based on a SQLite Database) has been developed.

Three reasons:
- The school API was mainly designed to deliver classes timetables. Getting information about rooms availability needed multiple requests.
- I didn't had an official access to the school API and didn't wanted being responsible of an unintentional Denial of service attack 😄.
- It was an excellent opportunity to learn stuff about Backend development 🚀.

This Backend server is responsible of polling the school API every hour to get information about classes timetables, deduce rooms availability from it, store it in a SQLite database and serve all these information through a simple RESTful API.


## EpiRoom Android App

This app has been developed in Java with the help of some well known libraries:
- [Retrofit](https://github.com/square/retrofit): A type-safe HTTP client for Android and Java.
- [Butterknife](https://github.com/JakeWharton/butterknife): Field and method binding for Android views using annotations.
- [MPAndroidChart](https://github.com/PhilJay/MPAndroidChart): A powerful & easy to use chart library.
- ...

![EpiRoom Android app](epiroom.png "EpiRoom Android app")

The app follows Material Design guidelines and has been thought to address user's need (Know which room to go to) as quick as possible. To do so, the approach was to display these information in the form of a horizontal bar graph, with rooms ordered by availability time.
