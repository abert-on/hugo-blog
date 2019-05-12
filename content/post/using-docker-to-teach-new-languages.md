---
title: "Using Docker to teach new languages"
date: 2019-05-13 15:00:00 +0100
tags:
- docker
- docker-compose
- go
- golang
- mongoDB
- coaching
- programming
params:
  description: "Often the hardest, most time-consuming, part of running a hands-on teaching session to a room of developers is getting everyone's environment set up. What if there was an easy way to get everyone up and running quickly at the start of the session? Here are my experiences with using Docker to do just that."
  images:
  - "img/go-docker.png"
draft: true
---
Often the hardest, most time-consuming, part of running a hands-on teaching session to a room of developers, is getting everyone's environment set up. What if there was an easy way to get everyone up and running quickly at the start of the session? Here are my experiences with using Docker to do just that.
<!--more-->

### Headless chickens

As part of our monthly "Hive" or community days, the development community quite often run sessions to look at languages or frameworks outside of our usual tool set. Having previously run sessions on React and Kotlin, we decided next to take a look at the Go programming language. Previous sessions, however, had taught us that a lot of the start of the session ends up with session lead running around like a headless chicken, helping everyone get the right tools installed and configured. With each developer's PC often producing different results, combined with different people having preferred ways of doing things, means that this initial part is often the most challenging. This often resulted in people losing interest and not getting anything out of the session. So how could we avoid this in our Go session and give, not only ourselves more time for teaching, but also our participants more time for learning?

Luckily for us, each developer that joined our session had one thing in common. They used Docker as part of their day-to-day work. It was thought that we could utilise this to provide out-of-the-box environments for building and running everyone's Go coding examples.

![Go Docker]("img/go-docker.png)

### The set up

Having not long finished a project to create a new set of RESTful APIs using Java and Spring Boot and Web MVC, the goal of the session was to create a simple set of APIs in Golang. With the experience of Java fresh in our minds, it would be an interesting comparison.

A set of movie data would be put in to a MongoDB database, and people would then use Mux and ??? in Go to expose it to GET, POST, PUT and DELETE endpoints.

A docker volume would link the code people had written locally to the Go container, with the code being compiled on start-up of the container. If the container failed to start, then the Docker logs would tell us why. One slight complication was that throughout the office we had a split of people using Docker in Linux and people using Docker for Windows. This meant we had to be careful declaring the volumes so both the Go and Mongo containers would work in both set-ups.

Here's what the docker-compose file looked like:

``` yaml

```

A simple `docker-compose up -d` would bring the stack up, compile and then start the application on port ???.

### The result

Apart from some initial confusion caused by a typo in the set-up guide, the general consensus at the end of the session was that this set-up worked well.  Whether they were using a Linux VM or Docker for Windows, many attendees commented on how easy it was to get up-and-running and that they were able to quickly get to grips with developing in Go. Personally, I felt I had to help out a lot less at the beginning and was able to relax and attend other session running at the same time.

Of course we were massively helped by the fact that everyone already had familiarity with Docker and had been using for their everyday development. Without this, the start of the session would have involved running around getting everyone up-and-running on Docker.

Overall it was a success and something we hope to utilise in the development community again in future sessions.

---

> This session on Go was run at one of the monthly community (or "Hive") days at Equiniti. If you'd like to join our culture of learning, then check out our [current vacancies](http://equiniticareers.com/opportunities/).