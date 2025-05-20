-- LocalScript em StarterPlayerScripts

local Players = game:GetService("Players")
local UserInputService = game:GetService("UserInputService")
local RunService = game:GetService("RunService")

local player = Players.LocalPlayer
local camera = workspace.CurrentCamera

-- Criando GUI
local screenGui = Instance.new("ScreenGui")
screenGui.Name = "FF_GUI"
screenGui.ResetOnSpawn = false
screenGui.Parent = player:WaitForChild("PlayerGui")

-- Criando frame principal
local frame = Instance.new("Frame")
frame.Size = UDim2.new(0.25, 0, 0.1, 0)
frame.Position = UDim2.new(0.375, 0, 0.05, 0)
frame.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
frame.BackgroundTransparency = 0.3
frame.BorderSizePixel = 0
frame.Visible = false -- começa oculto
frame.Parent = screenGui

-- Texto
local title = Instance.new("TextLabel")
title.Size = UDim2.new(1, 0, 1, 0)
title.Position = UDim2.new(0, 0, 0, 0)
title.BackgroundTransparency = 1
title.Text = "🔥 GARENA FREE FIRE MAX GUI 🔥"
title.TextScaled = true
title.TextColor3 = Color3.fromRGB(255, 255, 255)
title.Font = Enum.Font.SourceSansBold
title.Parent = frame

-- Toggle da GUI com tecla Q
local guiVisible = false

UserInputService.InputBegan:Connect(function(input, gameProcessed)
	if gameProcessed then return end
	if input.KeyCode == Enum.KeyCode.Q then
		guiVisible = not guiVisible
		frame.Visible = guiVisible
	end
end)

-- Aimbot + ESP simples (opcional, mantém sua lógica anterior se quiser)
