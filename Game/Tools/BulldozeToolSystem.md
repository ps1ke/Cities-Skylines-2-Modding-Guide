# Game.Tools.BulldozeToolSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.Tools.ToolBaseSystem`  
**Implements:** `System.IEquatable<Game.Tools.ToolBaseSystem>`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class BulldozeToolSystem : Game.Tools.ToolBaseSystem, System.IEquatable<Game.Tools.ToolBaseSystem>
{
    private Game.Tools.BulldozeToolSystem+Mode <mode>k__BackingField;
    private System.Boolean <underground>k__BackingField;
    private System.Boolean <allowManipulation>k__BackingField;
    private System.Boolean <debugBypassBulldozeConfirmation>k__BackingField;
    private Game.Prefabs.BulldozePrefab <prefab>k__BackingField;
    public System.Action EventConfirmationRequested;
    private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
    private Game.Audio.AudioManager m_AudioManager;
    private Game.Achievements.AchievementTriggerSystem m_AchievementTriggerSystem;
    private Unity.Entities.EntityQuery m_DefinitionQuery;
    private Unity.Entities.EntityQuery m_BuildingQuery;
    private Unity.Entities.EntityQuery m_RoadQuery;
    private Unity.Entities.EntityQuery m_PlantQuery;
    private Unity.Entities.EntityQuery m_SoundQuery;
    private Game.Tools.ControlPoint m_LastRaycastPoint;
    private Game.Tools.BulldozeToolSystem+State m_State;
    private Unity.Collections.NativeList<Game.Tools.ControlPoint> m_ControlPoints;
    private Game.Input.IProxyAction m_Bulldoze;
    private Game.Input.IProxyAction m_BulldozeDiscard;
    private System.Boolean m_ApplyBlocked;
    private Game.Tools.BulldozeToolSystem+TypeHandle __TypeHandle;
    public static const System.String kToolID;

    public System.String toolID { get; }
    public System.Int32 uiModeIndex { get; }
    public System.Boolean allowUnderground { get; }
    public Game.Tools.BulldozeToolSystem+Mode mode { get; set; }
    public Game.Tools.BulldozeToolSystem+Mode actualMode { get; }
    public System.Boolean underground { get; set; }
    public System.Boolean allowManipulation { get; set; }
    public System.Boolean debugBypassBulldozeConfirmation { get; set; }
    public Game.Prefabs.BulldozePrefab prefab { get; set; }
    private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get; }

    public BulldozeToolSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private Unity.Jobs.JobHandle Apply(Unity.Jobs.JobHandle inputDeps);
    public System.Void ConfirmAction(System.Boolean confirm);
    private System.Boolean ConfirmationNeeded();
    public virtual System.Void ElevationDown();
    public virtual System.Void ElevationScroll();
    public virtual System.Void ElevationUp();
    public virtual Game.Prefabs.PrefabBase GetPrefab();
    protected virtual System.Boolean GetRaycastResult(Game.Tools.ControlPoint& controlPoint);
    protected virtual System.Boolean GetRaycastResult(Game.Tools.ControlPoint& controlPoint, System.Boolean& forceUpdate);
    public virtual System.Void GetUIModes(System.Collections.Generic.List<Game.Tools.ToolMode> modes);
    public virtual System.Void InitializeRaycast();
    private System.Boolean IsMultiSelection();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnStartRunning();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
    public virtual System.Void SetUnderground(System.Boolean underground);
    private Unity.Jobs.JobHandle SnapControlPoints(Unity.Jobs.JobHandle inputDeps);
    public virtual System.Boolean TrySetPrefab(Game.Prefabs.PrefabBase prefab);
    private Unity.Jobs.JobHandle Update(Unity.Jobs.JobHandle inputDeps, System.Boolean fullUpdate);
    private virtual System.Void UpdateActions();
    private Unity.Jobs.JobHandle UpdateDefinitions(Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Game.Tools.BulldozeToolSystem+Mode <mode>k__BackingField`  

```csharp
private Game.Tools.BulldozeToolSystem+Mode <mode>k__BackingField;
```

- `private System.Boolean <underground>k__BackingField`  

```csharp
private System.Boolean <underground>k__BackingField;
```

- `private System.Boolean <allowManipulation>k__BackingField`  

```csharp
private System.Boolean <allowManipulation>k__BackingField;
```

- `private System.Boolean <debugBypassBulldozeConfirmation>k__BackingField`  

```csharp
private System.Boolean <debugBypassBulldozeConfirmation>k__BackingField;
```

- `private Game.Prefabs.BulldozePrefab <prefab>k__BackingField`  

```csharp
private Game.Prefabs.BulldozePrefab <prefab>k__BackingField;
```

- `public System.Action EventConfirmationRequested`  

```csharp
public System.Action EventConfirmationRequested;
```

- `private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier`  

```csharp
private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
```

- `private Game.Audio.AudioManager m_AudioManager`  

```csharp
private Game.Audio.AudioManager m_AudioManager;
```

- `private Game.Achievements.AchievementTriggerSystem m_AchievementTriggerSystem`  

```csharp
private Game.Achievements.AchievementTriggerSystem m_AchievementTriggerSystem;
```

- `private Unity.Entities.EntityQuery m_DefinitionQuery`  

```csharp
private Unity.Entities.EntityQuery m_DefinitionQuery;
```

- `private Unity.Entities.EntityQuery m_BuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingQuery;
```

- `private Unity.Entities.EntityQuery m_RoadQuery`  

```csharp
private Unity.Entities.EntityQuery m_RoadQuery;
```

- `private Unity.Entities.EntityQuery m_PlantQuery`  

```csharp
private Unity.Entities.EntityQuery m_PlantQuery;
```

- `private Unity.Entities.EntityQuery m_SoundQuery`  

```csharp
private Unity.Entities.EntityQuery m_SoundQuery;
```

- `private Game.Tools.ControlPoint m_LastRaycastPoint`  

```csharp
private Game.Tools.ControlPoint m_LastRaycastPoint;
```

- `private Game.Tools.BulldozeToolSystem+State m_State`  

```csharp
private Game.Tools.BulldozeToolSystem+State m_State;
```

- `private Unity.Collections.NativeList<Game.Tools.ControlPoint> m_ControlPoints`  

```csharp
private Unity.Collections.NativeList<Game.Tools.ControlPoint> m_ControlPoints;
```

- `private Game.Input.IProxyAction m_Bulldoze`  

```csharp
private Game.Input.IProxyAction m_Bulldoze;
```

- `private Game.Input.IProxyAction m_BulldozeDiscard`  

```csharp
private Game.Input.IProxyAction m_BulldozeDiscard;
```

- `private System.Boolean m_ApplyBlocked`  

```csharp
private System.Boolean m_ApplyBlocked;
```

- `private Game.Tools.BulldozeToolSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.BulldozeToolSystem+TypeHandle __TypeHandle;
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

- `public System.Int32 uiModeIndex { get }`  

```csharp
public System.Int32 uiModeIndex { get; }
```

- `public System.Boolean allowUnderground { get }`  

```csharp
public System.Boolean allowUnderground { get; }
```

- `public Game.Tools.BulldozeToolSystem+Mode mode { get; set }`  

```csharp
public Game.Tools.BulldozeToolSystem+Mode mode { get; set; }
```

- `public Game.Tools.BulldozeToolSystem+Mode actualMode { get }`  

```csharp
public Game.Tools.BulldozeToolSystem+Mode actualMode { get; }
```

- `public System.Boolean underground { get; set }`  

```csharp
public System.Boolean underground { get; set; }
```

- `public System.Boolean allowManipulation { get; set }`  

```csharp
public System.Boolean allowManipulation { get; set; }
```

- `public System.Boolean debugBypassBulldozeConfirmation { get; set }`  

```csharp
public System.Boolean debugBypassBulldozeConfirmation { get; set; }
```

- `public Game.Prefabs.BulldozePrefab prefab { get; set }`  

```csharp
public Game.Prefabs.BulldozePrefab prefab { get; set; }
```

- `private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get }`  

```csharp
private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get; }
```


## Constructors

- `public BulldozeToolSystem()`  

```csharp
[Preserve]
	public BulldozeToolSystem()
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

- `private Apply(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle Apply(JobHandle inputDeps)
	{
		if (GetAllowApply())
		{
			int num = m_BuildingQuery.CalculateEntityCount();
			if (num > 0 || m_RoadQuery.CalculateEntityCount() > 0)
			{
				m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_BulldozeSound);
			}
			else
			{
				m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_PropPlantBulldozeSound);
			}
			if (num > 0 && m_ToolSystem.actionMode.IsGame())
			{
				m_AchievementTriggerSystem.m_SquasherDownerBuffer.AddProgress(num);
			}
			base.applyMode = ApplyMode.Apply;
			m_LastRaycastPoint = default(ControlPoint);
			m_ControlPoints.Clear();
			return DestroyDefinitions(m_DefinitionQuery, m_ToolOutputBarrier, inputDeps);
		}
		if (m_ControlPoints.Length >= 2)
		{
			m_ControlPoints.RemoveRange(0, m_ControlPoints.Length - 1);
		}
		return Update(inputDeps, fullUpdate: true);
	}
```

- `public ConfirmAction(System.Boolean confirm) : System.Void`  

```csharp
public void ConfirmAction(bool confirm)
	{
		if (m_State == State.Waiting)
		{
			m_State = (confirm ? State.Confirmed : State.Cancelled);
		}
	}
```

- `private ConfirmationNeeded() : System.Boolean`  

```csharp
private bool ConfirmationNeeded()
	{
		NativeArray<Entity> nativeArray = m_BuildingQuery.ToEntityArray(Allocator.TempJob);
		bool result = false;
		for (int i = 0; i < nativeArray.Length; i++)
		{
			Entity entity = nativeArray[i];
			if ((base.EntityManager.GetComponentData<Temp>(entity).m_Flags & TempFlags.Delete) != 0 && base.EntityManager.TryGetComponent<PrefabRef>(entity, out var component) && (!base.EntityManager.HasComponent<SpawnableBuildingData>(component.m_Prefab) || base.EntityManager.HasComponent<SignatureBuildingData>(component.m_Prefab)))
			{
				result = true;
			}
		}
		nativeArray.Dispose();
		return result;
	}
```

- `public virtual ElevationDown() : System.Void`  

```csharp
public override void ElevationDown()
	{
		underground = true;
	}
```

- `public virtual ElevationScroll() : System.Void`  

```csharp
public override void ElevationScroll()
	{
		underground = !underground;
	}
```

- `public virtual ElevationUp() : System.Void`  

```csharp
public override void ElevationUp()
	{
		underground = false;
	}
```

- `public virtual GetPrefab() : Game.Prefabs.PrefabBase`  

```csharp
public override PrefabBase GetPrefab()
	{
		return prefab;
	}
```

- `protected virtual GetRaycastResult(Game.Tools.ControlPoint& controlPoint) : System.Boolean`  

```csharp
protected override bool GetRaycastResult(out ControlPoint controlPoint, out bool forceUpdate)
	{
		if (GetRaycastResult(out var entity, out var hit, out forceUpdate))
		{
			if (m_ToolSystem.actionMode.IsEditor() && base.EntityManager.HasComponent<Game.Buildings.ServiceUpgrade>(entity) && base.EntityManager.TryGetComponent<Owner>(entity, out var component))
			{
				controlPoint.m_OriginalEntity = component.m_Owner;
			}
			if (base.EntityManager.HasComponent<Game.Net.Node>(entity) && base.EntityManager.HasComponent<Edge>(hit.m_HitEntity))
			{
				entity = hit.m_HitEntity;
			}
			controlPoint = new ControlPoint(entity, hit);
			return true;
		}
		controlPoint = default(ControlPoint);
		return false;
	}
```

- `protected virtual GetRaycastResult(Game.Tools.ControlPoint& controlPoint, System.Boolean& forceUpdate) : System.Boolean`  

```csharp
protected override bool GetRaycastResult(out ControlPoint controlPoint, out bool forceUpdate)
	{
		if (GetRaycastResult(out var entity, out var hit, out forceUpdate))
		{
			if (m_ToolSystem.actionMode.IsEditor() && base.EntityManager.HasComponent<Game.Buildings.ServiceUpgrade>(entity) && base.EntityManager.TryGetComponent<Owner>(entity, out var component))
			{
				controlPoint.m_OriginalEntity = component.m_Owner;
			}
			if (base.EntityManager.HasComponent<Game.Net.Node>(entity) && base.EntityManager.HasComponent<Edge>(hit.m_HitEntity))
			{
				entity = hit.m_HitEntity;
			}
			controlPoint = new ControlPoint(entity, hit);
			return true;
		}
		controlPoint = default(ControlPoint);
		return false;
	}
```

- `public virtual GetUIModes(System.Collections.Generic.List<Game.Tools.ToolMode> modes) : System.Void`  

```csharp
public override void GetUIModes(List<ToolMode> modes)
	{
		modes.Add(new ToolMode(Mode.MainElements.ToString(), 0));
		if (m_ToolSystem.actionMode.IsEditor())
		{
			modes.Add(new ToolMode(Mode.SubElements.ToString(), 1));
			modes.Add(new ToolMode(Mode.Everything.ToString(), 2));
		}
	}
```

- `public virtual InitializeRaycast() : System.Void`  

```csharp
public override void InitializeRaycast()
	{
		base.InitializeRaycast();
		m_ToolRaycastSystem.typeMask = TypeMask.StaticObjects | TypeMask.Net;
		m_ToolRaycastSystem.netLayerMask = Layer.All;
		m_ToolRaycastSystem.raycastFlags |= RaycastFlags.BuildingLots;
		if (underground)
		{
			m_ToolRaycastSystem.collisionMask = CollisionMask.Underground;
		}
		else
		{
			m_ToolRaycastSystem.collisionMask = CollisionMask.OnGround | CollisionMask.Overground;
		}
		switch (actualMode)
		{
		case Mode.SubElements:
			m_ToolRaycastSystem.raycastFlags |= RaycastFlags.SubElements | RaycastFlags.NoMainElements;
			break;
		case Mode.Everything:
			m_ToolRaycastSystem.raycastFlags |= RaycastFlags.SubElements;
			break;
		}
		if (m_ToolSystem.actionMode.IsEditor())
		{
			m_ToolRaycastSystem.raycastFlags |= RaycastFlags.Markers | RaycastFlags.UpgradeIsMain | RaycastFlags.EditorContainers;
			m_ToolRaycastSystem.typeMask |= TypeMask.Areas;
			if (underground)
			{
				m_ToolRaycastSystem.areaTypeMask = AreaTypeMask.Spaces;
			}
			else
			{
				m_ToolRaycastSystem.areaTypeMask = AreaTypeMask.Lots | AreaTypeMask.Spaces | AreaTypeMask.Surfaces;
			}
		}
		else
		{
			m_ToolRaycastSystem.raycastFlags |= RaycastFlags.SubBuildings;
			if (!underground)
			{
				m_ToolRaycastSystem.typeMask |= TypeMask.Areas;
				m_ToolRaycastSystem.areaTypeMask = AreaTypeMask.Lots | AreaTypeMask.Surfaces;
			}
		}
		if (allowManipulation)
		{
			m_ToolRaycastSystem.typeMask |= TypeMask.MovingObjects;
		}
		m_ToolRaycastSystem.raycastFlags |= RaycastFlags.Placeholders | RaycastFlags.Decals;
	}
```

- `private IsMultiSelection() : System.Boolean`  

```csharp
private bool IsMultiSelection()
	{
		if (m_ControlPoints.Length == 0)
		{
			return false;
		}
		if (base.EntityManager.HasComponent<Game.Net.Node>(m_ControlPoints[0].m_OriginalEntity) || base.EntityManager.HasComponent<Edge>(m_ControlPoints[0].m_OriginalEntity))
		{
			return m_ControlPoints.Length > 4;
		}
		return m_ControlPoints.Length > 1;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ToolOutputBarrier = base.World.GetOrCreateSystemManaged<ToolOutputBarrier>();
		m_AudioManager = base.World.GetOrCreateSystemManaged<AudioManager>();
		m_AchievementTriggerSystem = base.World.GetOrCreateSystemManaged<AchievementTriggerSystem>();
		m_ControlPoints = new NativeList<ControlPoint>(4, Allocator.Persistent);
		m_DefinitionQuery = GetDefinitionQuery();
		m_BuildingQuery = GetEntityQuery(ComponentType.ReadOnly<Building>(), ComponentType.ReadOnly<Temp>(), ComponentType.Exclude<Deleted>());
		m_RoadQuery = GetEntityQuery(ComponentType.ReadOnly<Edge>(), ComponentType.ReadOnly<Temp>(), ComponentType.Exclude<Deleted>());
		m_PlantQuery = GetEntityQuery(ComponentType.ReadOnly<Plant>(), ComponentType.ReadOnly<Temp>(), ComponentType.Exclude<Deleted>());
		m_SoundQuery = GetEntityQuery(ComponentType.ReadOnly<ToolUXSoundSettingsData>());
		m_Bulldoze = InputManager.instance.toolActionCollection.GetActionState("Bulldoze", "BulldozeToolSystem");
		m_BulldozeDiscard = InputManager.instance.toolActionCollection.GetActionState("Bulldoze Discard", "BulldozeToolSystem");
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

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		m_ControlPoints.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnStartRunning() : System.Void`  

```csharp
[Preserve]
	protected override void OnStartRunning()
	{
		base.OnStartRunning();
		m_ControlPoints.Clear();
		m_LastRaycastPoint = default(ControlPoint);
		m_State = State.Default;
		m_ApplyBlocked = false;
		base.requireUnderground = false;
		base.requireStopIcons = false;
		base.requireAreas = AreaTypeMask.None;
		base.requireNet = Layer.None;
	}
```

- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
[Preserve]
	protected override JobHandle OnUpdate(JobHandle inputDeps)
	{
		base.requireUnderground = underground;
		base.requireStopIcons = true;
		if (underground)
		{
			base.requireAreas = (m_ToolSystem.actionMode.IsEditor() ? AreaTypeMask.Spaces : AreaTypeMask.None);
			base.requireNet = Layer.None;
		}
		else
		{
			base.requireAreas = (m_ToolSystem.actionMode.IsEditor() ? (AreaTypeMask.Lots | AreaTypeMask.Spaces | AreaTypeMask.Surfaces) : AreaTypeMask.None);
			base.requireNet = Layer.Waterway;
		}
		UpdateActions();
		if (m_State == State.Applying && !base.applyAction.enabled)
		{
			m_State = State.Default;
			m_ControlPoints.Clear();
			base.applyMode = ApplyMode.Clear;
			inputDeps = DestroyDefinitions(m_DefinitionQuery, m_ToolOutputBarrier, inputDeps);
		}
		switch (m_State)
		{
		case State.Default:
			if (m_ApplyBlocked)
			{
				if (base.applyAction.WasReleasedThisFrame() || base.secondaryApplyAction.WasReleasedThisFrame())
				{
					m_ApplyBlocked = false;
				}
				return Update(inputDeps, fullUpdate: false);
			}
			if (base.cancelAction.IsInProgress())
			{
				base.applyMode = ApplyMode.None;
				return inputDeps;
			}
			if (m_ControlPoints.Length > 0 && base.applyAction.WasPressedThisFrame())
			{
				m_State = State.Applying;
				return Update(inputDeps, fullUpdate: true);
			}
			return Update(inputDeps, fullUpdate: false);
		case State.Applying:
			if (base.cancelAction.IsInProgress())
			{
				m_State = State.Default;
				m_ApplyBlocked = true;
				if (m_ControlPoints.Length >= 2)
				{
					m_ControlPoints.RemoveRange(0, m_ControlPoints.Length - 1);
				}
				return Update(inputDeps, fullUpdate: true);
			}
			if (!base.applyAction.IsInProgress())
			{
				if (!m_BuildingQuery.IsEmptyIgnoreFilter && !m_ToolSystem.actionMode.IsEditor() && EventConfirmationRequested != null && !debugBypassBulldozeConfirmation && ConfirmationNeeded())
				{
					m_State = State.Waiting;
					base.applyMode = ApplyMode.None;
					EventConfirmationRequested();
					return inputDeps;
				}
				m_State = State.Default;
				return Apply(inputDeps);
			}
			return Update(inputDeps, fullUpdate: false);
		case State.Confirmed:
			m_State = State.Default;
			return Apply(inputDeps);
		case State.Cancelled:
			m_State = State.Default;
			if (m_ControlPoints.Length >= 2)
			{
				m_ControlPoints.RemoveRange(0, m_ControlPoints.Length - 1);
			}
			return Update(inputDeps, fullUpdate: true);
		default:
			base.applyMode = ApplyMode.None;
			return inputDeps;
		}
	}
```

- `public virtual SetUnderground(System.Boolean underground) : System.Void`  

```csharp
public override void SetUnderground(bool underground)
	{
		this.underground = underground;
	}
```

- `private SnapControlPoints(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle SnapControlPoints(JobHandle inputDeps)
	{
		return IJobExtensions.Schedule(new SnapJob
		{
			m_EditorMode = m_ToolSystem.actionMode.IsEditor(),
			m_Mode = actualMode,
			m_State = m_State,
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_StaticData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Static_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OutsideConnectionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_OutsideConnection_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ServiceUpgradeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_ServiceUpgrade_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NodeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Node_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabNetData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ConnectedEdges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedEdge_RO_BufferLookup, ref base.CheckedStateRef),
			m_ControlPoints = m_ControlPoints
		}, inputDeps);
	}
```

- `public virtual TrySetPrefab(Game.Prefabs.PrefabBase prefab) : System.Boolean`  

```csharp
public override bool TrySetPrefab(PrefabBase prefab)
	{
		if (prefab is BulldozePrefab bulldozePrefab)
		{
			this.prefab = bulldozePrefab;
			return true;
		}
		return false;
	}
```

- `private Update(Unity.Jobs.JobHandle inputDeps, System.Boolean fullUpdate) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle Update(JobHandle inputDeps, bool fullUpdate)
	{
		if (GetRaycastResult(out ControlPoint controlPoint, out bool forceUpdate))
		{
			fullUpdate = fullUpdate || forceUpdate;
			if (m_ControlPoints.Length == 0)
			{
				base.applyMode = ApplyMode.Clear;
				m_ControlPoints.Add(in controlPoint);
				inputDeps = SnapControlPoints(inputDeps);
				inputDeps = UpdateDefinitions(inputDeps);
			}
			else
			{
				base.applyMode = ApplyMode.None;
				if (fullUpdate || !m_LastRaycastPoint.Equals(controlPoint))
				{
					m_LastRaycastPoint = controlPoint;
					ControlPoint controlPoint2 = m_ControlPoints[m_ControlPoints.Length - 1];
					if (m_State == State.Applying && controlPoint.m_OriginalEntity != m_ControlPoints[m_ControlPoints.Length - 1].m_OriginalEntity)
					{
						m_ControlPoints.Add(in controlPoint);
					}
					else
					{
						m_ControlPoints[m_ControlPoints.Length - 1] = controlPoint;
					}
					inputDeps = SnapControlPoints(inputDeps);
					JobHandle.ScheduleBatchedJobs();
					inputDeps.Complete();
					ControlPoint other = default(ControlPoint);
					if (m_ControlPoints.Length != 0)
					{
						other = m_ControlPoints[m_ControlPoints.Length - 1];
					}
					if (fullUpdate || !controlPoint2.EqualsIgnoreHit(other))
					{
						base.applyMode = ApplyMode.Clear;
						inputDeps = UpdateDefinitions(inputDeps);
					}
				}
			}
		}
		else
		{
			if (m_State == State.Default)
			{
				m_ControlPoints.Clear();
			}
			base.applyMode = ApplyMode.Clear;
			inputDeps = DestroyDefinitions(m_DefinitionQuery, m_ToolOutputBarrier, inputDeps);
		}
		return inputDeps;
	}
```

- `private virtual UpdateActions() : System.Void`  

```csharp
private protected override void UpdateActions()
	{
		using (ProxyAction.DeferStateUpdating())
		{
			base.applyActionOverride = m_Bulldoze;
			base.applyAction.enabled = base.actionsEnabled && m_State != State.Waiting && m_ControlPoints.Length != 0;
			base.cancelActionOverride = m_BulldozeDiscard;
			base.cancelAction.enabled = base.actionsEnabled && m_State == State.Applying && IsMultiSelection();
		}
	}
```

- `private UpdateDefinitions(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle UpdateDefinitions(JobHandle inputDeps)
	{
		JobHandle job = DestroyDefinitions(m_DefinitionQuery, m_ToolOutputBarrier, inputDeps);
		JobHandle jobHandle = IJobExtensions.Schedule(new CreateDefinitionsJob
		{
			m_EditorMode = m_ToolSystem.actionMode.IsEditor(),
			m_Mode = actualMode,
			m_State = m_State,
			m_ControlPoints = m_ControlPoints,
			m_CachedNodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Tools_LocalNodeCache_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubNets = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubNet_RO_BufferLookup, ref base.CheckedStateRef),
			m_ConnectedEdges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedEdge_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubAreas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_SubArea_RO_BufferLookup, ref base.CheckedStateRef),
			m_AreaNodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Node_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Objects_SubObject_RO_BufferLookup, ref base.CheckedStateRef),
			m_InstalledUpgrades = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferLookup, ref base.CheckedStateRef),
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LocalTransformCacheData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_LocalTransformCache_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NodeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Node_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
			m_FixedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Fixed_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LotData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_Lot_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EditorContainerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_EditorContainer_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AttachedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Attached_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ElevationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Elevation_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PlaceholderData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Placeholder_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AttachmentData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Attachment_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ServiceUpgradeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_ServiceUpgrade_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabNetData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CommandBuffer = m_ToolOutputBarrier.CreateCommandBuffer()
		}, inputDeps);
		m_ToolOutputBarrier.AddJobHandleForProducer(jobHandle);
		return JobHandle.CombineDependencies(job, jobHandle);
	}
```


## Nested types

- `Game.Tools.BulldozeToolSystem+Mode`  
- `Game.Tools.BulldozeToolSystem+State`  
- `Game.Tools.BulldozeToolSystem+PathEdge`  
- `Game.Tools.BulldozeToolSystem+PathItem`  
- `Game.Tools.BulldozeToolSystem+SnapJob`  
- `Game.Tools.BulldozeToolSystem+CreateDefinitionsJob`  
- `Game.Tools.BulldozeToolSystem+TypeHandle`  
- `Game.Tools.BulldozeToolSystem+<get_toolActions>d__47`  

