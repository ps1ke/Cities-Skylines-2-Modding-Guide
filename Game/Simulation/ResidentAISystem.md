# Game.Simulation.ResidentAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ResidentAISystem : Game.GameSystemBase
{
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
    private Game.Simulation.TimeSystem m_TimeSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Simulation.ResidentAISystem+Actions m_Actions;
    private Game.Prefabs.PersonalCarSelectData m_PersonalCarSelectData;
    private Unity.Entities.EntityQuery m_CreatureQuery;
    private Unity.Entities.EntityQuery m_GroupCreatureQuery;
    private Unity.Entities.EntityQuery m_CarPrefabQuery;
    private Unity.Entities.EntityArchetype m_ResetTripArchetype;
    private Unity.Entities.ComponentTypeSet m_ParkedToMovingCarRemoveTypes;
    private Unity.Entities.ComponentTypeSet m_ParkedToMovingCarAddTypes;
    private Unity.Entities.ComponentTypeSet m_ParkedToMovingTrailerAddTypes;
    private Unity.Collections.NativeArray<System.Int32> m_DeletedResidents;
    private Game.Simulation.ResidentAISystem+TypeHandle __TypeHandle;

    public ResidentAISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem`  

```csharp
private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
```

- `private Game.Simulation.TimeSystem m_TimeSystem`  

```csharp
private Game.Simulation.TimeSystem m_TimeSystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Simulation.ResidentAISystem+Actions m_Actions`  

```csharp
private Game.Simulation.ResidentAISystem+Actions m_Actions;
```

- `private Game.Prefabs.PersonalCarSelectData m_PersonalCarSelectData`  

```csharp
private Game.Prefabs.PersonalCarSelectData m_PersonalCarSelectData;
```

- `private Unity.Entities.EntityQuery m_CreatureQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatureQuery;
```

- `private Unity.Entities.EntityQuery m_GroupCreatureQuery`  

```csharp
private Unity.Entities.EntityQuery m_GroupCreatureQuery;
```

- `private Unity.Entities.EntityQuery m_CarPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_CarPrefabQuery;
```

- `private Unity.Entities.EntityArchetype m_ResetTripArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_ResetTripArchetype;
```

- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingCarRemoveTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_ParkedToMovingCarRemoveTypes;
```

- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingCarAddTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_ParkedToMovingCarAddTypes;
```

- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingTrailerAddTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_ParkedToMovingTrailerAddTypes;
```

- `private Unity.Collections.NativeArray<System.Int32> m_DeletedResidents`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_DeletedResidents;
```

- `private Game.Simulation.ResidentAISystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.ResidentAISystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ResidentAISystem()`  

```csharp
public ResidentAISystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
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

- `Game.Simulation.ResidentAISystem+Actions`  
- `Game.Simulation.ResidentAISystem+Boarding`  
- `Game.Simulation.ResidentAISystem+ResidentAction`  
- `Game.Simulation.ResidentAISystem+BoardingType`  
- `Game.Simulation.ResidentAISystem+ResidentActionType`  
- `Game.Simulation.ResidentAISystem+DeletedResidentType`  
- `Game.Simulation.ResidentAISystem+ResidentTickJob`  
- `Game.Simulation.ResidentAISystem+BoardingJob`  
- `Game.Simulation.ResidentAISystem+ResidentActionJob`  
- `Game.Simulation.ResidentAISystem+TypeHandle`  

