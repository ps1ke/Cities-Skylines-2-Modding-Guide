# Game.UI.Tooltip.TooltipSystemBase

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class abstract public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public abstract class TooltipSystemBase : Game.GameSystemBase
{
    private Game.UI.Tooltip.TooltipUISystem m_TooltipUISystem;

    protected TooltipSystemBase();

    protected System.Void AddGroup(Game.UI.Tooltip.TooltipGroup group);
    protected System.Void AddMouseTooltip(Game.UI.Widgets.IWidget tooltip);
    protected virtual System.Void OnCreate();
    protected static Unity.Mathematics.float2 WorldToTooltipPos(UnityEngine.Vector3 worldPos, System.Boolean& onScreen);
}
```


## Fields

- `private Game.UI.Tooltip.TooltipUISystem m_TooltipUISystem`  

```csharp
private Game.UI.Tooltip.TooltipUISystem m_TooltipUISystem;
```


## Constructors

- `protected TooltipSystemBase()`  

```csharp
[Preserve]
	protected TooltipSystemBase()
	{
	}
```


## Methods

- `protected AddGroup(Game.UI.Tooltip.TooltipGroup group) : System.Void`  

```csharp
protected void AddGroup(TooltipGroup group)
	{
		if (group.path != PathSegment.Empty && m_TooltipUISystem.groups.Any((TooltipGroup g) => g.path == group.path))
		{
			UnityEngine.Debug.LogError($"Trying to add tooltip group with duplicate path '{group.path}'");
		}
		else
		{
			m_TooltipUISystem.groups.Add(group);
		}
	}
```

- `protected AddMouseTooltip(Game.UI.Widgets.IWidget tooltip) : System.Void`  

```csharp
protected void AddMouseTooltip(IWidget tooltip)
	{
		if (tooltip.path != PathSegment.Empty && m_TooltipUISystem.mouseGroup.children.Any((IWidget t) => t.path == tooltip.path))
		{
			UnityEngine.Debug.LogError($"Trying to add mouse tooltip with duplicate path '{tooltip.path}'");
		}
		else
		{
			m_TooltipUISystem.mouseGroup.children.Add(tooltip);
		}
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_TooltipUISystem = base.World.GetOrCreateSystemManaged<TooltipUISystem>();
	}
```

- `protected static WorldToTooltipPos(UnityEngine.Vector3 worldPos, System.Boolean& onScreen) : Unity.Mathematics.float2`  

```csharp
protected static float2 WorldToTooltipPos(Vector3 worldPos, out bool onScreen)
	{
		float2 xy = ((float3)Camera.main.WorldToScreenPoint(worldPos)).xy;
		xy.y = (float)Screen.height - xy.y;
		onScreen = xy.x >= 0f && xy.y >= 0f && xy.x <= (float)Screen.width && xy.y <= (float)Screen.height;
		return xy;
	}
```


## Nested types

- `Game.UI.Tooltip.TooltipSystemBase+<>c__DisplayClass2_0`  
- `Game.UI.Tooltip.TooltipSystemBase+<>c__DisplayClass3_0`  

