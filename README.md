loadstring(game:HttpGet("https://raw.githubusercontent.com/EdgeIY/infiniteyield/master/source"))()

local Players = game:GetService("Players")
local player = Players.LocalPlayer
local gui = player:WaitForChild("PlayerGui"):WaitForChild("ScreenGui") or Instance.new("ScreenGui")
gui.Name = "NinjaLegendsGUI"
gui.Parent = player:WaitForChild("PlayerGui")
gui.ResetOnSpawn = false

local mainFrame = Instance.new("Frame")
mainFrame.Size = UDim2.new(0, 350, 0, 450)
mainFrame.Position = UDim2.new(0.5, -175, 0.5, -225)
mainFrame.BackgroundColor3 = Color3.fromRGB(20, 20, 40)
mainFrame.BorderSizePixel = 0
mainFrame.Parent = gui

local corner = Instance.new("UICorner")
corner.CornerRadius = UDim.new(0, 20)
corner.Parent = mainFrame

local title = Instance.new("TextLabel")
title.Size = UDim2.new(1, 0, 0, 60)
title.Position = UDim2.new(0, 0, 0, 0)
title.BackgroundTransparency = 1
title.Text = "🥷 NINJA LEGENDS HACKS"
title.TextColor3 = Color3.fromRGB(255, 215, 0)
title.TextScaled = true
title.Font = Enum.Font.SourceSansBold
title.Parent = mainFrame

local function createButton(text, posY, func)
    local btn = Instance.new("TextButton")
    btn.Size = UDim2.new(0.9, 0, 0, 50)
    btn.Position = UDim2.new(0.05, 0, 0, posY)
    btn.BackgroundColor3 = Color3.fromRGB(50, 20, 100)
    btn.Text = text
    btn.TextColor3 = Color3.fromRGB(255, 255, 255)
    btn.TextScaled = true
    btn.Font = Enum.Font.SourceSansBold
    btn.Parent = mainFrame
    
    local btnCorner = Instance.new("UICorner")
    btnCorner.CornerRadius = UDim.new(0, 15)
    btnCorner.Parent = btn
    
    btn.MouseButton1Click:Connect(func)
end

-- Função 1: Reset dinheiro (Coins/Yen)
createButton("💰 Reset Dinheiro", 80, function()
    local leaderstats = player:FindFirstChild("leaderstats")
    if leaderstats then
        local coins = leaderstats:FindFirstChild("Coins") or leaderstats:FindFirstChild("Yen")
        if coins then coins.Value = 0 end
    end
end)

-- Função 2: Chi 999T (999 Trillion)
createButton("☯️ Chi 999T", 140, function()
    local leaderstats = player:FindFirstChild("leaderstats")
    if leaderstats then
        local chi = leaderstats:FindFirstChild("Chi")
        if chi then chi.Value = 999000000000000 end
    end
end)

-- Função 3: 5T XP Pet
createButton("🐾 5T XP Pet", 200, function()
    local pets = player:FindFirstChild("Pets")
    if pets then
        for _, pet in pairs(pets:GetChildren()) do
            if pet:FindFirstChild("XP") then pet.XP.Value = 5000000000000 end
        end
    end
end)

-- Função 4: 9M Karma Negativo
createButton("🌑 9M Karma Negativo", 260, function()
    local leaderstats = player:FindFirstChild("leaderstats")
    if leaderstats then
        local karma = leaderstats:FindFirstChild("Karma")
        if karma then karma.Value = -9000000 end
    end
end)

-- Função 5: 9M Almas (Souls)
createButton("💀 9M Almas", 320, function()
    local leaderstats = player:FindFirstChild("leaderstats")
    if leaderstats then
        local souls = leaderstats:FindFirstChild("Souls")
        if souls then souls.Value = 9000000 end
    end
end)

-- Botão fechar
local closeBtn = Instance.new("TextButton")
closeBtn.Size = UDim2.new(0, 40, 0, 40)
closeBtn.Position = UDim2.new(1, -45, 0, 5)
closeBtn.BackgroundColor3 = Color3.fromRGB(200, 50, 50)
closeBtn.Text = "✕"
closeBtn.TextColor3 = Color3.fromRGB(255, 255, 255)
closeBtn.TextScaled = true
closeBtn.Font = Enum.Font.SourceSansBold
closeBtn.Parent = mainFrame

local closeCorner = Instance.new("UICorner")
closeCorner.CornerRadius = UDim.new(0, 20)
closeCorner.Parent = closeBtn

closeBtn.MouseButton1Click:Connect(function()
    gui:Destroy()
end)

-- Gradiente anime
local gradient = Instance.new("UIGradient")
gradient.Color = ColorSequence.new{
    ColorSequenceKeypoint.new(0, Color3.fromRGB(100, 50, 200)),
    ColorSequenceKeypoint.new(1, Color3.fromRGB(20, 20, 60))
}
gradient.Parent = mainFrame
