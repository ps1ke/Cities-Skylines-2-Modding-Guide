# Game.Events.AddMeetingSystem

**Assembly:** `Game`  
**Namespace:** `Game.Events`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AddMeetingSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier1 m_ModificationBarrier;
    private Unity.Collections.NativeQueue<Game.Events.AddMeetingSystem+AddMeeting> m_MeetingQueue;
    private Unity.Entities.EntityQuery m_LeisureSettingsQuery;
    private Unity.Entities.EntityArchetype m_JournalDataArchetype;
    private Game.Triggers.TriggerSystem m_TriggerSystem;
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Unity.Jobs.JobHandle m_Deps;
    private Game.Events.AddMeetingSystem+TypeHandle __TypeHandle;

    public AddMeetingSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddWriter(Unity.Jobs.JobHandle reader);
    public Unity.Collections.NativeQueue<Game.Events.AddMeetingSystem+AddMeeting> GetMeetingQueue(Unity.Jobs.JobHandle& deps);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationBarrier1 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier1 m_ModificationBarrier;
```

- `private Unity.Collections.NativeQueue<Game.Events.AddMeetingSystem+AddMeeting> m_MeetingQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.Events.AddMeetingSystem+AddMeeting> m_MeetingQueue;
```

- `private Unity.Entities.EntityQuery m_LeisureSettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_LeisureSettingsQuery;
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

- `private Unity.Jobs.JobHandle m_Deps`  

```csharp
private Unity.Jobs.JobHandle m_Deps;
```

- `private Game.Events.AddMeetingSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Events.AddMeetingSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public AddMeetingSystem()`  

```csharp
public AddMeetingSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public AddWriter(Unity.Jobs.JobHandle reader) : System.Void`  

```csharp
public System.Void AddWriter(Unity.Jobs.JobHandle reader);
```

- `public GetMeetingQueue(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeQueue<Game.Events.AddMeetingSystem+AddMeeting>`  

```csharp
public Unity.Collections.NativeQueue<Game.Events.AddMeetingSystem+AddMeeting> GetMeetingQueue(Unity.Jobs.JobHandle& deps);
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

- `Game.Events.AddMeetingSystem+AddMeeting`  
- `Game.Events.AddMeetingSystem+TravelJob`  
- `Game.Events.AddMeetingSystem+TypeHandle`  

