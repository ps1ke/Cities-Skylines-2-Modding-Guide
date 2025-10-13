# Game.Simulation.PowerPlantAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PowerPlantAISystem : Game.GameSystemBase
{
    private Game.Simulation.PlanetarySystem m_PlanetarySystem;
    private Game.Simulation.WindSystem m_WindSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
    private Game.Simulation.ClimateSystem m_ClimateSystem;
    private Unity.Entities.EntityQuery m_PowerPlantQuery;
    private Game.Simulation.PowerPlantAISystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_833752410_0;
    public static const System.Int32 MAX_WATERPOWERED_SIZE;

    public PowerPlantAISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static Unity.Mathematics.float2 GetGroundWaterProduction(Game.Prefabs.GroundWaterPoweredData groundWaterData, Unity.Mathematics.float3 position, System.Single efficiency, Unity.Collections.NativeArray<Game.Simulation.GroundWater> groundWaterMap);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
    public static System.Single GetWaterCapacity(Game.Buildings.WaterPowered waterPowered, Game.Prefabs.WaterPoweredData waterData);
    public static Unity.Mathematics.float2 GetWindProduction(Game.Prefabs.WindPoweredData windData, Game.Simulation.Wind wind, System.Single efficiency);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.PlanetarySystem m_PlanetarySystem`  

```csharp
private Game.Simulation.PlanetarySystem m_PlanetarySystem;
```

- `private Game.Simulation.WindSystem m_WindSystem`  

```csharp
private Game.Simulation.WindSystem m_WindSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Game.Simulation.GroundWaterSystem m_GroundWaterSystem`  

```csharp
private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
```

- `private Game.Simulation.ClimateSystem m_ClimateSystem`  

```csharp
private Game.Simulation.ClimateSystem m_ClimateSystem;
```

- `private Unity.Entities.EntityQuery m_PowerPlantQuery`  

```csharp
private Unity.Entities.EntityQuery m_PowerPlantQuery;
```

- `private Game.Simulation.PowerPlantAISystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.PowerPlantAISystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_833752410_0`  

```csharp
private Unity.Entities.EntityQuery __query_833752410_0;
```

- `public static const System.Int32 MAX_WATERPOWERED_SIZE`  

```csharp
public static const System.Int32 MAX_WATERPOWERED_SIZE;
```


## Constructors

- `public PowerPlantAISystem()`  

```csharp
public PowerPlantAISystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public static GetGroundWaterProduction(Game.Prefabs.GroundWaterPoweredData groundWaterData, Unity.Mathematics.float3 position, System.Single efficiency, Unity.Collections.NativeArray<Game.Simulation.GroundWater> groundWaterMap) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 GetGroundWaterProduction(Game.Prefabs.GroundWaterPoweredData groundWaterData, Unity.Mathematics.float3 position, System.Single efficiency, Unity.Collections.NativeArray<Game.Simulation.GroundWater> groundWaterMap);
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
```

- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
```

- `public static GetWaterCapacity(Game.Buildings.WaterPowered waterPowered, Game.Prefabs.WaterPoweredData waterData) : System.Single`  

```csharp
public static System.Single GetWaterCapacity(Game.Buildings.WaterPowered waterPowered, Game.Prefabs.WaterPoweredData waterData);
```

- `public static GetWindProduction(Game.Prefabs.WindPoweredData windData, Game.Simulation.Wind wind, System.Single efficiency) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 GetWindProduction(Game.Prefabs.WindPoweredData windData, Game.Simulation.Wind wind, System.Single efficiency);
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


## Nested types

- `Game.Simulation.PowerPlantAISystem+PowerPlantTickJob`  
- `Game.Simulation.PowerPlantAISystem+TypeHandle`  

