---
layout: post
title: 70 Leaderboards Ought to Be Enough for Anybody
category: dev
tags: [android, games, google play services]
published: false
comments: true
---

*Google Play Games Services* allows games to easily integrate stuff like achievements, leaderboards and online multiplayer. It's the obvious service to use on Android, as almost every user is pretty much guaranteed to have an account ready to use without a hassle.

I had glanced at the API when implementing support for Apple's *Game Center* to make sure the same game features would work on both. However, I missed one major limitation: the Google service **has a hard maximum limit of 70 leaderboards per game**.

The game we are developing is a great fit for online leaderboards as the whole idea of the game is racing on separate levels to grind the best possible time you can for each level. This also requires that we have a separate leaderboard for each level. So we are basically forced to limit the number of levels in the game to 70 or use some other third party solution instead of play services.

I also basically wasted 2 days trying to figure out if there was a feasible workaround to get around the limit and still use *Google Play Games Services*. I finally came to the conclusion that it's basically not possible without sacrificing the UX. One solution would be addinng a separate game entry to the game services for the extra leaderboards and connecting to that separately (but that really isn't a feasible at all as you would need to sign in separately either by using oauth or a separate proxy APK).

This basically limits every game like this to 70 levels max. If we want to release more levels after the release we basically have to make it a separate app. I really hate that.

It might be a long wait
-----------------------

There really isn't much I can do but to limit the level count for now and hope that Google improves their service, or start researching using some third party service and hope they are still up when your game comes out.

Also doesn't 70 seem like a strange limit to use. I would think the de facto standard for levels in a game is 99. Wouldn't it make a lot more sense to make the limit nice metric 100? A better solution would be to add leaderboard groups. For example Apple's *Game Center* uses a much more reasonable limit of 100 leaderboards in a group and max 500 total leaderboards.

As a side note: I feel kind of bad for having to say that Google should take a look what Apple is doing. Apple may build great hardware, but the *Game Center* is just an abomination. Terrible UX (especially for developers), buggy and slow.
