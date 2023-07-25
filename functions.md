# LUCIFER V1.34 - API DOCUMENTATION [FUNCTIONS]

* `sleep(ms: number)` : Sleeps script for certain milliseconds.
* `getInfo(name: string or id: number) -> ItemInfo` : Get Item Info by item's id or item's name.
* `getInfos() -> table` : Get All Item Infos. (Returns table of ItemInfos)
* `addBot(name: string, password: string)` :  Adds bot if it doesnt exist.
* `addBot(name: string)` :  Adds a guest bot if it doesnt exist.
* `addBot(name: string, password: string, mac: string, rid: string)` :  Adds bot if it doesnt exist.
* `addBot(name: string, mac: string, rid: string)` :  Adds bot if it doesnt exist.
* `removeBot(name: string)` : Removes bot if it exists.
* `getBot(name: string) -> Bot` : Returns the target bot with its name. If not found then it returns nil.
* `getBot() -> Bot` : Returns the parent bot that executor executed in.
* `addEvent(Event: type, lua_function: function)` : Adds a event.
* `removeEvent(Event: type)` : Removes the events by specific type.
* `removeEvents()` : Removes all signed events.
* `removeColor(text: string) -> string` : Removes all the colors from the text.
* `getProxyManager() -> ProxyManager` : Returns app proxy manager.
* `addProxy(proxy_data: string)` : Adds proxy if it doesnt exist in menu.
* `removeProxy(ip: string, port: string)` : Removes proxy if it exists.

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
