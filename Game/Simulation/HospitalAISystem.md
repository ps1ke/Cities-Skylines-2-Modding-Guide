# Game.Simulation.HospitalAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class HospitalAISystem : Game.GameSystemBase
{
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.CitySystem m_CitySystem;
    private Unity.Entities.EntityQuery m_HospitalQuery;
    private Unity.Entities.EntityQuery m_HealthcareVehiclePrefabQuery;
    private Unity.Entities.EntityQuery m_HealthcareParameterQuery;
    private Unity.Entities.EntityArchetype m_HealthcareRequestArchetype;
    private Unity.Entities.EntityArchetype m_HandleRequestArchetype;
    private Unity.Entities.EntityArchetype m_ResetTripArchetype;
    private Unity.Entities.ComponentTypeSet m_ParkedToMovingRemoveTypes;
    private Unity.Entities.ComponentTypeSet m_ParkedToMovingCarAddTypes;
    private Unity.Entities.ComponentTypeSet m_ParkedToMovingAircraftAddTypes;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Prefabs.HealthcareVehicleSelectData m_HealthcareVehicleSelectData;
    private Game.Simulation.HospitalAISystem+TypeHandle __TypeHandle;

    public HospitalAISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Unity.Entities.EntityQuery m_HospitalQuery`  

```csharp
private Unity.Entities.EntityQuery m_HospitalQuery;
```

- `private Unity.Entities.EntityQuery m_HealthcareVehiclePrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_HealthcareVehiclePrefabQuery;
```

- `private Unity.Entities.EntityQuery m_HealthcareParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_HealthcareParameterQuery;
```

- `private Unity.Entities.EntityArchetype m_HealthcareRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_HealthcareRequestArchetype;
```

- `private Unity.Entities.EntityArchetype m_HandleRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_HandleRequestArchetype;
```

- `private Unity.Entities.EntityArchetype m_ResetTripArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_ResetTripArchetype;
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

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Prefabs.HealthcareVehicleSelectData m_HealthcareVehicleSelectData`  

```csharp
private Game.Prefabs.HealthcareVehicleSelectData m_HealthcareVehicleSelectData;
```

- `private Game.Simulation.HospitalAISystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.HospitalAISystem+TypeHandle __TypeHandle;
```


## Constructors

- `public HospitalAISystem()`  

```csharp
public HospitalAISystem();
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

- `Game.Simulation.HospitalAISystem+HospitalAction`  
- `Game.Simulation.HospitalAISystem+HospitalTickJob`  
- `Game.Simulation.HospitalAISystem+HospitalActionJob`  
- `Game.Simulation.HospitalAISystem+TypeHandle`  

