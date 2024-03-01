local Players = game:GetService("Players")
local LocalPlayer = Players.LocalPlayer
local Camera = game.Workspace.CurrentCamera

local function findNearestPlayer()
    local nearestDistance = math.huge
    local nearestPlayer = nil
    
    for _, player in ipairs(Players:GetPlayers()) do
        if player ~= LocalPlayer and player.Character and player.Character:FindFirstChild("HumanoidRootPart") then
            local distance = (player.Character.HumanoidRootPart.Position - LocalPlayer.Character.HumanoidRootPart.Position).magnitude
            if distance < nearestDistance then
                nearestDistance = distance
                nearestPlayer = player
            end
        end
    end
    
    return nearestPlayer
end

local function lockOntoPlayer(player)
    if player then
        local target = player.Character.HumanoidRootPart.Position
        local offset = Vector3.new(0, 3, 0) -- Adjust this offset to position the camera behind the player
        Camera.CFrame = CFrame.new(target + offset, target)
    end
end

while true do
    local nearestPlayer = findNearestPlayer()
    lockOntoPlayer(nearestPlayer)
    wait(0.1) -- Adjust this delay as needed
end
