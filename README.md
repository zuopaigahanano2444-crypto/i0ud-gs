-- Orion UI Full Example Script

local OrionLib = loadstring(game:HttpGet(('https://raw.githubusercontent.com/shlexware/Orion/main/source')))()

local Window = OrionLib:MakeWindow({
	Name = "My Advanced Hub",
	HidePremium = false,
	SaveConfig = true,
	ConfigFolder = "MyHubConfig"
})

-- ===== Main Tab =====
local MainTab = Window:MakeTab({
	Name = "Main",
	Icon = "rbxassetid://4483345998",
	PremiumOnly = false
})

-- Button
MainTab:AddButton({
	Name = "Print Hello",
	Callback = function()
		print("Hello from Orion UI!")
	end
})

-- Toggle
MainTab:AddToggle({
	Name = "Show Player Name",
	Default = false,
	Callback = function(Value)
		if Value then
			print("Player:", game.Players.LocalPlayer.Name)
		else
			print("Toggle Off")
		end
	end
})

-- Slider
MainTab:AddSlider({
	Name = "Test Value",
	Min = 0,
	Max = 100,
	Default = 50,
	Increment = 1,
	ValueName = "Value",
	Callback = function(Value)
		print("Slider Value:", Value)
	end
})

-- Notification Button
MainTab:AddButton({
	Name = "Show Notification",
	Callback = function()
		OrionLib:MakeNotification({
			Name = "Notification",
			Content = "This is a test message!",
			Image = "rbxassetid://4483345998",
			Time = 3
		})
	end
})

OrionLib:Init()
