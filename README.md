# The relationship of pocket monsters in the game


In this case, we use the game's publicly available dataset, imported into studio, to show you how to take advantage of the Nebula Graph to demonstrate the value of the graph database. Interested users can try it out for themselves (GameMonsters Graph database).

## Quick start.
1. Visit Nebula Playground: [Game_monsters](https://playground.nebula-graph.com.cn/explore?name_space=Game_Monsters)
2. Click on "Start exploring". 3.
3. There are 2 ways to import data.
    > Method 1: VID query, fill in a list of IDs for the following vertices:<br>
      monster001 <br>
      monster002 <br>
      monster003 <br>
      monster025 <br>
      monster026 <br>
      monster133 <br>
      monster134 <br>
      monster135 <br>
      monster136 <br>

    > Method 2: Click on the index query, select the tag and index, add a quantity limit, e.g. 50, click on the plus sign and add an index condition, for example：monster、person、property

4. By this time the vertices should be displayed, you can double click them, or use the right sidebar to expand the conditions for edge expansion.



## Details.
Game business scenarios often encounter relationship problems, characters and characters, characters and monsters, pets, NPCs, props, etc.

With the traditional form of tables, it is impossible to find the required relationships intuitively, here we take the game as an example, using publicly available data to provide everyone online experience Nebula Graph graph database.

The structure of this game dataset, as shown in the figure:<br
##### Tag: monster, property, person <br>
##### Vertex: 151 monsters, 9 properties, 13 characters <br>
##### Edge: property relationship, damage doubling, damage halving, attribution, evolution relationship <br>

! [monsters](game-monsters-images/Frame1.png)


Let's start by looking up something related to a famous 025 yellow monster.
* Go to the studio graph exploration screen.
* The top left corner confirms that we are currently in the Game_Monsters space (the space of the game dataset)
! [monsters](game-monsters-images/image001.png)
* Click the Start Exploration button on the right
! [monsters](game-monsters-images/image002.png)
* Enter vid: monster025

* Click to confirm
! [monsters](game-monsters-images/image003.png)

You can find out the vertex of the yellow charged monster number 025. (VID is monster001 - monster151)

! [monsters](game-monsters-images/image004.png)
Double click on the point to automatically expand all related points

For example, you can see the vertex of a certain monster with a longer tail and a charged partner, 026, of the evolutionary relation 025.
! [monsters](game-monsters-images/image005.png)

At the same time click on the attribute display button, check the box to select the attributes we need to display, you can see the vertex in the figure corresponding to the value of the attribute. For example: name, attack power, defense power, etc.
! [monsters](game-monsters-images/image006.png)

! [monsters](game-monsters-images/image007.png)

! [monsters](game-monsters-images/image008.png)

In the result of the query, we can also see that there is a vertex for the attribute, and the tag for the monster attribute, with the same name.

> How to build the data structure often needs to be designed by the user

! [monsters](game-monsters-images/image009.png)

Clicking on this attribute vertex will automatically expand it, at this vertex we can visually view all the monsters with electric attributes, each vertices shows the corresponding attribute value, and intuitively find all the monsters of the electric family
! [monsters](game-monsters-images/image010.png)

With the right sidebar, we can also expand the edges exactly as needed.

For example, keeping only one vertex of the canvas, the electric property
* delete the rest of the vertices of the canvas.
* click on the edge type in the right sidebar and select only damage
* Select outflow for direction, 1 for step, and leave everything else the same
! [monsters](game-monsters-images/image011.png)
* This time click the expand button, you can expand the attribute relationship, you can see the relationship of attacking other attributes through the edge, electricity attribute can do double damage to water attribute, but half damage to grass attribute, and very low damage to rock attribute.
! [monsters](game-monsters-images/image012.png)


### Now, let's look up the character relationships
By vid query enter <br>
person1 <br>
person2 <br>
person3 <br>
person4 <br>
person5 <br>
person6 <br>
person7 <br>
person8 <br>
person9 <br>
person10 <br>
person11 <br>
person12 <br>
person13 <br>

! [monsters](game-monsters-images/image013.png)

From the results, you can see 8 big city dojo directors, former champions, and 4 major divas
! [monsters](game-monsters-images/image014.png)

Double click on a person's vertex to see the monsters he has
! [monsters](game-monsters-images/image015.png)

Clicking on each monster allows us to quickly expand the relationship and find the attributes that are incompatible with each other
! [monsters](game-monsters-images/image016.png)

Double click on the restraining attribute to quickly expand a group of monsters with that attribute, and select the monsters you have to double the damage on the boss's monsters, or select the monsters that halve the damage for defense.
! [monsters](game-monsters-images/image017.png)



> #### This is a typical way to use graphs for quick game strategy search, and they have a huge advantage over the traditional table format in terms of correlations.

We hope this public data demo is helpful for you to win the game.

If you are interested in the example, click Quick Start and try it out for yourself.

[Game_monsters](https://playground.nebula-graph.com.cn/explore?name_space=Game_Monsters)

Reference.

Studio video presentation https://www.bilibili.com/video/BV1QN411Z7Vh . <br>
Figure Exploration, Nebula-Studio Manual https://docs.nebula-graph.com.cn/master/nebula-studio/st-ug-toc/ <br>
nGQL, CRUD manual https://docs.nebula-graph.com.cn/master/2.quick-start/4.nebula-graph-crud
 Translated with www.DeepL.com/Translator (free version)
