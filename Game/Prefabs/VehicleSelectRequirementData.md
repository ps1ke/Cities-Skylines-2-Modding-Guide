# Game.Prefabs.VehicleSelectRequirementData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct VehicleSelectRequirementData
{
    private Unity.Entities.ComponentTypeHandle<Game.Prefabs.Locked> m_LockedType;
    private Unity.Entities.BufferTypeHandle<Game.Prefabs.ObjectRequirementElement> m_ObjectRequirementType;
    private Unity.Entities.ComponentLookup<Game.Prefabs.ThemeData> m_ThemeData;
    private Unity.Entities.Entity m_DefaultTheme;

    public VehicleSelectRequirementData(Unity.Entities.SystemBase system);

    public System.Boolean CheckRequirements(Game.Prefabs.VehicleSelectRequirementData+Chunk& chunk, System.Int32 index, System.Boolean ignoreTheme);
    public Game.Prefabs.VehicleSelectRequirementData+Chunk GetChunk(Unity.Entities.ArchetypeChunk chunk);
    public System.Void Update(Unity.Entities.SystemBase system, Game.City.CityConfigurationSystem cityConfigurationSystem);
}
```


## Fields

- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.Locked> m_LockedType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Prefabs.Locked> m_LockedType;
```

- `private Unity.Entities.BufferTypeHandle<Game.Prefabs.ObjectRequirementElement> m_ObjectRequirementType`  

```csharp
private Unity.Entities.BufferTypeHandle<Game.Prefabs.ObjectRequirementElement> m_ObjectRequirementType;
```

- `private Unity.Entities.ComponentLookup<Game.Prefabs.ThemeData> m_ThemeData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Prefabs.ThemeData> m_ThemeData;
```

- `private Unity.Entities.Entity m_DefaultTheme`  

```csharp
private Unity.Entities.Entity m_DefaultTheme;
```


## Constructors

- `public VehicleSelectRequirementData(Unity.Entities.SystemBase system)`  

```csharp
public VehicleSelectRequirementData(Unity.Entities.SystemBase system);
```


## Methods

- `public CheckRequirements(Game.Prefabs.VehicleSelectRequirementData+Chunk& chunk, System.Int32 index, System.Boolean ignoreTheme = False) : System.Boolean`  

```csharp
public System.Boolean CheckRequirements(Game.Prefabs.VehicleSelectRequirementData+Chunk& chunk, System.Int32 index, System.Boolean ignoreTheme);
```

- `public GetChunk(Unity.Entities.ArchetypeChunk chunk) : Game.Prefabs.VehicleSelectRequirementData+Chunk`  

```csharp
public Game.Prefabs.VehicleSelectRequirementData+Chunk GetChunk(Unity.Entities.ArchetypeChunk chunk);
```

- `public Update(Unity.Entities.SystemBase system, Game.City.CityConfigurationSystem cityConfigurationSystem) : System.Void`  

```csharp
public System.Void Update(Unity.Entities.SystemBase system, Game.City.CityConfigurationSystem cityConfigurationSystem);
```


## Nested types

- `Game.Prefabs.VehicleSelectRequirementData+Chunk`  

