# LUCIFER V1.74 - API DOCUMENTATION [FUNCTIONS]

* `sleep(ms: number)` : Sleeps script for certain milliseconds.
#### Example
```lua
bot = getBot()
while true do
  bot:say("Advanced Multibot Application by Nuron")
  sleep(math.random(4500, 6500))
end
```

* `getInfo(name: string or id: number) -> ItemInfo` : Get Item Info by item's id or item's name.
* `getInfos() -> table` : Get All Item Infos. (Returns table of ItemInfos)
#### Example
```lua
for i, item in pairs(getInfos()) do
  if getInfo(4584).name == item.name then
    print("Found Pepper Tree on database.")
  end
end
```

* `addBot(name: string, password: string) -> Bot` :  Adds bot if it doesnt exist.
* `addBot(name: string) -> Bot` :  Adds a guest bot if it doesnt exist.
* `addBot(name: string, password: string, mac: string, rid: string) -> Bot` :  Adds bot if it doesnt exist.
* `addBot(name: string, mac: string, rid: string) -> Bot` :  Adds ubi-bot if it doesnt exist.
* `addUbiBot(mail: string, password: string) -> Bot` :  Adds ubi-bot if it doesnt exist.
* `addUbiBot(mail: string, password: string, username: string) -> Bot` :  Adds and registers ubi-bot if it doesnt exist.
#### Example
```lua
addBot("nuron") -- Adding guest account.
addBot("nuron", "02:00:00:00:00:00", "rid_here") -- Adding guest account with device information.
addBot("nuron", "nuron123") -- Adding normal account.
addBot("nuron", "nuron123", "02:00:00:00:00:00", "RID") -- Adding normal account with device information.
addUbiBot("nuron@gmail.com", "gmail_password") -- Adding Ubi-Connect Account.
addUbiBot("nuron@gmail.com", "gmail_password", "NewAccount123") -- Creating New Ubi-Connect Account.

addBot("nuron"):connect() -- Adding account then using method. (You can use functions because addBot returns the bot instance.)
```

* `removeBot()` : Removes bot if it exists.
* `removeBot(name: string)` : Removes bot if it exists.
#### Example
```lua
removeBot() -- Removing the script parent bot.
removeBot("nuron") -- Removing bot with custom name.
```

* `getBot() -> Bot` : Returns the parent bot that executor executed in.
* `getBot(name: string) -> Bot` : Returns the target bot with its name. If not found then it returns nil.
* #### Example
```lua
getBot():say("Hello, my mate!") -- Getting script parent Bot then texting.
getBot("nuron"):disconnect() -- Getting specific bot with nuron growid and disconnecting it.
```

* `addEvent(Event: type, lua_function: function)` : Adds a event.
* `listenEvents(seconds: number)` :  Listens all added events with specific duration.
* `unlistenEvents()` :  Unlisten all events. (Mostly called on event functions to stop listening.)
* `removeEvent(Event: type)` : Removes the events by specific type.
* `removeEvents()` : Removes all signed events.
* #### Example
```lua
function OnVariantList(varlist, netid) -- Using the variantlist event parameters. You can view them from enums.md
  if variant:get(0):getString() == "OnConsoleMessage" then
    message = variant:get(1):getString()
    print(string.format("[Console]: %s", message))
    if message:match("!stop") then
      print("Stop has been requested by someone. Unlistening...")
      unlistenEvents() -- Now we don't have to wait 10000 seconds anymore. Since we have been unlistened.
    end
  end
end

addEvent(Event.variantlist, OnVariantList) -- Adding the variantlist event to the Event Manager.

listenEvents(10000) -- Listening incoming console messages for 10000 seconds.

removeEvent(Event.variantlist) -- Removing all attached variantlist events for cleanup.
removeEvents() -- You can also remove all events with this function.
```

* `removeColor(text: string) -> string` : Removes all the colors from the text.
#### Example
```lua
 colored_nickname = "`4Nuron"
 uncolored_nickname = removeColor(colored_nickname)
 print(string.format("%s -> %s", colored_nickname, uncolored_nickname))
```

* `getProxyManager() -> ProxyManager` : Returns app proxy manager.
#### Example
```lua
 proxy_manager = getProxyManager()
 proxy_manager:addProxy("127.0.0.1:80") -- Adding new proxy.
-- You can view struct.md for additional functions. This not all!
```

* `getWorldManager() -> WorldManager` : Returns app world manager.
#### Example
```lua
 world_manager = getWorldManager()
 world_manager:addFarm("PepperFarm:DoorID", 4584") -- Adding new pepper farm.
-- You can view struct.md for additional functions. This not all!
```

* `addProxy(proxy_data: string)` : Adds proxy if it doesnt exist in menu.
* `removeProxy(ip: string, port: string)` : Removes proxy if it exists.
#### Example
```lua
 addProxy("127.0.0.1:80") -- Adding Proxy
 removeProxy("127.0.0.1", 80) -- Removing Proxy
```

* `getUsername() -> string` : Returns the lucifer account username.
#### Example
```lua
 username = getUsername()
 print(string.format("Hello %s, thanks for using lucifer <3", username))
```

* `runThread(function, ...)` :  Runs a thread. You can use as many parameters as u need.
#### Example
```lua
function spam(text, interval) -- We have decleared 2 parameters.
  print(string.format("Starting Auto-Spam with text %s and interval %ims.", text, interval))
  while true do
    getBot():say(text)
    sleep(interval)
  end
end

runThread(spam, "Thanks for using Lunatic Lucifer", 8000) -- We need to add 2 additional parameters rather than function because function takes 2 parameters.
runThread(spam, "That is a very secret message that would occur anytime, math.random(1, 1000000))

while true do -- Main Script.
  sleep(...)
end
```

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
