---
layout: post
title: Day one
---

After a lot of indecisiveness I have chosen GameMaker Studio 2 over Unity as my first language for game development. This is mainly because my initial focus is on creating 2D games, which whilst possible in Unity, has a much steeper learning curve. Having created a platformer in GameMaker Language (GML) before, I thought a refresher on the code would ease me back into rhythm. I followed Shaun Spalding's platformer guide and fiddled around with it until I was comfortable with platformer physics. I then decided that I would test my knowledge by creating some classic games in GML, starting with Snake. I was not ready at all.

Conceptually Snake seemed like a simple, easy game to make. However, breaking it down revealed many new concepts for me to learn.
 - The snake is always moving.
 - The snake only ever moves in one direction at a time and cannot turn backwards.
 - Movement, or at the very least turning, is limited to square tiles.
 - Colliding with the wall or it's own tail ends the game.
 - Apples are randomly generated on any tile without a wall or snake tail.
 - **Colliding with an apple consumes the apple and generates an extra tail tile for the snake.**
 - **The snake consists of individual tail tile segments that follow the path of the head.**
 
Since I am clueless when dealing with GML, there will be a lot of extremely obvious information ahead. 

Tile-based movement was different to traditional movement in that rather than having a constant horizontal or vertical velocity, a repeated timer was used for each movement. The snake has a constant velocity equal to the tile size, however doesn't actually move unless the timer goes off. Pressing an arrow key before the timer goes off changes the direction of velocity and causes the snake to turn. The difficulty comes in when dealing with the snake's tail. Logically there were two ways to deal with this issue:

 - Recording each step of the snake head, and have each segment follow in their respective steps behind.
 - Have the first segment take the place of the head, then the second segment take the place of the first segment and so on like a conveyor chain.


 



