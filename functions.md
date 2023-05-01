# LUCIFER V1 - API DOCUMENTATION [FUNCTIONS]

* `sleep(ms: number)` : Sleeps script for certain milliseconds.
* `getInfo(name: string or id: number) -> ItemInfo` : Get Item Info by item's id or item's name.
* `getInfos() -> table` : Get All Item Infos. (Returns table of ItemInfos)
* `addBot(name: string, password:string)` :  Adds bot if it doesnt exist.
* `addBot(name: string)` :  Adds a guest bot if it doesnt exist.
* `removeBot(name: string)` : Removes bot if it exists.
* `getBot(name: string) -> Bot` : Returns the target bot with its name. If not found then it returns nil.
* `getBot() -> Bot` : Returns the parent bot that executor executed in.
