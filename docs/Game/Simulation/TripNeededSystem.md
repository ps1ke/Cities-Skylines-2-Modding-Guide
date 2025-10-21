# Game.Simulation.TripNeededSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TripNeededSystem : Game.GameSystemBase
{
    private System.Boolean <debugDisableSpawning>k__BackingField;
    private Unity.Entities.EntityQuery m_CitizenGroup;
    private Unity.Entities.EntityQuery m_ResidentPrefabGroup;
    private Unity.Entities.EntityQuery m_CompanyGroup;
    private Unity.Entities.EntityArchetype m_HandleRequestArchetype;
    private Unity.Entities.EntityArchetype m_ResetTripArchetype;
    private Unity.Entities.ComponentTypeSet m_HumanSpawnTypes;
    private Unity.Entities.ComponentTypeSet m_PathfindTypes;
    private Unity.Entities.ComponentTypeSet m_CurrentLaneTypesRelative;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.TimeSystem m_TimeSystem;
    private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem;
    private Game.Debug.DebugWatchDistribution m_DebugPathCostsCar;
    private Game.Debug.DebugWatchDistribution m_DebugPathCostsPublic;
    private Game.Debug.DebugWatchDistribution m_DebugPathCostsPedestrian;
    private Game.Debug.DebugWatchDistribution m_DebugPathCostsCarShort;
    private Game.Debug.DebugWatchDistribution m_DebugPathCostsPublicShort;
    private Game.Debug.DebugWatchDistribution m_DebugPathCostsPedestrianShort;
    private Game.Debug.DebugWatchDistribution m_DebugPublicTransportDuration;
    private Game.Debug.DebugWatchDistribution m_DebugTaxiDuration;
    private Game.Debug.DebugWatchDistribution m_DebugPedestrianDuration;
    private Game.Debug.DebugWatchDistribution m_DebugCarDuration;
    private Game.Debug.DebugWatchDistribution m_DebugPedestrianDurationShort;
    private Game.Simulation.TripNeededSystem+TypeHandle __TypeHandle;
    private static const System.Int32 UPDATE_INTERVAL;

    public System.Boolean debugDisableSpawning { get; set; }

    public TripNeededSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private System.Boolean <debugDisableSpawning>k__BackingField`  

```csharp
private System.Boolean <debugDisableSpawning>k__BackingField;
```

- `private Unity.Entities.EntityQuery m_CitizenGroup`  

```csharp
private Unity.Entities.EntityQuery m_CitizenGroup;
```

- `private Unity.Entities.EntityQuery m_ResidentPrefabGroup`  

```csharp
private Unity.Entities.EntityQuery m_ResidentPrefabGroup;
```

- `private Unity.Entities.EntityQuery m_CompanyGroup`  

```csharp
private Unity.Entities.EntityQuery m_CompanyGroup;
```

- `private Unity.Entities.EntityArchetype m_HandleRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_HandleRequestArchetype;
```

- `private Unity.Entities.EntityArchetype m_ResetTripArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_ResetTripArchetype;
```

- `private Unity.Entities.ComponentTypeSet m_HumanSpawnTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_HumanSpawnTypes;
```

- `private Unity.Entities.ComponentTypeSet m_PathfindTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_PathfindTypes;
```

- `private Unity.Entities.ComponentTypeSet m_CurrentLaneTypesRelative`  

```csharp
private Unity.Entities.ComponentTypeSet m_CurrentLaneTypesRelative;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Simulation.TimeSystem m_TimeSystem`  

```csharp
private Game.Simulation.TimeSystem m_TimeSystem;
```

- `private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem`  

```csharp
private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem`  

```csharp
private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem;
```

- `private Game.Debug.DebugWatchDistribution m_DebugPathCostsCar`  

```csharp
private Game.Debug.DebugWatchDistribution m_DebugPathCostsCar;
```

- `private Game.Debug.DebugWatchDistribution m_DebugPathCostsPublic`  

```csharp
private Game.Debug.DebugWatchDistribution m_DebugPathCostsPublic;
```

- `private Game.Debug.DebugWatchDistribution m_DebugPathCostsPedestrian`  

```csharp
private Game.Debug.DebugWatchDistribution m_DebugPathCostsPedestrian;
```

- `private Game.Debug.DebugWatchDistribution m_DebugPathCostsCarShort`  

```csharp
private Game.Debug.DebugWatchDistribution m_DebugPathCostsCarShort;
```

- `private Game.Debug.DebugWatchDistribution m_DebugPathCostsPublicShort`  

```csharp
private Game.Debug.DebugWatchDistribution m_DebugPathCostsPublicShort;
```

- `private Game.Debug.DebugWatchDistribution m_DebugPathCostsPedestrianShort`  

```csharp
private Game.Debug.DebugWatchDistribution m_DebugPathCostsPedestrianShort;
```

- `private Game.Debug.DebugWatchDistribution m_DebugPublicTransportDuration`  

```csharp
private Game.Debug.DebugWatchDistribution m_DebugPublicTransportDuration;
```

- `private Game.Debug.DebugWatchDistribution m_DebugTaxiDuration`  

```csharp
private Game.Debug.DebugWatchDistribution m_DebugTaxiDuration;
```

- `private Game.Debug.DebugWatchDistribution m_DebugPedestrianDuration`  

```csharp
private Game.Debug.DebugWatchDistribution m_DebugPedestrianDuration;
```

- `private Game.Debug.DebugWatchDistribution m_DebugCarDuration`  

```csharp
private Game.Debug.DebugWatchDistribution m_DebugCarDuration;
```

- `private Game.Debug.DebugWatchDistribution m_DebugPedestrianDurationShort`  

```csharp
private Game.Debug.DebugWatchDistribution m_DebugPedestrianDurationShort;
```

- `private Game.Simulation.TripNeededSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.TripNeededSystem+TypeHandle __TypeHandle;
```

- `private static const System.Int32 UPDATE_INTERVAL`  

```csharp
private static const System.Int32 UPDATE_INTERVAL;
```


## Properties

- `public System.Boolean debugDisableSpawning { get; set }`  

```csharp
public System.Boolean debugDisableSpawning { get; set; }
```


## Constructors

- `public TripNeededSystem()`  

```csharp
public TripNeededSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
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

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Simulation.TripNeededSystem+CompanyJob`  
- `Game.Simulation.TripNeededSystem+AnimalTargetInfo`  
- `Game.Simulation.TripNeededSystem+PetTargetJob`  
- `Game.Simulation.TripNeededSystem+CitizeLeaveJob`  
- `Game.Simulation.TripNeededSystem+CitizenJob`  
- `Game.Simulation.TripNeededSystem+TypeHandle`  

