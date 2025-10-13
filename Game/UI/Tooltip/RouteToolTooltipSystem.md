# Game.UI.Tooltip.RouteToolTooltipSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Tooltip.TooltipSystemBase`  

## Code

```csharp
public class RouteToolTooltipSystem : Game.UI.Tooltip.TooltipSystemBase
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Tools.RouteToolSystem m_RouteTool;
    private Game.UI.ImageSystem m_ImageSystem;
    private Game.UI.NameSystem m_NameSystem;
    private Unity.Entities.EntityQuery m_TempRouteQuery;
    private Unity.Entities.EntityQuery m_TempStopQuery;
    private Game.UI.Tooltip.NameTooltip m_StopName;
    private Game.UI.Tooltip.NameTooltip m_RouteName;

    public RouteToolTooltipSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
    public System.Void TryAddRouteName();
    public System.Void TryAddStopName();
}
```


## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Tools.RouteToolSystem m_RouteTool`  

```csharp
private Game.Tools.RouteToolSystem m_RouteTool;
```

- `private Game.UI.ImageSystem m_ImageSystem`  

```csharp
private Game.UI.ImageSystem m_ImageSystem;
```

- `private Game.UI.NameSystem m_NameSystem`  

```csharp
private Game.UI.NameSystem m_NameSystem;
```

- `private Unity.Entities.EntityQuery m_TempRouteQuery`  

```csharp
private Unity.Entities.EntityQuery m_TempRouteQuery;
```

- `private Unity.Entities.EntityQuery m_TempStopQuery`  

```csharp
private Unity.Entities.EntityQuery m_TempStopQuery;
```

- `private Game.UI.Tooltip.NameTooltip m_StopName`  

```csharp
private Game.UI.Tooltip.NameTooltip m_StopName;
```

- `private Game.UI.Tooltip.NameTooltip m_RouteName`  

```csharp
private Game.UI.Tooltip.NameTooltip m_RouteName;
```


## Constructors

- `public RouteToolTooltipSystem()`  

```csharp
[Preserve]
	public RouteToolTooltipSystem()
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
		m_RouteTool = base.World.GetOrCreateSystemManaged<RouteToolSystem>();
		m_ImageSystem = base.World.GetOrCreateSystemManaged<ImageSystem>();
		m_NameSystem = base.World.GetOrCreateSystemManaged<NameSystem>();
		m_TempRouteQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Temp>(),
				ComponentType.ReadOnly<Route>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Deleted>() }
		});
		m_TempStopQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Temp>(),
				ComponentType.ReadOnly<TransportStop>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Deleted>() }
		});
		m_StopName = new NameTooltip
		{
			path = "routeToolStopName",
			nameBinder = m_NameSystem
		};
		m_RouteName = new NameTooltip
		{
			path = "routeToolRouteName",
			nameBinder = m_NameSystem
		};
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (m_ToolSystem.activeTool == m_RouteTool && m_RouteTool.tooltip != RouteToolSystem.Tooltip.None)
		{
			switch (m_RouteTool.tooltip)
			{
			case RouteToolSystem.Tooltip.CreateRoute:
			case RouteToolSystem.Tooltip.AddWaypoint:
			case RouteToolSystem.Tooltip.CompleteRoute:
				TryAddStopName();
				break;
			case RouteToolSystem.Tooltip.CreateOrModify:
				TryAddStopName();
				TryAddRouteName();
				break;
			case RouteToolSystem.Tooltip.InsertWaypoint:
			case RouteToolSystem.Tooltip.MoveWaypoint:
			case RouteToolSystem.Tooltip.MergeWaypoints:
			case RouteToolSystem.Tooltip.RemoveWaypoint:
				TryAddStopName();
				TryAddRouteName();
				break;
			default:
				TryAddRouteName();
				break;
			}
		}
	}
```

- `public TryAddRouteName() : System.Void`  

```csharp
public void TryAddRouteName()
	{
		if (m_TempRouteQuery.IsEmptyIgnoreFilter)
		{
			return;
		}
		NativeArray<Temp> nativeArray = m_TempRouteQuery.ToComponentDataArray<Temp>(Allocator.TempJob);
		try
		{
			for (int i = 0; i < nativeArray.Length; i++)
			{
				Temp temp = nativeArray[i];
				if (temp.m_Original != Entity.Null)
				{
					AddMouseTooltip(m_RouteName);
					m_RouteName.icon = m_ImageSystem.GetInstanceIcon(temp.m_Original);
					m_RouteName.entity = temp.m_Original;
					break;
				}
			}
		}
		finally
		{
			nativeArray.Dispose();
		}
	}
```

- `public TryAddStopName() : System.Void`  

```csharp
public void TryAddStopName()
	{
		if (m_TempStopQuery.IsEmptyIgnoreFilter)
		{
			return;
		}
		NativeArray<Temp> nativeArray = m_TempStopQuery.ToComponentDataArray<Temp>(Allocator.TempJob);
		try
		{
			for (int i = 0; i < nativeArray.Length; i++)
			{
				Temp temp = nativeArray[i];
				if (temp.m_Original != Entity.Null)
				{
					AddMouseTooltip(m_StopName);
					m_StopName.icon = m_ImageSystem.GetInstanceIcon(temp.m_Original);
					m_StopName.entity = temp.m_Original;
					break;
				}
			}
		}
		finally
		{
			nativeArray.Dispose();
		}
	}
```


