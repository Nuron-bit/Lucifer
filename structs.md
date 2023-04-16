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
