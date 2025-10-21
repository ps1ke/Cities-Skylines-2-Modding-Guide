# Game.Triggers.ChirpLikeCountSystem

**Assembly:** `Game`  
**Namespace:** `Game.Triggers`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ChirpLikeCountSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Unity.Entities.EntityQuery m_ChirpQuery;
    private Game.Triggers.ChirpLikeCountSystem+TypeHandle __TypeHandle;

    public ChirpLikeCountSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Unity.Entities.EntityQuery m_ChirpQuery`  

```csharp
private Unity.Entities.EntityQuery m_ChirpQuery;
```

- `private Game.Triggers.ChirpLikeCountSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Triggers.ChirpLikeCountSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ChirpLikeCountSystem()`  

```csharp
public ChirpLikeCountSystem();
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

- `Game.Triggers.ChirpLikeCountSystem+LikeCountUpdateJob`  
- `Game.Triggers.ChirpLikeCountSystem+TypeHandle`  

