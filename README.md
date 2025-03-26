-- Settings
local gameName = "Mini City"

-- Create the panel
local panel = Instance.new("ScreenGui")
panel.Name = "WeaponDuplicator"
panel.Parent = game.StarterGui

-- Create the weapon buttons
local uziButton = Instance.new("TextButton")
uziButton.Name = "UziButton"
uziButton.Text = "Uzi (1)"
uziButton.Size = UDim2.new(0, 100, 0, 50)
uziButton.Position = UDim2.new(0, 10, 0, 10)
uziButton.Parent = panel

local akButton = Instance.new("TextButton")
akButton.Name = "AkButton"
akButton.Text = "AK (10)"
akButton.Size = UDim2.new(0, 100, 0, 50)
akButton.Position = UDim2.new(0, 120, 0, 10)
akButton.Parent = panel

local parafalButton = Instance.new("TextButton")
parafalButton.Name = "ParafalButton"
parafalButton.Text = "Parafal (100)"
parafalButton.Size = UDim2.new(0, 100, 0, 50)
parafalButton.Position = UDim2.new(0, 230, 0, 10)
parafalButton.Parent = panel

-- Function to duplicate weapon
local function duplicateWeapon(weapon, quantity)
    -- Find the local player
    local player = game.Players.LocalPlayer
    
    -- Find the player's character
    local character = player.Character
    
    -- Check if the character exists
    if character then
        -- Find the player's inventory
        local inventory = player.Backpack
        
        -- Check if the inventory exists
        if inventory then
            -- Duplicate the weapon
            for i = 1, quantity do
                local duplicatedWeapon = Instance.new("Tool")
                duplicatedWeapon.Name = weapon
                duplicatedWeapon.Parent = inventory
            end
        end
    end
end

-- Connect the weapon buttons to the duplicate weapon function
uziButton.MouseButton1Click:Connect(function()
    duplicateWeapon("Uzi", 1)
end)

akButton.MouseButton1Click:Connect(function()
    duplicateWeapon("AK", 10)
end)

parafalButton.MouseButton1Click:Connect(function()
    duplicateWeapon("Parafal", 100)
end)
