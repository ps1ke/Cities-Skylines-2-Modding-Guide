# Game.Simulation.ObsoleteChirpSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ObsoleteChirpSystem : Game.GameSystemBase
{
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_ChirpQuery;
    private Unity.Entities.EntityQuery m_LimitSettingQuery;
    private Game.Simulation.ObsoleteChirpSystem+TypeHandle __TypeHandle;

    public ObsoleteChirpSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
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

- `private Unity.Entities.EntityQuery m_ChirpQuery`  

```csharp
private Unity.Entities.EntityQuery m_ChirpQuery;
```

- `private Unity.Entities.EntityQuery m_LimitSettingQuery`  

```csharp
private Unity.Entities.EntityQuery m_LimitSettingQuery;
```

- `private Game.Simulation.ObsoleteChirpSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.ObsoleteChirpSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ObsoleteChirpSystem()`  

```csharp
public ObsoleteChirpSystem();
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

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Simulation.ObsoleteChirpSystem+ObsoleteChirpJob`  
- `Game.Simulation.ObsoleteChirpSystem+ChirpComparer`  
- `Game.Simulation.ObsoleteChirpSystem+TypeHandle`  

