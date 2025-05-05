# Kevinhodogral
-- GUI simples e segura para Brookhaven
local ScreenGui = Instance.new("ScreenGui")
local Frame = Instance.new("Frame")
local AvatarBtn = Instance.new("TextButton")
local MusicBtn = Instance.new("TextButton")

ScreenGui.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")
ScreenGui.Name = "FunGui"

Frame.Size = UDim2.new(0, 200, 0, 120)
Frame.Position = UDim2.new(0, 50, 0, 100)
Frame.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
Frame.Parent = ScreenGui

AvatarBtn.Size = UDim2.new(1, -20, 0, 40)
AvatarBtn.Position = UDim2.new(0, 10, 0, 10)
AvatarBtn.Text = "Copiar avatar"
AvatarBtn.Parent = Frame

MusicBtn.Size = UDim2.new(1, -20, 0, 40)
MusicBtn.Position = UDim2.new(0, 10, 0, 60)
MusicBtn.Text = "Tocar música"
MusicBtn.Parent = Frame

-- Função: copiar avatar do player escolhido
AvatarBtn.MouseButton1Click:Connect(function()
    local targetName = game.Players:GetPlayers()[2].Name -- Muda para quem você quiser
    local target = game.Players:FindFirstChild(targetName)
    if target then
        game.Players.LocalPlayer.CharacterAppearance = target.CharacterAppearance
        game.Players.LocalPlayer:LoadCharacter()
    end
end)

-- Função: tocar música (só funciona se tiver boombox)
MusicBtn.MouseButton1Click:Connect(function()
    local sound = Instance.new("Sound", game.Workspace)
    sound.SoundId = "rbxassetid://1843524017" -- Exemplo: beat estourado
    sound.Volume = 10
    sound:Play()
end)
