-- Référence à ReplicatedStorage
local ReplicatedStorage = game:GetService("ReplicatedStorage")

-- Obtenir la valeur Bool dans ReplicatedStorage pour activer/désactiver le spawn
local spawnEnabled = ReplicatedStorage:FindFirstChild("SpawnEnabled")

-- Fonction pour désactiver le spawn personnalisé
local function disableCustomSpawn()
    if spawnEnabled then
        spawnEnabled.Value = false
        print("Le spawn personnalisé a été désactivé.")
    else
        print("La valeur SpawnEnabled n'a pas été trouvée.")
    end
end

-- Appel de la fonction pour désactiver le spawn
disableCustomSpawn()
