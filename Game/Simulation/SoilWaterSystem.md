# Game.Simulation.SoilWaterSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.Simulation.CellMapSystem<Game.Simulation.SoilWater>`  
**Implements:** `Colossal.Serialization.Entities.IJobSerializable`, `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SoilWaterSystem : Game.Simulation.CellMapSystem<Game.Simulation.SoilWater>, Colossal.Serialization.Entities.IJobSerializable, Game.Serialization.IPostDeserialize
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Game.Simulation.ClimateSystem m_ClimateSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private UnityEngine.Texture2D m_SoilWaterTexture;
    private Unity.Entities.EntityQuery m_SoilWaterParameterQuery;
    private Unity.Entities.EntityQuery m_FloodQuery;
    private Unity.Entities.EntityQuery m_FloodPrefabQuery;
    private Game.Simulation.SoilWaterSystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_336595330_0;
    public static readonly System.Int32 kTextureSize;
    public static readonly System.Int32 kUpdatesPerDay;
    public static readonly System.Int32 kLoadDistribution;

    public Unity.Mathematics.int2 TextureSize { get; }
    public UnityEngine.Texture soilTexture { get; }

    public SoilWaterSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void CreateFloodCounter();
    public static Unity.Mathematics.float3 GetCellCenter(System.Int32 index);
    public static Game.Simulation.SoilWater GetSoilWater(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.SoilWater> soilWaterMap);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Game.Simulation.ClimateSystem m_ClimateSystem`  

```csharp
private Game.Simulation.ClimateSystem m_ClimateSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private UnityEngine.Texture2D m_SoilWaterTexture`  

```csharp
private UnityEngine.Texture2D m_SoilWaterTexture;
```

- `private Unity.Entities.EntityQuery m_SoilWaterParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_SoilWaterParameterQuery;
```

- `private Unity.Entities.EntityQuery m_FloodQuery`  

```csharp
private Unity.Entities.EntityQuery m_FloodQuery;
```

- `private Unity.Entities.EntityQuery m_FloodPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_FloodPrefabQuery;
```

- `private Game.Simulation.SoilWaterSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.SoilWaterSystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_336595330_0`  

```csharp
private Unity.Entities.EntityQuery __query_336595330_0;
```

- `public static readonly System.Int32 kTextureSize`  

```csharp
public static readonly System.Int32 kTextureSize;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```

- `public static readonly System.Int32 kLoadDistribution`  

```csharp
public static readonly System.Int32 kLoadDistribution;
```


## Properties

- `public Unity.Mathematics.int2 TextureSize { get }`  

```csharp
public Unity.Mathematics.int2 TextureSize { get; }
```

- `public UnityEngine.Texture soilTexture { get }`  

```csharp
public UnityEngine.Texture soilTexture { get; }
```


## Constructors

- `public SoilWaterSystem()`  

```csharp
public SoilWaterSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private CreateFloodCounter() : System.Void`  

```csharp
private System.Void CreateFloodCounter();
```

- `public static GetCellCenter(System.Int32 index) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 GetCellCenter(System.Int32 index);
```

- `public static GetSoilWater(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.SoilWater> soilWaterMap) : Game.Simulation.SoilWater`  

```csharp
public static Game.Simulation.SoilWater GetSoilWater(Unity.Mathematics.float3 position, Unity.Collections.NativeArray<Game.Simulation.SoilWater> soilWaterMap);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
```


## Nested types

- `Game.Simulation.SoilWaterSystem+SoilWaterTickJob`  
- `Game.Simulation.SoilWaterSystem+TypeHandle`  

