# Part 1 | Project Setup

## Set up project

- Make project 2D mode;
- Go to your icon.png;
- Go to the "Import" tab;
- De-select "Filter", by clicking the checkbox;
- Reimport;
- Go to "Preset";
- Click "2D Pixel";
- Reimport;
- On "Preset", click "Set as default for "Texture""
- Reimport;
- Now drag all your sprites, images, etc to your project.

## Set up World Scene

- Create a 2D root node;
- Save scene;
- Run the game;
- Set "World" as main scene;

## Project Settings

- Go to "Project Settings" on the "Project" tab;
- Go to "Display", "Window";
- Set "Width" to 320 and "Height" to 180;
- Set "Test Width" to 1280 and "Test Height" to 720;
- Set "Strech", "Mode" to 2d;
- Set "Strech", "Aspect" to keep;

## Learn Project Structure

- The Main building block in Godot are Scenes;
- Scenes are composed of Nodes;
- It's all organized in a tree structure;

## Make a Player

- Create a new Player scene;
- Create a "KinematicBodyType2D" scene as the root node for the player;
- Create a child "Sprite" node;
- Give it "Sprite", "Texture", your player texture, with all the animation frames;
- Change the HFrame to the initial Player stance (ex. 60);

## Add a Script to the player

- Debug using `print()` to log values;
- Use the "Search help" feature to search for documentation on Godot script;
- Gd script uses tabbing, and python-like syntax;
- Use `func` to create functions;
- The `func _ready()` function is called when the node is intialized;
- Using `func _<func_name>()` the "\_" means it's a callback function;
- Use the function `func _physics_process(delta)` function, like;
- This function gets called every single tick that the physics update;

## Getting Input

- In the `func _physics_process(delta)` function, insert `if Input.is_action_pressed("ui_right):`;
- For example:

```py
extends KinematicBody2D

func _physics_process(delta):
    if Input.is_action_pressed("ui_right"):
        print("The right key has been pressed")
```

- Or, for player movement:

```py
extends KinematicBody2D

func _physics_process(delta):
    if Input.is_action_pressed("ui_right"):
        position.x += 10
```

## Links

- <https://www.youtube.com/watch?v=mAbG8Oi-SvQ&list=PL9FzW-m48fn2SlrW0KoLT4n5egNdX-W9a> ;
