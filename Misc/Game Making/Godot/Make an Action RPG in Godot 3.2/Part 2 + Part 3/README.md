# Part 2 & Part 3

## Character Movement

- To make character movement smooth, set the following script to the player:

```py
extends KinematicBody2D

const ACCELARATION = 500
const MAX_SPEED = 100
const FRICTION = 500

var velocity = Vector2.ZERO

func _physics_process(delta):
	var input_vector = Vector2.ZERO
	input_vector.x = Input.get_action_strength("ui_right") - Input.get_action_strength("ui_left")
	input_vector.y = Input.get_action_strength("ui_down") - Input.get_action_strength("ui_up")
	input_vector = input_vector.normalized()

	if(input_vector != Vector2.ZERO):
		velocity = velocity.move_toward(input_vector * MAX_SPEED, ACCELARATION * delta)
	else:
		velocity = velocity.move_toward(Vector2.ZERO, FRICTION * delta)

	move_and_collide(velocity * delta)
```

- Here:
  - `ACCELARATION`, `MAX_SPEED`, `FRICTION`, `velocity` and `input_vector` are what their names imply;
  - `delta` is the value correlated to FPS that regulated the player movement and action in relation to FPS;
  - `input_vector.normalized()` makes the player walk with consistent speed diagonally instead of going faster;
  - `velocity.move_toward` makes the player move in the direction of a vector, with a certain accelaration (which can be negative ex. Friction);
  - `move_and_collide` makes the player move and collide with coliders.

## Make the player collider

- Create a "CollisionShape2D" node as a child of Player;
- Set Shape as "CapsuleShape2D";
- Go to "Snap" options and turn pixel snap;
- Set "Transform", "Rotation" to -90;
- Make the shape at about the Player's feet;
- For testing, add a "StaticBody2D" node to the World, and make a random shape;
- Attach a "CollisionPolygon2D" to the Static Body;
- Create a random collision shape from the points;
- In the Debug tab, turn on "Visible Collision Shapes";
- Change the `move_and_collide` to `move_and_slide` and don't multiply the final `velocity` by `delta`;
- Equal `velocity`to the `move_and_slide` return value, like so:

```py
extends KinematicBody2D

const ACCELARATION = 500
const MAX_SPEED = 100
const FRICTION = 500

var velocity = Vector2.ZERO

func _physics_process(delta):
	var input_vector = Vector2.ZERO
	input_vector.x = Input.get_action_strength("ui_right") - Input.get_action_strength("ui_left")
	input_vector.y = Input.get_action_strength("ui_down") - Input.get_action_strength("ui_up")
	input_vector = input_vector.normalized()

	if(input_vector != Vector2.ZERO):
		velocity = velocity.move_toward(input_vector * MAX_SPEED, ACCELARATION * delta)
	else:
		velocity = velocity.move_toward(Vector2.ZERO, FRICTION * delta)

	velocity =  move_and_slide(velocity)

```

## Links

- <https://www.youtube.com/watch?v=EQA9MJ5_TxU&list=PL9FzW-m48fn2SlrW0KoLT4n5egNdX-W9a&index=2> ;
- <https://www.youtube.com/watch?v=TQKXU7iSWUU&list=PL9FzW-m48fn2SlrW0KoLT4n5egNdX-W9a&index=3> ;
