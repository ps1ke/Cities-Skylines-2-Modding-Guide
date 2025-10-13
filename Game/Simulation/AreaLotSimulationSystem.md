# Game.Simulation.AreaLotSimulationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AreaLotSimulationSystem : Game.GameSystemBase
{
    private Game.Objects.SearchSystem m_ObjectSearchSystem;
    private Game.Areas.SearchSystem m_AreaSearchSystem;
    private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem;
    private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.WaterSystem m_Watersystem;
    private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_AreaQuery;
    private Unity.Entities.EntityQuery m_ExtractorQuery;
    private Unity.Entities.EntityQuery m_VehiclePrefabQuery;
    private Unity.Entities.EntityQuery m_ExtractorParameterQuery;
    private Game.Prefabs.WorkVehicleSelectData m_WorkVehicleSelectData;
    private Game.Simulation.AreaLotSimulationSystem+TypeHandle __TypeHandle;
    private static const System.UInt32 UPDATE_INTERVAL;

    public AreaLotSimulationSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static System.Int32 GetUnlimitedTotalAmount(System.Int32 used, System.Int32 originalAmount, System.Single mu);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  

```csharp
private Game.Objects.SearchSystem m_ObjectSearchSystem;
```

- `private Game.Areas.SearchSystem m_AreaSearchSystem`  

```csharp
private Game.Areas.SearchSystem m_AreaSearchSystem;
```

- `private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem`  

```csharp
private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem;
```

- `private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem`  

```csharp
private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.WaterSystem m_Watersystem`  

```csharp
private Game.Simulation.WaterSystem m_Watersystem;
```

- `private Game.Simulation.GroundWaterSystem m_GroundWaterSystem`  

```csharp
private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_AreaQuery`  

```csharp
private Unity.Entities.EntityQuery m_AreaQuery;
```

- `private Unity.Entities.EntityQuery m_ExtractorQuery`  

```csharp
private Unity.Entities.EntityQuery m_ExtractorQuery;
```

- `private Unity.Entities.EntityQuery m_VehiclePrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_VehiclePrefabQuery;
```

- `private Unity.Entities.EntityQuery m_ExtractorParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_ExtractorParameterQuery;
```

- `private Game.Prefabs.WorkVehicleSelectData m_WorkVehicleSelectData`  

```csharp
private Game.Prefabs.WorkVehicleSelectData m_WorkVehicleSelectData;
```

- `private Game.Simulation.AreaLotSimulationSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.AreaLotSimulationSystem+TypeHandle __TypeHandle;
```

- `private static const System.UInt32 UPDATE_INTERVAL`  

```csharp
private static const System.UInt32 UPDATE_INTERVAL;
```


## Constructors

- `public AreaLotSimulationSystem()`  

```csharp
public AreaLotSimulationSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public static GetUnlimitedTotalAmount(System.Int32 used, System.Int32 originalAmount, System.Single mu) : System.Int32`  

```csharp
public static System.Int32 GetUnlimitedTotalAmount(System.Int32 used, System.Int32 originalAmount, System.Single mu);
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
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

- `Game.Simulation.AreaLotSimulationSystem+ManageVehiclesJob`  
- `Game.Simulation.AreaLotSimulationSystem+ExtractResourcesJob`  
- `Game.Simulation.AreaLotSimulationSystem+TypeHandle`  

