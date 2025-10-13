# Game.Tools.ToolRaycastSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class ToolRaycastSystem : Game.GameSystemBase
{
    private Game.Common.RaycastFlags <raycastFlags>k__BackingField;
    private Game.Common.TypeMask <typeMask>k__BackingField;
    private Game.Common.CollisionMask <collisionMask>k__BackingField;
    private Game.Net.Layer <netLayerMask>k__BackingField;
    private Game.Areas.AreaTypeMask <areaTypeMask>k__BackingField;
    private Game.Routes.RouteType <routeType>k__BackingField;
    private Game.Prefabs.TransportType <transportType>k__BackingField;
    private Game.Notifications.IconLayerMask <iconLayerMask>k__BackingField;
    private Game.Net.UtilityTypes <utilityTypeMask>k__BackingField;
    private Unity.Mathematics.float3 <rayOffset>k__BackingField;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Common.RaycastSystem m_RaycastSystem;
    private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;

    public Game.Common.RaycastFlags raycastFlags { get; set; }
    public Game.Common.TypeMask typeMask { get; set; }
    public Game.Common.CollisionMask collisionMask { get; set; }
    public Game.Net.Layer netLayerMask { get; set; }
    public Game.Areas.AreaTypeMask areaTypeMask { get; set; }
    public Game.Routes.RouteType routeType { get; set; }
    public Game.Prefabs.TransportType transportType { get; set; }
    public Game.Notifications.IconLayerMask iconLayerMask { get; set; }
    public Game.Net.UtilityTypes utilityTypeMask { get; set; }
    public Unity.Mathematics.float3 rayOffset { get; set; }

    public ToolRaycastSystem();

    public static Colossal.Mathematics.Line3+Segment CalculateRaycastLine(UnityEngine.Camera mainCamera);
    public System.Boolean GetRaycastResult(Game.Common.RaycastResult& result);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.RaycastFlags <raycastFlags>k__BackingField`  

```csharp
private Game.Common.RaycastFlags <raycastFlags>k__BackingField;
```

- `private Game.Common.TypeMask <typeMask>k__BackingField`  

```csharp
private Game.Common.TypeMask <typeMask>k__BackingField;
```

- `private Game.Common.CollisionMask <collisionMask>k__BackingField`  

```csharp
private Game.Common.CollisionMask <collisionMask>k__BackingField;
```

- `private Game.Net.Layer <netLayerMask>k__BackingField`  

```csharp
private Game.Net.Layer <netLayerMask>k__BackingField;
```

- `private Game.Areas.AreaTypeMask <areaTypeMask>k__BackingField`  

```csharp
private Game.Areas.AreaTypeMask <areaTypeMask>k__BackingField;
```

- `private Game.Routes.RouteType <routeType>k__BackingField`  

```csharp
private Game.Routes.RouteType <routeType>k__BackingField;
```

- `private Game.Prefabs.TransportType <transportType>k__BackingField`  

```csharp
private Game.Prefabs.TransportType <transportType>k__BackingField;
```

- `private Game.Notifications.IconLayerMask <iconLayerMask>k__BackingField`  

```csharp
private Game.Notifications.IconLayerMask <iconLayerMask>k__BackingField;
```

- `private Game.Net.UtilityTypes <utilityTypeMask>k__BackingField`  

```csharp
private Game.Net.UtilityTypes <utilityTypeMask>k__BackingField;
```

- `private Unity.Mathematics.float3 <rayOffset>k__BackingField`  

```csharp
private Unity.Mathematics.float3 <rayOffset>k__BackingField;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Common.RaycastSystem m_RaycastSystem`  

```csharp
private Game.Common.RaycastSystem m_RaycastSystem;
```

- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  

```csharp
private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
```


## Properties

- `public Game.Common.RaycastFlags raycastFlags { get; set }`  

```csharp
public Game.Common.RaycastFlags raycastFlags { get; set; }
```

- `public Game.Common.TypeMask typeMask { get; set }`  

```csharp
public Game.Common.TypeMask typeMask { get; set; }
```

- `public Game.Common.CollisionMask collisionMask { get; set }`  

```csharp
public Game.Common.CollisionMask collisionMask { get; set; }
```

- `public Game.Net.Layer netLayerMask { get; set }`  

```csharp
public Game.Net.Layer netLayerMask { get; set; }
```

- `public Game.Areas.AreaTypeMask areaTypeMask { get; set }`  

```csharp
public Game.Areas.AreaTypeMask areaTypeMask { get; set; }
```

- `public Game.Routes.RouteType routeType { get; set }`  

```csharp
public Game.Routes.RouteType routeType { get; set; }
```

- `public Game.Prefabs.TransportType transportType { get; set }`  

```csharp
public Game.Prefabs.TransportType transportType { get; set; }
```

- `public Game.Notifications.IconLayerMask iconLayerMask { get; set }`  

```csharp
public Game.Notifications.IconLayerMask iconLayerMask { get; set; }
```

- `public Game.Net.UtilityTypes utilityTypeMask { get; set }`  

```csharp
public Game.Net.UtilityTypes utilityTypeMask { get; set; }
```

- `public Unity.Mathematics.float3 rayOffset { get; set }`  

```csharp
public Unity.Mathematics.float3 rayOffset { get; set; }
```


## Constructors

- `public ToolRaycastSystem()`  

```csharp
[Preserve]
	public ToolRaycastSystem()
	{
	}
```


## Methods

- `public static CalculateRaycastLine(UnityEngine.Camera mainCamera) : Colossal.Mathematics.Line3+Segment`  

```csharp
public static Line3.Segment CalculateRaycastLine(Camera mainCamera)
	{
		Ray ray = mainCamera.ScreenPointToRay(InputManager.instance.mousePosition);
		float3 @float = ray.direction;
		float3 y = mainCamera.transform.forward;
		Line3.Segment result = default(Line3.Segment);
		result.a = ray.origin;
		result.b = result.a + @float * (mainCamera.farClipPlane / math.clamp(math.dot(@float, y), 0.25f, 1f));
		return result;
	}
```

- `public GetRaycastResult(Game.Common.RaycastResult& result) : System.Boolean`  

```csharp
public bool GetRaycastResult(out RaycastResult result)
	{
		NativeArray<RaycastResult> result2 = m_RaycastSystem.GetResult(this);
		if (result2.Length != 0)
		{
			result = result2[0];
			return result.m_Owner != Entity.Null;
		}
		result = default(RaycastResult);
		return false;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_RaycastSystem = base.World.GetOrCreateSystemManaged<RaycastSystem>();
		m_CameraUpdateSystem = base.World.GetOrCreateSystemManaged<CameraUpdateSystem>();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (m_ToolSystem.activeTool != null)
		{
			m_ToolSystem.activeTool.InitializeRaycast();
		}
		if (m_CameraUpdateSystem.TryGetViewer(out var viewer))
		{
			if (m_ToolSystem.fullUpdateRequired)
			{
				raycastFlags |= RaycastFlags.ToolDisable;
			}
			else
			{
				raycastFlags &= ~RaycastFlags.ToolDisable;
			}
			if (InputManager.instance.controlOverWorld)
			{
				raycastFlags &= ~RaycastFlags.UIDisable;
			}
			else
			{
				raycastFlags |= RaycastFlags.UIDisable;
			}
			RaycastInput input = new RaycastInput
			{
				m_Line = CalculateRaycastLine(viewer.camera),
				m_Offset = rayOffset,
				m_TypeMask = typeMask,
				m_Flags = raycastFlags,
				m_CollisionMask = collisionMask,
				m_NetLayerMask = netLayerMask,
				m_AreaTypeMask = areaTypeMask,
				m_RouteType = routeType,
				m_TransportType = transportType,
				m_IconLayerMask = iconLayerMask,
				m_UtilityTypeMask = utilityTypeMask
			};
			m_RaycastSystem.AddInput(this, input);
		}
	}
```


