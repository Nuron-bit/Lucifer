# LUCIFER V1.8 - API DOCUMENTATION [AUTOMATION]

## AutoSpam
AutoSpam Instance which accessible from bot struct.

#### Properties
* `enabled` : A boolean indicating whether the auto-spam feature is on or off.
* `interval` : The time interval between spam messages.
* `random_interval` : A boolean indicating whether bot should send messages with random interval when auto-spam is active.
* `show_emote` : A boolean indicating whether the bot should send player emotions during auto-spam.

#### Methods
* `setText(index: number, message: string)` : A function that sets the spam text by using index. Index Range: [0-3]

#### Example
```lua
spam = getBot().auto_spam -- Accessing AutoSpam from bot class.
spam.enabled = true -- Toggling auto-spam.
spam.interval = 5 -- Changing Interval.
spam.random_interval = true -- Enabling random interval feature.
spam.show_emote = true -- Enabling emote show feature
spam:setText(0, "This is a text message") -- 0: First Message Input.
```

## AutoGeiger
AutoGeiger Instance which accessible from bot struct.

#### Properties
* `enabled` : A boolean indicating whether the auto-geiger feature is on or off.
* `afk` : A boolean indicating whether if bot is forced to stand in main door.

#### Example
```lua
geiger = getBot().auto_geiger -- Accessing AutoGeiger from bot class.
geiger.enabled = true -- Toggling auto-geiger.
geiger.afk = true -- Enabling afk on main door feature.
```

## AutoMessage
AutoMessage Instance which accessible from bot struct.

#### Properties
* `enabled` : A boolean indicating whether the auto-message feature is on or off.
* `type` : A integer that represents type of the auto-message. [0 - Message, 1 - UID Message, 2 - List Message, 3 - Single Message]
* `ignore_admin` : A boolean indicating if admins are ignored while messaging.
* `auto_sb` : A boolean indicating if bot forced to go sb worlds.
* `loop_mode` : A boolean, you can check information on menu by checking help-marker(?).
* `uid_count` : A read-only integer that represents collected uid count by list message.
* `messaging` : A read-only boolean that represents if bot is messaging. [List Message]
* `uid_count` : A number indicating uid count.
* `message` : A string indicating message.

#### Methods
* `start()` : A function that will start messaging.
* `load()` : Loads uid-list from file.
* `save()` : Saves uid-list to a file.
* `clear()` : Deleted uid-list file + Clears uids that collected.

#### Example
```lua
msg = getBot().auto_message -- Accessing AutoMessage from bot class.
msg.enabled = true -- Toggling auto-message.
msg.message = "Hello, come my world!" -- Changing Message Text.
msg.type = 1 -- Changing Message Type.
msg:start() -- Starting auto message.
```

## AutoFish
AutoFish Instance which accessible from bot struct.

#### Properties
* `enabled` : A boolean indicating whether the auto-fish feature is on or off.
* `auto_rod` : A boolean indicating if auto-rod on or not.
* `auto_trash` : A boolean indicating if auto-trash on or not.
* `auto_drill` : A boolean indicating if auto-drill on or not.

#### Methods
* `setRod(id: number)` : A function that will set fishing rod.
* `setBait(id: number)` : A function that will set fishing bait.

#### Example
```lua
fish = getBot().auto_fish -- Accessing AutoFish from bot class.
fish.enabled = true -- Toggling auto-fish.
fish.auto_rod = true -- Enabling Auto-Rod feature.
fish.auto_drill = true -- Enabling Auto-Drill feature.
fish:setRod(3040) -- Changing Rod id.
fish:setBait(5526) -- Changing bait id.
```

## AutoFarm
AutoFarm Instance which accessible from bot struct.

#### Properties
* `enabled` : A boolean indicating whether the auto-farm feature is on or off.
* `speed` : Farming Speed.
* `id` : Farming Item id.
* `auto_break` : Is Auto-Break mode actived.
* `auto_place` : Is Auto-Place mode actived.

#### Methods
* `setActive(index: number, active: boolean)` : A function that will toggle active status by menu index.

#### Example
```lua
farm = getBot().auto_farm -- Accessing AutoFarm from bot class.
farm.enabled = true -- Toggling auto-farm.
farm.auto_place = true
farm.auto_break = true
farm.id = 4584
farm.speed = 100

for i = 0, 4 do
  farm:setActive(i, true) -- Enabling first 5 tile.
end
```

## AutoCrime
AutoFarm Instance which accessible from bot struct.

#### Properties
* `enabled` : A boolean indicating whether the auto-crime feature is on or off.

#### Methods
* `setActive(index: number, active: boolean)` : A function that will toggle active status by menu index.

#### Example
```lua
crime = getBot().auto_crime -- Accessing AutoCrime from bot class.
crime.enabled = true -- Toggling auto-crime.
crime:setActive(0, true) -- Enabling the first villain in the menu.
```

## AutoCook
AutoCook instance which accessible from bot struct.

#### Properties
* `is_cooking` : A boolean indicating whether the bot is cooking or not.
* `interval` : The interval between packets.

#### Methods
* `setActive(index: number, active: boolean)` : A function that changes state of selected tiles on menu.
* `setFood(index: number)` : A function that updates selected food by food index. Range: [0, 33]
* `setTemperature(level: number)` : A function that updates selected temperature. (0: low, 1: medium, 2: high)
* `start()` : A function that starts auto-cook.
* `stop()` : A function that stops auto-cook.

#### Example
```lua
cook = getBot().auto_cook -- Accessing AutoCook from bot struct.
for i = 0, 63 do
  cook:setActive(i, true) -- Activating all tiles
end

cook:setFood(0) -- Berry Crepes
cook:setTemperature(1) -- Low Temperature
cook:start()

while cook.is_cooking do
  print("Bot is currently cooking berry crepes.")
  sleep(1000)
end
```

## AutoCarnival
AutoCarnival instance which accessible from bot struct.

#### Properties
* `enabled` : A boolean indicating whether the auto-carnival feature is on or off.
* `auto_trash` : A boolean indicating whether the auto-trash feature is on or off.
* `auto_buy` : A boolean indicating whether the auto-buy feature is on or off.
* `selected_game` : The selected game index on the menu.

#### Example
```lua
carnival = getBot().auto_carnival -- Accessing AutoCarnival from bot struct.
carnival.enabled = true
carnival.auto_trash = true
carnival.auto_buy = true
carnival.selected_game = 1 -- Selecting the 2nd game on the menu.
```

## AutoParkour
AutoParkour instance which accessible from bot struct.

#### Properties
* `enabled` : A boolean indicating whether the auto-parkour feature is on or off.
* `type` : The type of parkour. (0: wolf, 1: fenrir, 2: clash)
* `limit` : The limit of the consuming ticket.

#### Methods
* `setWebhook(webhook_link: string)` : A function that updates the webhook link.
* `setTicket(world_with_id: string)` : A function that updates the ticket storage. (Must be uppercase.) (Format: NAME|ID)
* `setWebhook(world_with_id: string)` : A function that updates the reward storage. (Must be uppercase.) (Format: NAME|ID)

#### Example
```lua
parkour = getBot().auto_parkour -- Accessing AutoParkour from bot struct.
parkour.enabled = true
parkour.limit = 1
parkour.type = 1
parkour:setTicket("FENRIRSTORAGE|ID1")
parkour:setReward("FENRIROUTPUT|ID1")
```

## AutoTransfer
AutoTransfer instance which accessible from bot struct.

#### Properties
* `enabled` : A boolean indicating whether the auto-transfer feature is on or off.
* `drop_vertical` : A boolean indicating whether the drop-vertical feature is on or off.
* `auto_vend` : A boolean indicating whether the auto-vend feature is on or off.
* `restock_vend` : A boolean indicating whether the restock-vend feature is on or off.
* `set_price` : Item's price to set on vend.
* `buy_price` : Item's price to buy from vend.
* `per_item` : Item's buy method.
* `itemid` : The itemid of transfering item.

#### Example
```lua
transfer = getBot().auto_transfer -- Accessing AutoTransfer from bot struct.
transfer.enabled = true
transfer.drop_vertical = true
transfer.restock_vend = true
transfer.itemid = 4584 -- Pepper ID
```

## AutoHarvest
AutoHarvest instance which accessible from bot struct.

#### Properties
* `enabled` : A boolean indicating whether the auto-harvest feature is on or off.

#### Methods
* `add(string format)` : A function that lets you to add worlds.
* `remove(string name)` : A function that lets you to remove worlds.
* `setStorage(string name|id)` : A function that lets you to update storage world.

#### Example
```lua
harvest = getBot().auto_harvest -- Accessing AutoHarvest from bot struct.
harvest:setStorage("NURON|123")
harvest:add("NURON:ID:4585")
harvest.enabled = true
```

## AutoPlant
AutoPlant instance which accessible from bot struct.

#### Properties
* `enabled` : A boolean indicating whether the auto-plant feature is on or off.

#### Methods
* `add(string format)` : A function that lets you to add worlds.
* `remove(string name)` : A function that lets you to remove worlds.
* `setStorage(string name|id)` : A function that lets you to update storage world.

#### Example
```lua
plant = getBot().auto_plant -- Accessing AutoPlant from bot struct.
plant:setStorage("NURON|123")
plant:add("NURON:ID:4585")
plant.enabled = true
```
