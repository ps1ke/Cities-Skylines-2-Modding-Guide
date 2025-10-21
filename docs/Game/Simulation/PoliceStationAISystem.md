# Game.Simulation.PoliceStationAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PoliceStationAISystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_BuildingQuery;
    private Unity.Entities.EntityQuery m_VehiclePrefabQuery;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Prefabs.PoliceCarSelectData m_PoliceCarSelectData;
    private Unity.Entities.EntityArchetype m_PrisonerTransportRequestArchetype;
    private Unity.Entities.EntityArchetype m_PolicePatrolRequestArchetype;
    private Unity.Entities.EntityArchetype m_PoliceEmergencyRequestArchetype;
    private Unity.Entities.EntityArchetype m_HandleRequestArchetype;
    private Unity.Entities.ComponentTypeSet m_ParkedToMovingRemoveTypes;
    private Unity.Entities.ComponentTypeSet m_ParkedToMovingCarAddTypes;
    private Unity.Entities.ComponentTypeSet m_ParkedToMovingAircraftAddTypes;
    private Game.Simulation.PoliceStationAISystem+TypeHandle __TypeHandle;

    public PoliceStationAISystem();

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

- `private Unity.Entities.EntityQuery m_VehiclePrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_VehiclePrefabQuery;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Prefabs.PoliceCarSelectData m_PoliceCarSelectData`  

```csharp
private Game.Prefabs.PoliceCarSelectData m_PoliceCarSelectData;
```

- `private Unity.Entities.EntityArchetype m_PrisonerTransportRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_PrisonerTransportRequestArchetype;
```

- `private Unity.Entities.EntityArchetype m_PolicePatrolRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_PolicePatrolRequestArchetype;
```

- `private Unity.Entities.EntityArchetype m_PoliceEmergencyRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_PoliceEmergencyRequestArchetype;
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

- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingAircraftAddTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_ParkedToMovingAircraftAddTypes;
```

- `private Game.Simulation.PoliceStationAISystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.PoliceStationAISystem+TypeHandle __TypeHandle;
```


## Constructors

- `public PoliceStationAISystem()`  

```csharp
public PoliceStationAISystem();
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

- `Game.Simulation.PoliceStationAISystem+PoliceStationAction`  
- `Game.Simulation.PoliceStationAISystem+PoliceStationTickJob`  
- `Game.Simulation.PoliceStationAISystem+PoliceStationActionJob`  
- `Game.Simulation.PoliceStationAISystem+TypeHandle`  

