# Game.Citizens.MeetingInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Citizens`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class MeetingInitializeSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier5 m_ModificationBarrier5;
    private Unity.Entities.EntityQuery m_MeetingQuery;
    private Game.Citizens.MeetingInitializeSystem+TypeHandle __TypeHandle;

    public MeetingInitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationBarrier5 m_ModificationBarrier5`  

```csharp
private Game.Common.ModificationBarrier5 m_ModificationBarrier5;
```

- `private Unity.Entities.EntityQuery m_MeetingQuery`  

```csharp
private Unity.Entities.EntityQuery m_MeetingQuery;
```

- `private Game.Citizens.MeetingInitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Citizens.MeetingInitializeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public MeetingInitializeSystem()`  

```csharp
public MeetingInitializeSystem();
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

- `Game.Citizens.MeetingInitializeSystem+InitializeMeetingJob`  
- `Game.Citizens.MeetingInitializeSystem+TypeHandle`  

