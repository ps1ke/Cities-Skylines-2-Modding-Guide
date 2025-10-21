# Game.Simulation.FindEventAttendantsSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class FindEventAttendantsSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_EventQuery;
    private Unity.Entities.EntityQuery m_HouseholdQuery;
    private Unity.Collections.NativeQueue<Game.Simulation.FindEventAttendantsSystem+Attend> m_AttendQueue;
    private Unity.Entities.EntityArchetype m_MeetingArchetype;
    private Unity.Entities.EntityArchetype m_JournalDataArchetype;
    private Game.Simulation.FindEventAttendantsSystem+TypeHandle __TypeHandle;
    private static const System.UInt32 UPDATE_INTERVAL;

    public FindEventAttendantsSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_EventQuery`  

```csharp
private Unity.Entities.EntityQuery m_EventQuery;
```

- `private Unity.Entities.EntityQuery m_HouseholdQuery`  

```csharp
private Unity.Entities.EntityQuery m_HouseholdQuery;
```

- `private Unity.Collections.NativeQueue<Game.Simulation.FindEventAttendantsSystem+Attend> m_AttendQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.Simulation.FindEventAttendantsSystem+Attend> m_AttendQueue;
```

- `private Unity.Entities.EntityArchetype m_MeetingArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_MeetingArchetype;
```

- `private Unity.Entities.EntityArchetype m_JournalDataArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_JournalDataArchetype;
```

- `private Game.Simulation.FindEventAttendantsSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.FindEventAttendantsSystem+TypeHandle __TypeHandle;
```

- `private static const System.UInt32 UPDATE_INTERVAL`  

```csharp
private static const System.UInt32 UPDATE_INTERVAL;
```


## Constructors

- `public FindEventAttendantsSystem()`  

```csharp
public FindEventAttendantsSystem();
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

- `Game.Simulation.FindEventAttendantsSystem+Attend`  
- `Game.Simulation.FindEventAttendantsSystem+AttendJob`  
- `Game.Simulation.FindEventAttendantsSystem+ConsiderAttendanceJob`  
- `Game.Simulation.FindEventAttendantsSystem+TypeHandle`  

