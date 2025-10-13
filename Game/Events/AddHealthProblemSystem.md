# Game.Events.AddHealthProblemSystem

**Assembly:** `Game`  
**Namespace:** `Game.Events`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AddHealthProblemSystem : Game.GameSystemBase
{
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Game.Common.ModificationBarrier4 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_AddHealthProblemQuery;
    private Unity.Entities.EntityQuery m_HealthcareSettingsQuery;
    private Unity.Entities.EntityQuery m_CitizenQuery;
    private Unity.Entities.EntityArchetype m_JournalDataArchetype;
    private Game.Triggers.TriggerSystem m_TriggerSystem;
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Game.Events.AddHealthProblemSystem+TypeHandle __TypeHandle;

    public AddHealthProblemSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Game.Common.ModificationBarrier4 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier4 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_AddHealthProblemQuery`  

```csharp
private Unity.Entities.EntityQuery m_AddHealthProblemQuery;
```

- `private Unity.Entities.EntityQuery m_HealthcareSettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_HealthcareSettingsQuery;
```

- `private Unity.Entities.EntityQuery m_CitizenQuery`  

```csharp
private Unity.Entities.EntityQuery m_CitizenQuery;
```

- `private Unity.Entities.EntityArchetype m_JournalDataArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_JournalDataArchetype;
```

- `private Game.Triggers.TriggerSystem m_TriggerSystem`  

```csharp
private Game.Triggers.TriggerSystem m_TriggerSystem;
```

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Game.Events.AddHealthProblemSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Events.AddHealthProblemSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public AddHealthProblemSystem()`  

```csharp
public AddHealthProblemSystem();
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

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Events.AddHealthProblemSystem+FindCitizensInBuildingJob`  
- `Game.Events.AddHealthProblemSystem+AddHealthProblemJob`  
- `Game.Events.AddHealthProblemSystem+TypeHandle`  

