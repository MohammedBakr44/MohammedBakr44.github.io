---
author: Mohamed Bakr
pubDatetime: 2025-03-29T03:41:36.086Z
title: Connectors' CTF RE writeup 
featured: true
draft: true
tags:
    - CTF
    - Reverse Engineering
    - Game Hacking 
description:
    Starwars2 and Rusty challengs writeup from Connectors CTF finals.
---

الْحَمْدُ لِلَّهِ حَمْدًا كَثِيرًا طَيِّبًا مُبَارَكًا فِيهِ

Recently I participated in Connectors CTF along with my team "منتخب القهوة".
[Awad](https://www.linkedin.com/in/awad-ramadan-42571a2a6) and I were tackling Reverse Engineering challenges, unfortunately we couldn't get the flags on time but we achieved a great progress and learned a lot in the journey.

## Starwars2 

We were able to secure to the first blood for this challenge only 35 minutes in competition.

![](https://cdn.imgchest.com/files/3318f13bd3ec.png)

![](https://cdn.imgchest.com/files/97abf9f0fc66.png)

First I started the game to show off my gaming skills

![](https://cdn.imgchest.com/files/1b939354136f.png)

First two levels were easy I was able to 360 my way in. However, the 3rd level was an impossible to beat souls level.

![](https://cdn.imgchest.com/files/12146ce18f62.PNG)

Since the game is created using Gamemaker, I started [Undertalemodtool](https://github.com/UnderminersTeam/UndertaleModTool).

![](https://cdn.imgchest.com/files/e4fb9d362e2f.png)

I ignored the error and started digging, the game didn't have a code section unlike Starwars 1

![](https://cdn.imgchest.com/files/32d48a45df39.png)

But we have other interesting options.

### Aha moment!

I thought for a minute, what if we made ourselves invincible so I GPTed my way to find out how can I disable collision in the game.

Expanding game objects and checking properties for `Obj_rock_big` I found a collision event but it was between the bullet and the rock so it won't help, I moved to check the the player object and voila!

![](https://cdn.imgchest.com/files/e91aee9826f9.png)

We can see it has a collision event with the player's sprite. After removing the event we don't have a collision with the rock but it wasn't enough to beat the 3rd level.

![](https://cdn.imgchest.com/files/e248a298a9eb.png)

So I decided to get back the rock object.

The rock object contains two other important events that I overlooked previously.

![](https://cdn.imgchest.com/files/2c6837cdea9f.png)

1- Creates a new rock.
2- step event which works every frame.

I removed both events and tested again, and still didn't work. I removed all events of the rock object but I kept losing to the last room.

So I decided to remove the whole sprite because why not.

![](https://cdn.imgchest.com/files/7b6cfb1c9466.png)

Now I'm alone in the space

![](https://cdn.imgchest.com/files/86896e0bb974.png)

All I had to do was to wait for the timers to finish.

![](https://media1.tenor.com/m/XMVz4JeILUMAAAAC/ladies-and-gentleman-we-got-him.gif)


![](https://cdn.imgchest.com/files/32c5ff1e7de9.png)


That solution was never intended, that's Karim's reaction after I showed him the steps.

![](https://cdn.imgchest.com/files/ca5fcea4120c.png)


