# Game.UI.Tooltip.TempXPTooltipSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Tooltip.TooltipSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TempXPTooltipSystem : Game.UI.Tooltip.TooltipSystemBase
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Unity.Entities.EntityQuery m_TempQuery;
    private Unity.Entities.EntityQuery m_LockedMilestoneQuery;
    private Game.UI.Tooltip.IntTooltip m_Tooltip;
    private Game.UI.Tooltip.TempXPTooltipSystem+TypeHandle __TypeHandle;

    public TempXPTooltipSystem();

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

- `private Unity.Entities.EntityQuery m_TempQuery`  

```csharp
private Unity.Entities.EntityQuery m_TempQuery;
```

- `private Unity.Entities.EntityQuery m_LockedMilestoneQuery`  

```csharp
private Unity.Entities.EntityQuery m_LockedMilestoneQuery;
```

- `private Game.UI.Tooltip.IntTooltip m_Tooltip`  

```csharp
private Game.UI.Tooltip.IntTooltip m_Tooltip;
```

- `private Game.UI.Tooltip.TempXPTooltipSystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.Tooltip.TempXPTooltipSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TempXPTooltipSystem()`  

```csharp
public TempXPTooltipSystem();
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

- `Game.UI.Tooltip.TempXPTooltipSystem+TypeHandle`  

