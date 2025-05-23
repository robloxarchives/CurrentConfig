# Lobby
```
setfflag("DebugRunParallelLuaOnMainThread","True");
```

# Loader
```lua
local scripts = {
    'https://raw.githubusercontent.com/robloxarchives/CurrentConfig/main/AmongusOBFUSCATED',
    'https://raw.githubusercontent.com/robloxarchives/Trident/main/ATVONLY',
    'https://raw.githubusercontent.com/robloxarchives/Trident/main/SwimStyleSPRINT',
    'https://raw.githubusercontent.com/NotH4xor/trident/main/UD_ESP',
    'https://raw.githubusercontent.com/NotH4xor/trident/main/ChunkRemoval(HoldR)',
    'https://raw.githubusercontent.com/1337h4xx/1/main/X_3rd_Person',
    'https://raw.githubusercontent.com/NotH4xor/trident/main/UD_FREECAM',
    'https://raw.githubusercontent.com/robloxarchives/CurrentConfig/main/Delete',
    'https://raw.githubusercontent.com/robloxarchives/CurrentConfig/main/NoAtvRestriction',
    'https://raw.githubusercontent.com/robloxarchives/CurrentConfig/main/ATVNoclip_KeybindT',
    'https://raw.githubusercontent.com/robloxarchives/CurrentConfig/main/LongNeck(L)',
    'https://raw.githubusercontent.com/robloxarchives/CurrentConfig/main/DepoLootAll(B)',
    'https://raw.githubusercontent.com/robloxarchives/CurrentConfig/main/LootAll(V)',
    'https://raw.githubusercontent.com/robloxarchives/CurrentConfig/main/UnloadAllWeapons(H)',
    'https://raw.githubusercontent.com/robloxarchives/CurrentConfig/main/DespawnLoot(U)',
    'https://raw.githubusercontent.com/robloxarchives/CurrentConfig/main/BackpackCleanup(RightBracket)',
    'https://raw.githubusercontent.com/robloxarchives/CurrentConfig/main/ATV(Anti-Fall)',
    'https://raw.githubusercontent.com/robloxarchives/CurrentConfig/main/ATV%20Fly/Atv%20Fly%20Better',
    'https://raw.githubusercontent.com/1337h4xx/1/main/RGB%20Notification'
}
for _, url in ipairs(scripts) do
    local thread = coroutine.create(function()
        loadstring(game:HttpGet(url, true))()
    end)
    coroutine.resume(thread)
end
table.insert(scripts, "new_script_url")
```
