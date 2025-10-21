# Game.Tools.NodeReductionSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class NodeReductionSystem : Game.GameSystemBase
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Unity.Entities.EntityQuery m_TempNodeQuery;
    private Game.Tools.NodeReductionSystem+TypeHandle __TypeHandle;

    public NodeReductionSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Unity.Entities.EntityQuery m_TempNodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_TempNodeQuery;
```

- `private Game.Tools.NodeReductionSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.NodeReductionSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public NodeReductionSystem()`  

```csharp
public NodeReductionSystem();
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

- `Game.Tools.NodeReductionSystem+FindCandidatesJob`  
- `Game.Tools.NodeReductionSystem+ReductionData`  
- `Game.Tools.NodeReductionSystem+NodeReductionJob`  
- `Game.Tools.NodeReductionSystem+TypeHandle`  

