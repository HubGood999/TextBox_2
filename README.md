
local Paragraph = {}
Paragraph.__index = Paragraph

function Paragraph.new(text, parent)
    local self = setmetatable({}, Paragraph)
    local paragraphLabel = Instance.new("TextLabel")
    paragraphLabel.Size = UDim2.new(1, -10, 0, 40)
    paragraphLabel.BackgroundTransparency = 1
    paragraphLabel.TextWrapped = true
    paragraphLabel.TextXAlignment = Enum.TextXAlignment.Left
    paragraphLabel.TextYAlignment = Enum.TextYAlignment.Top
    paragraphLabel.Font = Enum.Font.SourceSans
    paragraphLabel.TextSize = 16
    paragraphLabel.TextColor3 = Color3.fromRGB(220, 220, 220)
    paragraphLabel.Text = text

    paragraphLabel.Parent = parent or game.CoreGui

    self.Label = paragraphLabel
    return self
end

function Paragraph:SetText(newText)
    self.Label.Text = newText
end

function Paragraph:Destroy()
    if self.Label then
        self.Label:Destroy()
    end
end

return Paragraph
