# Game.Simulation.DeathcareFacilityAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class DeathcareFacilityAISystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_FacilityQuery;
    private Unity.Entities.EntityQuery m_HealthcareVehiclePrefabQuery;
    private Unity.Entities.EntityQuery m_HealthcareSettingsQuery;
    private Unity.Entities.EntityArchetype m_HealthcareRequestArchetype;
    private Unity.Entities.EntityArchetype m_HandleRequestArchetype;
    private Unity.Entities.ComponentTypeSet m_ParkedToMovingRemoveTypes;
    private Unity.Entities.ComponentTypeSet m_ParkedToMovingCarAddTypes;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.BudgetSystem m_BudgetSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Prefabs.HealthcareVehicleSelectData m_HealthcareVehicleSelectData;
    private Game.Simulation.DeathcareFacilityAISystem+TypeHandle __TypeHandle;

    public DeathcareFacilityAISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_FacilityQuery`  

```csharp
private Unity.Entities.EntityQuery m_FacilityQuery;
```

- `private Unity.Entities.EntityQuery m_HealthcareVehiclePrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_HealthcareVehiclePrefabQuery;
```

- `private Unity.Entities.EntityQuery m_HealthcareSettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_HealthcareSettingsQuery;
```

- `private Unity.Entities.EntityArchetype m_HealthcareRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_HealthcareRequestArchetype;
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

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Simulation.BudgetSystem m_BudgetSystem`  

```csharp
private Game.Simulation.BudgetSystem m_BudgetSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Prefabs.HealthcareVehicleSelectData m_HealthcareVehicleSelectData`  

```csharp
private Game.Prefabs.HealthcareVehicleSelectData m_HealthcareVehicleSelectData;
```

- `private Game.Simulation.DeathcareFacilityAISystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.DeathcareFacilityAISystem+TypeHandle __TypeHandle;
```


## Constructors

- `public DeathcareFacilityAISystem()`  

```csharp
public DeathcareFacilityAISystem();
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

- `Game.Simulation.DeathcareFacilityAISystem+DeathcareFacilityAction`  
- `Game.Simulation.DeathcareFacilityAISystem+DeathcareFacilityTickJob`  
- `Game.Simulation.DeathcareFacilityAISystem+DeathcareFacilityActionJob`  
- `Game.Simulation.DeathcareFacilityAISystem+TypeHandle`  

