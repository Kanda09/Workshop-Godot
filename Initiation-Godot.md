# Workshop - Initiation à Godot

## What is Godot

Godot is a free and open source game engine to develop and create 2D and 3D games, that can be played in linux, windows and even in web !

## Install Godot

In order to install Godot follow this link: https://godotengine.org/download/linux/ (for Linux) and https://godotengine.org/download/windows/ (for Windows).

Install the version of godot corresponding to your compute

If you have issue at install feel free to contact us !

## Create a new project

Create a new Godot project in the path you want.

__NOTE__: You may need this: [Godot Documentation](https://docs.godotengine.org/en/stable/)

## Create a Player !

We will here try to create few nodes representing the player, the player's root node, the collision node or the animation sprite node.

Then we will assign to this new player we had scripts to make him move and have a beautiful life :3.

### Godot is pretty :blush:

**APPRECIATE HOW PRETTY IS GODOT !**

![Image](img/godot-new-project.png)

Oh...

You're not conviced ?
Let's see what godot is capable of !

### Node and Scene

Godot Game Engine works with 2 main components **scenes** and **nodes**.

* A **node** is a "*block*" containing informations about the game logic, the rendering or the User Interface (UI) display.
**Nodes** are organised as a tree, you have a main node which has childs nodes and thoses childs nodes have childs too and so on.

* A **scene** is a regroupment of node that are organised as a tree, they represents specific logics in the game, like a `Player` or an `Enemy`.

Understanding this game engine architecture is the key to the development of amazing games in Godot. We **encourage** you to look at the documentation about that: [nodes and scenes](https://docs.godotengine.org/en/stable/getting_started/step_by_step/nodes_and_scenes.html).

### Create your first scene !

Try creating you first scene and name it `player.tscn`, this scene should contains a `Node2D` as the root node. 

All the player's subnode will inherit of this node.

### Create Player nodes

As we said before we need a few nodes for the player to handle 2D physics or collisions.

#### Player base node

First, create a new player node for the player, to do so we suggest you to take a look at `CharacterBody2D`, it has everything you want :3.

Name this base node, `Player` (It will be simpler to handle it).

Create a child node to the node `Player` and choose a collision node (we let you figure it out which one :D), and choose a Rectangle Shape for this node.

Now let's take a look at the 2D view of godot:

![](img/godot-rectangle-shape.png)

Here you can manipulate and move you collision shape as you wish !

#### Sprite Player

Our player is really ugly when we think about it.

Yeah, I know, what player you're asking ?

You're right, a collision shape cannot represent how **Magnificient** our player can be !

So let's try to change his look a little bit !

Add the to `Player` a `AnimatedSprite2D` node and select the spritesheet you want !

Yes, as we are really good people, we did not choose to steal other's work...

Yeah people like us still exists !

We still suggest you a really good spritesheet: [pixel-adventure-1](https://pixelfrog-assets.itch.io/pixel-adventure-1)

>! Don't forget the tip !

#### Handle enemy collisions

*Hey, but didn't we already added a collision node ?*

Yeah, you're right, but we only handled the physical effect of a collision without taking account of the object we collide with or the side effect we would have wanted !

>! If you did not understand my last sentence take a look at the difference between `CharacterBody2D` and `Area2D`.

### Player Script

Now let's do some coding, we have to attach a script to the `Player` node to be able to control him.

#### Sprite Movements

It will be probable that the Godot UI already gives you the `_physics_process` function which permits to implement the character physics.

However, let's try to go a little bit further in the exercice !

* Implement player's movements with arrow keys
* The player should not fall below 100 on Y coordinate (We will later add a floor).
* If the player has the SHIFT Key pressed it should go `k` times further (value `k` is yours to choose)

#### Sprite Animation

In a script there is a function that is called one time at the begining, when the scene is load, it is: `_ready` and there is also a function that is called each time you want the game updates and it is `_process`.

Inside this function, call a function named `add_animation` (that you must create), that will update the animation state based on the velocity, the position, everything you want.

Exemple:
```gd
func add_animation():
    if velocity.x == 0:
        ....
    ....
```

### Repository

Hey, I saw you !

Does your repository look like this ?:

![Bad File architecture](img/godot-file-bad-architecture.png)

If so we're going to change it, imagine you want to add 10 scenes, you would put it all these files in specific directories.

* All scenes should be in a `scenes` directory
* All scripts should be in a `scripts` directory
* All assets should be in a `assets` directory

Like:

![Good File architecture](img/godot-file-good-architecture.png)

Isn't it better now ?

## Floor

## Enemies

## Bonus

=> Custom End of game
=> New enemies
=> The floor is lava

