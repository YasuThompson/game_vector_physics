
## Task 3.2
Currently, in this chapter's game project, the spaceship does not collide with asteroids. Let's add collision to the spaceship. To do this, first create a `CircleComponent` for the `Ship` and specify its radius. Next, within `Ship::UpdateActor`, check for collisions with all asteroids (similar to how collision detection works with lasers). If the spaceship collides with an asteroid, reset it forcibly to the position at the center of the screen with zero rotation. As an additional feature, when colliding with an asteroid, make the spaceship disappear for 1 or 2 seconds. After that, the spaceship should reappear at the center of the screen.

### TODO
    [x] Add a collusion detection between the ship and asteroids.
    [x] Set reappearance of the ship after collision
    [ ] Wait some seconds until the reappearance of the ship. 

## Task 3.3
Modify the `MoveComponent` to utilize Newtonian physics. Specifically, introduce mass, total force, and velocity as member variables. In the `Update` function, change the code for forward motion to calculate acceleration from the total force, velocity from acceleration, and position from velocity. Next, a method to set force on the component is needed. One approach is to add an `AddForce` function that takes a single `Vector2` argument and adds it to the "total force" variable. It's advisable to clear the total force after calculating acceleration each frame. By doing this, applying force only requires calling `AddForce` once. For constant forces, call `AddForce` every frame for each force. Finally, make modifications to `InputComponent`, `Asteroid`, and `Ship` to support Newtonian physics and ensure this new `MoveComponent` functions correctly.
