local tool = Instance.new("Tool")
tool.Name = "AimFovTool"
tool.RequiresHandle = true

local handle = Instance.new("Part")
handle.Name = "Handle"
handle.Size = Vector3.new(1, 1, 1)
handle.Anchored = false
handle.CanCollide = false
handle.Parent = tool

tool.Parent = game.Players.LocalPlayer.Backpack

local player = game.Players.LocalPlayer
local camera = workspace.CurrentCamera

-- Ajuste o FOV aqui
local defaultFOV = camera.FieldOfView
local aimFOV = 50 -- FOV quando mira

tool.Equipped:Connect(function()
    camera.FieldOfView = aimFOV
end)

tool.Unequipped:Connect(function()
    camera.FieldOfView = defaultFOV
end)
