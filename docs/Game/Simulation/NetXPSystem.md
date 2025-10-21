# Game.Simulation.NetXPSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class NetXPSystem : Game.GameSystemBase
{
    private Game.Simulation.XPSystem m_XPSystem;
    private Unity.Entities.EntityQuery m_CreatedNetQuery;
    private Unity.Entities.EntityQuery m_DeletedNetQuery;
    private Game.Simulation.NetXPSystem+TypeHandle __TypeHandle;
    private static readonly System.Single kXPRewardLength;

    public NetXPSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.XPSystem m_XPSystem`  

```csharp
private Game.Simulation.XPSystem m_XPSystem;
```

- `private Unity.Entities.EntityQuery m_CreatedNetQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedNetQuery;
```

- `private Unity.Entities.EntityQuery m_DeletedNetQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeletedNetQuery;
```

- `private Game.Simulation.NetXPSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.NetXPSystem+TypeHandle __TypeHandle;
```

- `private static readonly System.Single kXPRewardLength`  

```csharp
private static readonly System.Single kXPRewardLength;
```


## Constructors

- `public NetXPSystem()`  

```csharp
public NetXPSystem();
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

- `Game.Simulation.NetXPSystem+NetXPJob`  
- `Game.Simulation.NetXPSystem+NetXPs`  
- `Game.Simulation.NetXPSystem+TypeHandle`  

