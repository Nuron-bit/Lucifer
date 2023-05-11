# LUCIFER V1 - API DOCUMENTATION [STRUCTURES]

## Bot
A structure representing a bot.

#### Properties
* `status` : The status of the player.
* `captcha_status` : The status of the captcha.
* `gem_count` : The number of gems the bot has.
* `pearl_count` : The number of pearls the bot has.
* `voucher_count` : The number of vouchers the bot has.
* `level` : The level of the bot.
* `is_account_secured` : A read-only property that returns whether the bot account is secured.
* `auto_reconnect` : A boolean property that enables/disables auto-reconnect.
* `auto_accept` : A boolean property that enables/disables auto-accept.
* `auto_leave_on_admin` : A boolean property that enables/disables auto-leave when an admin is in the world.
* `auto_leave_on_mod` : A boolean property that enables/disables auto-leave when a mod is in the world.
* `auto_ban` : A boolean property that enables/disables auto-ban.
* `auto_tutorial` : A boolean property that enables/disables auto-tutorial.
* `auto_collect` : A boolean property that enables/disables auto-collect.
* `ignore_gems` : A boolean property that enables/disables ignoring gems.
* `ignore_essences` : A boolean property that enables/disables ignoring essences.
* `object_collect_delay` : A number property that sets the delay for collecting spawned objects.
* `collect_interval` : A number property that sets the interval for collecting.
* `collect_range` : A number property that sets the range for collecting.
* `auto_geiger` : AutoGeiger Instance.
* `auto_message` : AutoMessage Instance.
* `auto_spam` : AutoSpam Instance.

#### Methods
* `getWorld() -> World` : Returns bot world.
* `getInventory() -> Inventory` : Returns bot inventory.
* `getConsole() -> Console` : Returns bot console.
* `getLog() -> Log` : Returns bot log.
* `getLogin() -> Login` : Returns bot login.
* `connect() -> boolean` : Makes bot connect to the game server.
* `disconnect()` : Makes bot disconnect from the game server.
* `sendRaw(packet: GameUpdatePacket)` : Sends Raw packet if its valid & connected & no captcha.
* `sendPacket(type: number, packet: string)` : Sends packet if its valid & connected & no capctcha.
* `warp(name: string) | warp(name: string, id: string)` : Warps to specific world with id (optional).
* `say(text: string)` : Sends a message to world, if bot is in a world.
* `use(item_id: number)` : Uses the item if its consumable & in inventory.
* `wear(item_id: number)` : Wears an item if bot isn't wearing.
* `unwear(item_id: number)` : Unwears an item if bot is wearing.
* `drop(item_id: number, item_count: number)` : Drops the item if item's id & count is valid.
* `trash(item_id: number, item_count: number)` : Trashes the item if item's id & count is valid.
* `buy(store_id: string)` : Buys item from store with its store_id.
* `leaveWorld()` : Leaves from world if bot is in a world.
* `setBubble(bubble: BubbleType)` : Sets Bot bubble status, you can check enum for more information.
* `place(x: number, y: number, item: number)` : Places block if its valid.
* `hit(x: number, y: number)` : Hit to tile if range safe & valid position.
* `wrench(x: number, y: number)` : Wrench to tile if range safe & valid position.
* `wrenchPlayer(netID: number)` : Wrenchs to a player if player exists.
* `moveTo(difference_x: number, difference_y: number)` : Moves to tile with x and y difference. Ex: moveTo(1, 0) makes u move right.
* `moveTile(tilex: number, tiley: number)` : Moves to the tile if range safe & valid position.
* `moveLeft()` : Moves bot to left if its valid position
* `moveRight()` : Moves bot to right if its valid position
* `moveUp()` : Moves bot to up if its valid position
* `moveDown()` : Moves bot to down if its valid position
* `enter()` : Enters the door, if there is door.
* `respawn()` : Respawns the bot.
* `getPath(x: number, y: number) -> table` : Returns table of PathNodes if path found. Returns empty table if not found.
* `findPath(x: number, y: number)` : Finds tile path and moves to destination.
* `findWorldPath(x: number, y: number)` : Finds world path and moves to destination.
* `collectObject(oid: number, range: number)` : Collects the object if bot is in range.
* `collect(range: number)` : Collect all objects by range.
* `isInWorld() -> bool` : Returns true if bot is in a world.
* `getPing() -> number` : Returns the ping value of the bot.
* `getSignal() -> Signal` : Returns the latest geiger signal.

## Console or Log

A structure representing a console for displaying text.

#### Properties
* `content` : a string containing the current contents of the console/log.

#### Methods
* `append(text: string)` : appends the specified text to the console/log's content.

## Login
A structure that holds login details like growid, password, mac, klv or so.

#### Properties
Soon.

## Signal
A container that have details about latest geiger area.

#### Properties
* `x` : Tile position x of signal.
* `y` : Tile position y of signal.
* `type` : GeigerArea type.

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
* `findItem(itemID: number | string) or getItemCount(itemID: number | string) -> number` : Returns the InventoryItem count with the specified item ID. It returns 0 if not found.
* `canCollect(itemID: number) -> boolean` : Returns true if the player can collect the item with the specified item ID, false otherwise.
* `hasItems() -> boolean` : Returns true if the player has item.

## InventoryItem

A structure representing an item in an inventory.

#### Properties
* `id` : an integer representing the ID of the item.
* `count` : an integer representing the number of this item in the inventory.
* `isActive` : a boolean indicating whether or not the item is currently weared.

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
- `type` : The type of the npc.
- `id` : The world index of the npc.
- `x` : Current x-coordinate of npc.
- `y` : Current y-coordinate of npc.
- `destx` : Destination x of npc. (Aka next position)
- `desty` : Destination y of npc. (Aka next position)
- `var` : NPC variable.
- `unk` : Unk Value.

## TileExtra

#### Properties
Soon

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
* `canHarvest() -> boolean` : Returns true if tree is ready.

## PathNode

The PathNode class represents a node in a pathfinding algorithm.

#### Properties
* `x` : The x-coordinate of the node.
* `y` : The y-coordinate of the node.

## Growscan

The Growscan class represents the result of a "growscan" operation, which is used to scan the environment around a player and identify nearby tiles and objects.

#### Properties
* `tiles` : A table containing the IDs of the tiles that were found in the growscan, along with the number of times each tile was found.
* `objects` : A table containing the IDs of the objects that were found in the growscan, along with the number of times each object was found.

#### Methods
* `getTiles() -> map<id, count>` : Returns tiles.
* `getObjects() -> map<id, count>` : Returns objects.

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
* `getTiles() -> table<Tile>` : Returns tiles. 
* `getObjects() -> table<NetObject>` : Returns objects. 
* `getPlayers() -> table<Player>` : Returns players. 
* `getNPCs() -> table<NPC>` : Returns npcs. 
* `getLocal() -> Player` : Returns the NetAvatar object representing the local player.
* `getTileParent(tile: Tile) -> Tile` : Returns the Tile that the specified Tile is attached to.
* `hasAccess(x: number, y: number) -> boolean` : Returns true if the player has access to the specified x,y position, false otherwise.
* `isValidPosition(x: number, y: number) -> boolean` : Returns true if the specified x,y position is within the bounds of the world.

## ItemInfo
The ItemInfo class represents information about an item in the game. It contains information about the item's id, category, kind, collision, rarity, name, texture, and more.

#### Properties
* `id` : The unique identifier for the item.
* `editable_type` : The type of the item for the purpose of the item.
* `item_category` : The category of the item.
* `action_type` : The type of the item's action.
* `hit_sound_type` : The type of the item's hit sound.
* `item_kind` : The kind of the item.
* `collision_type` : The type of the item's collision.
* `clothing_type` : The type of clothing for the item, if its clothing.
* `rarity` : The rarity of the item.
* `seed_color` : The color of the seed base.
* `seed_overlay_color` : The color of the seed overlay.
* `grow_time` : The grow time of the item, if it is a plant.
* `drop_chance` : The drop chance of the item.
* `name` : The name of the item.
* `texture` : The texture file for the item.
* `texture_hash` : The hash of the texture file for the item.
* `texture_x` : The x-coordinate of the texture for the item. (Sprite Position)
* `texture_y` : The y-coordinate of the texture for the item. (Sprite Position)
* `null_Item` : True if item name contains null.

## GameUpdatePacket

Represents a packet that updates the state of an object in the game.

- `type` : The type of packet.
- `object_type` : The type of object change type.
- `count1` : A count variable used in certain types of packets.
- `count2` : A count variable used in certain types of packets.
- `netid` : The network ID of the object/player... being updated.
- `item` : The item being updated.
- `flags` : A set of flags used in certain types of packets.
- `float_var` : A floating point variable used in certain types of update packets.
- `int_data` : An integer variable used in certain types of update packets.
- `vec_x` | `pos_x` : The x position of a component being updated.
- `vec_y` | `pos_y` : The y position of a component being updated.
- `vec2_x` | `pos2_x` : The velocity x of a component being updated.
- `vec2_y` | `pos2_y` : The velocity y of a component being updated.
- `particle_rotation` : The rotation of a particle being updated.
- `int_x` : An integer variable used in certain types of update packets. (Ex Tile Position)
- `int_y` : An integer variable used in certain types of update packets. (Ex Tile Position)

## Vector2
A Vector2 is a container that holds x and y positions.

#### Properties
- `x` : x position.
- `y` : y position. 

## Vector3
A Vector3 is a container that holds x, y and z positions.

#### Properties
- `x` : x position.
- `y` : y position. 
- `z` : z position. 

## variant
Represents a variant type that can store different types of data.

#### Methods
- `getType() -> VariantType` : Returns the type of the stored data.
- `print()` : Dumps the stored data to a string.
- `set(string)` : Sets the stored data to a string.
- `set(int)` : Sets the stored data to an integer.
- `set(float)` : Sets the stored data to a floating-point number.
- `set(float, float)` : Sets the stored data to a 2D vector.
- `set(float, float, float)` : Sets the stored data to a 3D vector.
- `set(vector2)` : Sets the stored data to a 2D vector.
- `set(vector3)` : Sets the stored data to a 3D vector.
- `reset()` : Resets the stored data to an empty state.
- `getString() -> string` : Returns the stored data as a string.
- `getInt() -> number` : Returns the stored data as an integer.
- `getFloat() -> float` : Returns the stored data as a floating-point number.
- `getVector2() -> Vector2` : Returns the stored data as a 2D vector.
- `getVector3() -> Vector3` : Returns the stored data as a 3D vector.

## variantlist
Represents a list of variant objects.

#### Methods
- `get(index) -> variant` : Returns the variant object at the specified index.
- `print() -> string` : Dumps the entire list to a string.

## RTParam

### Properties
- `parameters` : The list of parameters (table)
- `key` : The key (string)
- `has_seperator` : Whether or not the parameter has a separator at the end (boolean)

## RTVAR
RTVAR represents a runtime variable that can have multiple parameters.

#### Methods
- `RTVAR.new()` : Constructs a new RTVAR object with an empty parameter list.
- `RTVAR.new(string)` : Constructs a new RTVAR object with the given string as its parameter list.
- `params() -> string` : Returns the parameter list as a string.
- `append(key: string, value: string, separator: bool)` : Appends a new parameter with the given key and value to the parameter list. If separator is true, a separator character is added at the end of the parameter list.
- `append(key: string, value: number, separator: bool)` : Appends a new parameter with the given key and numeric value to the parameter list. If separator is true, a separator character is added at the end of the parameter list.
- `contains(key: string) -> bool` : Returns true if the parameter list contains a parameter with the given key, false otherwise.
- `dump() -> string` : Dumps the RTVAR to a string.
- `erase(key: string)` : Removes the parameter with the given key from the parameter list.
- `find(key: string) -> number` : Returns the RTPARAM with the given key, nil if its not found.
- `get(key: string) -> string` : Returns the value of the parameter with the given key as a string.
- `getInt(key: string) -> number` : Returns the value of the parameter with the given key as an integer.
- `getLong(key: string) -> number` : Returns the value of the parameter with the given key as a long integer.
- `getParam(key: string) -> rtparam` : Returns the rtparam with given key.
- `getParams(key: string) -> table` : Returns the table of rtparams with given key.
- `modify(key: string, parameters: table, hasSeperator: boolean)` : Modifies rtparam with the given key.
- `parse(str: string)` : Parses a string and updates the parameter list accordingly.
- `size() -> number` : Returns the number of rtparams in the RTVAR.

## Embed
The Embed class represents an embed object that can be used to display rich content in a Discord message. It has the following properties and methods:

#### Properties
- `use` : Boolean value indicating whether the embed should be used or not.
- `color` : Integer value representing the color of the embed.
- `title` : String value representing the title of the embed.
- `type` : String value representing the type of the embed.
- `description` : String value representing the description of the embed.
- `url` : String value representing the URL associated with the embed.
- `thumbnail` : String value representing the URL of the thumbnail image
- `image` : The image url of the embed.
- `footer` : Object representing the footer of the embed. It has the following properties:
  - `text` : String value representing the text of the footer.
  - `icon_url` : String value representing the URL of the icon associated with the footer.
- `author` : Object representing the author of the embed. It has the following properties:
  - `name` : String value representing the name of the author.
  - `url` : String value representing the URL associated with the author.
  - `icon_url` : String value representing the URL of the icon associated with the author.
## Methods
- `addField(name: string, value: string, inline: boolean)` : Adds a new field to the embed. It takes three arguments:
  - `name` : String value representing the name of the field.
  - `value` : String value representing the value of the field.
  - `is_inline` : Boolean value indicating whether the field should be displayed inline or not.

## Webhook class
A discord webhook class where you can send webhooks.

#### Properties
- `url` : string : string variable representing the webhook url.
- `content` : string : string variable representing the content of the message to be sent.
- `username` : string : string variable representing the username of the webhook.
- `avatar_url` : string : string variable representing the avatar url of the webhook.
- `embed1` : variable representing the first embed of the webhook message.
- `embed2` : variable representing the second embed of the webhook message.

#### Methods
- `makeContent() -> string` : Function that returns the combined content of the message and its embeds. (Json format)
- `send()` : Function that sends the webhook message.
- `edit(message_id: number)`  : Function that edits the webhook message with message_id.

## HttpResult
HttpResult is a container where it stores http response datas.

#### Properties
- `body` : The body of the HTTP response as a string.
- `error` : An integer error code in case of a network error. If there was no error, this property returns 0.
- `status` : The HTTP status code as an integer.

#### Methods
- `getError()` : A function that returns a string error message in case of a network error.

## HttpClient
HttpClient represents a class that uses curl library to send http/s requests.

#### Properties
- `content` : A string that represents the HTTP request body.
- `method` : A string that represents the HTTP method.
- `headers` : A Lua table that represents the HTTP request headers. (Ex: headers["User-Agent"] = "Lucifer")
- `url` : A string that represents the target URL.

#### Methods
- `setMethod(method: Method)` : A function that sets the HTTP method.
- `request() -> httpresult` : A function that sends the HTTP request and returns an HttpResult object.
