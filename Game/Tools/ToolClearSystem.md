# Game.Tools.ToolClearSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ToolClearSystem : Game.GameSystemBase
{
    private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
    private Unity.Entities.EntityQuery m_ClearQuery;
    private Game.Tools.ToolClearSystem+TypeHandle __TypeHandle;

    public ToolClearSystem();

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

- `private Unity.Entities.EntityQuery m_ClearQuery`  

```csharp
private Unity.Entities.EntityQuery m_ClearQuery;
```

- `private Game.Tools.ToolClearSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.ToolClearSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ToolClearSystem()`  

```csharp
public ToolClearSystem();
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

- `Game.Tools.ToolClearSystem+ClearEntitiesJob`  
- `Game.Tools.ToolClearSystem+TypeHandle`  

