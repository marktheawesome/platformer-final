# Pygame Platformer (2019)

## Animation

This is the animated branch. 

### Hero Animation

The hero has four additional attributes.

- `facing_right` is a boolean which is `True` when the hero is facing right and `False` otherwise. When the hero is first initialized, `facing_right` is set to `True`. Using the arrows to move right or left set this variable while playing.
- `steps` is a variable that tracks how many iterations of the game loop have elapsed while the hero is walking.
- `step_rate` is the number of frames that elapse before incrementing the `walk_index` to advance to the next image.
- `walk_index` is the index of the image in the walk list to show.

Two functions have been added to the hero.

`step` is called whenever the player is pressing either the right or left arrow key. This function increments the `steps` variable by one. Each time the `steps` variable reaches the `step_ rate`, it resets to zero and the `walk_index` is incremented. The `walk_index` resets to zero when equal to the length of the walk image list.

In  the heros `update` function calls a new function set_image. `set_image` looks at the current direction and state of the hero (hurt, jumping/falling, idle, or walking) to set the appropriate image.

### Enemy Animation

Enemies do not have a direction. Instead, they just cycle through all images in their `images` list. The `step_rate` is the number of frames that pass before the `walk_index` is incremented.
