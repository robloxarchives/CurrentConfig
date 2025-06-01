# Loader
```lua
-- ✅ Smart executor-aware one-time script runner
local HttpService = game:GetService("HttpService")

-- If already completed previously, abort script immediately
if shared.allScriptsExecutedOnce then
    warn("🚫 All scripts have already been executed this session. Aborting.")
    return
end

-- First-time init
shared.executedURLs = shared.executedURLs or {}
shared.failedURLs = {}

local scripts = {
    'https://raw.githubusercontent.com/robloxarchives/CurrentConfig/main/AmongusOBFUSCATED', -- Amongus
    'https://raw.githubusercontent.com/robloxarchives/Trident/main/Forcesprint',
    'https://raw.githubusercontent.com/robloxarchives/Trident/main/SwimStyleSPRINT',
    'https://raw.githubusercontent.com/NotH4xor/trident/main/ChunkRemoval(HoldR)',
    'https://raw.githubusercontent.com/1337h4xx/1/main/X_3rd_Person',
    'https://raw.githubusercontent.com/NotH4xor/trident/main/UD_FREECAM',
    'https://raw.githubusercontent.com/robloxarchives/CurrentConfig/main/Delete',
    'https://raw.githubusercontent.com/robloxarchives/CurrentConfig/main/NoAtvRestriction',
    'https://raw.githubusercontent.com/robloxarchives/CurrentConfig/main/LongNeck(L)',
    'https://raw.githubusercontent.com/robloxarchives/CurrentConfig/main/DepoLootAll(B)',
    'https://raw.githubusercontent.com/robloxarchives/CurrentConfig/main/LootAll(V)',
    'https://raw.githubusercontent.com/robloxarchives/CurrentConfig/main/UnloadAllWeapons(H)',
    'https://raw.githubusercontent.com/robloxarchives/CurrentConfig/main/DespawnLoot(U)',
    'https://raw.githubusercontent.com/robloxarchives/CurrentConfig/main/BackpackCleanup(RightBracket)',
    'https://raw.githubusercontent.com/robloxarchives/CurrentConfig/main/ATV(Anti-Fall)',
    'https://raw.githubusercontent.com/1337h4xx/1/main/RGB%20Notification',
    'https://raw.githubusercontent.com/robloxarchives/CurrentConfig/main/ESP/EspTable', -- ESP
    'https://raw.githubusercontent.com/robloxarchives/CurrentConfig/main/Vehicles/FlyCars', -- FlyCar
    'https://raw.githubusercontent.com/robloxarchives/CurrentConfig/main/Vehicles/NoclipCars', -- Noclip
    'https://raw.githubusercontent.com/robloxarchives/CurrentConfig/main/Vehicles/BetterFly(Y)' -- BetterFly
}

-- Optional: encode () to avoid rawgit parsing issues
local function encodeURL(url)
    return url:gsub("[(]", "%%28"):gsub("[)]", "%%29")
end

-- Execution logic
for _, rawUrl in ipairs(scripts) do
    local url = encodeURL(rawUrl)

    if not shared.executedURLs[url] then
        local success, result = pcall(function()
            return loadstring(game:HttpGet(url, true))()
        end)

        if success then
            shared.executedURLs[url] = true
            print("✅ Executed:", url)
        else
            table.insert(shared.failedURLs, url)
            warn("❌ Failed to load:", url, "\nError:", result)
        end
    else
        print("⏭️ Skipping already executed:", url)
    end
end

-- End marker: prevent any re-run at all in future
shared.allScriptsExecutedOnce = true

-- Optional delay to log failures after everything else
task.delay(3, function()
    if #shared.failedURLs > 0 then
        warn("=== ❌ Failed URLs ===")
        for _, url in ipairs(shared.failedURLs) do
            warn(url)
        end
    else
        print("✅ All scripts executed successfully.")
    end
end)

```

# Lobby
```
setfflag("DebugRunParallelLuaOnMainThread","True");
```
