# LUCIFER V1 - API DOCUMENTATION [ENUMS]

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
* `http_block` : the server is blocking HTTP connections from bot ip.
* `bad_name_length` : the bot name is too short or too long.
* `invalid_account` : the bot is invalid.
* `error_connecting` : there was an error connecting to the server.
* `logon_fail` : the bot failed to log in.

#### Example Usage
```lua
-- Get the current status of the bot
local status = GetBot().status

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

#### Example Usage
```lua
-- Check if a captcha has been solved
local captchaStatus = GetBot().captcha_status

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

#### Example Usage
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
* `variantlist` : Variant List event.
* `game_message` : Game Message event.
* `generic_text` : Generic Text event.
* `update_packet` : Game Update Packet event.
* `track_packet` : Track Packet event.
* `render` : ImGui Render event.
* `discord` : Discord event.

#### Example Usage
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

#### Example Usage
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

#### Example Usage
```lua
bot = GetBot()

signal = bot:getSignal()

if signal.type ~= GeigerArea.null then
    print(string.format("Latest geiger area found on (%i:%i)", signal.x, signal.y))
end
```

## BubbleType
## PlayerState
## TileType
## TileFlag
## NpcType
