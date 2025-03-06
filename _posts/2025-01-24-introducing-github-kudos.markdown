---
layout: post
title:  "🙌Introducing GitHub Kudos"
date:   2025-01-24 08:18:37 +0100
categories: post
---

One thing about being a developer, is how frustrating the job search process can be. One of the things I encountered was the request for recommendations from other colleagues.

I am lately quite active in GitHub, I created some small libraries, and I also contributed to others, so, in case any recruiter checks my GitHub profile (most recruiters don't do), they can see my repositories, but there’s no straightforward way to showcase who you’ve worked with or who recommends working with you.

# App GitHub Kudos
GitHub lacks a simple, personalized way to share personalized shoutouts, so I decided to build a solution: GitHub Kudos.

GitHub Kudos is an app that generates an image featuring a GitHub user's avatar with their recommendation. My intention is that these images can be displayed in GitHub profiles and/or personal websites to share how other developers recommend you (or who you recommend).

If you want to see how it looks, you can check [my profile](https://github.com/manuelarte#-people-i-recommend)

Or if you want to see how the image looks by itself [link](https://github-kudos.com/manuelarte/kudos/octocat)

![](https://github-kudos.com/manuelarte/kudos/octocat)


I don’t think this will completely eliminate recruiters asking for recommendations, but I hope it makes it easier to share and showcase them. 😊

# How Does It Work

The app is quite simple, let's say Alice (GitHub login alice) wants to recommend Bob (GitHub username bob), then these are the steps:

+ Alice creates a repository called github-kudos (alice/github-kudos).
+ Alice creates a file bob.md in which she writes her recommendation to Bob.
+ Either Alice or Bob can access the kudos image by https://github-kudos.com/alice/kudos/bob
+ (I created a [template repository](https://github.com/manuelarte/github-kudos-template) in GitHub to facilitate this setup)