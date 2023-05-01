# LUCIFER V1 - API DOCUMENTATION [AUTOMATIONS]

## AutoSpam
AutoSpam Instance which accessible from bot struct.

#### Properties
* `enabled` : A boolean indicating whether the auto-spam feature is on or off.
* `show_bubble` : A boolean indicating whether a speech bubble should be displayed when auto-spam is active.
* `show_color` : A boolean indicating whether the message should be displayed with colored text.
* `show_emote` : A boolean indicating whether the bot should send player emotions during auto-spam.
* `detect_spam` : A boolean indicating if spam detector is enabled.
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
* `uids` : A table that contains collected uids.

#### Methods
* `Start()` : A function that will start messaging.
* `Load()` : Loads uid-list from file.
* `Save()` : Saves uid-list to a file.
* `Clear()` : Deleted uid-list file + Clears uids that collected.
