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
[Preserve]
	public InputHintsTooltipSystem()
	{
	}
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		ToolBaseSystem activeTool = m_ToolSystem.activeTool;
		InputManager.DeviceType deviceType = InputManager.instance.activeControlScheme switch
		{
			InputManager.ControlScheme.Gamepad => InputManager.DeviceType.Gamepad, 
			InputManager.ControlScheme.KeyboardAndMouse => InputManager.DeviceType.Mouse, 
			_ => InputManager.DeviceType.None, 
		};
		if (m_LastActiveTool != activeTool || m_ControlScheme != InputManager.instance.activeControlScheme)
		{
			m_LastActiveTool = activeTool;
			m_ControlScheme = InputManager.instance.activeControlScheme;
			m_Tooltips.Clear();
			if (m_LastActiveTool != null)
			{
				foreach (IProxyAction action in activeTool.actions)
				{
					if (!(action is UIBaseInputAction.IState state))
					{
						if (action is ProxyAction proxyAction && !m_Tooltips.ContainsKey(proxyAction))
						{
							m_Tooltips.Add(proxyAction, new InputHintTooltip(proxyAction, deviceType));
						}
						continue;
					}
					foreach (ProxyAction action2 in state.actions)
					{
						if (!m_Tooltips.ContainsKey(action2))
						{
							m_Tooltips.Add(action2, new InputHintTooltip(action2, deviceType));
						}
					}
				}
			}
		}
		foreach (var (proxyAction3, inputHintTooltip2) in m_Tooltips)
		{
			if ((proxyAction3.mask & deviceType) != InputManager.DeviceType.None && proxyAction3.displayOverride != null && proxyAction3.displayOverride.priority != -1)
			{
				inputHintTooltip2.Refresh();
				AddMouseTooltip(inputHintTooltip2);
			}
		}
	}
```


