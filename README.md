-- Gui to Lua
-- Version: 3.2

-- Instances:

local ScreenGui = Instance.new("ScreenGui")
local Main = Instance.new("Frame")
local By = Instance.new("TextLabel")
local On = Instance.new("TextButton")
local Off = Instance.new("TextButton")
local discord = Instance.new("TextButton")
local risky = Instance.new("TextButton")
local OpenShop = Instance.new("TextButton")
--Properties:

ScreenGui.Parent = game.CoreGui

Main.Name = "Main"
Main.Parent = ScreenGui
Main.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Main.Position = UDim2.new(0.739050984, 0, 0.230674848, 0)
Main.Size = UDim2.new(0, 205, 0, 286)
Main.Active = true
Main.Draggable = true

By.Name = "By"
By.Parent = Main
By.BackgroundColor3 = Color3.fromRGB(143, 255, 160)
By.Position = UDim2.new(-0.000773851818, 0, -0.0299755707, 0)
By.Size = UDim2.new(0, 206, 0, 58)
By.Font = Enum.Font.SourceSans
By.Text = "Saber Simulator by youGONNASHUTUP#0145"
By.TextColor3 = Color3.fromRGB(0, 0, 0)
By.TextSize = 12.000

On.Name = "On"
On.Parent = Main
On.BackgroundColor3 = Color3.fromRGB(48, 110, 255)
On.Position = UDim2.new(0, 0, 0.171328679, 0)
On.Size = UDim2.new(0, 205, 0, 107)
On.Font = Enum.Font.SourceSans
On.Text = "AutoFarm On (turns off when u die, make sure your saber is out)"
On.TextColor3 = Color3.fromRGB(0, 0, 0)
On.TextSize = 12.000
On.MouseButton1Down:connect(function()
	shared.Enabled = true
	repeat
		oldpos = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame
		game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(532.807312, 183.837784, 149.856171) - Vector3.new(0, -7, 0)
		wait (0.5)
		game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = oldpos
		wait(0.5)
		game:GetService("ReplicatedStorage").Events.Clicked:FireServer()
		wait (0)
		game:GetService("ReplicatedStorage").Events.BuyAll:FireServer("Swords")
		wait (0)
		game:GetService("ReplicatedStorage").Events.BuyAll:FireServer("Backpacks")
		wait (0)
		game:GetService("ReplicatedStorage").Events.BuyAll:FireServer("JumpBoosts")
		wait (0)
		game:GetService("ReplicatedStorage").Events.BuyAll:FireServer("BossBoosts")

	until shared.Enabled == false
end)

Off.Name = "Off"
Off.Parent = Main
Off.BackgroundColor3 = Color3.fromRGB(255, 46, 49)
Off.Position = UDim2.new(0, 0, 0.545454562, 0)
Off.Size = UDim2.new(0, 205, 0, 130)
Off.Font = Enum.Font.SourceSans
Off.Text = "AutoFarm Off"
Off.TextColor3 = Color3.fromRGB(0, 0, 0)
Off.TextSize = 14.000
Off.MouseButton1Down:connect(function()
	shared.Enabled = false
	repeat
		oldpos = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame
		game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(532.807312, 183.837784, 149.856171)
		wait(1)
		game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = oldpos
		wait(1)
	until shared.Enabled == false
end)

discord.Name = "discord"
discord.Parent = Main
discord.BackgroundColor3 = Color3.fromRGB(41, 44, 42)
discord.Position = UDim2.new(0, 0, 1.31468534, 0)
discord.Size = UDim2.new(0, 206, 0, 50)
discord.Font = Enum.Font.SourceSans
discord.Text = "join the discord"
discord.TextColor3 = Color3.fromRGB(0, 0, 0)
discord.TextSize = 14.000
local requestfunc = syn and syn.request or http and http.request or http_request or fluxus and fluxus.request or getgenv().request or request
discord.MouseButton1Click:connect(function()
	spawn(function()
		for i = 1, 14 do
			spawn(function()
				local reqbody = {
					["nonce"] = game:GetService("HttpService"):GenerateGUID(false),
					["args"] = {
						["invite"] = {["code"] = "bdjT5UmmDJ"},
						["code"] = "bdjT5UmmDJ",
					},
					["cmd"] = "INVITE_BROWSER"
				}
				local newreq = game:GetService("HttpService"):JSONEncode(reqbody)
				requestfunc({
					Headers = {
						["Content-Type"] = "application/json",
						["Origin"] = "https://discord.com"
					},
					Url = "http://127.0.0.1:64"..(53 + i).."/rpc?v=1",
					Method = "POST",
					Body = newreq
				})
			end)
		end
	end)
end)

-- you can easily die from this
risky.Name = "risky"
risky.Parent = Main
risky.BackgroundColor3 = Color3.fromRGB(255, 0, 4)
risky.Position = UDim2.new(-0.00487804879, 0, 1, 0)
risky.Size = UDim2.new(0, 206, 0, 50)
risky.Font = Enum.Font.SourceSans
risky.Text = "Later Game AutoFarm (u can die)"
risky.TextColor3 = Color3.fromRGB(0, 0, 0)
risky.TextSize = 14.000
risky.MouseButton1Click:connect(function()
	risky.MouseButton1Down:connect(function()
		shared.Enabled = true
		repeat
			oldpos = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame
			game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(532.807312, 183.837784, 149.856171) - Vector3.new(0, -10, 0)
			wait (0.5)
			game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(791.358337, 252.104965, 32.121006, 1, 0, 0, 0, 1, 0, 0, 0, 1) - Vector3.new(0, 7, 0)
			wait(2)
			game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = oldpos
			wait(0)
			game:GetService("ReplicatedStorage").Events.Clicked:FireServer()
			wait (0)
			game:GetService("ReplicatedStorage").Events.BuyAll:FireServer("Swords")
			wait (0)
			game:GetService("ReplicatedStorage").Events.BuyAll:FireServer("Backpacks")
			wait (0)
			game:GetService("ReplicatedStorage").Events.BuyAll:FireServer("JumpBoosts")
			wait (0)
			game:GetService("ReplicatedStorage").Events.BuyAll:FireServer("BossBoosts")

		until shared.Enabled == false
	end)
end)

OpenShop.Name = "OpenShop (can break autofarm)"
OpenShop.Parent = Main
OpenShop.BackgroundColor3 = Color3.fromRGB(98, 206, 255)
OpenShop.Position = UDim2.new(-0.00487804879, 0, 1.17482519, 0)
OpenShop.Size = UDim2.new(0, 206, 0, 40)
OpenShop.Font = Enum.Font.SourceSans
OpenShop.Text = "OpenShop"
OpenShop.TextColor3 = Color3.fromRGB(0, 0, 0)
OpenShop.TextSize = 13.000
OpenShop.MouseButton1Click:connect(function()
	oldpos = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame
	game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(474.126984, 184.502411, 53.9981308, 0.23579514, -2.68487117e-08, 0.971802771, 2.69384355e-08, 1, 2.10914806e-08, -0.971802771, 2.12055777e-08, 0.23579514)
	wait (0.2)
	game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = oldpos
end)
