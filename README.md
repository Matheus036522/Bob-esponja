local segmentsFolder = workspace.segmentSystem.Segments

for i = 1, 55 do
    local segment = segmentsFolder:FindFirstChild("Segment" .. i)
    
    if segment then
        local folder = segment:FindFirstChild("Folder")

        if folder then
            for _, part in ipairs(folder:GetChildren()) do
                if part:IsA("Part") and part:FindFirstChildOfClass("BoolValue") then
                    part:Destroy()
                end
            end
        end
    end
end
