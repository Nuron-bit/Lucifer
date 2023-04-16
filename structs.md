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

### NetObject
The object class represents an object in a world.

#### Properties
- `id` : read-only property that returns the `NetObject` ID.
- `x` : read-only property that returns the x-coordinate of the `NetObject`.
- `y` : read-only property that returns the y-coordinate of the `NetObject`.
- `count` : read-only property that returns the count of the `NetObject`.
- `flags` : read-only property that returns the flags of the `NetObject`.
- `oid` : read-only property that returns the `NetObject` oid.

### NPC
The NPC class that represents a npc in a world. Which is like ghost, pinata etc.

#### Properties
- `npcType` : read-only property that returns the type of the `NPC`.
- `npcID` : read-only property that returns the ID of the `NPC`.
- `x` : read-only property that returns the x-coordinate of the `NPC`.
- `y` : read-only property that returns the y-coordinate of the `NPC`.
- `destx` : read-only property that returns the x-coordinate of the destination of the `NPC`.
- `desty` : read-only property that returns the y-coordinate of the destination of the `NPC`.
- `npcVar` : read-only property that returns the `npcVar` of the `NPC`.
- `unk` : read-only property that returns the `unk` of the `NPC`.
