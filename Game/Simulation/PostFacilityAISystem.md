# Game.Simulation.PostFacilityAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PostFacilityAISystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_BuildingQuery;
    private Unity.Entities.EntityQuery m_PostVanPrefabQuery;
    private Unity.Entities.EntityQuery m_PostConfigurationQuery;
    private Unity.Entities.EntityArchetype m_MailTransferRequestArchetype;
    private Unity.Entities.EntityArchetype m_PostVanRequestArchetype;
    private Unity.Entities.EntityArchetype m_HandleRequestArchetype;
    private Unity.Entities.ComponentTypeSet m_ParkedToMovingRemoveTypes;
    private Unity.Entities.ComponentTypeSet m_ParkedToMovingCarAddTypes;
    private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Prefabs.PostVanSelectData m_PostVanSelectData;
    private Game.Simulation.PostFacilityAISystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kUpdatesPerDay;

    public PostFacilityAISystem();

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

- `private Unity.Entities.EntityQuery m_PostVanPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_PostVanPrefabQuery;
```

- `private Unity.Entities.EntityQuery m_PostConfigurationQuery`  

```csharp
private Unity.Entities.EntityQuery m_PostConfigurationQuery;
```

- `private Unity.Entities.EntityArchetype m_MailTransferRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_MailTransferRequestArchetype;
```

- `private Unity.Entities.EntityArchetype m_PostVanRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_PostVanRequestArchetype;
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

- `private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem`  

```csharp
private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Prefabs.PostVanSelectData m_PostVanSelectData`  

```csharp
private Game.Prefabs.PostVanSelectData m_PostVanSelectData;
```

- `private Game.Simulation.PostFacilityAISystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.PostFacilityAISystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```


## Constructors

- `public PostFacilityAISystem()`  

```csharp
public PostFacilityAISystem();
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

- `Game.Simulation.PostFacilityAISystem+PostFacilityAction`  
- `Game.Simulation.PostFacilityAISystem+PostFacilityTickJob`  
- `Game.Simulation.PostFacilityAISystem+PostFacilityActionJob`  
- `Game.Simulation.PostFacilityAISystem+TypeHandle`  

