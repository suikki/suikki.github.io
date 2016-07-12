---
layout: post
title: Google Play: Unexpected error (4800403)
category: dev
tags: [google play services]
published: false
comments: true
share: true
---

Just documenting an error I came across for other poor souls that may encounter this.

---

I'm using my own google account to access the Google Play Developer Console. On the actual account owning the game I have configured my personal account to have administrator access to the project.
One day, out of the blue, I started getting an error every time I tried to save something under the Game Services.

> An unexpected error occurred. Please try again later. (4800403)

I'm not sure what changed and I'm fairly certain everything worked on both accounts before. The number 403 in the error suggests some kind of authorization problem.


The solution
------------

As a Google search gave no hits with the same error code, I contacted Google support. Their first suggestion was to check permmissions in both the Play Console and
Google API Console. Indeed, adding my personal account also to the API console fixed the error.

(Under https://console.developers.google.com/iam-admin/projects I selected my project and added the other account with the permissions I needed.)

