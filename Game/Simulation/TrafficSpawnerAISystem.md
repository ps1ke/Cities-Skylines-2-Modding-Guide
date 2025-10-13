# Game.Simulation.TrafficSpawnerAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TrafficSpawnerAISystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_BuildingQuery;
    private Unity.Entities.EntityQuery m_PersonalCarQuery;
    private Unity.Entities.EntityQuery m_TransportVehicleQuery;
    private Unity.Entities.EntityQuery m_CreaturePrefabQuery;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.ClimateSystem m_ClimateSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityArchetype m_TrafficRequestArchetype;
    private Unity.Entities.EntityArchetype m_HandleRequestArchetype;
    private Unity.Entities.ComponentTypeSet m_CurrentLaneTypesRelative;
    private Game.Prefabs.PersonalCarSelectData m_PersonalCarSelectData;
    private Game.Prefabs.TransportVehicleSelectData m_TransportVehicleSelectData;
    private Game.Simulation.TrafficSpawnerAISystem+TypeHandle __TypeHandle;

    public TrafficSpawnerAISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_BuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingQuery;
```

- `private Unity.Entities.EntityQuery m_PersonalCarQuery`  

```csharp
private Unity.Entities.EntityQuery m_PersonalCarQuery;
```

- `private Unity.Entities.EntityQuery m_TransportVehicleQuery`  

```csharp
private Unity.Entities.EntityQuery m_TransportVehicleQuery;
```

- `private Unity.Entities.EntityQuery m_CreaturePrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreaturePrefabQuery;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.ClimateSystem m_ClimateSystem`  

```csharp
private Game.Simulation.ClimateSystem m_ClimateSystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem`  

```csharp
private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityArchetype m_TrafficRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_TrafficRequestArchetype;
```

- `private Unity.Entities.EntityArchetype m_HandleRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_HandleRequestArchetype;
```

- `private Unity.Entities.ComponentTypeSet m_CurrentLaneTypesRelative`  

```csharp
private Unity.Entities.ComponentTypeSet m_CurrentLaneTypesRelative;
```

- `private Game.Prefabs.PersonalCarSelectData m_PersonalCarSelectData`  

```csharp
private Game.Prefabs.PersonalCarSelectData m_PersonalCarSelectData;
```

- `private Game.Prefabs.TransportVehicleSelectData m_TransportVehicleSelectData`  

```csharp
private Game.Prefabs.TransportVehicleSelectData m_TransportVehicleSelectData;
```

- `private Game.Simulation.TrafficSpawnerAISystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.TrafficSpawnerAISystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TrafficSpawnerAISystem()`  

```csharp
public TrafficSpawnerAISystem();
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

- `Game.Simulation.TrafficSpawnerAISystem+TrafficSpawnerTickJob`  
- `Game.Simulation.TrafficSpawnerAISystem+TypeHandle`  

