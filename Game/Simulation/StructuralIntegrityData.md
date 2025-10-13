# Game.Simulation.EventHelpers+StructuralIntegrityData

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct StructuralIntegrityData
{
    public Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> m_PrefabSpawnableBuildingData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.DestructibleObjectData> m_PrefabDestructibleObjectData;
    public Game.Prefabs.FireConfigurationData m_FireConfigurationData;

    public StructuralIntegrityData(Unity.Entities.SystemBase system);

    public System.Single GetStructuralIntegrity(Unity.Entities.Entity prefab, System.Boolean isBuilding);
    public System.Void Update(Unity.Entities.SystemBase system, Game.Prefabs.FireConfigurationData fireConfigurationData);
}
```


## Fields

- `public Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> m_PrefabSpawnableBuildingData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> m_PrefabSpawnableBuildingData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.DestructibleObjectData> m_PrefabDestructibleObjectData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.DestructibleObjectData> m_PrefabDestructibleObjectData;
```

- `public Game.Prefabs.FireConfigurationData m_FireConfigurationData`  

```csharp
public Game.Prefabs.FireConfigurationData m_FireConfigurationData;
```


## Constructors

- `public StructuralIntegrityData(Unity.Entities.SystemBase system)`  

```csharp
public StructuralIntegrityData(Unity.Entities.SystemBase system);
```


## Methods

- `public GetStructuralIntegrity(Unity.Entities.Entity prefab, System.Boolean isBuilding) : System.Single`  

```csharp
public System.Single GetStructuralIntegrity(Unity.Entities.Entity prefab, System.Boolean isBuilding);
```

- `public Update(Unity.Entities.SystemBase system, Game.Prefabs.FireConfigurationData fireConfigurationData) : System.Void`  

```csharp
public System.Void Update(Unity.Entities.SystemBase system, Game.Prefabs.FireConfigurationData fireConfigurationData);
```


