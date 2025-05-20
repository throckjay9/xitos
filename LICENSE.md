-- LocalScript em StarterPlayerScripts

local Players = game:GetService("Players")
local UserInputService = game:GetService("UserInputService")
local player = Players.LocalPlayer

-- Criar a GUI
local screenGui = Instance.new("ScreenGui")
screenGui.Name = "FF_GUI"
screenGui.ResetOnSpawn = false
screenGui.Parent = player:WaitForChild("PlayerGui")

-- Criar o Frame da GUI
local mainFrame = Instance.new("Frame")
mainFrame.Name = "MainFrame"
mainFrame.Size = UDim2.new(0.3, 0, 0.15, 0)
mainFrame.Position = UDim2.new(0.35, 0, 0.1, 0)
mainFrame.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
mainFrame.BackgroundTransparency = 0.2
mainFrame.BorderSizePixel = 0
mainFrame.Visible = false
mainFrame.Parent = screenGui

-- Título da GUI
local titleLabel = Instance.new("TextLabel")
titleLabel.Name = "TitleLabel"
titleLabel.Size = UDim2.new(1, 0, 1, 0)
titleLabel.Position = UDim2.new(0, 0, 0, 0)
titleLabel.BackgroundTransparency = 1
titleLabel.Text = "🔥 GARENA FREE FIRE MAX GUI 🔥"
titleLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
titleLabel.TextScaled = true
titleLabel.Font = Enum.Font.GothamBold
titleLabel.Parent = mainFrame

-- Lógica para alternar a GUI com tecla Q
local guiVisible = false

UserInputService.InputBegan:Connect(function(input, gameProcessed)
	if not gameProcessed and input.KeyCode == Enum.KeyCode.Q then
		guiVisible = not guiVisible
		mainFrame.Visible = guiVisible
	end
end)
