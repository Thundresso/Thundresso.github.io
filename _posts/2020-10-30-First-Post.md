---
layout: post
title: Day one
---

After a lot of indecisiveness I have chosen GameMaker Studio 2 over Unity as my first language for game development. This is mainly because my initial focus is on creating 2D games, which whilst possible in Unity, has a much steeper learning curve. Having created a platformer in GameMaker Language (GML) before, I thought a refresher on the code would ease me back into rhythm. I followed Shaun Spalding's platformer guide and fiddled around with it until I was comfortable with platformer physics. I then decided that I would test my knowledge by creating some classic games in GML, starting with Snake. I was not ready at all.

Breaking it down, Snake is a game where:
 - The snake is always moving.
 - The snake only ever moves in one direction at a time and cannot turn backwards.
 - Movement, or at the very least turning, is limited to square tiles.
 - Colliding with the wall or it's own tail ends the game.
 - Apples are randomly generated on any tile without a wall or snake tail.
 - **Colliding with an apple consumes the apple and generates an extra tail tile for the snake.**
 - **The snake consists of individual tail tile segments that follow the path of the head.**
 
Generating the tail segments posed the biggest issue, as it wasn't intuitive to me how to generate an object and make it follow another generated object. The long-winded and most likely inefficient solution was upon collision, generate an instance of a tail segment one movement behind the previously generated tail segment.

```
tail[segments] = instance_create_depth(global.tail_id[segments-1].x-global.tail_id[segments-1].hsp,
global.tail_id[segments-1].y-global.tail_id[segments-1].vsp, 0, oSegment)
```

Each tail segment is stored in the array tail[segments] and can be referenced by another tail. They can then be made to follow the previous tail's movement by finding the difference in their x and y values, and setting it as how many pixels to next move.

```
if !(oSnake.hsp = 0 && oSnake.vsp = 0)
{
	if (segments = 0)
	{
	hsp = oSegment2.x-x
	vsp = oSegment2.y-y
	}
	else
	{
	hsp = global.tail_id[segments-1].x-x
	vsp = global.tail_id[segments-1].y-y
	}
}
```
Finally, creating a new title screen to choose difficulty was much simpler. Setting difficulty only needed to change the time required between each snake tile movement. A score system could also easily be added with the draw_text function. 

The project took one day overall to learn and complete.

Bugs:
 - Tails sometimes generated in unexpected positions (FIXED)
 - Apples disappeared sometimes (FIXED)
 - Upon death, the third tail segment disappears because the first two segments follow into the head. (Fixed during export?)
 
 [Play here](https://thundresso.github.io/Snake-ripoff/)
