local OrionLib = loadstring(game:HttpGet(('https://raw.githubusercontent.com/shlexware/Orion/main/source')))()
local Player = game.Players.LocalPlayer
local Window = OrionLib:MakeWindow({Name = "Key System", HidePremium = false, SaveConfig = true, IntroEnabled = false})

OrionLib:MakeNotification({
	Name = "Logged in!",
	Content = "Hello, you are logged in as "..Player.Name..".",
	Image = "rbxassetid://4483345998",
	Time = 5
})

_G.Key = "Get_Khoi080"
_G.KeyInput = "string"

function MakeScriptHub()
	local Window = OrionLib:MakeWindow({Name = "Script Hub", HidePremium = false, SaveConfig = true, IntroEnabled = true, IntroText = "Script Hub"})
end

function IncorrectKeyNotification()
	OrionLib:MakeNotification({
		Name = "Incorrect Key!",
		Content = "Hello",
		Image = "rbxassetid://4483345998",
		Time = 5
	})
end

function CorrectKeyNotification()
	OrionLib:MakeNotification({
		Name = "Correct Key!",
		Content = "Hello",
		Image = "rbxassetid://4483345998",
		Time = 5
	})
end


local Tab = Window:MakeTab({
	Name = "Key",
	Icon = "rbxassetid://4483345998",
	PremiumOnly = false
})

Tab:AddTextbox({
	Name = "Enter Key",
	Default = "",
	TextDisappear = true,
	Callback = function(Value)
		_G.KeyInput = Value
	end	  
})

Tab:AddButton({
	Name = "Check Key",
	Callback = function()
      	if _G.KeyInput == _G.Key then
        MakeScriptHub()
		CorrectKeyNotification()
		else
			IncorrectKeyNotification()
		end
  	end    
})
