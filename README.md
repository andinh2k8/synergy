getgenv().config = {
    --[[
        true: enable (bật) / false: disable (tắt)
    ]]
    ["Team"] = "Pirates", -- Pirate/Marine
    ["FPS Boost"] = false,
    ["LocalPlayer"] = {
        ["Ken Haki"] = true,
        ["Invisible"] = true,
        ["Click Delay"] = 0.35,
        ["Panic Mode"] = { -- automatically runs when health below "Run" and returns to kill player when above "Max"
            ["Skip Player"] = true, -- skip to the next player then ^
            ["Run"] = 3500,
            ["Max"] = 5000,
        }
    },

    ["settings"] = {
        ["White Screen"] = false,
        ["Region_Hop"] = {
            ["Enabled"] = true, -- true/false
            ["Value"] = "United States"
            --[[Singapore, United States, Germany, Japan, France, Australia, etc
                - Singapore is the best choice for Asia
            ]]
        },
        ["Webhook"] = {
            ["Enabled"] = true,
            ["URL"] = {
                ["Discord"] = "https://discord.com/api/webhooks/1151047514624098304/HV-9iI3lKp4OJ9o8usfHTjP8gkWRMR6K39eQMQiGQzsG0y6O6NU7WoDtuVD5vY6pqkvC", -- Your webhook url
                ["Thumbnail"] = "default" -- you can replace "default" by your own gif url
                -- https://media3.giphy.com/media/koTcC0UFlN4WY/giphy.gif?cid=ecf05e479x5d7wlvndaefjdrktdlchzthfrsqc1s3m5qzhm3&ep=v1_gifs_search&rid=giphy.gif&ct=g
            }
        },
        ["Chatkill"] = {
            ["Enabled"] = false,
            ["Text"] = {
                "No Skill? Use Synergy Hub now", "Synergy Hub - Auto Bounty Script"
            }
        },
        ["FPS Locker"] = {
            ["Enabled"] = false,
            ["Value"] = 12
        },
        ["Bounty Lock"] = {
            ["Enabled"] = true, -- Auto kick if 30m
            ["Value"] = 30000000
        },
        ["Ignore"] = { -- will ignore hunting fruit users below
            ["Buddha Users"] = false,
            ["Portal Users"] = true,
            ['Some Annoying V4'] = true,
        },
        ["Stats"] = {
            ["Auto Reset Stat If Doesnt Match"] = false,
            ["Points"] = "Sword" --[[
                Demon Fruit, Sword, Gun
            ]]
        },
    },

    ["Skills"] = {
        ["Melee"] = {
            ["Time"] = 2.75,
            ["Enabled"] = true,
            ["Z"] = {["Enabled"] = true, ["HoldTime"] = 0.2},
            ["X"] = {["Enabled"] = true, ["HoldTime"] = 0.1},
            ["C"] = {["Enabled"] = true, ["HoldTime"] = 2}
        },
        ["Fruit"] = {
            ["Time"] = 1,
            ["Enabled"] = false,
            ["Z"] = {["Enabled"] = true, ["HoldTime"] = 1.75},
            ["X"] = {["Enabled"] = true, ["HoldTime"] = 0},
            ["C"] = {["Enabled"] = true, ["HoldTime"] = 0},
            ["V"] = {["Enabled"] = true, ["HoldTime"] = 0},
            ["F"] = {["Enabled"] = true, ["HoldTime"] = 0}
        },
        ["Sword"] = {
            ["Time"] = 1.4,
            ["Enabled"] = true,
            ["Z"] = {["Enabled"] = true, ["HoldTime"] = 1.5},
            ["X"] = {["Enabled"] = true, ["HoldTime"] = 0.5},
        },
        ["Gun"] = {
            ["Time"] = 2,
            ["Enabled"] = false,
            ["GunMode"] = false,
            ["Z"] = {["Enabled"] = true, ["HoldTime"] = 0},
            ["X"] = {["Enabled"] = true, ["HoldTime"] = 0},
        }
    }
};
repeat wait() until game:IsLoaded()
delay(20, function()
    if getgenv().ScriptExecuted then
        return;
    end

    game:GetService("TeleportService"):TeleportToPlaceInstance(game.PlaceId, game.JobId, game.Players.LocalPlayers)
end)
loadstring(game:HttpGet("https://raw.githubusercontent.com/PhamBaAnh08/LuaU/main/Blox%20Fruits/AutoBounty/Loader.lua"))()
