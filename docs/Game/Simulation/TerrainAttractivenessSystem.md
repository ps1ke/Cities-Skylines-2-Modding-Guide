# Game.Simulation.TerrainAttractivenessSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.Simulation.CellMapSystem<Game.Simulation.TerrainAttractiveness>`  
**Implements:** `Colossal.Serialization.Entities.IJobSerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TerrainAttractivenessSystem : Game.Simulation.CellMapSystem<Game.Simulation.TerrainAttractiveness>, Colossal.Serialization.Entities.IJobSerializable
{
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Game.Simulation.ZoneAmbienceSystem m_ZoneAmbienceSystem;
    private Unity.Entities.EntityQuery m_AttractivenessParameterGroup;
    private Unity.Collections.NativeArray<Unity.Mathematics.float3> m_AttractFactorData;
    public static readonly System.Int32 kTextureSize;
    public static readonly System.Int32 kUpdatesPerDay;

    public Unity.Mathematics.int2 TextureSize { get; }

    public TerrainAttractivenessSystem();

    public static System.Single EvaluateAttractiveness(System.Single terrainHeight, Game.Simulation.TerrainAttractiveness attractiveness, Game.Prefabs.AttractivenessParameterData parameters);
    public static System.Single EvaluateAttractiveness(Unity.Mathematics.float3 position, Game.Simulation.CellMapData<Game.Simulation.TerrainAttractiveness> data, Game.Simulation.TerrainHeightData heightData, Game.Prefabs.AttractivenessParameterData parameters, Unity.Collections.NativeArray<System.Int32> factors);
    public static Game.Simulation.TerrainAttractiveness GetAttractiveness(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.TerrainAttractiveness> attractivenessMap);
    public static Unity.Mathematics.float3 GetCellCenter(System.Int32 index);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Game.Simulation.ZoneAmbienceSystem m_ZoneAmbienceSystem`  

```csharp
private Game.Simulation.ZoneAmbienceSystem m_ZoneAmbienceSystem;
```

- `private Unity.Entities.EntityQuery m_AttractivenessParameterGroup`  

```csharp
private Unity.Entities.EntityQuery m_AttractivenessParameterGroup;
```

- `private Unity.Collections.NativeArray<Unity.Mathematics.float3> m_AttractFactorData`  

```csharp
private Unity.Collections.NativeArray<Unity.Mathematics.float3> m_AttractFactorData;
```

- `public static readonly System.Int32 kTextureSize`  

```csharp
public static readonly System.Int32 kTextureSize;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```


## Properties

- `public Unity.Mathematics.int2 TextureSize { get }`  

```csharp
public Unity.Mathematics.int2 TextureSize { get; }
```


## Constructors

- `public TerrainAttractivenessSystem()`  

```csharp
public TerrainAttractivenessSystem();
```


## Methods

- `public static EvaluateAttractiveness(System.Single terrainHeight, Game.Simulation.TerrainAttractiveness attractiveness, Game.Prefabs.AttractivenessParameterData parameters) : System.Single`  

```csharp
public static System.Single EvaluateAttractiveness(System.Single terrainHeight, Game.Simulation.TerrainAttractiveness attractiveness, Game.Prefabs.AttractivenessParameterData parameters);
```

- `public static EvaluateAttractiveness(Unity.Mathematics.float3 position, Game.Simulation.CellMapData<Game.Simulation.TerrainAttractiveness> data, Game.Simulation.TerrainHeightData heightData, Game.Prefabs.AttractivenessParameterData parameters, Unity.Collections.NativeArray<System.Int32> factors) : System.Single`  

```csharp
public static System.Single EvaluateAttractiveness(Unity.Mathematics.float3 position, Game.Simulation.CellMapData<Game.Simulation.TerrainAttractiveness> data, Game.Simulation.TerrainHeightData heightData, Game.Prefabs.AttractivenessParameterData parameters, Unity.Collections.NativeArray<System.Int32> factors);
```

- `public static GetAttractiveness(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.TerrainAttractiveness> attractivenessMap) : Game.Simulation.TerrainAttractiveness`  

```csharp
public static Game.Simulation.TerrainAttractiveness GetAttractiveness(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.TerrainAttractiveness> attractivenessMap);
```

- `public static GetCellCenter(System.Int32 index) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 GetCellCenter(System.Int32 index);
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Simulation.TerrainAttractivenessSystem+TerrainAttractivenessPrepareJob`  
- `Game.Simulation.TerrainAttractivenessSystem+TerrainAttractivenessJob`  

