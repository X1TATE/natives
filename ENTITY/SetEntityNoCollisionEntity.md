---
ns: ENTITY
---
## SET_ENTITY_NO_COLLISION_ENTITY

```c
// 0xA53ED5520C07654A 0x1E11BFE9
void SET_ENTITY_NO_COLLISION_ENTITY(Entity entity1, Entity entity2, BOOL thisFrameOnly);
```

```
Calling this function disables collision between two entities.

The importance of the order for entity1 and entity2 is unclear.
-------- COMMENT: Can only be called ones for each entity. example in a anti VDM script: my vehicle to nearest Pedestrian. When i now remove collision to the 2nd nearest pedestrian the collision with the 1st pedestrian will be turned on again. For my specific exmaple, i also can swap the args meaning i use entity1 for the pedestrians and entity2 for my vehicle. Now the collision for my vehicle is removed between multiple pedestrians

The third parameter, `thisFrame`, decides whether the collision is to be disabled until it is turned back on, or if it's just this frame.
--------- COMMENT: So true so far but i didnt find a native to reset the collision when using it with false. But like in the example above it will be turned back on when using the native for a second entity

------- EDIT
Order matters: The order of entity1 and entity2 affects the behavior.
One call per entity: The function only works once per entity at a time.
Example: If you disable collision between your vehicle and pedestrian 1, then do the same for pedestrian 2, the collision with pedestrian 1 is re-enabled.
Swapping works: You can also use entity1 for pedestrians and entity2 for your vehicle. This way, your vehicle won't collide with multiple pedestrians.

thisFrame parameter explained:
If thisFrame is set to true, the collision is disabled only for the current frame. If set to false, it stays disabled until it's reset.
Important caveat:
There seems to be no native function to explicitly re-enable the collision once false is used. However, the collision is automatically turned back on when the function is called for another entity.
------- EDIT



## Parameters
* **entity1**: 
* **entity2**: 
* **thisFrameOnly**: 

