# Game.Areas.AreaResourceSystem

**Assembly:** `Game`  
**Namespace:** `Game.Areas`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AreaResourceSystem : Game.GameSystemBase, Game.Serialization.IPostDeserialize
{
    private Game.Objects.UpdateCollectSystem m_ObjectUpdateCollectSystem;
    private Game.Areas.SearchSystem m_AreaSearchSystem;
    private Game.Objects.SearchSystem m_ObjectSearchSystem;
    private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem;
    private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Unity.Entities.EntityQuery m_UpdatedAreaQuery;
    private Unity.Entities.EntityQuery m_MapTileQuery;
    private Unity.Entities.EntityQuery m_BrushQuery;
    private Unity.Collections.NativeArray<Unity.Mathematics.float2> m_LastCityModifiers;
    private Game.Areas.AreaResourceSystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_596039173_0;

    public AreaResourceSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static System.Single CalculateBuildable(Unity.Mathematics.float3 worldPos, Unity.Mathematics.float2 cellSize, Game.Simulation.WaterSurfaceData m_WaterSurfaceData, Game.Simulation.TerrainHeightData terrainHeightData, Colossal.Mathematics.Bounds1 buildableLandMaxSlope);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
    public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Game.Objects.UpdateCollectSystem m_ObjectUpdateCollectSystem`  

```csharp
private Game.Objects.UpdateCollectSystem m_ObjectUpdateCollectSystem;
```

- `private Game.Areas.SearchSystem m_AreaSearchSystem`  

```csharp
private Game.Areas.SearchSystem m_AreaSearchSystem;
```

- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  

```csharp
private Game.Objects.SearchSystem m_ObjectSearchSystem;
```

- `private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem`  

```csharp
private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem;
```

- `private Game.Simulation.GroundWaterSystem m_GroundWaterSystem`  

```csharp
private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Unity.Entities.EntityQuery m_UpdatedAreaQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedAreaQuery;
```

- `private Unity.Entities.EntityQuery m_MapTileQuery`  

```csharp
private Unity.Entities.EntityQuery m_MapTileQuery;
```

- `private Unity.Entities.EntityQuery m_BrushQuery`  

```csharp
private Unity.Entities.EntityQuery m_BrushQuery;
```

- `private Unity.Collections.NativeArray<Unity.Mathematics.float2> m_LastCityModifiers`  

```csharp
private Unity.Collections.NativeArray<Unity.Mathematics.float2> m_LastCityModifiers;
```

- `private Game.Areas.AreaResourceSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Areas.AreaResourceSystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_596039173_0`  

```csharp
private Unity.Entities.EntityQuery __query_596039173_0;
```


## Constructors

- `public AreaResourceSystem()`  

```csharp
public AreaResourceSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public static CalculateBuildable(Unity.Mathematics.float3 worldPos, Unity.Mathematics.float2 cellSize, Game.Simulation.WaterSurfaceData m_WaterSurfaceData, Game.Simulation.TerrainHeightData terrainHeightData, Colossal.Mathematics.Bounds1 buildableLandMaxSlope) : System.Single`  

```csharp
public static System.Single CalculateBuildable(Unity.Mathematics.float3 worldPos, Unity.Mathematics.float2 cellSize, Game.Simulation.WaterSurfaceData m_WaterSurfaceData, Game.Simulation.TerrainHeightData terrainHeightData, Colossal.Mathematics.Bounds1 buildableLandMaxSlope);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
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

- `Game.Areas.AreaResourceSystem+FindUpdatedAreasWithBrushesJob`  
- `Game.Areas.AreaResourceSystem+FindUpdatedAreasWithBoundsJob`  
- `Game.Areas.AreaResourceSystem+CollectUpdatedAreasJob`  
- `Game.Areas.AreaResourceSystem+UpdateAreaResourcesJob`  
- `Game.Areas.AreaResourceSystem+TreeIterator`  
- `Game.Areas.AreaResourceSystem+WoodIterator`  
- `Game.Areas.AreaResourceSystem+TypeHandle`  

