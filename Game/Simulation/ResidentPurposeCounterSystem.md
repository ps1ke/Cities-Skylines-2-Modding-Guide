# Game.Simulation.ResidentPurposeCounterSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `DebugWatchOnly`, `CompilerGenerated`  

## Code

```csharp
public class ResidentPurposeCounterSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_CreatureQuery;
    private Unity.Collections.NativeArray<System.Int32> m_Results;
    private Game.Simulation.ResidentPurposeCounterSystem+TypeHandle __TypeHandle;

    public ResidentPurposeCounterSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_CreatureQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatureQuery;
```

- `private Unity.Collections.NativeArray<System.Int32> m_Results`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_Results;
```

- `private Game.Simulation.ResidentPurposeCounterSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.ResidentPurposeCounterSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ResidentPurposeCounterSystem()`  

```csharp
public ResidentPurposeCounterSystem();
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

- `Game.Simulation.ResidentPurposeCounterSystem+CountPurpose`  
- `Game.Simulation.ResidentPurposeCounterSystem+PurposeCountJob`  
- `Game.Simulation.ResidentPurposeCounterSystem+TypeHandle`  

