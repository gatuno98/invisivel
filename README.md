-- Variáveis para controle do estado de invisibilidade
local invisível = false
local humano = game.Players.LocalPlayer.Character:WaitForChild("Humanoid") -- Assumindo que o personagem tem um "Humanoid"

-- Função para alternar entre visível e invisível
local function alternarInvisibilidade()
    if invisível then
        -- Tornar o personagem visível
        humano.Transparency = 0
        humano.Parent:FindFirstChild("Head").Transparency = 0  -- Torna a cabeça visível também
        humano.Parent:FindFirstChild("Torso").Transparency = 0
        humano.Parent:FindFirstChild("LeftLeg").Transparency = 0
        humano.Parent:FindFirstChild("RightLeg").Transparency = 0
        humano.Parent:FindFirstChild("LeftArm").Transparency = 0
        humano.Parent:FindFirstChild("RightArm").Transparency = 0
        invisível = false
    else
        -- Tornar o personagem invisível
        humano.Transparency = 1
        humano.Parent:FindFirstChild("Head").Transparency = 1
        humano.Parent:FindFirstChild("Torso").Transparency = 1
        humano.Parent:FindFirstChild("LeftLeg").Transparency = 1
        humano.Parent:FindFirstChild("RightLeg").Transparency = 1
        humano.Parent:FindFirstChild("LeftArm").Transparency = 1
        humano.Parent:FindFirstChild("RightArm").Transparency = 1
        invisível = true
    end
end

-- Função para detectar pressionamento da tecla 'P'
local function onKeyPress(input)
    if input.KeyCode == Enum.KeyCode.P then
        alternarInvisibilidade()
    end
end

-- Conectar a função de pressionamento de tecla ao evento
game:GetService("UserInputService").InputBegan:Connect(onKeyPress)
