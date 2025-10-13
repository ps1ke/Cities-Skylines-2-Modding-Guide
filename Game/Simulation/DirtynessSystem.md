# Game.Simulation.DirtynessSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class DirtynessSystem : Game.GameSystemBase
{
    private Game.Simulation.CitySystem m_CitySystem;
    private Unity.Entities.EntityQuery m_SurfaceQuery;
    private Game.Simulation.DirtynessSystem+TypeHandle __TypeHandle;

    public DirtynessSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Unity.Entities.EntityQuery m_SurfaceQuery`  

```csharp
private Unity.Entities.EntityQuery m_SurfaceQuery;
```

- `private Game.Simulation.DirtynessSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.DirtynessSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public DirtynessSystem()`  

```csharp
public DirtynessSystem();
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

- `Game.Simulation.DirtynessSystem+DirtynessJob`  
- `Game.Simulation.DirtynessSystem+TypeHandle`  

