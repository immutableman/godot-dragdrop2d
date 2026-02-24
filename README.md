# DragDrop

DragDrop2D is a simple GDScript framework to allow the player to drag/drop CharacterBody2Ds around. It supports:
 * Collision bodies for detecting mouse events.
 * Compatibility with 2D physics for bounds checking and constraining where the player can drag to.
 * Tracking drop regions using arbitrary Area2Ds.
 * Validating/filtering drop areas via collision layers or per physics frame.

## Usage
 * Create instances of Draggable in your scene.
 * Add at least one CollisionShape2D or CollisionPolygon2D with a layer (required for mouse detection).
 * Assign collision layer/mask for bounds checking.
 * Add other children to create the desired visuals.
 * Optionally assign a drop mask to detect drop regions.
 * Listen to the events (hovered, drag_started, drop_target_changed, drag_ended) to add logic and visual effects.

## Caveats
Because these bodies are characters, they must be the the root of the collision objects.
You could probably use RemoteTransform2D to sync the drag/drop with a sibling node, but I haven't tried that.
You can also control Draggables in script, but do so in `_physics_process` via `move_and_slide` or other physics-compatible ways.
Remember to call `super()` for overriden methods and use caution if attempting to do so while the player is dragging.

I have not tested this for mobile.
