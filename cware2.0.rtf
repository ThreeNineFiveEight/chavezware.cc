--// LocalScript in StarterPlayerScripts
--// Chavezware GUI + ESP Toggle + Aimlock + Trigger Bot + Silent Aim

-- Services
local Players = game:GetService("Players")
local UIS = game:GetService("UserInputService")
local RunService = game:GetService("RunService")
local Workspace = game:GetService("Workspace")
local TweenService = game:GetService("TweenService")

local LocalPlayer = Players.LocalPlayer
local Camera = Workspace.CurrentCamera

-- Configuration
local GUI_TOGGLE_KEY = Enum.KeyCode.RightShift
local ESP_TOGGLE_KEYS = { Enum.KeyCode.E, Enum.KeyCode.Delete }
local ESP_FILL_COLOR = Color3.fromRGB(255, 0, 0)
local ESP_OUTLINE_COLOR = Color3.fromRGB(255, 255, 255)
local ESP_FILL_TRANSPARENCY = 0.6
local ESP_OUTLINE_TRANSPARENCY = 0

-- Aimlock Configuration
local AIMLOCK_KEY = Enum.KeyCode.RightControl
local AIM_SMOOTHNESS = 5
local AIM_FOV_SIZE = 200
local AIM_TARGET_PART = "Head"
local AIM_TEAM_CHECK = true
local AIM_FOV_VISIBLE = true
local AIM_VISIBLE_CHECK = true

-- Trigger Bot Configuration
local TRIGGER_BOT_ENABLED = false

-- Silent Aim Configuration
local SILENT_AIM_KEY = Enum.KeyCode.RightAlt
local SILENT_AIM_ENABLED = false
local SILENT_AIM_TEAM_CHECK = true
local SILENT_AIM_VISIBLE_CHECK = true
local SILENT_AIM_TARGET_PART = "Head"
local SILENT_AIM_FOV_SIZE = 130
local SILENT_AIM_FOV_VISIBLE = false
local SILENT_AIM_HIT_CHANCE = 100
local SILENT_AIM_PREDICTION = false
local SILENT_AIM_PREDICTION_AMOUNT = 0.165

-- State
local espEnabled = false
local guiVisible = false
local highlights = {}
local currentColorPicker = nil
local currentPickerType = nil
local aimlockEnabled = false
local currentTarget = nil
local aimlockConnection = nil
local triggerBotConnection = nil
local watermarksVisible = true
local rainbowHue = 0
local loadingComplete = false

--// Create Loading Screen
local loadingScreen = Instance.new("ScreenGui")
loadingScreen.Name = "ChavezwareLoading"
loadingScreen.ResetOnSpawn = false
loadingScreen.IgnoreGuiInset = true
loadingScreen.Parent = LocalPlayer:WaitForChild("PlayerGui")

local loadingFrame = Instance.new("Frame")
loadingFrame.Size = UDim2.new(1, 0, 1, 0)
loadingFrame.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
loadingFrame.BorderSizePixel = 0
loadingFrame.Parent = loadingScreen

local loadingText = Instance.new("TextLabel")
loadingText.Size = UDim2.new(0, 400, 0, 40)
loadingText.Position = UDim2.new(0.5, -200, 0.5, -50)
loadingText.BackgroundTransparency = 1
loadingText.Text = "loading chavezware+release-2.0"
loadingText.Font = Enum.Font.Code
loadingText.TextColor3 = Color3.fromRGB(0, 255, 0)
loadingText.TextSize = 20
loadingText.TextStrokeTransparency = 0
loadingText.TextStrokeColor3 = Color3.fromRGB(0, 0, 0)
loadingText.Parent = loadingFrame

local progressBar = Instance.new("Frame")
progressBar.Size = UDim2.new(0, 400, 0, 20)
progressBar.Position = UDim2.new(0.5, -200, 0.5, 0)
progressBar.BackgroundColor3 = Color3.fromRGB(40, 40, 40)
progressBar.BorderSizePixel = 0
progressBar.Parent = loadingFrame

local progressFill = Instance.new("Frame")
progressFill.Size = UDim2.new(0, 0, 1, 0)
progressFill.Position = UDim2.new(0, 0, 0, 0)
progressFill.BackgroundColor3 = Color3.fromRGB(0, 255, 0)
progressFill.BorderSizePixel = 0
progressFill.Parent = progressBar

-- Animate loading bar
local function startLoadingAnimation()
	local tweenInfo = TweenInfo.new(3, Enum.EasingStyle.Linear)
	local tween = TweenService:Create(progressFill, tweenInfo, {Size = UDim2.new(1, 0, 1, 0)})
	tween:Play()

	delay(3, function()
		loadingScreen:Destroy()
		guiVisible = true
		loadingComplete = true
		mainFrame.Visible = true
		updateWatermarkVisibility()
		updateFOVVisibility()
	end)
end

-- Start loading animation
startLoadingAnimation()

--// Create Watermark
local watermark = Instance.new("ScreenGui")
watermark.Name = "ChavezwareWatermark"
watermark.ResetOnSpawn = false
watermark.IgnoreGuiInset = true
watermark.Parent = LocalPlayer:WaitForChild("PlayerGui")

-- Main watermark (chavezware.cc)
local watermarkLabel = Instance.new("TextLabel")
watermarkLabel.Size = UDim2.new(0, 200, 0, 30)
watermarkLabel.Position = UDim2.new(0.5, -100, 0, 10)
watermarkLabel.BackgroundTransparency = 1
watermarkLabel.Text = "chavezware.cc"
watermarkLabel.Font = Enum.Font.Code
watermarkLabel.TextColor3 = Color3.fromRGB(255, 0, 0)
watermarkLabel.TextSize = 18
watermarkLabel.TextStrokeTransparency = 0
watermarkLabel.TextStrokeColor3 = Color3.fromRGB(0, 0, 0)
watermarkLabel.Visible = true
watermarkLabel.Parent = watermark

-- Middle watermark (version 2.0)
local versionWatermarkLabel = Instance.new("TextLabel")
versionWatermarkLabel.Size = UDim2.new(0, 200, 0, 20)
versionWatermarkLabel.Position = UDim2.new(0.5, -100, 0, 40)
versionWatermarkLabel.BackgroundTransparency = 1
versionWatermarkLabel.Text = "version 2.0"
versionWatermarkLabel.Font = Enum.Font.Code
versionWatermarkLabel.TextColor3 = Color3.fromRGB(255, 0, 0)
versionWatermarkLabel.TextSize = 14
versionWatermarkLabel.TextStrokeTransparency = 0
versionWatermarkLabel.TextStrokeColor3 = Color3.fromRGB(0, 0, 0)
versionWatermarkLabel.Visible = true
versionWatermarkLabel.Parent = watermark

-- Small watermark below (622354228)
local smallWatermarkLabel = Instance.new("TextLabel")
smallWatermarkLabel.Size = UDim2.new(0, 200, 0, 20)
smallWatermarkLabel.Position = UDim2.new(0.5, -100, 0, 60)
smallWatermarkLabel.BackgroundTransparency = 1
smallWatermarkLabel.Text = "622354228"
smallWatermarkLabel.Font = Enum.Font.Code
smallWatermarkLabel.TextColor3 = Color3.fromRGB(255, 0, 0)
smallWatermarkLabel.TextSize = 14
smallWatermarkLabel.TextStrokeTransparency = 0
smallWatermarkLabel.TextStrokeColor3 = Color3.fromRGB(0, 0, 0)
smallWatermarkLabel.Visible = true
smallWatermarkLabel.Parent = watermark

--// Create GUI
local screenGui = Instance.new("ScreenGui")
screenGui.Name = "ChavezwareGUI"
screenGui.ResetOnSpawn = false
screenGui.IgnoreGuiInset = true
screenGui.Parent = LocalPlayer:WaitForChild("PlayerGui")

-- Main frame
local mainFrame = Instance.new("Frame")
mainFrame.Size = UDim2.new(0, 250, 0, 520)
mainFrame.Position = UDim2.new(0.5, -125, 0.3, 0)
mainFrame.BackgroundColor3 = Color3.fromRGB(25, 25, 25)
mainFrame.BorderColor3 = Color3.fromRGB(255, 0, 0)
mainFrame.Active = true
mainFrame.Draggable = true
mainFrame.Visible = false
mainFrame.Parent = screenGui

-- Rainbow border effect
local function updateRainbowBorder()
	while true do
		rainbowHue = (rainbowHue + 0.01) % 1
		mainFrame.BorderColor3 = Color3.fromHSV(rainbowHue, 1, 1)
		wait(0.05)
	end
end

spawn(updateRainbowBorder)

-- Title
local title = Instance.new("TextLabel")
title.Size = UDim2.new(1, 0, 0, 30)
title.BackgroundColor3 = Color3.fromRGB(35, 35, 35)
title.Text = "Chavezware"
title.Font = Enum.Font.Code
title.TextColor3 = Color3.fromRGB(255, 0, 0)
title.TextScaled = true
title.Parent = mainFrame

-- Made by 3958 under title
local madeByLabel = Instance.new("TextLabel")
madeByLabel.Size = UDim2.new(1, 0, 0, 15)
madeByLabel.Position = UDim2.new(0, 0, 0, 30)
madeByLabel.BackgroundTransparency = 1
madeByLabel.Text = "made by 3958"
madeByLabel.Font = Enum.Font.Code
madeByLabel.TextColor3 = Color3.fromRGB(180, 180, 180)
madeByLabel.TextSize = 10
madeByLabel.TextXAlignment = Enum.TextXAlignment.Center
madeByLabel.Parent = mainFrame

-- ESP Section
local espTitle = Instance.new("TextLabel")
espTitle.Size = UDim2.new(1, -10, 0, 20)
espTitle.Position = UDim2.new(0, 5, 0, 55)
espTitle.BackgroundTransparency = 1
espTitle.Text = "ESP:"
espTitle.Font = Enum.Font.Code
espTitle.TextColor3 = Color3.fromRGB(255, 255, 255)
espTitle.TextSize = 14
espTitle.TextXAlignment = Enum.TextXAlignment.Left
espTitle.Parent = mainFrame

-- ESP Toggle Button
local toggleButton = Instance.new("TextButton")
toggleButton.Size = UDim2.new(0, 220, 0, 25)
toggleButton.Position = UDim2.new(0.5, -110, 0, 80)
toggleButton.BackgroundColor3 = Color3.fromRGB(40, 40, 40)
toggleButton.Text = "ESP: OFF"
toggleButton.Font = Enum.Font.Code
toggleButton.TextColor3 = Color3.fromRGB(255, 255, 255)
toggleButton.TextSize = 12
toggleButton.Parent = mainFrame

-- Color Buttons Row
local fillColorButton = Instance.new("TextButton")
fillColorButton.Size = UDim2.new(0, 100, 0, 25)
fillColorButton.Position = UDim2.new(0, 10, 0, 110)
fillColorButton.BackgroundColor3 = ESP_FILL_COLOR
fillColorButton.Text = "Fill Color"
fillColorButton.Font = Enum.Font.Code
fillColorButton.TextColor3 = Color3.fromRGB(255, 255, 255)
fillColorButton.TextSize = 12
fillColorButton.Parent = mainFrame

local outlineColorButton = Instance.new("TextButton")
outlineColorButton.Size = UDim2.new(0, 100, 0, 25)
outlineColorButton.Position = UDim2.new(1, -110, 0, 110)
outlineColorButton.BackgroundColor3 = ESP_OUTLINE_COLOR
outlineColorButton.Text = "Outline Color"
outlineColorButton.Font = Enum.Font.Code
outlineColorButton.TextColor3 = Color3.fromRGB(0, 0, 0)
outlineColorButton.TextSize = 12
outlineColorButton.Parent = mainFrame

-- Watermark Toggle Button
local watermarkToggleButton = Instance.new("TextButton")
watermarkToggleButton.Size = UDim2.new(0, 220, 0, 25)
watermarkToggleButton.Position = UDim2.new(0.5, -110, 0, 140)
watermarkToggleButton.BackgroundColor3 = Color3.fromRGB(40, 40, 40)
watermarkToggleButton.Text = "Watermark: ON"
watermarkToggleButton.Font = Enum.Font.Code
watermarkToggleButton.TextColor3 = Color3.fromRGB(255, 255, 255)
watermarkToggleButton.TextSize = 12
watermarkToggleButton.Parent = mainFrame

-- Aimlock Section
local aimlockTitle = Instance.new("TextLabel")
aimlockTitle.Size = UDim2.new(1, -10, 0, 20)
aimlockTitle.Position = UDim2.new(0, 5, 0, 175)
aimlockTitle.BackgroundTransparency = 1
aimlockTitle.Text = "AIMLOCK:"
aimlockTitle.Font = Enum.Font.Code
aimlockTitle.TextColor3 = Color3.fromRGB(255, 255, 255)
aimlockTitle.TextSize = 14
aimlockTitle.TextXAlignment = Enum.TextXAlignment.Left
aimlockTitle.Parent = mainFrame

-- Aimlock Toggle Button
local aimlockToggleButton = Instance.new("TextButton")
aimlockToggleButton.Size = UDim2.new(0, 220, 0, 25)
aimlockToggleButton.Position = UDim2.new(0.5, -110, 0, 200)
aimlockToggleButton.BackgroundColor3 = Color3.fromRGB(40, 40, 40)
aimlockToggleButton.Text = "AIMLOCK: OFF (RightCtrl)"
aimlockToggleButton.Font = Enum.Font.Code
aimlockToggleButton.TextColor3 = Color3.fromRGB(255, 255, 255)
aimlockToggleButton.TextSize = 12
aimlockToggleButton.Parent = mainFrame

-- Trigger Bot Toggle Button
local triggerBotToggleButton = Instance.new("TextButton")
triggerBotToggleButton.Size = UDim2.new(0, 220, 0, 25)
triggerBotToggleButton.Position = UDim2.new(0.5, -110, 0, 230)
triggerBotToggleButton.BackgroundColor3 = Color3.fromRGB(40, 40, 40)
triggerBotToggleButton.Text = "TRIGGER BOT: OFF"
triggerBotToggleButton.Font = Enum.Font.Code
triggerBotToggleButton.TextColor3 = Color3.fromRGB(255, 255, 255)
triggerBotToggleButton.TextSize = 12
triggerBotToggleButton.Parent = mainFrame

-- Aimlock Settings Row 1
local targetPartButton = Instance.new("TextButton")
targetPartButton.Size = UDim2.new(0, 100, 0, 25)
targetPartButton.Position = UDim2.new(0, 10, 0, 265)
targetPartButton.BackgroundColor3 = Color3.fromRGB(50, 50, 50)
targetPartButton.Text = "Target: Head"
targetPartButton.Font = Enum.Font.Code
targetPartButton.TextColor3 = Color3.fromRGB(255, 255, 255)
targetPartButton.TextSize = 12
targetPartButton.Parent = mainFrame

local teamCheckButton = Instance.new("TextButton")
teamCheckButton.Size = UDim2.new(0, 100, 0, 25)
teamCheckButton.Position = UDim2.new(1, -110, 0, 265)
teamCheckButton.BackgroundColor3 = Color3.fromRGB(50, 50, 50)
teamCheckButton.Text = "Team Check: ON"
teamCheckButton.Font = Enum.Font.Code
teamCheckButton.TextColor3 = Color3.fromRGB(255, 255, 255)
teamCheckButton.TextSize = 12
teamCheckButton.Parent = mainFrame

-- Aimlock Settings Row 2
local visibleCheckButton = Instance.new("TextButton")
visibleCheckButton.Size = UDim2.new(0, 100, 0, 25)
visibleCheckButton.Position = UDim2.new(0, 10, 0, 295)
visibleCheckButton.BackgroundColor3 = Color3.fromRGB(50, 50, 50)
visibleCheckButton.Text = "Visible Check: ON"
visibleCheckButton.Font = Enum.Font.Code
visibleCheckButton.TextColor3 = Color3.fromRGB(255, 255, 255)
visibleCheckButton.TextSize = 12
visibleCheckButton.Parent = mainFrame

local fovVisibleButton = Instance.new("TextButton")
fovVisibleButton.Size = UDim2.new(0, 100, 0, 25)
fovVisibleButton.Position = UDim2.new(1, -110, 0, 295)
fovVisibleButton.BackgroundColor3 = Color3.fromRGB(50, 50, 50)
fovVisibleButton.Text = "FOV Circle: ON"
fovVisibleButton.Font = Enum.Font.Code
fovVisibleButton.TextColor3 = Color3.fromRGB(255, 255, 255)
fovVisibleButton.TextSize = 12
fovVisibleButton.Parent = mainFrame

-- Smoothness Settings
local smoothnessLabel = Instance.new("TextLabel")
smoothnessLabel.Size = UDim2.new(0, 80, 0, 20)
smoothnessLabel.Position = UDim2.new(0, 10, 0, 330)
smoothnessLabel.BackgroundTransparency = 1
smoothnessLabel.Text = "Smooth: " .. AIM_SMOOTHNESS
smoothnessLabel.Font = Enum.Font.Code
smoothnessLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
smoothnessLabel.TextSize = 12
smoothnessLabel.TextXAlignment = Enum.TextXAlignment.Left
smoothnessLabel.Parent = mainFrame

local smoothnessSlider = Instance.new("TextButton")
smoothnessSlider.Size = UDim2.new(0, 140, 0, 10)
smoothnessSlider.Position = UDim2.new(0, 95, 0, 333)
smoothnessSlider.BackgroundColor3 = Color3.fromRGB(60, 60, 60)
smoothnessSlider.Text = ""
smoothnessSlider.Parent = mainFrame

local smoothnessFill = Instance.new("Frame")
smoothnessFill.Size = UDim2.new(AIM_SMOOTHNESS/10, 0, 1, 0)
smoothnessFill.Position = UDim2.new(0, 0, 0, 0)
smoothnessFill.BackgroundColor3 = Color3.fromRGB(255, 0, 0)
smoothnessFill.BorderSizePixel = 0
smoothnessFill.Parent = smoothnessSlider

-- FOV Size Settings
local fovSizeLabel = Instance.new("TextLabel")
fovSizeLabel.Size = UDim2.new(0, 80, 0, 20)
fovSizeLabel.Position = UDim2.new(0, 10, 0, 350)
fovSizeLabel.BackgroundTransparency = 1
fovSizeLabel.Text = "FOV: " .. AIM_FOV_SIZE
fovSizeLabel.Font = Enum.Font.Code
fovSizeLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
fovSizeLabel.TextSize = 12
fovSizeLabel.TextXAlignment = Enum.TextXAlignment.Left
fovSizeLabel.Parent = mainFrame

local fovSizeSlider = Instance.new("TextButton")
fovSizeSlider.Size = UDim2.new(0, 140, 0, 10)
fovSizeSlider.Position = UDim2.new(0, 95, 0, 353)
fovSizeSlider.BackgroundColor3 = Color3.fromRGB(60, 60, 60)
fovSizeSlider.Text = ""
fovSizeSlider.Parent = mainFrame

local fovSizeFill = Instance.new("Frame")
fovSizeFill.Size = UDim2.new(AIM_FOV_SIZE/500, 0, 1, 0)
fovSizeFill.Position = UDim2.new(0, 0, 0, 0)
fovSizeFill.BackgroundColor3 = Color3.fromRGB(255, 0, 0)
fovSizeFill.BorderSizePixel = 0
fovSizeFill.Parent = fovSizeSlider

-- Silent Aim Section
local silentAimTitle = Instance.new("TextLabel")
silentAimTitle.Size = UDim2.new(1, -10, 0, 20)
silentAimTitle.Position = UDim2.new(0, 5, 0, 380)
silentAimTitle.BackgroundTransparency = 1
silentAimTitle.Text = "SILENT AIM:"
silentAimTitle.Font = Enum.Font.Code
silentAimTitle.TextColor3 = Color3.fromRGB(255, 255, 255)
silentAimTitle.TextSize = 14
silentAimTitle.TextXAlignment = Enum.TextXAlignment.Left
silentAimTitle.Parent = mainFrame

-- Silent Aim Toggle Button
local silentAimToggleButton = Instance.new("TextButton")
silentAimToggleButton.Size = UDim2.new(0, 220, 0, 25)
silentAimToggleButton.Position = UDim2.new(0.5, -110, 0, 405)
silentAimToggleButton.BackgroundColor3 = Color3.fromRGB(40, 40, 40)
silentAimToggleButton.Text = "SILENT AIM: OFF (RightAlt)"
silentAimToggleButton.Font = Enum.Font.Code
silentAimToggleButton.TextColor3 = Color3.fromRGB(255, 255, 255)
silentAimToggleButton.TextSize = 12
silentAimToggleButton.Parent = mainFrame

-- Silent Aim Settings Row 1
local silentTeamCheckButton = Instance.new("TextButton")
silentTeamCheckButton.Size = UDim2.new(0, 100, 0, 25)
silentTeamCheckButton.Position = UDim2.new(0, 10, 0, 435)
silentTeamCheckButton.BackgroundColor3 = Color3.fromRGB(50, 50, 50)
silentTeamCheckButton.Text = "Team Check: ON"
silentTeamCheckButton.Font = Enum.Font.Code
silentTeamCheckButton.TextColor3 = Color3.fromRGB(255, 255, 255)
silentTeamCheckButton.TextSize = 12
silentTeamCheckButton.Parent = mainFrame

local silentVisibleCheckButton = Instance.new("TextButton")
silentVisibleCheckButton.Size = UDim2.new(0, 100, 0, 25)
silentVisibleCheckButton.Position = UDim2.new(1, -110, 0, 435)
silentVisibleCheckButton.BackgroundColor3 = Color3.fromRGB(50, 50, 50)
silentVisibleCheckButton.Text = "Visible Check: ON"
silentVisibleCheckButton.Font = Enum.Font.Code
silentVisibleCheckButton.TextColor3 = Color3.fromRGB(255, 255, 255)
silentVisibleCheckButton.TextSize = 12
silentVisibleCheckButton.Parent = mainFrame

-- Silent Aim Settings Row 2
local silentTargetPartButton = Instance.new("TextButton")
silentTargetPartButton.Size = UDim2.new(0, 100, 0, 25)
silentTargetPartButton.Position = UDim2.new(0, 10, 0, 465)
silentTargetPartButton.BackgroundColor3 = Color3.fromRGB(50, 50, 50)
silentTargetPartButton.Text = "Target: Head"
silentTargetPartButton.Font = Enum.Font.Code
silentTargetPartButton.TextColor3 = Color3.fromRGB(255, 255, 255)
silentTargetPartButton.TextSize = 12
silentTargetPartButton.Parent = mainFrame

local silentFOVVisibleButton = Instance.new("TextButton")
silentFOVVisibleButton.Size = UDim2.new(0, 100, 0, 25)
silentFOVVisibleButton.Position = UDim2.new(1, -110, 0, 465)
silentFOVVisibleButton.BackgroundColor3 = Color3.fromRGB(50, 50, 50)
silentFOVVisibleButton.Text = "FOV Circle: OFF"
silentFOVVisibleButton.Font = Enum.Font.Code
silentFOVVisibleButton.TextColor3 = Color3.fromRGB(255, 255, 255)
silentFOVVisibleButton.TextSize = 12
silentFOVVisibleButton.Parent = mainFrame

-- Silent Aim FOV Size Settings
local silentFOVSizeLabel = Instance.new("TextLabel")
silentFOVSizeLabel.Size = UDim2.new(0, 80, 0, 20)
silentFOVSizeLabel.Position = UDim2.new(0, 10, 0, 495)
silentFOVSizeLabel.BackgroundTransparency = 1
silentFOVSizeLabel.Text = "FOV: " .. SILENT_AIM_FOV_SIZE
silentFOVSizeLabel.Font = Enum.Font.Code
silentFOVSizeLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
silentFOVSizeLabel.TextSize = 12
silentFOVSizeLabel.TextXAlignment = Enum.TextXAlignment.Left
silentFOVSizeLabel.Parent = mainFrame

local silentFOVSizeSlider = Instance.new("TextButton")
silentFOVSizeSlider.Size = UDim2.new(0, 140, 0, 10)
silentFOVSizeSlider.Position = UDim2.new(0, 95, 0, 498)
silentFOVSizeSlider.BackgroundColor3 = Color3.fromRGB(60, 60, 60)
silentFOVSizeSlider.Text = ""
silentFOVSizeSlider.Parent = mainFrame

local silentFOVSizeFill = Instance.new("Frame")
silentFOVSizeFill.Size = UDim2.new(SILENT_AIM_FOV_SIZE/500, 0, 1, 0)
silentFOVSizeFill.Position = UDim2.new(0, 0, 0, 0)
silentFOVSizeFill.BackgroundColor3 = Color3.fromRGB(0, 150, 255)
silentFOVSizeFill.BorderSizePixel = 0
silentFOVSizeFill.Parent = silentFOVSizeSlider

-- FOV Circles
local fovCircleGui = Instance.new("ScreenGui")
fovCircleGui.Name = "FOVCircle"
fovCircleGui.ResetOnSpawn = false
fovCircleGui.IgnoreGuiInset = true
fovCircleGui.Parent = LocalPlayer:WaitForChild("PlayerGui")

-- Aimlock FOV Circle (Red)
local aimlockFOVCircle = Instance.new("Frame")
aimlockFOVCircle.Size = UDim2.new(0, AIM_FOV_SIZE, 0, AIM_FOV_SIZE)
aimlockFOVCircle.Position = UDim2.new(0.5, -AIM_FOV_SIZE/2, 0.5, -AIM_FOV_SIZE/2)
aimlockFOVCircle.BackgroundTransparency = 0.9
aimlockFOVCircle.BackgroundColor3 = Color3.fromRGB(255, 0, 0)
aimlockFOVCircle.BorderSizePixel = 1
aimlockFOVCircle.BorderColor3 = Color3.fromRGB(255, 255, 255)
aimlockFOVCircle.Visible = false
aimlockFOVCircle.Parent = fovCircleGui

-- Silent Aim FOV Circle (Blue)
local silentAimFOVCircle = Instance.new("Frame")
silentAimFOVCircle.Size = UDim2.new(0, SILENT_AIM_FOV_SIZE, 0, SILENT_AIM_FOV_SIZE)
silentAimFOVCircle.Position = UDim2.new(0.5, -SILENT_AIM_FOV_SIZE/2, 0.5, -SILENT_AIM_FOV_SIZE/2)
silentAimFOVCircle.BackgroundTransparency = 0.9
silentAimFOVCircle.BackgroundColor3 = Color3.fromRGB(0, 150, 255)
silentAimFOVCircle.BorderSizePixel = 1
silentAimFOVCircle.BorderColor3 = Color3.fromRGB(255, 255, 255)
silentAimFOVCircle.Visible = false
silentAimFOVCircle.Parent = fovCircleGui

--// ESP Functions
local function applyESP(player)
	if player.Character and not player.Character:FindFirstChild("ChavezwareESP") then
		local highlight = Instance.new("Highlight")
		highlight.Name = "ChavezwareESP"
		highlight.FillColor = ESP_FILL_COLOR
		highlight.OutlineColor = ESP_OUTLINE_COLOR
		highlight.FillTransparency = ESP_FILL_TRANSPARENCY
		highlight.OutlineTransparency = ESP_OUTLINE_TRANSPARENCY
		highlight.Parent = player.Character
		highlights[player] = highlight
	end
end

local function removeESP(player)
	if player.Character then
		local highlight = player.Character:FindFirstChild("ChavezwareESP")
		if highlight then
			highlight:Destroy()
		end
	end
	highlights[player] = nil
end

local function updateAllESP()
	for player, highlight in pairs(highlights) do
		if player.Character and highlight then
			highlight.FillColor = ESP_FILL_COLOR
			highlight.OutlineColor = ESP_OUTLINE_COLOR
			highlight.FillTransparency = ESP_FILL_TRANSPARENCY
			highlight.OutlineTransparency = ESP_OUTLINE_TRANSPARENCY
		end
	end
end

local function toggleESP()
	espEnabled = not espEnabled
	toggleButton.Text = espEnabled and "ESP: ON" or "ESP: OFF"

	if espEnabled then
		for _, plr in pairs(Players:GetPlayers()) do
			if plr ~= LocalPlayer then
				applyESP(plr)
			end
		end
	else
		for _, plr in pairs(Players:GetPlayers()) do
			removeESP(plr)
		end
	end
end

--// Aimlock Functions
local function isOnSameTeam(player)
	if not AIM_TEAM_CHECK and not SILENT_AIM_TEAM_CHECK then return false end
	if not LocalPlayer.Team then return false end
	if not player.Team then return false end
	return LocalPlayer.Team == player.Team
end

local function isVisible(targetPart)
	if not AIM_VISIBLE_CHECK and not SILENT_AIM_VISIBLE_CHECK then return true end

	local camera = Workspace.CurrentCamera
	local origin = camera.CFrame.Position
	local target = targetPart.Position

	-- Raycast to check for walls
	local raycastParams = RaycastParams.new()
	raycastParams.FilterType = Enum.RaycastFilterType.Blacklist
	raycastParams.FilterDescendantsInstances = {LocalPlayer.Character, targetPart.Parent}

	local raycastResult = Workspace:Raycast(origin, target - origin, raycastParams)

	-- If raycast hits nothing, target is visible
	return raycastResult == nil
end

local function findNearestTarget(forSilentAim)
	local nearestPlayer = nil
	local nearestDistance = forSilentAim and SILENT_AIM_FOV_SIZE or AIM_FOV_SIZE
	local localChar = LocalPlayer.Character
	local localRoot = localChar and localChar:FindFirstChild("HumanoidRootPart")

	if not localRoot then return nil end

	for _, player in pairs(Players:GetPlayers()) do
		if player ~= LocalPlayer then
			-- Team check
			local teamCheck = forSilentAim and SILENT_AIM_TEAM_CHECK or AIM_TEAM_CHECK
			if teamCheck and isOnSameTeam(player) then
				continue
			end

			local char = player.Character
			if char then
				local targetPartName = forSilentAim and SILENT_AIM_TARGET_PART or AIM_TARGET_PART
				local targetPart = char:FindFirstChild(targetPartName)
				local humanoid = char:FindFirstChild("Humanoid")

				if targetPart and humanoid and humanoid.Health > 0 then
					-- Visible check
					local visibleCheck = forSilentAim and SILENT_AIM_VISIBLE_CHECK or AIM_VISIBLE_CHECK
					if visibleCheck and not isVisible(targetPart) then
						continue
					end

					local screenPoint, onScreen = Camera:WorldToViewportPoint(targetPart.Position)

					if onScreen then
						local mousePos = UIS:GetMouseLocation()
						local distance = (Vector2.new(screenPoint.X, screenPoint.Y) - mousePos).Magnitude

						if distance < nearestDistance then
							nearestDistance = distance
							nearestPlayer = player
						end
					end
				end
			end
		end
	end

	return nearestPlayer
end

local function aimAtTarget()
	if not aimlockEnabled then return end

	currentTarget = findNearestTarget(false)

	if currentTarget and currentTarget.Character then
		local targetPart = currentTarget.Character:FindFirstChild(AIM_TARGET_PART)
		if targetPart then
			local camera = Workspace.CurrentCamera
			local targetPos = targetPart.Position

			-- Smooth aiming
			local currentCFrame = camera.CFrame
			local targetCFrame = CFrame.lookAt(currentCFrame.Position, targetPos)
			local smoothFactor = math.clamp(1 / AIM_SMOOTHNESS, 0.1, 1)

			camera.CFrame = currentCFrame:Lerp(targetCFrame, smoothFactor)
		end
	end
end

--// Trigger Bot Functions
local function triggerBot()
	if not TRIGGER_BOT_ENABLED then return end
	if not aimlockEnabled then return end

	if currentTarget and currentTarget.Character then
		local targetPart = currentTarget.Character:FindFirstChild(AIM_TARGET_PART)
		if targetPart and isVisible(targetPart) then
			-- Instantly click mouse when target is visible and locked
			mouse1click()
		end
	end
end

local function toggleAimlock()
	aimlockEnabled = not aimlockEnabled
	aimlockToggleButton.Text = aimlockEnabled and "AIMLOCK: ON (RightCtrl)" or "AIMLOCK: OFF (RightCtrl)"

	if aimlockEnabled then
		aimlockConnection = RunService.RenderStepped:Connect(aimAtTarget)
		if TRIGGER_BOT_ENABLED then
			triggerBotConnection = RunService.RenderStepped:Connect(triggerBot)
		end
	else
		if aimlockConnection then
			aimlockConnection:Disconnect()
			aimlockConnection = nil
		end
		if triggerBotConnection then
			triggerBotConnection:Disconnect()
			triggerBotConnection = nil
		end
		currentTarget = nil
	end
end

local function toggleTriggerBot()
	TRIGGER_BOT_ENABLED = not TRIGGER_BOT_ENABLED

	triggerBotToggleButton.Text = TRIGGER_BOT_ENABLED and "TRIGGER BOT: ON" or "TRIGGER BOT: OFF"

	if TRIGGER_BOT_ENABLED and aimlockEnabled then
		triggerBotConnection = RunService.RenderStepped:Connect(triggerBot)
	elseif triggerBotConnection then
		triggerBotConnection:Disconnect()
		triggerBotConnection = nil
	end
end

local function cycleTargetPart()
	local parts = {"Head", "Torso", "HumanoidRootPart"}
	local currentIndex = table.find(parts, AIM_TARGET_PART) or 1
	local nextIndex = currentIndex % #parts + 1
	AIM_TARGET_PART = parts[nextIndex]
	targetPartButton.Text = "Target: " .. AIM_TARGET_PART
end

local function toggleTeamCheck()
	AIM_TEAM_CHECK = not AIM_TEAM_CHECK
	teamCheckButton.Text = AIM_TEAM_CHECK and "Team Check: ON" or "Team Check: OFF"
end

local function toggleVisibleCheck()
	AIM_VISIBLE_CHECK = not AIM_VISIBLE_CHECK
	visibleCheckButton.Text = AIM_VISIBLE_CHECK and "Visible Check: ON" or "Visible Check: OFF"
end

local function toggleFOVVisible()
	AIM_FOV_VISIBLE = not AIM_FOV_VISIBLE
	fovVisibleButton.Text = AIM_FOV_VISIBLE and "FOV Circle: ON" or "FOV Circle: OFF"
	updateFOVVisibility()
end

--// Silent Aim Functions
local function calculateSilentAimChance(percentage)
	percentage = math.floor(percentage)
	local chance = math.random(0, 100) / 100
	return chance <= percentage / 100
end

local function getSilentAimTarget()
	if not calculateSilentAimChance(SILENT_AIM_HIT_CHANCE) then
		return nil
	end
	return findNearestTarget(true)
end

local function toggleSilentAim()
	SILENT_AIM_ENABLED = not SILENT_AIM_ENABLED
	silentAimToggleButton.Text = SILENT_AIM_ENABLED and "SILENT AIM: ON (RightAlt)" or "SILENT AIM: OFF (RightAlt)"
	updateFOVVisibility()
end

local function toggleSilentTeamCheck()
	SILENT_AIM_TEAM_CHECK = not SILENT_AIM_TEAM_CHECK
	silentTeamCheckButton.Text = SILENT_AIM_TEAM_CHECK and "Team Check: ON" or "Team Check: OFF"
end

local function toggleSilentVisibleCheck()
	SILENT_AIM_VISIBLE_CHECK = not SILENT_AIM_VISIBLE_CHECK
	silentVisibleCheckButton.Text = SILENT_AIM_VISIBLE_CHECK and "Visible Check: ON" or "Visible Check: OFF"
end

local function cycleSilentTargetPart()
	local parts = {"Head", "Torso", "HumanoidRootPart"}
	local currentIndex = table.find(parts, SILENT_AIM_TARGET_PART) or 1
	local nextIndex = currentIndex % #parts + 1
	SILENT_AIM_TARGET_PART = parts[nextIndex]
	silentTargetPartButton.Text = "Target: " .. SILENT_AIM_TARGET_PART
end

local function toggleSilentFOVVisible()
	SILENT_AIM_FOV_VISIBLE = not SILENT_AIM_FOV_VISIBLE
	silentFOVVisibleButton.Text = SILENT_AIM_FOV_VISIBLE and "FOV Circle: ON" or "FOV Circle: OFF"
	updateFOVVisibility()
end

-- SIMPLE WATERMARK TOGGLE
local function toggleWatermarks()
	watermarksVisible = not watermarksVisible
	watermarkToggleButton.Text = watermarksVisible and "Watermark: ON" or "Watermark: OFF"

	-- Directly set visibility
	watermarkLabel.Visible = watermarksVisible
	versionWatermarkLabel.Visible = watermarksVisible
	smallWatermarkLabel.Visible = watermarksVisible
end

local function updateWatermarkVisibility()
	-- Direct control - no complex conditions
	watermarkLabel.Visible = watermarksVisible
	versionWatermarkLabel.Visible = watermarksVisible
	smallWatermarkLabel.Visible = watermarksVisible
end

local function updateFOVVisibility()
	-- Aimlock FOV (Red)
	aimlockFOVCircle.Visible = AIM_FOV_VISIBLE and not guiVisible

	-- Silent Aim FOV (Blue)
	silentAimFOVCircle.Visible = SILENT_AIM_FOV_VISIBLE and not guiVisible
end

-- Close color picker function
local function closeColorPicker()
	if currentColorPicker then
		currentColorPicker:Destroy()
		currentColorPicker = nil
		currentPickerType = nil
	end
end

-- Simple Color Picker
local function createColorPicker(isFillColor)
	if currentColorPicker and currentPickerType == (isFillColor and "fill" or "outline") then
		closeColorPicker()
		return
	end

	closeColorPicker()

	local colors = {
		{Color3.fromRGB(255, 0, 0), "Red"},
		{Color3.fromRGB(0, 255, 0), "Green"},
		{Color3.fromRGB(0, 0, 255), "Blue"},
		{Color3.fromRGB(255, 255, 0), "Yellow"},
		{Color3.fromRGB(255, 0, 255), "Pink"},
		{Color3.fromRGB(0, 255, 255), "Cyan"},
		{Color3.fromRGB(255, 255, 255), "White"},
		{Color3.fromRGB(0, 0, 0), "Black"},
		{Color3.fromRGB(255, 165, 0), "Orange"},
		{Color3.fromRGB(128, 0, 128), "Purple"}
	}

	local colorPicker = Instance.new("Frame")
	colorPicker.Size = UDim2.new(0, 180, 0, 140)
	colorPicker.Position = UDim2.new(0.5, -90, 0.5, -70)
	colorPicker.BackgroundColor3 = Color3.fromRGB(40, 40, 40)
	colorPicker.BorderColor3 = Color3.fromRGB(255, 0, 0)
	colorPicker.Parent = screenGui

	currentColorPicker = colorPicker
	currentPickerType = isFillColor and "fill" or "outline"

	local title = Instance.new("TextLabel")
	title.Size = UDim2.new(1, 0, 0, 25)
	title.BackgroundColor3 = Color3.fromRGB(255, 0, 0)
	title.Text = isFillColor and "Select Fill Color" or "Select Outline Color"
	title.Font = Enum.Font.Code
	title.TextColor3 = Color3.fromRGB(255, 255, 255)
	title.TextSize = 14
	title.Parent = colorPicker

	for i, colorData in ipairs(colors) do
		local color = colorData[1]
		local row = math.ceil(i / 5)
		local col = (i - 1) % 5 + 1

		local buttonSize = 30
		local spacing = 5
		local totalWidth = (buttonSize * 5) + (spacing * 4)
		local startX = (180 - totalWidth) / 2
		local startY = 30

		local colorBtn = Instance.new("TextButton")
		colorBtn.Size = UDim2.new(0, buttonSize, 0, buttonSize)
		colorBtn.Position = UDim2.new(0, startX + ((col-1) * (buttonSize + spacing)), 0, startY + ((row-1) * (buttonSize + spacing)))
		colorBtn.BackgroundColor3 = color
		colorBtn.Text = ""
		colorBtn.Parent = colorPicker

		colorBtn.MouseButton1Click:Connect(function()
			if isFillColor then
				ESP_FILL_COLOR = color
				fillColorButton.BackgroundColor3 = color
				local brightness = (color.R * 255 * 0.299 + color.G * 255 * 0.587 + color.B * 255 * 0.114)
				fillColorButton.TextColor3 = brightness > 127 and Color3.fromRGB(0, 0, 0) or Color3.fromRGB(255, 255, 255)
			else
				ESP_OUTLINE_COLOR = color
				outlineColorButton.BackgroundColor3 = color
				local brightness = (color.R * 255 * 0.299 + color.G * 255 * 0.587 + color.B * 255 * 0.114)
				outlineColorButton.TextColor3 = brightness > 127 and Color3.fromRGB(0, 0, 0) or Color3.fromRGB(255, 255, 255)
			end
			updateAllESP()
			closeColorPicker()
		end)
	end

	local closeBtn = Instance.new("TextButton")
	closeBtn.Size = UDim2.new(0, 80, 0, 20)
	closeBtn.Position = UDim2.new(0.5, -40, 1, -25)
	closeBtn.BackgroundColor3 = Color3.fromRGB(255, 0, 0)
	closeBtn.Text = "Close"
	closeBtn.Font = Enum.Font.Code
	closeBtn.TextColor3 = Color3.fromRGB(255, 255, 255)
	closeBtn.TextSize = 12
	closeBtn.Parent = colorPicker

	closeBtn.MouseButton1Click:Connect(function()
		closeColorPicker()
	end)
end

-- Slider functionality for aimlock
local function setupAimlockSlider(slider, fill, valueLabel, isSmoothness)
	local dragging = false

	slider.MouseButton1Down:Connect(function()
		dragging = true
	end)

	UIS.InputEnded:Connect(function(input)
		if input.UserInputType == Enum.UserInputType.MouseButton1 then
			dragging = false
		end
	end)

	slider.MouseMoved:Connect(function()
		if dragging then
			local x = UIS:GetMouseLocation().X
			local sliderAbsPos = slider.AbsolutePosition.X
			local sliderSize = slider.AbsoluteSize.X
			local relativeX = math.clamp((x - sliderAbsPos) / sliderSize, 0, 1)

			if isSmoothness then
				AIM_SMOOTHNESS = math.floor(1 + (relativeX * 9))
				valueLabel.Text = "Smooth: " .. AIM_SMOOTHNESS
				fill.Size = UDim2.new(AIM_SMOOTHNESS/10, 0, 1, 0)
			else
				AIM_FOV_SIZE = math.floor(50 + (relativeX * 450))
				valueLabel.Text = "FOV: " .. AIM_FOV_SIZE
				fill.Size = UDim2.new(AIM_FOV_SIZE/500, 0, 1, 0)
				aimlockFOVCircle.Size = UDim2.new(0, AIM_FOV_SIZE, 0, AIM_FOV_SIZE)
				aimlockFOVCircle.Position = UDim2.new(0.5, -AIM_FOV_SIZE/2, 0.5, -AIM_FOV_SIZE/2)
				updateFOVVisibility()
			end
		end
	end)
end

-- Silent Aim FOV Slider functionality
local function setupSilentAimFOVSlider()
	local dragging = false

	silentFOVSizeSlider.MouseButton1Down:Connect(function()
		dragging = true
	end)

	UIS.InputEnded:Connect(function(input)
		if input.UserInputType == Enum.UserInputType.MouseButton1 then
			dragging = false
		end
	end)

	silentFOVSizeSlider.MouseMoved:Connect(function()
		if dragging then
			local x = UIS:GetMouseLocation().X
			local sliderAbsPos = silentFOVSizeSlider.AbsolutePosition.X
			local sliderSize = silentFOVSizeSlider.AbsoluteSize.X
			local relativeX = math.clamp((x - sliderAbsPos) / sliderSize, 0, 1)

			SILENT_AIM_FOV_SIZE = math.floor(50 + (relativeX * 450))
			silentFOVSizeLabel.Text = "FOV: " .. SILENT_AIM_FOV_SIZE
			silentFOVSizeFill.Size = UDim2.new(SILENT_AIM_FOV_SIZE/500, 0, 1, 0)
			silentAimFOVCircle.Size = UDim2.new(0, SILENT_AIM_FOV_SIZE, 0, SILENT_AIM_FOV_SIZE)
			silentAimFOVCircle.Position = UDim2.new(0.5, -SILENT_AIM_FOV_SIZE/2, 0.5, -SILENT_AIM_FOV_SIZE/2)
			updateFOVVisibility()
		end
	end)
end

-- Button Connections
fillColorButton.MouseButton1Click:Connect(function()
	createColorPicker(true)
end)

outlineColorButton.MouseButton1Click:Connect(function()
	createColorPicker(false)
end)

watermarkToggleButton.MouseButton1Click:Connect(toggleWatermarks)
aimlockToggleButton.MouseButton1Click:Connect(toggleAimlock)
triggerBotToggleButton.MouseButton1Click:Connect(toggleTriggerBot)
targetPartButton.MouseButton1Click:Connect(cycleTargetPart)
teamCheckButton.MouseButton1Click:Connect(toggleTeamCheck)
visibleCheckButton.MouseButton1Click:Connect(toggleVisibleCheck)
fovVisibleButton.MouseButton1Click:Connect(toggleFOVVisible)

silentAimToggleButton.MouseButton1Click:Connect(toggleSilentAim)
silentTeamCheckButton.MouseButton1Click:Connect(toggleSilentTeamCheck)
silentVisibleCheckButton.MouseButton1Click:Connect(toggleSilentVisibleCheck)
silentTargetPartButton.MouseButton1Click:Connect(cycleSilentTargetPart)
silentFOVVisibleButton.MouseButton1Click:Connect(toggleSilentFOVVisible)

-- Setup sliders
setupAimlockSlider(smoothnessSlider, smoothnessFill, smoothnessLabel, true)
setupAimlockSlider(fovSizeSlider, fovSizeFill, fovSizeLabel, false)
setupSilentAimFOVSlider()

-- Player Handling
Players.PlayerAdded:Connect(function(player)
	player.CharacterAdded:Connect(function()
		if espEnabled then
			task.wait(0.5)
			applyESP(player)
		end
	end)
end)

Players.PlayerRemoving:Connect(function(player)
	removeESP(player)
end)

LocalPlayer.CharacterAdded:Connect(function()
	if espEnabled then
		task.wait(2)
		for _, player in pairs(Players:GetPlayers()) do
			if player ~= LocalPlayer then
				applyESP(player)
			end
		end
	end
end)

-- Button toggle
toggleButton.MouseButton1Click:Connect(toggleESP)

-- Key handling
UIS.InputBegan:Connect(function(input, gp)
	if gp then return end

	if input.KeyCode == GUI_TOGGLE_KEY then
		guiVisible = not guiVisible
		mainFrame.Visible = guiVisible
		updateFOVVisibility()
		return
	end

	if input.KeyCode == AIMLOCK_KEY then
		toggleAimlock()
		return
	end

	if input.KeyCode == SILENT_AIM_KEY then
		toggleSilentAim()
		return
	end

	for _, key in ipairs(ESP_TOGGLE_KEYS) do
		if input.KeyCode == key then
			toggleESP()
			return
		end
	end
end)

-- Recenter watermarks
RunService.RenderStepped:Connect(function()
	watermarkLabel.Position = UDim2.new(0.5, -100, 0, 10)
	versionWatermarkLabel.Position = UDim2.new(0.5, -100, 0, 40)
	smallWatermarkLabel.Position = UDim2.new(0.5, -100, 0, 60)
end)

-- Initial visibility
updateWatermarkVisibility()
updateFOVVisibility()
