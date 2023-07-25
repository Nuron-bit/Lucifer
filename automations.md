# LUCIFER V1.34 - API DOCUMENTATION [AUTOMATION]

## AutoSpam
AutoSpam Instance which accessible from bot struct.

#### Properties
* `enabled` : A boolean indicating whether the auto-spam feature is on or off.
* `random_interval` : A boolean indicating whether bot should send messages with random interval when auto-spam is active.
* `rest_mode` : A boolean indicating whether bot should rest after spamming a while.
* `show_emote` : A boolean indicating whether the bot should send player emotions during auto-spam.
* `interval` : The time interval between spam messages.
* `message` : A table of messages where you can set your spam-texts. ( message[1] to message[4] )

## AutoGeiger
AutoGeiger Instance which accessible from bot struct.

#### Properties
* `enabled` : A boolean indicating whether the auto-geiger feature is on or off.
* `afk` : A boolean indicating whether if bot is forced to stand in main door.

## AutoMessage
AutoMessage Instance which accessible from bot struct.

#### Properties
* `enabled` : A boolean indicating whether the auto-message feature is on or off.
* `type` : A integer that represents type of the auto-message. [0 - Message, 1 - List Message, 2 - Single Message]
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

## AutoCrime
AutoFarm Instance which accessible from bot struct.

#### Properties
* `enabled` : A boolean indicating whether the auto-crime feature is on or off.

#### Methods
* `setActive(index: number, active: boolean)` : A function that will toggle active status by menu index.
