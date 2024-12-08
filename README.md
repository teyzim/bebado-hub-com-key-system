-- Criação da interface (Hub)
local screenGui = Instance.new("ScreenGui")
screenGui.Name = "KeySystem"
screenGui.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")

local frame = Instance.new("Frame")
frame.Size = UDim2.new(0, 300, 0, 200)
frame.Position = UDim2.new(0.5, -150, 0.5, -100)
frame.BackgroundColor3 = Color3.fromRGB(25, 25, 25)
frame.Parent = screenGui

local titleLabel = Instance.new("TextLabel")
titleLabel.Text = "Teyz Key systen"
titleLabel.Size = UDim2.new(0, 300, 0, 50)
titleLabel.Position = UDim2.new(0, 0, 0, 0)
titleLabel.BackgroundColor3 = Color3.fromRGB(50, 50, 50)
titleLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
titleLabel.TextScaled = true
titleLabel.Parent = frame

local keyTextBox = Instance.new("TextBox")
keyTextBox.Size = UDim2.new(0, 200, 0, 50)
keyTextBox.Position = UDim2.new(0.5, -100, 0, 60)
keyTextBox.PlaceholderText = "Enter your key"
keyTextBox.TextColor3 = Color3.fromRGB(255, 255, 255)
keyTextBox.BackgroundColor3 = Color3.fromRGB(40, 40, 40)
keyTextBox.Parent = frame

local validateButton = Instance.new("TextButton")
validateButton.Size = UDim2.new(0, 200, 0, 50)
validateButton.Position = UDim2.new(0.5, -100, 0, 120)
validateButton.Text = "Validate Key"
validateButton.BackgroundColor3 = Color3.fromRGB(0, 255, 0)
validateButton.TextColor3 = Color3.fromRGB(255, 255, 255)
validateButton.Parent = frame

local copyButton = Instance.new("TextButton")
copyButton.Size = UDim2.new(0, 200, 0, 50)
copyButton.Position = UDim2.new(0.5, -100, 0, 180)
copyButton.Text = "Copy URL"
copyButton.BackgroundColor3 = Color3.fromRGB(0, 0, 255)
copyButton.TextColor3 = Color3.fromRGB(255, 255, 255)
copyButton.Parent = frame

local statusLabel = Instance.new("TextLabel")
statusLabel.Size = UDim2.new(0, 300, 0, 30)
statusLabel.Position = UDim2.new(0, 0, 0, 230)
statusLabel.BackgroundColor3 = Color3.fromRGB(255, 0, 0)
statusLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
statusLabel.TextScaled = true
statusLabel.Text = ""
statusLabel.Parent = screenGui

-- Função para copiar a URL
copyButton.MouseButton1Click:Connect(function()
    setclipboard("https://rekonise.com/teyzhub-key-system-mnzn5")
    statusLabel.Text = "copiado para area de trabalho"
end)

-- Função para validar a chave
validateButton.MouseButton1Click:Connect(function()
    local inputKey = keyTextBox.Text
    local correctKey = "de1ijhedu891hd78"

    if inputKey == correctKey then
        -- Mensagem de confirmação
        statusLabel.Text = "correta rodando o codigo aguarde....."
        
        -- Destruir a interface
        frame:Destroy()

        -- Rodar o código do Pastebin
loadstring(game:HttpGet("https://raw.githubusercontent.com/teyzim/wadsdas/refs/heads/main/README.md", true))()

        -- Notificar que o código está sendo executado
        local successLabel = Instance.new("TextLabel")
        successLabel.Size = UDim2.new(0, 300, 0, 30)
        successLabel.Position = UDim2.new(0, 0, 0, 230)
        successLabel.BackgroundColor3 = Color3.fromRGB(0, 255, 0)
        successLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
        successLabel.TextScaled = true
        successLabel.Text = "Code is Running!"
        successLabel.Parent = screenGui
    else
        -- Mensagem de erro
        statusLabel.Text = "Chave Invalida"
    end
end)
