# Game.Tools.ToolApplySystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ToolApplySystem : Game.GameSystemBase
{
    private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
    private Game.Simulation.CitySystem m_CitySystem;
    private Unity.Entities.EntityQuery m_ApplyQuery;
    private Game.Tools.ToolApplySystem+TypeHandle __TypeHandle;

    public ToolApplySystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier`  

```csharp
private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Unity.Entities.EntityQuery m_ApplyQuery`  

```csharp
private Unity.Entities.EntityQuery m_ApplyQuery;
```

- `private Game.Tools.ToolApplySystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.ToolApplySystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ToolApplySystem()`  

```csharp
public ToolApplySystem();
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

- `Game.Tools.ToolApplySystem+ApplyEntitiesJob`  
- `Game.Tools.ToolApplySystem+TypeHandle`  

