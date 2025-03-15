local TextBox = {}
TextBox.__index = TextBox

function TextBox.new(context: table)
	local self = setmetatable(context, TextBox)	
	return self
end

function TextBox:handleTextBox()
	self:autoSizeTextBox()
	
	self.TextBox:GetPropertyChangedSignal("Text"):Connect(function()
		self:autoSizeTextBox()
	end)
	
	self.TextBox.FocusLost:Connect(function(enterPressed)
		if enterPressed then
			self.callback(self.TextBox.Text)
		end
	end)
end
function TextBox:SetText(text: string)
	if self.TextBox then
		self.TextBox.Text = text
	end
end
function TextBox:SetDefault(text: string)
	if self.TextBox then
		self.TextBox.Text = text
	end
end

return TextBox
