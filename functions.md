# LUCIFER V1.74 - API DOCUMENTATION [FUNCTIONS]

* `sleep(ms: number)` : Sleeps script for certain milliseconds.
* `getInfo(name: string or id: number) -> ItemInfo` : Get Item Info by item's id or item's name.
* `getInfos() -> table` : Get All Item Infos. (Returns table of ItemInfos)
* `addBot(name: string, password: string)` :  Adds bot if it doesnt exist.
* `addBot(name: string)` :  Adds a guest bot if it doesnt exist.
* `addBot(name: string, password: string, mac: string, rid: string)` :  Adds bot if it doesnt exist.
* `addBot(name: string, mac: string, rid: string)` :  Adds ubi-bot if it doesnt exist.
* `addUbiBot(mail: string, password: string)` :  Adds ubi-bot if it doesnt exist.
* `addUbiBot(mail: string, password: string, username: string)` :  Adds and registers ubi-bot if it doesnt exist.
* `removeBot(name: string)` : Removes bot if it exists.
* `getBot(name: string) -> Bot` : Returns the target bot with its name. If not found then it returns nil.
* `getBot() -> Bot` : Returns the parent bot that executor executed in.
* `addEvent(Event: type, lua_function: function)` : Adds a event.
* `listenEvents(seconds: number)` :  Listens all added events with specific duration.
* `unlistenEvents()` :  Unlisten all events. (Mostly called on event functions to stop listening.)
* `removeEvent(Event: type)` : Removes the events by specific type.
* `removeEvents()` : Removes all signed events.
* `removeColor(text: string) -> string` : Removes all the colors from the text.
* `getProxyManager() -> ProxyManager` : Returns app proxy manager.
* `getWorldManager() -> WorldManager` : Returns app world manager.
* `addProxy(proxy_data: string)` : Adds proxy if it doesnt exist in menu.
* `removeProxy(ip: string, port: string)` : Removes proxy if it exists.
* `getUsername() -> string` : Returns the lucifer account username.
* `runThread(function, ...)` :  Runs a thread. You can use as many parameters as u need.

## Here list of shortcut functions that u can access.
* getTile
* getTiles
* getObject
* getObjects
* getPlayer
* getPlayers
* getNPC
* getNPCs
* getLocal
* hasAccess
* getWorld
* getInventory
