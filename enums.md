# LUCIFER V1.8 - API DOCUMENTATION [ENUMS]

## BotStatus

An enumeration representing the different statuses a bot can have.

#### Values
* `offline` : the bot is currently offline.
* `online` : the bot is currently online.
* `wrong_password` : the bot's account password is incorrect.
* `account_banned` : the bot is banned.
* `location_banned` : the bot's device location is banned.
* `version_update` : the game version is outdated and needs to be updated.
* `advanced_account_protection` : the bot's account has advanced protection that prevents it from being logged in.
* `server_overload` : the server is currently overloaded and cannot handle any more connections.
* `too_many_login` : there have been too many login attempts to the game server.
* `maintenance` : the server is currently undergoing maintenance and is unavailable.
* `server_busy` : the server is currently busy and cannot handle any more connections.
* `guest_limit` : the maximum number of guests for the ip has been reached.
* `guest_disabled` : guest accounts are currently disabled.
* `account_restricted` : the account is restricted from growtopia.
* `network_restricted` : maximum supported number of bots in network is reached.
* `http_block` : the server is blocking HTTP connections from bot ip.
* `bad_name_length` : the bot name is too short or too long.
* `invalid_account` : the bot is invalid.
* `error_connecting` : there was an error connecting to the server.
* `logon_fail` : the bot failed to log in.
* `captcha_requested` : captcha requested by gt.
* `mod_entered` : a mod entered bot's world.
* `player_entered` : a player entered bot's world.
* `high_load` : the bot's subserver is currently on high load.
* `high_ping` : the bot's ping is currently is higher than maximum-ping.
* `changing_subserver` : the bot's subserver is currently switching.
* `stopped` : the bot's actions have been stopped by 'Auto-Stop'.
* `getting_server_data` : bot is currently getting server data from gt-1 or gt-2.
* `bypassing_server_data` : bot is currently bypassing server data with another proxy.

#### Example
```lua
-- Get the current status of the bot
local status = getBot().status

-- Check if the bot is online
if status == BotStatus.online then
    print("Bot is online!")
end
```

## CaptchaStatus

An enumeration representing the different status codes for a captcha.

#### Values
* `no_captcha` : there is no captcha to solve.
* `not_found` : the captcha could not be found.
* `solved` : the captcha was successfully solved.
* `solving` : the captcha is currently being solved.
* `wrong` : the answer to the captcha was incorrect.
* `failed` : the captcha could not be solved.
* `no_access` : the captcha could not be solved due to http forbidden or bad gateway error.
* `invalid_key` : the captcha could not be solved due to wrong captcha api key.
* `invalid_token` : the captcha could not be solved due to corrupted website.

#### Example
```lua
-- Check if a captcha has been solved
local captchaStatus = getBot().captcha_status

if captchaStatus == CaptchaStatus.solved then
    print("Captcha has been solved!")
end
```

## Method

An enumeration representing the different HTTP methods.

#### Values
* `get` : HTTP GET method.
* `post` : HTTP POST method.
* `put` : HTTP PUT method.
* `patch` : HTTP PATCH method.
* `delete` : HTTP DELETE method.
* `head` : HTTP HEAD method.

#### Example
```lua
-- Make an HTTP request using the GET method

local client = HttpClient.new()

client.method = Method.get
client.url = "https://www.google.com"

response = client:request()
print(response.body)
```

## Event

An enumeration representing the different types of events.

#### Values
* `variantlist` : Variant List event. -- function(variantlist, netid)
* `game_message` : Game Message event. -- function(message)
* `generic_text` : Generic Text event. -- function(message)
* `update_packet` : Game Update Packet event. -- function(packet)
* `track_packet` : Track Packet event. -- function(message)

#### Example
```lua
addEvent(Event.variantlist, function(variant, netid)
  getBot():getLog():append(
     string.format(
        "Type: %s\n",
        variant:get(0):getString()
     )
  )
end)
```

## VariantType

An enumeration representing the variant type of a variant.

#### Values
* `float` : type float.
* `int32` : type int32.
* `uint32` : type uint32.
* `string` : type string.
* `unused` : type unused.
* `vector2` : type vector2.
* `vector3` : type vector3.
* `component` : type component.
* `entity` : type entity.

#### Example
```lua
vlist = variantlist.new()

vlist:get(4):set("nuron")
if vlist:get(4):getType() == VariantType.string then
    print("Successfully modified variant[4] value.")
end
```

## GeigerArea

An enumeration representing the type of geiger area.

#### Values
* `null` : No Area
* `red` : Red Area.
* `yellow` : Yellow Area.
* `green` : Green Area.
* `rapid` : Rapid Green Area.
* `prize` : Prize Area.

#### Example
```lua
bot = getBot()

signal = bot:getSignal()

if signal.type ~= GeigerArea.null then
    print(string.format("Latest geiger area found on (%i:%i)", signal.x, signal.y))
end
```

## Role

An enumeration representing the role type.

#### Values
* `farm` : Farmer Role
* `build` : Builder Role
* `surg` : Master Surgeon Role.
* `fish` : Fisher Role.
* `cook` : Chef Role.
* `startopia` : Star Captain Role.

## Bubble

An enumeration representing bubble type.

#### Values
* `none` : No Bubble.
* `talk` : Talking Bubble.
* `brb` : Busy(brb) Bubble.

#### Example
```lua
bot = getBot()
bot:setBubble(Bubble.talk)
```

## Platform

An enumeration representing login platform.

#### Values
* `windows` : PLATFORM_WINDOWS.
* `android` : PLATFORM_ANDROID.
* `macos` : PLATFORM_MACOS.

#### Example
```lua
addBot("name", "password", "", "", Platform.android) -- Adding bot with Android Platform.
```

## StorageType

An enumeration representing storage type on rotation.

#### Values
* `pack` : Type Pack Storage.
* `seed` : Type Seed Storage.

## Proxy

An enumeration representing proxy type.

#### Values
* `none` : No Proxy.
* `http` : HTTP Proxy.
* `https` : HTTPs Proxy.
* `socks5` : Socks5 Proxy.

## PlayerState
## TileType
## TileFlag
## NpcType
