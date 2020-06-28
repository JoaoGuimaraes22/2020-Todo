# Part 6

## AnimationTree

- Create an "AnimationTree" as a child to Player;
- Assign it the previusly created "AnimationPlayer";
- Make the tree root "AnimationNodeStateMachine";
- Make it active;
- Add a "BlendSpace2D" to the "AnimationTree" space, called Idle, which will contain all of the idle animations;
- Add the animations for their correspoding directions in the vector map (up and down are inverted);
- Change Blend to the little dots;
- Repeat for the Run animation;
- Set "Parameter", "Blend", to (0,0) for both animations;
- Connect both animations goint to and from;
- Make Iddle start on start;
- Make AnimationTree Inactive;
- Change script to play AnimationTree, like:

```py
extends KinematicBody2D

const ACCELARATION = 500
const MAX_SPEED = 80
const FRICTION = 500

var velocity = Vector2.ZERO

onready var animatioPlayer = $AnimationPlayer
onready var animationTree = $AnimationTree
onready var animationState = animationTree.get("parameters/playback")

func _ready():
	animationTree.active = true

func _physics_process(delta):
	var input_vector = Vector2.ZERO
	input_vector.x = Input.get_action_strength("ui_right") - Input.get_action_strength("ui_left")
	input_vector.y = Input.get_action_strength("ui_down") - Input.get_action_strength("ui_up")
	input_vector = input_vector.normalized()

	if(input_vector != Vector2.ZERO):
		animationTree.set("parameters/Idle/blend_position", input_vector)
		animationTree.set("parameters/Run/blend_position", input_vector)
		animationState.travel("Run")
		velocity = velocity.move_toward(input_vector * MAX_SPEED, ACCELARATION * delta)
	else:
		animationState.travel("Idle")
		velocity = velocity.move_toward(Vector2.ZERO, FRICTION * delta)

	velocity =  move_and_slide(velocity)

```

- To prioritize one movement over another, alter the AnimationTree (ex. add +1 -1 to the y value).

## Links

- <https://www.youtube.com/watch?v=Z9aR9IiiHT8&list=PL9FzW-m48fn2SlrW0KoLT4n5egNdX-W9a&index=6>
