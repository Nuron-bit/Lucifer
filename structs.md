# LUCIFER V1 - API DOCUMENTATION [STRUCTURES]


## Console

A structure representing a console for displaying text.

#### Properties
* `content` : a string containing the current contents of the console.

#### Methods
* `append(text: string)` : appends the specified text to the console's content.

#### Example Usage
```lua
local console = GetBot():getConsole()
console:append("Hello, world!")

print(console.content)
```
## Inventory

The Inventory class represents a player's inventory in the game. It contains information about the items the player has, including the item ID, count, and whether the item is active.

#### Properties
* `items` : A table containing all the InventoryItem objects in the inventory.
* `itemcount` : The number of items in the inventory.
* `slotcount` : The number of slots available in the inventory.
* `version` : The version of the inventory.
#### Methods
* `getItem(itemID: number | string) -> InventoryItem` : Returns the InventoryItem with the specified item ID. It returns nil if not found.
* `getItems() -> table` : Returns a table containing all the InventoryItem objects in the inventory.
* `findItem(itemID: number | string) -> number` : Returns the InventoryItem with the specified item ID. It returns nil if not found.
* `canCollect(itemID: number) -> boolean` : Returns true if the player can collect the item with the specified item ID, false otherwise.
* `hasItems() -> boolean` : Returns true if the player has item.

#### Example Usage
```lua
for i, item in pairs(GetBot():getInventory().items) do
  print(GetInfo(item.id).name)
end
```

## InventoryItem

A structure representing an item in an inventory.

#### Properties
* `id` : an integer representing the ID of the item.
* `count` : an integer representing the number of this item in the inventory.
* `isActive` : a boolean indicating whether or not the item is currently weared.

#### Example Usage
```lua
local item = GetBot():getInventory():getItem(18)

print(item.id)
print(item.count)
print(item.isActive)
```

## Clothes

The `Clothes` class represents the clothing items that a player's avatar is wearing. It contains information about each item, including the item ID.

#### Properties
* `hat` : The ID of the hat the avatar is wearing.
* `shirt` : The ID of the shirt the avatar is wearing.
* `pants` : The ID of the pants the avatar is wearing.
* `shoes` : The ID of the shoes the avatar is wearing.
* `face` : The ID of the face item the avatar is wearing.
* `hand` : The ID of the hand item the avatar is wearing.
* `wings` : The ID of the wings item the avatar is wearing.
* `mask` : The ID of the mask the avatar is wearing.
* `neck` : The ID of the neck item the avatar is wearing.
* `ances` : The ID of the accessory item the avatar is wearing.
* `unk1` : An unknown value related to the avatar's clothing.
* `unk2` : An unknown value related to the avatar's clothing.

## Player
The Player class represents an in-game player and contains various properties to access information about the player.

#### Properties
* `name` : The display name of the player.
* `altName` : The alternative name of the player.
* `country` : The country of the player as a string.
* `netid` : The network ID of the player.
* `userid` : The user ID of the player.
* `bubble` : The text bubble of the player.
* `posx` : The X position of the player.
* `posy` : The Y position of the player.
* `vecx` : The X velocity of the player.
* `vecy` : The Y velocity of the player.
* `avatarFlags` : The avatar flags of the player.
* `isModerator` : A boolean indicating whether the player is a moderator.
* `isSuperModerator` : A boolean indicating whether the player is a super moderator.
* `isLocalPlayer` : A boolean indicating whether the player is the local player.
* `isFriendWithOwner` : A boolean indicating whether the player is a friend of the owner.
* `flag2019` : The 2019 flag of the player.
* `skincolor` : The skin color of the player.
* `roleskin` : The role skin of the player.
* `roleicon` : The role icon of the player.
* `clothes` : An instance of the Clothes class representing the clothes of the player. See Clothes class documentation for more details.

## NetObject
The object class represents an object in a world.

#### Properties
- `id` : The item ID of object.
- `x` : The x-coordinate of object.
- `y` : The y-coordinate of object.
- `count` : The item count of object.
- `flags` : The object flags.
- `oid` : The object id.

## NPC
The NPC class that represents a npc in a world. Which is like ghost, pinata etc.

#### Properties
- `npcType` : The type of the npc.
- `npcID` : The world index of the npc.
- `x` : Current x-coordinate of npc.
- `y` : Current y-coordinate of npc.
- `destx` : Destination x of npc. (Aka next position)
- `desty` : Destination y of npc. (Aka next position)
- `npcVar` : NPC variable.
- `unk` : Unk Value.

## Tile

The Tile class represents a single tile in the game world.

#### Properties
* `foreground` (`fg`) : The foreground tile ID.
* `background` (`bg`) : The background tile ID.
* `x` : The x-coordinate of the tile.
* `y` : The y-coordinate of the tile.
* `parent` : The parent object of the tile.
* `flags` : The flags set for the tile.

#### Methods
* `hasExtra() -> boolean` : Returns true if the tile has an extra data field, false otherwise.
* `getExtra() -> TileExtra*` : Returns a pointer to the extra data field for the tile. Returns nil if the tile has no extra data.

#### Example Usage
```lua
tile = GetBot():getWorld():getTile(23, 30)
if tile:hasExtra() then
  local extra = tile:getExtra()
  print("Label: ", extra.label)
end
```

## PathNode

The PathNode class represents a node in a pathfinding algorithm.

#### Properties
* `x` : The x-coordinate of the node.
* `y` : The y-coordinate of the node.

#### Example Usage
```lua
bot = GetBot()
nodes = bot:getPath(23, 10)

for i, node in pairs(nodes) do
  print(string.format("Node(%i, %i)", node.x, node.y))
end
```

## Growscan

The Growscan class represents the result of a "growscan" operation, which is used to scan the environment around a player and identify nearby tiles and objects.

#### Properties
* `tiles` : A table containing the IDs of the tiles that were found in the growscan, along with the number of times each tile was found.
* `objects` : A table containing the IDs of the objects that were found in the growscan, along with the number of times each object was found.

#### Example Usage
```lua
local gs = GetBot():getWorld().growscan
for id, count in pairs(gs.tiles) do
    print("Found " .. count .. " tiles with name " ..GetInfo(id).name)
end
```

## World
The World class represents a game world. It contains information about the size of the world, tiles, objects, players, and NPCs.

#### Properties
* `name` : The name of the world.
* `x` : The width of the world.
* `y` : The height of the world.
* `tile_count` : The total number of tiles in the world.
* `growscan` : A Growscan object representing the world's growscan.
* `tiles` : A table containing all the Tiles in the world.
* `objects` : A table containing all the NetObjects in the world.
* `players` : A table containing all the Players in the world.
* `npcs` : A table containing all the Npcs in the world.
* `public` : A boolean value indicating whether the world is public or not.
* `version` : The version of the world.
#### Methods
* `getTile(x: number, y: number) -> Tile` : Returns the Tile object at the specified x,y position.
* `getObject(x: number) -> NetObject` : Returns the NetObject object at the specified objectid(oid).
* `getPlayer(netID: number | string) -> Player` : Returns the NetAvatar object with the specified player netID or name. It returns nil if not found.
* `getNPC(npcID: number) -> NPC` : Returns the NetNPC object with the specified NPC ID. It returns nil if not found.
* `getLocal() -> Player` : Returns the NetAvatar object representing the local player.
* `getTileParent(tile: Tile) -> Tile` : Returns the Tile that the specified Tile is attached to.
* `hasAccess(x: number, y: number) -> boolean` : Returns true if the player has access to the specified x,y position, false otherwise.
* `isValidPosition(x: number, y: number) -> boolean` : Returns true if the specified x,y position is within the bounds of the world.
