# Game.UI.Tooltip.InputHintsTooltipSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Tooltip.TooltipSystemBase`  

## Code

```csharp
public class InputHintsTooltipSystem : Game.UI.Tooltip.TooltipSystemBase
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Tools.ToolBaseSystem m_LastActiveTool;
    private Game.Input.InputManager+ControlScheme m_ControlScheme;
    private readonly System.Collections.Generic.Dictionary<Game.Input.ProxyAction, Game.UI.Tooltip.InputHintTooltip> m_Tooltips;

    public InputHintsTooltipSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Tools.ToolBaseSystem m_LastActiveTool`  

```csharp
private Game.Tools.ToolBaseSystem m_LastActiveTool;
```

- `private Game.Input.InputManager+ControlScheme m_ControlScheme`  

```csharp
private Game.Input.InputManager+ControlScheme m_ControlScheme;
```

- `private readonly System.Collections.Generic.Dictionary<Game.Input.ProxyAction, Game.UI.Tooltip.InputHintTooltip> m_Tooltips`  

```csharp
private readonly System.Collections.Generic.Dictionary<Game.Input.ProxyAction, Game.UI.Tooltip.InputHintTooltip> m_Tooltips;
```


## Constructors

- `public InputHintsTooltipSystem()`  

```csharp
public InputHintsTooltipSystem();
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


