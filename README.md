function Section:Paragraph(text)
    local Paragraph = Instance.new("TextLabel")
    Paragraph.Name = "Paragraph"
    Paragraph.Parent = self.Content or self.Section or self.Frame
    Paragraph.BackgroundTransparency = 1
    Paragraph.Size = UDim2.new(1, 0, 0, 20)
    Paragraph.Position = UDim2.new(0, 0, 0, self:CalculateNextElementPosition()) 
    Paragraph.Text = text
    Paragraph.Font = Enum.Font.SourceSans
    Paragraph.TextSize = 14
    Paragraph.TextColor3 = Color3.fromRGB(200, 200, 200)
    Paragraph.TextXAlignment = Enum.TextXAlignment.Left
    Paragraph.TextWrapped = true
    self:UpdateLayout()

    return Paragraph
end
