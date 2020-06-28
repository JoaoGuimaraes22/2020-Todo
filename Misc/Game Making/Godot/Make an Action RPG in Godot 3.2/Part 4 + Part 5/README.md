# Part 4 | Part 5

## Make a collidable bush

- Make the "StaticBody2D" with a collider;
- Put Bush scene multiple times in the world;
- Change World Type to YSort;
- Make the center of the objects correctly placed for YSort;

## AnimationPlayer

- Create an "AnimationPlayer" node as a child of Player;
- On the "Animation" Tab, click "Animation" and create a new animation;
- For example, create a "RunRight" animation;
- Change your snapping increments, in "Snap" to 0.1;
- Change Zoom to show 0.1 increments;
- Change "animation lenght" to 0.6 seconds;
- Go to "Sprite", "Animation", "Frames" and add the 1st frame to the 0th time in the animation and so on;
- Make the animation loop;
- Repeat for all animations;
- Get access to the AnimationPlayer in your script like so: `onready var animationPlayer = $AnimationPlayer`;

## Links

- <https://www.youtube.com/watch?v=UfKMgHbaGow&list=PL9FzW-m48fn2SlrW0KoLT4n5egNdX-W9a&index=4> ;
- <https://www.youtube.com/watch?v=wX145eoLFSM&list=PL9FzW-m48fn2SlrW0KoLT4n5egNdX-W9a&index=5> ;
