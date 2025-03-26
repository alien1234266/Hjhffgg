-- Configurações
local jogo = "Lucky Block Battlegrounds"

-- Criar o painel
local painel = Instance.new("ScreenGui")
painel.Name = "HUB Alien"
painel.Parent = game.StarterGui

-- Criar os botões de super blocos
local diamondBlockButton = Instance.new("TextButton")
diamondBlockButton.Name = "DiamondBlockButton"
diamondBlockButton.Text = "Diamond Block (1/10/100)"
diamondBlockButton.Size = UDim2.new(0, 150, 0, 50)
diamondBlockButton.Position = UDim2.new(0, 10, 0, 10)
diamondBlockButton.Parent = painel

local rainbowBlockButton = Instance.new("TextButton")
rainbowBlockButton.Name = "RainbowBlockButton"
rainbowBlockButton.Text = "Rainbow Block (1/10/100)"
rainbowBlockButton.Size = UDim2.new(0, 150, 0, 50)
rainbowBlockButton.Position = UDim2.new(0, 170, 0, 10)
rainbowBlockButton.Parent = painel

local galaxyBlockButton = Instance.new("TextButton")
galaxyBlockButton.Name = "GalaxyBlockButton"
galaxyBlockButton.Text = "Galaxy Block (1/10/100)"
galaxyBlockButton.Size = UDim2.new(0, 150, 0, 50)
galaxyBlockButton.Position = UDim2.new(0, 330, 0, 10)
galaxyBlockButton.Parent = painel

local voidBlockButton = Instance.new("TextButton")
voidBlockButton.Name = "VoidBlockButton"
voidBlockButton.Text = "Void Block (1/10/100)"
voidBlockButton.Size = UDim2.new(0, 150, 0, 50)
voidBlockButton.Position = UDim2.new(0, 490, 0, 10)
voidBlockButton.Parent = painel

-- Função para criar super blocos
local function criarSuperBloco(tipo, quantidade)
    -- Encontre o jogador local
    local jogador = game.Players.LocalPlayer
    
    -- Encontre o caractere do jogador
    local caractere = jogador.Character
    
    -- Verifique se o caractere existe
    if caractere then
        -- Encontre o Humanoid do caractere
        local humanoid = caractere:FindFirstChild("Humanoid")
        
        -- Verifique se o Humanoid existe
        if humanoid then
            -- Crie o super bloco
            for i = 1, quantidade do
                local superBloco = Instance.new("Part")
                superBloco.Name = tipo .. "Block"
                superBloco.Size = Vector3.new(1, 1, 1)
                superBloco.Position = caractere.HumanoidRootPart.Position + Vector3.new(0, 2, 0)
                superBloco.Anchored = true
                superBloco.CanCollide = false
                superBloco.Transparency = 0.5
                superBloco.Parent = game.Workspace
            end
        end
    end
end

-- Conectar os botões de super blocos à função de criar super blocos
diamondBlockButton.MouseButton1Click:Connect(function()
    criarSuperBloco("Diamond", 1)
end)

diamondBlockButton.MouseButton2Click:Connect(function()
    criarSuperBloco("Diamond", 10)
end)

diamondBlockButton.MouseButton3Click:Connect(function()
    criarSuperBloco("Diamond", 100)
end)

rainbowBlockButton.MouseButton1Click:Connect(function()
    criarSuperBloco("Rainbow", 1)
end)

rainbowBlockButton.MouseButton2Click:Connect(function()
    criarSuperBloco("Rainbow", 10)
end)

rainbowBlockButton.MouseButton3Click:Connect(function()
    criarSuperBloco("Rainbow", 100)
end)

galaxyBlockButton.MouseButton1Click:Connect(function()
    criarSuperBloco("Galaxy", 1)
end)

galaxyBlockButton.MouseButton2Click:Connect(function()
    criarSuperBloco("Galaxy", 10)
end)

galaxyBlockButton.MouseButton3Click:Connect(function()
    criarSuperBloco("Galaxy", 100)
end)

voidBlockButton.MouseButton1Click:Connect(function()
    criarSuperBloco("Void", 1)
end)

voidBlockButton.MouseButton2Click:Connect(function()
    criarSuperBloco("Void", 10)
end)

voidBlockButton.MouseButton3Click:Connect(function()
    criarSuperBloco("Void", 100)
end)
