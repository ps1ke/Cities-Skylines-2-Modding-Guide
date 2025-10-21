# Game.Simulation.MaintenanceDepotAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class MaintenanceDepotAISystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_BuildingQuery;
    private Unity.Entities.EntityQuery m_VehiclePrefabQuery;
    private Unity.Entities.EntityArchetype m_MaintenanceRequestArchetype;
    private Unity.Entities.EntityArchetype m_HandleRequestArchetype;
    private Unity.Entities.ComponentTypeSet m_ParkedToMovingRemoveTypes;
    private Unity.Entities.ComponentTypeSet m_ParkedToMovingCarAddTypes;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Prefabs.MaintenanceVehicleSelectData m_MaintenanceVehicleSelectData;
    private Game.Simulation.MaintenanceDepotAISystem+TypeHandle __TypeHandle;

    public MaintenanceDepotAISystem();

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

- `private Unity.Entities.EntityArchetype m_MaintenanceRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_MaintenanceRequestArchetype;
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

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Prefabs.MaintenanceVehicleSelectData m_MaintenanceVehicleSelectData`  

```csharp
private Game.Prefabs.MaintenanceVehicleSelectData m_MaintenanceVehicleSelectData;
```

- `private Game.Simulation.MaintenanceDepotAISystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.MaintenanceDepotAISystem+TypeHandle __TypeHandle;
```


## Constructors

- `public MaintenanceDepotAISystem()`  

```csharp
public MaintenanceDepotAISystem();
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

- `Game.Simulation.MaintenanceDepotAISystem+MaintenanceDepotAction`  
- `Game.Simulation.MaintenanceDepotAISystem+MaintenanceDepotTickJob`  
- `Game.Simulation.MaintenanceDepotAISystem+MaintenanceDepotActionJob`  
- `Game.Simulation.MaintenanceDepotAISystem+TypeHandle`  

