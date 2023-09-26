## Rotation
Rotation instance that stored on bot struct.

#### Properties
- `enabled` : Rotation active. (Boolean)
- `anti_fire` : Rotation's Anti Fire feature. (Boolean)
- `anti_toxic` : Rotation's Anti Toxic feature. (Boolean)
- `take_fossil` : Rotation's Take Fossil feature. (Boolean)
- `gem_limit` : Rotation Gem Limit. (number)
- `world_limit` : Rotation Farm Limit. (number)
- `id` : Rotation Anti Fire feature. (number)
- `pack` : Rotation Selected Pack Index. (number)
- `seed_storage` : Rotation Seed Storage. (string) (read-only)
- `pack_storage` : Rotation Pack Storage. (string) (read-only)
- `farms` : Rotation Farm List. (table-string) (read-only)
- `index` : Rotation Current World Index. (number) (read-only)

#### Example
```lua
getBot().rotation.enabled = true/false
getBot().rotation.anti_fire = true/false -- Not Implemented.
getBot().rotation.anti_toxic = true/false -- Not Implemented.
getBot().rotation.take_fossil = true/false -- Not Implemented.
getBot().rotation.gem_limit = 2000
getBot().rotation.world_limit = 9
getBot().rotation.id = 4584
getBot().rotation.pack = 0 -- Pack Index on menu
getBot().rotation.seed_storage -- Read only Seed Storage to view.
getBot().rotation.pack_storage -- Read only Pack Storage to view.
getBot().rotation.farms -- Read only table of rotation worlds to view.
getBot().rotation.index -- Read only index of the current rotation world.
```

## World Manager

App's global world manager.

#### Methods
- `addFarm(string name_and_id, number item_id)` : Adds new rotation farm to the list.
- `removeFarm(string name)` : Removes Farm World from list if it exists.
- `addStorage(string name_and_id, StorageType type, number seed_id)` : Adds new storage world to the list. (If u want to add pack storage, keep seed as 0)
- `removeStorage(string name, StorageType type)` : Removes Storage World from list if it exists.
- `assign()` : Distributes everything to the bots.
- `assignFarm()` : Distributes farm worlds to the bots.
- `assignStorage()` : Distributes storage worlds to the bots.
- `apply(Bot bot)` : Applies selected farms and storages to the bot.
- `applyFarm(Bot bot)` : Applies selected farms to the bot.
- `applyStorage(Bot bot)` : Applies selected storages to the bot.
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

world_manager:assign() -- Spreads all worlds automatically.
world_manager:assignFarm() -- Spreads farm worlds automatically.
world_manager:assignStorage() -- Spreads storage worlds automatically.

world_manager:apply(getBot()); -- Will assign the selected worlds to specific bot.
world_manager:applyFarm(getBot()) -- Will assign the selected farm worlds to specific bot.
world_manager:applyStorage(getBot()) -- Will assign the selected storages to specific bot.

world_manager:unselectAll()
world_manager:selectAll()
world_manager:selectFarm("name")
world_manager:unselectFarm("name")
world_manager:selectStorage("name", StorageType)
world_manager:unselectStorage("name", StorageType)
```
