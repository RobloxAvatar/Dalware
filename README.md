--©Copyright 2022-5 Dalware
--Updated
for i,v in pairs(game:GetService("CoreGui"):GetChildren()) do
	if v.Name == "Dalware" then
		return v
	end
end

local Dalware = Instance.new("ScreenGui")
local LoadingFrame = Instance.new("ImageLabel")
local LoadingFrame_2 = Instance.new("Frame")
local LoadingBar = Instance.new("Frame")
local LoadingText = Instance.new("TextLabel")
local Title = Instance.new("TextLabel")
local above_triangle = Instance.new("ImageButton")
local down_triangle = Instance.new("ImageButton")

Dalware.Name = "Dalware"
Dalware.Parent = game:GetService("CoreGui")

LoadingFrame.Name = "LoadingFrame"
LoadingFrame.Parent = Dalware
LoadingFrame.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
LoadingFrame.BackgroundTransparency = 1.000
LoadingFrame.Position = UDim2.new(0.431661278, 0, 0.445925921, 0)
LoadingFrame.Size = UDim2.new(0, 262, 0, 116)
LoadingFrame.Image = "rbxassetid://3570695787"
LoadingFrame.ImageColor3 = Color3.fromRGB(30, 30, 30)
LoadingFrame.ScaleType = Enum.ScaleType.Slice
LoadingFrame.SliceCenter = Rect.new(100, 100, 100, 100)
LoadingFrame.SliceScale = 0.090

LoadingFrame_2.Name = "LoadingFrame"
LoadingFrame_2.Parent = LoadingFrame
LoadingFrame_2.BackgroundColor3 = Color3.fromRGB(25, 25, 25)
LoadingFrame_2.BorderSizePixel = 0
LoadingFrame_2.Position = UDim2.new(-0.00105848908, 0, 0.537149429, 0)
LoadingFrame_2.Size = UDim2.new(0, 262, 0, 12)

LoadingBar.Name = "LoadingBar"
LoadingBar.Parent = LoadingFrame_2
LoadingBar.BackgroundColor3 = Color3.fromRGB(252, 0, 16)
LoadingBar.BorderSizePixel = 0
LoadingBar.Size = UDim2.new(0, 0, 0, 12)

LoadingText.Name = "LoadingText"
LoadingText.Parent = LoadingFrame
LoadingText.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
LoadingText.BackgroundTransparency = 1.000
LoadingText.Position = UDim2.new(0, 0, 0.637931049, 0)
LoadingText.Size = UDim2.new(0, 262, 0, 42)
LoadingText.Font = Enum.Font.SourceSans
LoadingText.Text = "Loading..."
LoadingText.TextColor3 = Color3.fromRGB(252, 0, 16)
LoadingText.TextSize = 14.000

Title.Name = "Title"
Title.Parent = LoadingFrame
Title.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Title.BackgroundTransparency = 1.000
Title.Size = UDim2.new(0, 261, 0, 50)
Title.Font = Enum.Font.GothamBold
Title.Text = "Dalware"
Title.TextColor3 = Color3.fromRGB(252, 0, 16)
Title.TextSize = 20.000

above_triangle.Name = "above_triangle"
above_triangle.Parent = LoadingFrame
above_triangle.BackgroundTransparency = 1.000
above_triangle.LayoutOrder = 9
above_triangle.Rotation = 270.000
above_triangle.Size = UDim2.new(0, 25, 0, 25)
above_triangle.ZIndex = 2
above_triangle.Image = "rbxassetid://3926307971"
above_triangle.ImageColor3 = Color3.fromRGB(252, 0, 16)
above_triangle.ImageRectOffset = Vector2.new(764, 244)
above_triangle.ImageRectSize = Vector2.new(36, 36)

down_triangle.Name = "down_triangle"
down_triangle.Parent = LoadingFrame
down_triangle.BackgroundTransparency = 1.000
down_triangle.LayoutOrder = 9
down_triangle.Position = UDim2.new(0, 0, 0.0517241396, 0)
down_triangle.Rotation = 90.000
down_triangle.Size = UDim2.new(0, 25, 0, 25)
down_triangle.ZIndex = 2
down_triangle.Image = "rbxassetid://3926307971"
down_triangle.ImageColor3 = Color3.fromRGB(252, 0, 16)
down_triangle.ImageRectOffset = Vector2.new(764, 244)
down_triangle.ImageRectSize = Vector2.new(36, 36)

local function NLXJD_fake_script()
	local script = Instance.new('LocalScript', LoadingBar)

	local bar = script.Parent.Parent.LoadingBar
	local loadingtext = script.Parent.Parent.Parent.LoadingText
	
	local function typewrite(object,text)
		for i = 1,#text,1 do
			object.Text = string.sub(text,1,i)
			wait(0.05)
		end
	end
	
	function wrfile()
		if isfile("Dalware-Version.txt") and string.find(readfile("Dalware-Version.txt"), game:HttpGet("https://raw.githubusercontent.com/RobloxAvatar/Dalware/main/version.dw", true)) then
			return readfile("Dalware-Version.txt")
		else
			if isfile("Dalware-Version.txt") and not string.find(readfile("Dalware-Version.txt"), game:HttpGet("https://raw.githubusercontent.com/RobloxAvatar/Dalware/main/version.dw", true)) then
				writefile("Dalware-Version.txt", game:HttpGet("https://raw.githubusercontent.com/RobloxAvatar/Dalware/main/version.dw", true))
				return "oldVersion"
			else
				writefile("Dalware-Version.txt", game:HttpGet("https://raw.githubusercontent.com/RobloxAvatar/Dalware/main/version.dw", true))
				return "createFile"
			end
		end
	end
	
	version = wrfile()
	
	for i = 1,100 do
		if i == 25 then
			typewrite(loadingtext, "Checking dalware status...")
			wait(1.75)
			if string.find(game:HttpGet("https://raw.githubusercontent.com/RobloxAvatar/Dalware/main/status.dw"), "Offline") then
				typewrite(loadingtext, "Dalware is offline, closing!")
				wait(1.75)
				game:GetService("CoreGui"):FindFirstChild("Dalware"):Destroy()
			end
		end
		if i == 50 then
			typewrite(loadingtext, "Checking Version...")
			if version == "oldVersion" then
				wait(1.75)
				typewrite(loadingtext, "The version you are using is outdated, updating!")
				wait(1.75)
			else
				if version == "createFile" then
					wait(1.75)
					typewrite(loadingtext, "Downloading Version!")
					wait(1.75)
				else
					wait(1.75)
					typewrite(loadingtext, "Correct Version!")
					wait(1.75)
				end
			end
		end
		if i == 75 then
			typewrite(loadingtext, "Checking whitelist...")
			wait(1.75)
		end
		if string.find(game:HttpGet("https://raw.githubusercontent.com/RobloxAvatar/Dalware/main/people.txt"), game:GetService("Players").LocalPlayer.Name) then
			if i == 100 then
				typewrite(loadingtext, "Done, opening dalware!")
				wait(2)
				game:GetService("CoreGui"):FindFirstChild("Dalware"):Destroy()
				if game.PlaceId == 6403373529 then
					wait(0.5)
					loadstring(game:HttpGet("https://raw.githubusercontent.com/RobloxAvatar/Dalware/main/slap-battles.dw", true))()
				else
					if game.PlaceId == 7346416636 then
						wait(0.5)
						loadstring(game:HttpGet("https://raw.githubusercontent.com/RobloxAvatar/Dalware/main/pop-it-trading.dw", true))()
					else
						if game.PlaceId == 3527629287 then
							loadstring(game:HttpGet("https://raw.githubusercontent.com/RobloxAvatar/Dalware/main/big-paintball.dw", true))()
						end
					end				
				end
			end
		else
			if i == 75 then
				typewrite(loadingtext, "Whitelist failed!")
				wait(2.25)
				game:GetService("Players").LocalPlayer:Kick("Your account has not been whitelisted!")
			end
		end
		wait(0.045)
	
		local formula = i/100
	
		bar:TweenSize(UDim2.new(formula, 0, 1, 0), Enum.EasingDirection.Out, Enum.EasingStyle.Linear, 0.2, true)
	end
end
coroutine.wrap(NLXJD_fake_script)()
