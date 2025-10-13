# Game.Tools.WaterToolSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.Tools.ToolBaseSystem`  
**Implements:** `System.IEquatable<Game.Tools.ToolBaseSystem>`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WaterToolSystem : Game.Tools.ToolBaseSystem, System.IEquatable<Game.Tools.ToolBaseSystem>
{
    private Game.Tools.WaterToolSystem+Attribute <attribute>k__BackingField;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
    private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
    private Unity.Entities.EntityQuery m_DefinitionQuery;
    private Game.Tools.ControlPoint m_RaycastPoint;
    private Game.Tools.ControlPoint m_StartPoint;
    private Game.Tools.WaterToolSystem+State m_State;
    private Game.Tools.WaterToolSystem+TypeHandle __TypeHandle;
    public static const System.String kToolID;

    public System.String toolID { get; }
    public Game.Tools.WaterToolSystem+Attribute attribute { get; private set; }

    public WaterToolSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private Unity.Jobs.JobHandle Apply(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly);
    private Unity.Jobs.JobHandle Cancel(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly);
    private Unity.Jobs.JobHandle Clear(Unity.Jobs.JobHandle inputDeps);
    private Game.Tools.WaterToolSystem+Attribute GetAttribute(Game.Tools.ControlPoint controlPoint);
    public virtual System.Void GetAvailableSnapMask(Game.Tools.Snap& onMask, Game.Tools.Snap& offMask);
    public virtual Game.Prefabs.PrefabBase GetPrefab();
    protected virtual System.Boolean GetRaycastResult(Game.Tools.ControlPoint& controlPoint);
    public virtual System.Void InitializeRaycast();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnStartRunning();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
    public virtual System.Boolean TrySetPrefab(Game.Prefabs.PrefabBase prefab);
    private Unity.Jobs.JobHandle Update(Unity.Jobs.JobHandle inputDeps);
    private virtual System.Void UpdateActions();
    private Unity.Jobs.JobHandle UpdateDefinitions(Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Game.Tools.WaterToolSystem+Attribute <attribute>k__BackingField`  

```csharp
private Game.Tools.WaterToolSystem+Attribute <attribute>k__BackingField;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  

```csharp
private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
```

- `private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier`  

```csharp
private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
```

- `private Unity.Entities.EntityQuery m_DefinitionQuery`  

```csharp
private Unity.Entities.EntityQuery m_DefinitionQuery;
```

- `private Game.Tools.ControlPoint m_RaycastPoint`  

```csharp
private Game.Tools.ControlPoint m_RaycastPoint;
```

- `private Game.Tools.ControlPoint m_StartPoint`  

```csharp
private Game.Tools.ControlPoint m_StartPoint;
```

- `private Game.Tools.WaterToolSystem+State m_State`  

```csharp
private Game.Tools.WaterToolSystem+State m_State;
```

- `private Game.Tools.WaterToolSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.WaterToolSystem+TypeHandle __TypeHandle;
```

- `public static const System.String kToolID`  

```csharp
public static const System.String kToolID;
```


## Properties

- `public System.String toolID { get }`  

```csharp
public System.String toolID { get; }
```

- `public Game.Tools.WaterToolSystem+Attribute attribute { get; private set }`  

```csharp
public Game.Tools.WaterToolSystem+Attribute attribute { get; private set; }
```


## Constructors

- `public WaterToolSystem()`  

```csharp
[Preserve]
	public WaterToolSystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		new EntityQueryBuilder(Allocator.Temp).Dispose();
	}
```

- `private Apply(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly = False) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle Apply(JobHandle inputDeps, bool singleFrameOnly = false)
	{
		switch (m_State)
		{
		case State.Default:
			if (m_RaycastPoint.m_OriginalEntity != Entity.Null && !singleFrameOnly)
			{
				m_State = State.MouseDown;
				m_StartPoint = m_RaycastPoint;
			}
			base.applyMode = ApplyMode.None;
			return inputDeps;
		case State.MouseDown:
			m_State = State.Default;
			base.applyMode = ApplyMode.Clear;
			return inputDeps;
		case State.Dragging:
			m_State = State.Default;
			base.applyMode = (GetAllowApply() ? ApplyMode.Apply : ApplyMode.Clear);
			return inputDeps;
		default:
			return Update(inputDeps);
		}
	}
```

- `private Cancel(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly = False) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle Cancel(JobHandle inputDeps, bool singleFrameOnly = false)
	{
		switch (m_State)
		{
		case State.Default:
			base.applyMode = ApplyMode.None;
			return inputDeps;
		case State.MouseDown:
			m_State = State.Default;
			base.applyMode = ApplyMode.Clear;
			return inputDeps;
		case State.Dragging:
			m_State = State.Default;
			base.applyMode = ApplyMode.Clear;
			return inputDeps;
		default:
			return Update(inputDeps);
		}
	}
```

- `private Clear(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle Clear(JobHandle inputDeps)
	{
		base.applyMode = ApplyMode.Clear;
		return inputDeps;
	}
```

- `private GetAttribute(Game.Tools.ControlPoint controlPoint) : Game.Tools.WaterToolSystem+Attribute`  

```csharp
private Attribute GetAttribute(ControlPoint controlPoint)
	{
		if (base.EntityManager.TryGetComponent<Game.Simulation.WaterSourceData>(controlPoint.m_OriginalEntity, out var component) && m_CameraUpdateSystem.TryGetViewer(out var viewer))
		{
			float2 @float = controlPoint.m_HitPosition.xz - controlPoint.m_Position.xz;
			if (math.length(@float) < component.m_Radius * 0.9f)
			{
				return Attribute.Location;
			}
			float2 xz = viewer.right.xz;
			float2 x = MathUtils.Left(xz);
			if (math.abs(math.dot(xz, @float)) > math.abs(math.dot(x, @float)))
			{
				return Attribute.Radius;
			}
			if (component.m_ConstantDepth != 0)
			{
				return Attribute.Height;
			}
			return Attribute.Rate;
		}
		return Attribute.None;
	}
```

- `public virtual GetAvailableSnapMask(Game.Tools.Snap& onMask, Game.Tools.Snap& offMask) : System.Void`  

```csharp
public override void GetAvailableSnapMask(out Snap onMask, out Snap offMask)
	{
		base.GetAvailableSnapMask(out onMask, out offMask);
		onMask |= Snap.ContourLines;
		offMask |= Snap.ContourLines;
	}
```

- `public virtual GetPrefab() : Game.Prefabs.PrefabBase`  

```csharp
public override PrefabBase GetPrefab()
	{
		return null;
	}
```

- `protected virtual GetRaycastResult(Game.Tools.ControlPoint& controlPoint) : System.Boolean`  

```csharp
protected override bool GetRaycastResult(out ControlPoint controlPoint)
	{
		if (m_State == State.Dragging && attribute != Attribute.None && attribute != Attribute.Location && base.EntityManager.TryGetComponent<Game.Simulation.WaterSourceData>(m_StartPoint.m_OriginalEntity, out var component) && m_CameraUpdateSystem.TryGetViewer(out var viewer))
		{
			TerrainHeightData data = m_TerrainSystem.GetHeightData();
			Line3.Segment line = ToolRaycastSystem.CalculateRaycastLine(viewer.camera);
			controlPoint = m_StartPoint;
			float2 t2;
			if (attribute == Attribute.Radius)
			{
				float3 position = m_StartPoint.m_Position;
				if (component.m_ConstantDepth > 0)
				{
					position.y = m_TerrainSystem.positionOffset.y + component.m_Amount;
				}
				else
				{
					position.y = TerrainUtils.SampleHeight(ref data, position) + component.m_Amount;
				}
				if (MathUtils.Intersect(line.y, position.y, out var t))
				{
					controlPoint.m_HitPosition = MathUtils.Position(line, t);
				}
			}
			else if (MathUtils.Intersect(new Circle2(component.m_Radius, m_StartPoint.m_Position.xz), line.xz, out t2))
			{
				float3 hitPosition = MathUtils.Position(line, t2.x);
				float3 hitPosition2 = MathUtils.Position(line, t2.y);
				if (math.distancesq(hitPosition.xz, m_StartPoint.m_HitPosition.xz) <= math.distancesq(hitPosition2.xz, m_StartPoint.m_HitPosition.xz))
				{
					controlPoint.m_HitPosition = hitPosition;
				}
				else
				{
					controlPoint.m_HitPosition = hitPosition2;
				}
			}
			return true;
		}
		return base.GetRaycastResult(out controlPoint);
	}
```

- `public virtual InitializeRaycast() : System.Void`  

```csharp
public override void InitializeRaycast()
	{
		base.InitializeRaycast();
		if (m_State == State.Dragging)
		{
			if (attribute != Attribute.Location)
			{
				return;
			}
			m_ToolRaycastSystem.typeMask = TypeMask.Terrain;
			m_ToolRaycastSystem.raycastFlags |= RaycastFlags.Outside;
			if (base.EntityManager.TryGetComponent<Game.Simulation.WaterSourceData>(m_StartPoint.m_OriginalEntity, out var component))
			{
				float num = component.m_Amount;
				if (component.m_ConstantDepth > 0)
				{
					TerrainHeightData data = m_TerrainSystem.GetHeightData();
					num += m_TerrainSystem.positionOffset.y - TerrainUtils.SampleHeight(ref data, m_StartPoint.m_Position);
				}
				m_ToolRaycastSystem.rayOffset = new float3(0f, 0f - num, 0f);
			}
		}
		else
		{
			m_ToolRaycastSystem.typeMask = TypeMask.WaterSources;
		}
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_WaterSystem = base.World.GetOrCreateSystemManaged<WaterSystem>();
		m_CameraUpdateSystem = base.World.GetOrCreateSystemManaged<CameraUpdateSystem>();
		m_ToolOutputBarrier = base.World.GetOrCreateSystemManaged<ToolOutputBarrier>();
		m_DefinitionQuery = GetDefinitionQuery();
	}
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected override void OnCreateForCompiler()
	{
		base.OnCreateForCompiler();
		__AssignQueries(ref base.CheckedStateRef);
		__TypeHandle.__AssignHandles(ref base.CheckedStateRef);
	}
```

- `protected virtual OnStartRunning() : System.Void`  

```csharp
[Preserve]
	protected override void OnStartRunning()
	{
		base.OnStartRunning();
		m_RaycastPoint = default(ControlPoint);
		m_State = State.Default;
		attribute = Attribute.None;
	}
```

- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
[Preserve]
	protected override JobHandle OnUpdate(JobHandle inputDeps)
	{
		UpdateInfoview(Entity.Null);
		GetAvailableSnapMask(out m_SnapOnMask, out m_SnapOffMask);
		if ((m_ToolRaycastSystem.raycastFlags & (RaycastFlags.DebugDisable | RaycastFlags.UIDisable)) == 0)
		{
			if (m_State != State.Default)
			{
				if (base.applyAction.WasPressedThisFrame() || base.applyAction.WasReleasedThisFrame())
				{
					return Apply(inputDeps);
				}
				if (base.secondaryApplyAction.WasPressedThisFrame() || base.secondaryApplyAction.WasReleasedThisFrame())
				{
					return Cancel(inputDeps);
				}
				return Update(inputDeps);
			}
			if (base.secondaryApplyAction.WasPressedThisFrame())
			{
				return Cancel(inputDeps, base.secondaryApplyAction.WasReleasedThisFrame());
			}
			if (base.applyAction.WasPressedThisFrame())
			{
				return Apply(inputDeps, base.applyAction.WasReleasedThisFrame());
			}
			return Update(inputDeps);
		}
		return Clear(inputDeps);
	}
```

- `public virtual TrySetPrefab(Game.Prefabs.PrefabBase prefab) : System.Boolean`  

```csharp
public override bool TrySetPrefab(PrefabBase prefab)
	{
		return false;
	}
```

- `private Update(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle Update(JobHandle inputDeps)
	{
		if (GetRaycastResult(out var controlPoint))
		{
			if (m_RaycastPoint.Equals(controlPoint))
			{
				base.applyMode = ApplyMode.None;
				return inputDeps;
			}
			if (m_State == State.Default)
			{
				attribute = GetAttribute(controlPoint);
			}
			base.applyMode = ApplyMode.Clear;
			m_RaycastPoint = controlPoint;
			if (m_State == State.MouseDown && math.distance(controlPoint.m_HitPosition, m_StartPoint.m_HitPosition) >= 1f)
			{
				inputDeps = UpdateDefinitions(inputDeps);
				m_State = State.Dragging;
			}
			else
			{
				inputDeps = UpdateDefinitions(inputDeps);
			}
			return inputDeps;
		}
		if (m_RaycastPoint.Equals(default(ControlPoint)))
		{
			base.applyMode = ApplyMode.None;
			return inputDeps;
		}
		base.applyMode = ApplyMode.Clear;
		m_RaycastPoint = default(ControlPoint);
		if (m_State == State.MouseDown)
		{
			inputDeps = UpdateDefinitions(inputDeps);
			m_State = State.Dragging;
		}
		else
		{
			if (m_State == State.Default)
			{
				attribute = Attribute.None;
			}
			inputDeps = UpdateDefinitions(inputDeps);
		}
		return inputDeps;
	}
```

- `private virtual UpdateActions() : System.Void`  

```csharp
private protected override void UpdateActions()
	{
		base.applyAction.enabled = base.actionsEnabled;
		base.secondaryApplyAction.enabled = base.actionsEnabled;
	}
```

- `private UpdateDefinitions(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle UpdateDefinitions(JobHandle inputDeps)
	{
		JobHandle jobHandle = DestroyDefinitions(m_DefinitionQuery, m_ToolOutputBarrier, inputDeps);
		if (m_RaycastPoint.m_OriginalEntity != Entity.Null)
		{
			JobHandle jobHandle2 = IJobExtensions.Schedule(new CreateDefinitionsJob
			{
				m_StartPoint = m_StartPoint,
				m_RaycastPoint = m_RaycastPoint,
				m_State = m_State,
				m_Attribute = attribute,
				m_WaterSourceData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_WaterSourceData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PositionOffset = m_TerrainSystem.positionOffset,
				m_CommandBuffer = m_ToolOutputBarrier.CreateCommandBuffer()
			}, inputDeps);
			m_ToolOutputBarrier.AddJobHandleForProducer(jobHandle2);
			jobHandle = JobHandle.CombineDependencies(jobHandle, jobHandle2);
		}
		return jobHandle;
	}
```


## Nested types

- `Game.Tools.WaterToolSystem+Attribute`  
- `Game.Tools.WaterToolSystem+State`  
- `Game.Tools.WaterToolSystem+CreateDefinitionsJob`  
- `Game.Tools.WaterToolSystem+TypeHandle`  

