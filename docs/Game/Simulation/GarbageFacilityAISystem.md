# Game.Simulation.GarbageFacilityAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class GarbageFacilityAISystem : Game.GameSystemBase
{
    private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Prefabs.GarbageTruckSelectData m_GarbageTruckSelectData;
    private Unity.Entities.EntityQuery m_BuildingQuery;
    private Unity.Entities.EntityQuery m_GarbageTruckPrefabQuery;
    private Unity.Entities.EntityQuery m_GarbageSettingsQuery;
    private Unity.Entities.EntityArchetype m_GarbageTransferRequestArchetype;
    private Unity.Entities.EntityArchetype m_GarbageCollectionRequestArchetype;
    private Unity.Entities.EntityArchetype m_HandleRequestArchetype;
    private Unity.Entities.ComponentTypeSet m_ParkedToMovingRemoveTypes;
    private Unity.Entities.ComponentTypeSet m_ParkedToMovingCarAddTypes;
    private Game.Simulation.GarbageFacilityAISystem+TypeHandle __TypeHandle;
    private static const System.Int32 kUpdatesPerDay;

    public GarbageFacilityAISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private static System.Single CalculateGarbageAmountFactor(System.Int32 garbageAmount, System.Int32 garbageCapacity);
    private static System.Single CalculateProcessingRate(System.Single maxProcessingRate, System.Single efficiency, System.Int32 garbageAmount, System.Int32 garbageCapacity);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem`  

```csharp
private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Prefabs.GarbageTruckSelectData m_GarbageTruckSelectData`  

```csharp
private Game.Prefabs.GarbageTruckSelectData m_GarbageTruckSelectData;
```

- `private Unity.Entities.EntityQuery m_BuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingQuery;
```

- `private Unity.Entities.EntityQuery m_GarbageTruckPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_GarbageTruckPrefabQuery;
```

- `private Unity.Entities.EntityQuery m_GarbageSettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_GarbageSettingsQuery;
```

- `private Unity.Entities.EntityArchetype m_GarbageTransferRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_GarbageTransferRequestArchetype;
```

- `private Unity.Entities.EntityArchetype m_GarbageCollectionRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_GarbageCollectionRequestArchetype;
```

- `private Unity.Entities.EntityArchetype m_HandleRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_HandleRequestArchetype;
```

- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingRemoveTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_ParkedToMovingRemoveTypes;
```

- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingCarAddTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_ParkedToMovingCarAddTypes;
```

- `private Game.Simulation.GarbageFacilityAISystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.GarbageFacilityAISystem+TypeHandle __TypeHandle;
```

- `private static const System.Int32 kUpdatesPerDay`  

```csharp
private static const System.Int32 kUpdatesPerDay;
```


## Constructors

- `public GarbageFacilityAISystem()`  

```csharp
public GarbageFacilityAISystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private static CalculateGarbageAmountFactor(System.Int32 garbageAmount, System.Int32 garbageCapacity) : System.Single`  

```csharp
private static System.Single CalculateGarbageAmountFactor(System.Int32 garbageAmount, System.Int32 garbageCapacity);
```

- `private static CalculateProcessingRate(System.Single maxProcessingRate, System.Single efficiency, System.Int32 garbageAmount, System.Int32 garbageCapacity) : System.Single`  

```csharp
private static System.Single CalculateProcessingRate(System.Single maxProcessingRate, System.Single efficiency, System.Int32 garbageAmount, System.Int32 garbageCapacity);
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
```

- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
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

- `Game.Simulation.GarbageFacilityAISystem+GarbageFacilityAction`  
- `Game.Simulation.GarbageFacilityAISystem+GarbageFacilityTickJob`  
- `Game.Simulation.GarbageFacilityAISystem+GarbageFacilityActionJob`  
- `Game.Simulation.GarbageFacilityAISystem+TypeHandle`  

