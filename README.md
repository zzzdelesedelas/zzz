cloneBtn.MouseButton1Click:Connect(function()
	local playerName = nameBox.Text
	local localPlayer = game.Players.LocalPlayer
	local targetPlayer = game.Players:FindFirstChild(playerName)
	if targetPlayer and targetPlayer.Character then
		local humanoidDesc = targetPlayer.Character:FindFirstChildOfClass("Humanoid"):GetAppliedDescription()
		localPlayer:LoadCharacter()
		task.wait(1)
		localPlayer.Character:FindFirstChildOfClass("Humanoid"):ApplyDescription(humanoidDesc)
		nameBox.Text = "Skin clonada com sucesso!"
	else
		nameBox.Text = "Jogador não encontrado"
	end
end)
