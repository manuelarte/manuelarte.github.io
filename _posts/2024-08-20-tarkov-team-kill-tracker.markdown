---
layout: post
title:  "Tarkov Team Kill Tracker"
date:   2024-08-20 17:10:37 +0100
categories: post
---

I want to learn 🦀Rust🦀, and for that I decided to do a fun project.

I confess I really like the game [Escape From Tarkov](https://www.escapefromtarkov.com/), for the ones don't know, it's a shooter-looter quite challenging.

Here you can find a video of me, killing one of the most difficult bosses in the game, [Killa](https://escapefromtarkov.fandom.com/wiki/Killa):

[![IMAGE ALT TEXT HERE](https://img.youtube.com/vi/0CEOcQhw3Is/0.jpg)](https://www.youtube.com/watch?v=0CEOcQhw3Is)

When you play with friends, there is no way to identify who is your teammate (apart from asking questions like: `is that you?`, `are you in <insert place>?`).

For that reason, it's quite common to have [team kills](https://en.wiktionary.org/wiki/teamkill). 👀

# 💡Idea
I thought it could be a good idea to create a [Discord bot](https://discord.com/developers/docs/intro) to keep track of the team-kills that happens. To make it a bit more fun it could have achievements. I came up with some of them, as an example:

+ 🎉First team kill registered🎉
+ 👺Killed by five different friends👺
...

+ Also, to promote people using this bot, I thought it could be nice if the `"killer"` get roasted by that team-kill. So then, once the team kill is registered, ChatGPT would reply to the command by roasting the player that made the team-kill.

# 👷Implementation

The flow is the following:
+ User registers who team-killed him using a discord command: `> /tk @Manuelarte`
+ App registers the team kill and
+ Checks for achievements
+ Requests to ChatGPT a Roast to the user.
+ Replies the message to the author plus the achievements achieved with that team-kill.


[comment]{% plantuml %}
[comment]@startuml

[comment]skinparam actorStyle awesome
[comment]node {
[comment]actor User
[comment]component [Discord]
[comment]}
[comment]
[comment]node Bot {
[comment]component [Backend]
[comment]database DB
[comment]}
[comment]
[comment]node {
[comment][ChatGPT]
[comment]}
[comment]
[comment]User --> [Discord]: User Writes TeamKill Command
[comment][Discord] --> [Backend]: Discord send TeamKill Command to bot
[comment][Backend] --> DB: Stores the team kill
[comment]DB --> [Backend]
[comment][Backend] --> [ChatGPT]
[comment][ChatGPT] --> [Backend]: Roast output
[comment][Backend] --> [Discord]: Command Reply
[comment][Discord] --> User: Roast Message
[comment]
[comment]@enduml
[comment]{% endplantuml %}

# Technologies/Frameworks Used:

Here is a list of some of the libraries used for this project:

+ [Poise](https://github.com/serenity-rs/poise)
+ [Diesel](https://diesel.rs/)
+ [r2d2](https://github.com/sfackler/r2d2)