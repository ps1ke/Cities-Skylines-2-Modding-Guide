# Game.UI.Tooltip.RaycastNotificationTooltipSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Tooltip.TooltipSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class RaycastNotificationTooltipSystem : Game.UI.Tooltip.TooltipSystemBase
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Tools.DefaultToolSystem m_DefaultTool;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.UI.NameSystem m_NameSystem;
    private Game.UI.ImageSystem m_ImageSystem;
    private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem;
    private Unity.Entities.EntityQuery m_ConfigurationQuery;
    private Game.UI.Tooltip.NotificationTooltip m_Tooltip;

    public RaycastNotificationTooltipSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Tools.DefaultToolSystem m_DefaultTool`  

```csharp
private Game.Tools.DefaultToolSystem m_DefaultTool;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.UI.NameSystem m_NameSystem`  

```csharp
private Game.UI.NameSystem m_NameSystem;
```

- `private Game.UI.ImageSystem m_ImageSystem`  

```csharp
private Game.UI.ImageSystem m_ImageSystem;
```

- `private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem`  

```csharp
private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem;
```

- `private Unity.Entities.EntityQuery m_ConfigurationQuery`  

```csharp
private Unity.Entities.EntityQuery m_ConfigurationQuery;
```

- `private Game.UI.Tooltip.NotificationTooltip m_Tooltip`  

```csharp
private Game.UI.Tooltip.NotificationTooltip m_Tooltip;
```


## Constructors

- `public RaycastNotificationTooltipSystem()`  

```csharp
[Preserve]
	public RaycastNotificationTooltipSystem()
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
		m_DefaultTool = base.World.GetOrCreateSystemManaged<DefaultToolSystem>();
		m_NameSystem = base.World.GetOrCreateSystemManaged<NameSystem>();
		m_ImageSystem = base.World.GetOrCreateSystemManaged<ImageSystem>();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_ToolRaycastSystem = base.World.GetOrCreateSystemManaged<ToolRaycastSystem>();
		m_ConfigurationQuery = GetEntityQuery(ComponentType.ReadOnly<IconConfigurationData>());
		RequireForUpdate(m_ConfigurationQuery);
		m_Tooltip = new NotificationTooltip
		{
			path = "raycastNotification",
			verbose = true
		};
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (m_ToolSystem.activeTool == m_DefaultTool && m_ToolRaycastSystem.GetRaycastResult(out var result) && base.EntityManager.TryGetComponent<Icon>(result.m_Owner, out var component) && base.EntityManager.TryGetComponent<PrefabRef>(result.m_Owner, out var component2))
		{
			IconConfigurationData singleton = m_ConfigurationQuery.GetSingleton<IconConfigurationData>();
			if (!(component2.m_Prefab == singleton.m_SelectedMarker) && !(component2.m_Prefab == singleton.m_FollowedMarker))
			{
				m_Tooltip.name = (m_PrefabSystem.TryGetPrefab<NotificationIconPrefab>(component2, out var prefab) ? prefab.name : m_PrefabSystem.GetObsoleteID(component2.m_Prefab).GetName());
				m_Tooltip.color = NotificationTooltip.GetColor(component.m_Priority);
				AddMouseTooltip(m_Tooltip);
			}
		}
	}
```


