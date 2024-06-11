# LUCIFER V2.32 - API DOCUMENTATION [ROTATION]

## Rotation
Rotation instance that stored on bot struct.

#### Properties
- `enabled` : Rotation active. (Boolean)
- `status` : Rotation status. (number)
- `custom_position` : Bot's Custom Break Tiles that managed by bitwise operations. (number)
- `break_x` : Bot's Custom Break Position X. (number)
- `break_y` : Bot's Custom Break Position Y. (number)
- `seed_drop_amount` : Bot's Seed Drop Amount in Storage. (number)
- `auto_rest` : Rotation's Auto Rest Feature. (Boolean)
- `auto_exchange` : Rotation's Auto Exchange Feature. (Boolean)
- `auto_jammer` : Rotation's Auto Jammer Feature. (Boolean)
- `auto_leave_on_player` : Rotation's Auto Leave on Player Feature. (Boolean)
- `dynamic_delay` : Rotation's Dynamic Delay Feature. (Boolean)
- `ignore_plant` : Rotation's Ignore Plant Feature. (Boolean)
- `harvest_roots` : Rotation's Harvest Roots Feature. (Boolean)
- `clear_objects` : Rotation's Clear Objects Feature. (Boolean)
- `one_by_one` : Rotation's One by One Feature. (Boolean)
- `pnb_in_home` : Rotation's PNB in Home Feature. (Boolean)
- `harvest_until_level` : Rotation's Harvest until Level Feature. (Boolean)
- `visit_random_worlds` : Rotation's Clear History Feature. (Boolean)
  - `pnb_world` : Customizable PNB World. (String)
- `harvest_interval` : Bot's Harvest Interval. (float)
- `plant_interval` : Bot's Plant Interval. (float)
- `break_interval` : Bot's Break/Place Interval. (float)
- `warp_interval` : Bot's Warp Interval. (float)

#### Example
```lua
local rotation = getBot().rotation
rotation.enabled = true
rotation.visit_random_worlds = true
rotation.dynamic_delay = true
rotation.harvest_interval = 0.18
rotation.break_interval = 0.20
rotation.plant_interval = 0.17
rotation.warp_interval = 12
```

## World Manager

App's global world manager.

#### Methods
- `addFarm(string name_and_id, number item_id)` : Adds new rotation farm to the list.
- `removeFarm(string name)` : Removes Farm World from list if it exists.
- `addStorage(string name_and_id, StorageType type, number seed_id)` : Adds new storage world to the list. (If u want to add pack storage, keep seed as 0)
- `removeStorage(string name, StorageType type)` : Removes Storage World from list if it exists.
- `selectAll()` : Selects all farm and storage worlds.
- `unselectAll()` : Unselects all farm and storage worlds.
- `selectFarm(string name)` : Selects the farm world on the menu.
- `unselectFarm(string name)` : Unselects the farm world on the menu.
- `selectStorage(string name, StorageType type)` : Selects the storage world on the menu.
- `unselectStorage(string name, StorageType type)` : Unselects the storage world on the menu.

#### Example
```lua
world_manager = getWorldManager()

world_manager:addFarm("expepper:id", 4584)
world_manager:removeFarm("expepper")

world_manager:addStorage("seedstorage:123", StorageType.seed, 4584)
world_manager:addStorage("packstorage:123", StorageType.pack, 0)

world_manager:removeStorage("packstorage", StorageType.pack)
world_manager:removeStorage("seedstorage", StorageType.seed)

world_manager:unselectAll()
world_manager:selectAll()
world_manager:selectFarm("name")
world_manager:unselectFarm("name")
world_manager:selectStorage("name", StorageType)
world_manager:unselectStorage("name", StorageType)
```
