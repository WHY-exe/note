# What is a Game Engine ?

From my pieces of view a game engine provides basic implementation of some fuctionality like:

1. Graphics Rendering
2. Physics Detection
3. Hardware Input Detection
4. Asset Imporing
5. Some other feature I've missing

And then provides api that access the properites that control the functionality above so that a developer could combine the functionality above to create games. It also provide a basic platform so that we don't have to implement the same basic feature over and over for different platform. Some game engine also provides an editor that helps developers  designning the game layout in a visulaized way

# Overview of Godot Key Concept

In Godot, a game is a **tree of nodes** that group together in **scene.** The nodes can wired together so they can communicating with each other using **signal**

# **Scene And Nodes**

A scene and node in the godot engine is more or less an abstract entity that represent certain component(like 2DSprite, 3D model, Animation and so on), a certain functionality (a character, a level and so on). A scene is consist of nodes and can also be consider as a "node " that made up other scenes, but often we refer to a node for it represent basic functionality. But the key concept here is : the scene and node provide a **common abstracted interface** for a game object

As the game become larger, all the scene would comes together and forming a scene tree.

# Signals

Node could emits signals when some events occours and other node could recieve signals and perform some actions.
