# Lobby
```
setfflag("DebugRunParallelLuaOnMainThread","True");
```

# PVP SHORTENED URL:
```lua
loadstring(game:HttpGet('https://shorturl.at/CPRQe'))()
```
# RAID SHORTENED URL:
```lua
loadstring(game:HttpGet('https://shorturl.at/CBBXt'))()
```

Note: I removed CamFix script to avoid crashes in the game if you use it with amongushook.

# PVP ORIGINAL
```lua
local scripts = {
	'https://raw.githubusercontent.com/NotH4xor/Fallen-Scripts/main/Amongus',
	'https://raw.githubusercontent.com/robloxarchives/Trident/main/NewATVFly',
	'https://raw.githubusercontent.com/NotH4xor/trident/main/FreeSwimhub',
	'https://raw.githubusercontent.com/NotH4xor/trident/main/UD_ESP',
	'https://raw.githubusercontent.com/NotH4xor/trident/main/ChunkRemoval(HoldR)',
	'https://raw.githubusercontent.com/1337h4xx/1/main/X_3rd_Person',
	'https://raw.githubusercontent.com/NotH4xor/trident/main/UD_FREECAM',
	'https://raw.githubusercontent.com/robloxarchives/CurrentConfig/main/Delete'
}
for _, url in ipairs(scripts) do
    local thread = coroutine.create(function()
        loadstring(game:HttpGet(url, true))()
    end)
    coroutine.resume(thread)
end
table.insert(scripts, "new_script_url")
```

# RAID ORIGINAL
```lua
local scripts = {
	'https://raw.githubusercontent.com/robloxarchives/Trident/refs/heads/main/CamFix',
	'https://raw.githubusercontent.com/robloxarchives/Trident/main/NewATVFly',
	'https://raw.githubusercontent.com/NotH4xor/trident/main/FreeSwimhub',
	'https://raw.githubusercontent.com/NotH4xor/trident/main/UD_ESP',
	'https://raw.githubusercontent.com/NotH4xor/trident/main/ChunkRemoval(HoldR)',
	'https://raw.githubusercontent.com/1337h4xx/1/main/X_3rd_Person',
	'https://raw.githubusercontent.com/NotH4xor/trident/main/UD_FREECAM',
	'https://raw.githubusercontent.com/robloxarchives/CurrentConfig/main/Delete'
}
for _, url in ipairs(scripts) do
    local thread = coroutine.create(function()
        loadstring(game:HttpGet(url, true))()
    end)
    coroutine.resume(thread)
end
table.insert(scripts, "new_script_url")
```
