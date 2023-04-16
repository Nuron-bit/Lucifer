# LUCIFER V1 - API DOCUMENTATION [FUNCTIONS]

* `Sleep(ms: number)` or `sleep(ms: number)` : Sleeps script for certain milliseconds.
* `GetInfo(name: string or id: number) -> ItemInfo` : Get Item Info by item's id or item's name.
* `GetInfos() -> table` : Get All Item Infos. (Returns table of ItemInfos)
* `AddBot(name: string, password:string)` :  Adds bot if it doesnt exist.
* `RemoveBot(name: string)` : Removes bot if it exists.
* `GetBot(name: string) -> Bot` : Returns the target bot with its name. If not found then it returns nil.
