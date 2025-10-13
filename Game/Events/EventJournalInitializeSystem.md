# Game.Events.EventJournalInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Events`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class EventJournalInitializeSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_CreatedEventQuery;
    private Unity.Entities.EntityArchetype m_EventJournalArchetype;
    private Game.Common.ModificationBarrier4 m_ModificationBarrier;
    private Game.Events.EventJournalInitializeSystem+TypeHandle __TypeHandle;

    public EventJournalInitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_CreatedEventQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedEventQuery;
```

- `private Unity.Entities.EntityArchetype m_EventJournalArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_EventJournalArchetype;
```

- `private Game.Common.ModificationBarrier4 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier4 m_ModificationBarrier;
```

- `private Game.Events.EventJournalInitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Events.EventJournalInitializeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public EventJournalInitializeSystem()`  

```csharp
public EventJournalInitializeSystem();
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

- `Game.Events.EventJournalInitializeSystem+InitEventJournalEntriesJob`  
- `Game.Events.EventJournalInitializeSystem+TypeHandle`  

