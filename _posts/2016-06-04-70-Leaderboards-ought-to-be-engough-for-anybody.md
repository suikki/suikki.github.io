---
layout: post
title: Google Play Games - 70 leaderboards ought to be enough for anybody
permalink: /:categories/:year/:title
slug: 70-leaderboards-ought-to-be-enough-for-anybody
category: dev
tags: android, games, google play services
published: true
comments: true
---

*Google Play Games Services* allows games to easily integrate stuff like achievements, leaderboards and even online multiplayer. It's the obvious service to use on Android, as almost every user is pretty much guaranteed to have an account ready to use without a hassle.

I had glanced at the API when implementing support for Apple's *Game Center* to make sure the same game features would work on both. However, I missed one major limitation: on the Google service **there is a hard maximum limit of 70 leaderboards per game**.

The game we are developing is a great fit with online leaderboards as the whole idea of the game is racing on separate levels to grind the best possible time you can for each level. This also requires that we have a separate leaderboard for each level. So we are basically forced to limit the number of levels in the game to 70 or use some other third party solution.

I also basically wasted 2 days trying to figure out if there was a feasible way to circumvent the limit and still use *Google Play Games Services*. I finally came to the conclusion that it's basically not possible without sacrificing the UX. The only solution that I came up with is adding a separate game entry to the game services for the extra leaderboards and connecting to that separately (but that really isn't a feasible solution at all as you would need to sign in separately either by using oauth or a separate proxy APK).

This basically limits every game like this to 70 levels max forever. If the game gets popular and we want to release more levels we have to make it a separate app. I really hate that.

No solution in sight?
---------------------

There really isn't much I can do but to limit the level count for now and hope that Google improves their service, or start researching using some third party service and hope they are still up when your game comes out.

Also doesn't 70 seem like a strange limit to use. I would think the de facto standard for levels in a game is 99. Wouldn't it make a lot more sense to make the limit nice metric 100? A better solution would be to add leaderboard groups. For example Apple's *Game Center* uses a much more reasonable limit of 100 leaderboards in a group and max 500 total leaderboards.

(As a side note: I feel kind of bad for having to say that Google should take a look what Apple is doing. Apple may build great hardware, but the *Game Center* is just an abomination. Terrible UX (especially for developers), buggy and slow.)
