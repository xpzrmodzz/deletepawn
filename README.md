-- Référence à ReplicatedStorage
local ReplicatedStorage = game:GetService("ReplicatedStorage")

-- Obtenir la valeur Bool dans ReplicatedStorage pour activer/désactiver le spawn
local spawnEnabled = ReplicatedStorage:FindFirstChild("SpawnEnabled")

-- Obtenir ou créer la valeur Bool pour indiquer si le spawn a été désactivé
local spawnDisabledFlag = ReplicatedStorage:FindFirstChild("SpawnDisabledFlag")
if not spawnDisabledFlag then
    spawnDisabledFlag = Instance.new("BoolValue")
    spawnDisabledFlag.Name = "SpawnDisabledFlag"
    spawnDisabledFlag.Value = false
    spawnDisabledFlag.Parent = ReplicatedStorage
end

-- Fonction pour désactiver le spawn personnalisé
local function disableCustomSpawn()
    if not spawnDisabledFlag.Value then
        if spawnEnabled then
            spawnEnabled.Value = false
            spawnDisabledFlag.Value = true
            print("Le spawn personnalisé a été désactivé.")
        else
            print("La valeur SpawnEnabled n'a pas été trouvée.")
        end
    else
        print("Le spawn personnalisé est déjà désactivé.")
    end
end

-- Fonction pour réactiver le spawn personnalisé
local function enableCustomSpawn()
    if spawnDisabledFlag.Value then
        if spawnEnabled then
            spawnEnabled.Value = true
            spawnDisabledFlag.Value = false
            print("Le spawn personnalisé a été réactivé.")
        else
            print("La valeur SpawnEnabled n'a pas été trouvée.")
        end
    else
        print("Le spawn personnalisé est déjà activé.")
    end
end

-- Appel de la fonction pour désactiver le spawn
disableCustomSpawn()

-- Pour réactiver le spawn à l'avenir, appelez enableCustomSpawn()
