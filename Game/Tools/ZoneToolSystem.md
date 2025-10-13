# Game.Tools.ZoneToolSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.Tools.ToolBaseSystem`  
**Implements:** `System.IEquatable<Game.Tools.ToolBaseSystem>`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ZoneToolSystem : Game.Tools.ToolBaseSystem, System.IEquatable<Game.Tools.ToolBaseSystem>
{
    private Game.Tools.ZoneToolSystem+Mode <mode>k__BackingField;
    private Game.Prefabs.ZonePrefab m_Prefab;
    private System.Boolean <overwrite>k__BackingField;
    private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
    private Game.Audio.AudioManager m_AudioManager;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Unity.Entities.EntityQuery m_DefinitionGroup;
    private Unity.Entities.EntityQuery m_TempBlockQuery;
    private Unity.Entities.EntityQuery m_SoundQuery;
    private Game.Input.IProxyAction m_ApplyZone;
    private Game.Input.IProxyAction m_RemoveZone;
    private Game.Input.IProxyAction m_DiscardZoning;
    private Game.Input.IProxyAction m_DiscardDezoning;
    private Game.Input.IProxyAction m_DefaultDiscardApply;
    private Game.Input.IProxyAction m_DefaultDiscardRemove;
    private System.Boolean m_ApplyBlocked;
    private Game.Tools.ControlPoint m_RaycastPoint;
    private Game.Tools.ControlPoint m_StartPoint;
    private Colossal.Collections.NativeValue<Game.Tools.ControlPoint> m_SnapPoint;
    private Game.Tools.ZoneToolSystem+State m_State;
    private Game.Tools.ZoneToolSystem+TypeHandle __TypeHandle;
    public static const System.String kToolID;

    public System.String toolID { get; }
    public System.Int32 uiModeIndex { get; }
    public Game.Tools.ZoneToolSystem+Mode mode { get; set; }
    public Game.Prefabs.ZonePrefab prefab { get; set; }
    public System.Boolean overwrite { get; set; }
    private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get; }

    public ZoneToolSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private Unity.Jobs.JobHandle Apply(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly);
    private Unity.Jobs.JobHandle Cancel(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly);
    private Unity.Jobs.JobHandle Clear(Unity.Jobs.JobHandle inputDeps);
    protected System.Boolean GetAllowApplyZone();
    protected System.Boolean GetAllowRemoveZone();
    public virtual System.Void GetAvailableSnapMask(Game.Tools.Snap& onMask, Game.Tools.Snap& offMask);
    public virtual Game.Prefabs.PrefabBase GetPrefab();
    public virtual System.Void GetUIModes(System.Collections.Generic.List<Game.Tools.ToolMode> modes);
    public virtual System.Void InitializeRaycast();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnStartRunning();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
    private Unity.Jobs.JobHandle SetZoneType(Unity.Jobs.JobHandle inputDeps);
    private Unity.Jobs.JobHandle SnapPoint(Unity.Jobs.JobHandle inputDeps);
    public virtual System.Boolean TrySetPrefab(Game.Prefabs.PrefabBase prefab);
    private Unity.Jobs.JobHandle Update(Unity.Jobs.JobHandle inputDeps);
    private virtual System.Void UpdateActions();
    private Unity.Jobs.JobHandle UpdateDefinitions(Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Game.Tools.ZoneToolSystem+Mode <mode>k__BackingField`  

```csharp
private Game.Tools.ZoneToolSystem+Mode <mode>k__BackingField;
```

- `private Game.Prefabs.ZonePrefab m_Prefab`  

```csharp
private Game.Prefabs.ZonePrefab m_Prefab;
```

- `private System.Boolean <overwrite>k__BackingField`  

```csharp
private System.Boolean <overwrite>k__BackingField;
```

- `private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier`  

```csharp
private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
```

- `private Game.Audio.AudioManager m_AudioManager`  

```csharp
private Game.Audio.AudioManager m_AudioManager;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Unity.Entities.EntityQuery m_DefinitionGroup`  

```csharp
private Unity.Entities.EntityQuery m_DefinitionGroup;
```

- `private Unity.Entities.EntityQuery m_TempBlockQuery`  

```csharp
private Unity.Entities.EntityQuery m_TempBlockQuery;
```

- `private Unity.Entities.EntityQuery m_SoundQuery`  

```csharp
private Unity.Entities.EntityQuery m_SoundQuery;
```

- `private Game.Input.IProxyAction m_ApplyZone`  

```csharp
private Game.Input.IProxyAction m_ApplyZone;
```

- `private Game.Input.IProxyAction m_RemoveZone`  

```csharp
private Game.Input.IProxyAction m_RemoveZone;
```

- `private Game.Input.IProxyAction m_DiscardZoning`  

```csharp
private Game.Input.IProxyAction m_DiscardZoning;
```

- `private Game.Input.IProxyAction m_DiscardDezoning`  

```csharp
private Game.Input.IProxyAction m_DiscardDezoning;
```

- `private Game.Input.IProxyAction m_DefaultDiscardApply`  

```csharp
private Game.Input.IProxyAction m_DefaultDiscardApply;
```

- `private Game.Input.IProxyAction m_DefaultDiscardRemove`  

```csharp
private Game.Input.IProxyAction m_DefaultDiscardRemove;
```

- `private System.Boolean m_ApplyBlocked`  

```csharp
private System.Boolean m_ApplyBlocked;
```

- `private Game.Tools.ControlPoint m_RaycastPoint`  

```csharp
private Game.Tools.ControlPoint m_RaycastPoint;
```

- `private Game.Tools.ControlPoint m_StartPoint`  

```csharp
private Game.Tools.ControlPoint m_StartPoint;
```

- `private Colossal.Collections.NativeValue<Game.Tools.ControlPoint> m_SnapPoint`  

```csharp
private Colossal.Collections.NativeValue<Game.Tools.ControlPoint> m_SnapPoint;
```

- `private Game.Tools.ZoneToolSystem+State m_State`  

```csharp
private Game.Tools.ZoneToolSystem+State m_State;
```

- `private Game.Tools.ZoneToolSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.ZoneToolSystem+TypeHandle __TypeHandle;
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

- `public Game.Tools.ZoneToolSystem+Mode mode { get; set }`  

```csharp
public Game.Tools.ZoneToolSystem+Mode mode { get; set; }
```

- `public Game.Prefabs.ZonePrefab prefab { get; set }`  

```csharp
public Game.Prefabs.ZonePrefab prefab { get; set; }
```

- `public System.Boolean overwrite { get; set }`  

```csharp
public System.Boolean overwrite { get; set; }
```

- `private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get }`  

```csharp
private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get; }
```


## Constructors

- `public ZoneToolSystem()`  

```csharp
[Preserve]
	public ZoneToolSystem()
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
		if (m_State == State.Default)
		{
			switch (mode)
			{
			case Mode.FloodFill:
				m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_ZoningFillSound);
				base.applyMode = ApplyMode.Apply;
				break;
			case Mode.Paint:
				m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_ZoningStartPaintSound);
				base.applyMode = ApplyMode.Apply;
				break;
			case Mode.Marquee:
				m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_ZoningMarqueeStartSound);
				base.applyMode = ApplyMode.Clear;
				break;
			}
			if (!singleFrameOnly)
			{
				m_StartPoint = m_SnapPoint.value;
				m_State = State.Zoning;
			}
			GetRaycastResult(out m_RaycastPoint);
			inputDeps = SnapPoint(inputDeps);
			return UpdateDefinitions(inputDeps);
		}
		if (m_State == State.Zoning)
		{
			base.applyMode = ApplyMode.Apply;
			if (math.distance(m_StartPoint.m_Position, m_RaycastPoint.m_Position) > 5f && mode == Mode.Marquee)
			{
				m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_ZoningMarqueeEndSound);
			}
			if (mode == Mode.Paint)
			{
				m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_ZoningEndPaintSound);
			}
			m_StartPoint = default(ControlPoint);
			m_State = State.Default;
			GetRaycastResult(out m_RaycastPoint);
			inputDeps = SnapPoint(inputDeps);
			return UpdateDefinitions(inputDeps);
		}
		base.applyMode = ApplyMode.Clear;
		m_StartPoint = default(ControlPoint);
		m_State = State.Default;
		GetRaycastResult(out m_RaycastPoint);
		inputDeps = SnapPoint(inputDeps);
		return UpdateDefinitions(inputDeps);
	}
```

- `private Cancel(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly = False) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle Cancel(JobHandle inputDeps, bool singleFrameOnly = false)
	{
		if (m_State == State.Default)
		{
			switch (mode)
			{
			case Mode.FloodFill:
				m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_ZoningRemoveFillSound);
				base.applyMode = ApplyMode.Apply;
				break;
			case Mode.Paint:
				m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_ZoningStartRemovePaintSound);
				base.applyMode = ApplyMode.Apply;
				break;
			case Mode.Marquee:
				m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_ZoningMarqueeClearStartSound);
				base.applyMode = ApplyMode.Clear;
				break;
			}
			if (!singleFrameOnly)
			{
				m_StartPoint = m_SnapPoint.value;
				m_State = State.Dezoning;
			}
			GetRaycastResult(out m_RaycastPoint);
			JobHandle jobHandle = SnapPoint(inputDeps);
			JobHandle job = SetZoneType(jobHandle);
			JobHandle job2 = UpdateDefinitions(jobHandle);
			return JobHandle.CombineDependencies(job, job2);
		}
		if (m_State == State.Dezoning)
		{
			base.applyMode = ApplyMode.Apply;
			if (math.distance(m_StartPoint.m_Position, m_RaycastPoint.m_Position) > 5f && mode == Mode.Marquee)
			{
				m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_ZoningMarqueeClearEndSound);
			}
			if (mode == Mode.Paint)
			{
				m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_ZoningEndRemovePaintSound);
			}
			m_StartPoint = default(ControlPoint);
			m_State = State.Default;
			GetRaycastResult(out m_RaycastPoint);
			inputDeps = SnapPoint(inputDeps);
			return UpdateDefinitions(inputDeps);
		}
		base.applyMode = ApplyMode.Clear;
		m_StartPoint = default(ControlPoint);
		m_State = State.Default;
		GetRaycastResult(out m_RaycastPoint);
		inputDeps = SnapPoint(inputDeps);
		return UpdateDefinitions(inputDeps);
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

- `protected GetAllowApplyZone() : System.Boolean`  

```csharp
protected bool GetAllowApplyZone()
	{
		Mode mode = this.mode;
		if ((uint)(mode - 1) <= 1u)
		{
			return true;
		}
		GetRaycastResult(out Entity entity, out RaycastHit _);
		if (entity == Entity.Null)
		{
			return false;
		}
		if (!base.EntityManager.TryGetComponent<Block>(entity, out var _))
		{
			return false;
		}
		Entity entity2 = m_PrefabSystem.GetEntity(prefab);
		if (entity2 == Entity.Null)
		{
			return false;
		}
		if (!base.EntityManager.TryGetComponent<ZoneData>(entity2, out var component2))
		{
			return false;
		}
		if (!base.EntityManager.TryGetBuffer(entity, isReadOnly: true, out DynamicBuffer<Cell> buffer))
		{
			return false;
		}
		for (int i = 0; i < buffer.Length; i++)
		{
			if (buffer[i].m_Zone.m_Index != component2.m_ZoneType.m_Index)
			{
				return true;
			}
		}
		return false;
	}
```

- `protected GetAllowRemoveZone() : System.Boolean`  

```csharp
protected bool GetAllowRemoveZone()
	{
		Mode mode = this.mode;
		if ((uint)(mode - 1) <= 1u)
		{
			return true;
		}
		GetRaycastResult(out Entity entity, out RaycastHit _);
		if (entity == Entity.Null)
		{
			return false;
		}
		if (!base.EntityManager.TryGetComponent<Block>(entity, out var _))
		{
			return false;
		}
		if (!base.EntityManager.TryGetBuffer(entity, isReadOnly: true, out DynamicBuffer<Cell> buffer))
		{
			return false;
		}
		for (int i = 0; i < buffer.Length; i++)
		{
			if (buffer[i].m_Zone.m_Index != 0)
			{
				return true;
			}
		}
		return false;
	}
```

- `public virtual GetAvailableSnapMask(Game.Tools.Snap& onMask, Game.Tools.Snap& offMask) : System.Void`  

```csharp
public override void GetAvailableSnapMask(out Snap onMask, out Snap offMask)
	{
		switch (mode)
		{
		case Mode.FloodFill:
		case Mode.Paint:
			onMask = Snap.ExistingGeometry;
			offMask = Snap.None;
			break;
		case Mode.Marquee:
			onMask = Snap.ExistingGeometry | Snap.CellLength;
			offMask = Snap.ExistingGeometry | Snap.CellLength;
			break;
		default:
			base.GetAvailableSnapMask(out onMask, out offMask);
			break;
		}
		onMask |= Snap.ContourLines;
		offMask |= Snap.ContourLines;
	}
```

- `public virtual GetPrefab() : Game.Prefabs.PrefabBase`  

```csharp
public override PrefabBase GetPrefab()
	{
		return prefab;
	}
```

- `public virtual GetUIModes(System.Collections.Generic.List<Game.Tools.ToolMode> modes) : System.Void`  

```csharp
public override void GetUIModes(List<ToolMode> modes)
	{
		modes.Add(new ToolMode(Mode.FloodFill.ToString(), 0));
		modes.Add(new ToolMode(Mode.Marquee.ToString(), 1));
		modes.Add(new ToolMode(Mode.Paint.ToString(), 2));
	}
```

- `public virtual InitializeRaycast() : System.Void`  

```csharp
public override void InitializeRaycast()
	{
		base.InitializeRaycast();
		if (prefab != null)
		{
			GetAvailableSnapMask(out var onMask, out var offMask);
			switch (mode)
			{
			case Mode.FloodFill:
			case Mode.Paint:
				m_ToolRaycastSystem.typeMask = TypeMask.Terrain | TypeMask.Zones;
				break;
			case Mode.Marquee:
				if ((ToolBaseSystem.GetActualSnap(selectedSnap, onMask, offMask) & Snap.ExistingGeometry) != Snap.None)
				{
					m_ToolRaycastSystem.typeMask = TypeMask.Terrain | TypeMask.Zones;
				}
				else
				{
					m_ToolRaycastSystem.typeMask = TypeMask.Terrain;
				}
				break;
			default:
				m_ToolRaycastSystem.typeMask = TypeMask.None;
				break;
			}
		}
		else
		{
			m_ToolRaycastSystem.typeMask = TypeMask.None;
		}
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
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_DefinitionGroup = GetDefinitionQuery();
		m_TempBlockQuery = GetEntityQuery(ComponentType.ReadOnly<Temp>(), ComponentType.ReadOnly<Block>(), ComponentType.ReadWrite<Cell>());
		m_SoundQuery = GetEntityQuery(ComponentType.ReadOnly<ToolUXSoundSettingsData>());
		m_ApplyZone = InputManager.instance.toolActionCollection.GetActionState("Apply Zone", "ZoneToolSystem");
		m_RemoveZone = InputManager.instance.toolActionCollection.GetActionState("Remove Zone", "ZoneToolSystem");
		m_DiscardZoning = InputManager.instance.toolActionCollection.GetActionState("Discard Zoning", "ZoneToolSystem");
		m_DiscardDezoning = InputManager.instance.toolActionCollection.GetActionState("Discard Dezoning", "ZoneToolSystem");
		m_DefaultDiscardApply = InputManager.instance.toolActionCollection.GetActionState("Discard Primary", "ZoneToolSystem");
		m_DefaultDiscardRemove = InputManager.instance.toolActionCollection.GetActionState("Discard Secondary", "ZoneToolSystem");
		m_SnapPoint = new NativeValue<ControlPoint>(Allocator.Persistent);
		overwrite = true;
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
		m_SnapPoint.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnStartRunning() : System.Void`  

```csharp
[Preserve]
	protected override void OnStartRunning()
	{
		base.OnStartRunning();
		base.requireZones = true;
		base.requireAreas = AreaTypeMask.Lots;
		m_RaycastPoint = default(ControlPoint);
		m_StartPoint = default(ControlPoint);
		m_State = State.Default;
		m_ApplyBlocked = false;
	}
```

- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
[Preserve]
	protected override JobHandle OnUpdate(JobHandle inputDeps)
	{
		UpdateActions();
		if (m_FocusChanged)
		{
			return inputDeps;
		}
		if (m_State != State.Default && (!base.applyAction.enabled || !base.cancelAction.enabled) && (!base.secondaryApplyAction.enabled || !base.cancelAction.enabled))
		{
			m_StartPoint = default(ControlPoint);
			m_State = State.Default;
			return Clear(inputDeps);
		}
		if (prefab != null)
		{
			UpdateInfoview(m_PrefabSystem.GetEntity(prefab));
			GetAvailableSnapMask(out m_SnapOnMask, out m_SnapOffMask);
			if ((m_ToolRaycastSystem.raycastFlags & (RaycastFlags.DebugDisable | RaycastFlags.UIDisable)) == 0)
			{
				switch (m_State)
				{
				case State.Default:
					if (m_ApplyBlocked)
					{
						if (mode != Mode.Marquee || base.applyAction.WasReleasedThisFrame() || base.secondaryApplyAction.WasReleasedThisFrame())
						{
							m_ApplyBlocked = false;
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
				case State.Zoning:
					if (base.cancelAction.WasPressedThisFrame())
					{
						m_ApplyBlocked = mode == Mode.Marquee;
						return Cancel(inputDeps);
					}
					if (base.applyAction.WasPressedThisFrame() || base.applyAction.WasReleasedThisFrame())
					{
						return Apply(inputDeps);
					}
					return Update(inputDeps);
				case State.Dezoning:
					if (base.cancelAction.WasPressedThisFrame())
					{
						m_ApplyBlocked = mode == Mode.Marquee;
						return Apply(inputDeps);
					}
					if (base.secondaryApplyAction.WasPressedThisFrame() || base.secondaryApplyAction.WasReleasedThisFrame())
					{
						return Cancel(inputDeps);
					}
					return Update(inputDeps);
				}
			}
		}
		else
		{
			UpdateInfoview(Entity.Null);
		}
		if (m_State != State.Default && (base.applyAction.WasReleasedThisFrame() || base.secondaryApplyAction.WasReleasedThisFrame()))
		{
			m_StartPoint = default(ControlPoint);
			m_State = State.Default;
		}
		return Clear(inputDeps);
	}
```

- `private SetZoneType(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle SetZoneType(JobHandle inputDeps)
	{
		if (m_TempBlockQuery.IsEmptyIgnoreFilter)
		{
			return inputDeps;
		}
		return JobChunkExtensions.ScheduleParallel(new SetZoneTypeJob
		{
			m_Type = default(ZoneType),
			m_BlockType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Zones_Block_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CellType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Zones_Cell_RW_BufferTypeHandle, ref base.CheckedStateRef)
		}, m_TempBlockQuery, inputDeps);
	}
```

- `private SnapPoint(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle SnapPoint(JobHandle inputDeps)
	{
		if (m_RaycastPoint.Equals(default(ControlPoint)))
		{
			m_SnapPoint.value = default(ControlPoint);
			return inputDeps;
		}
		JobHandle outJobHandle;
		NativeList<ArchetypeChunk> tempChunks = m_TempBlockQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle);
		Transform transform = Camera.main.transform;
		JobHandle jobHandle = IJobExtensions.Schedule(new SnapJob
		{
			m_Snap = GetActualSnap(),
			m_Mode = mode,
			m_State = m_State,
			m_CameraRight = transform.right,
			m_StartPoint = m_StartPoint,
			m_RaycastPoint = m_RaycastPoint,
			m_TempChunks = tempChunks,
			m_BlockType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Zones_Block_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CellType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Zones_Cell_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_BlockData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Zones_Block_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SnapPoint = m_SnapPoint
		}, JobHandle.CombineDependencies(inputDeps, outJobHandle));
		tempChunks.Dispose(jobHandle);
		return jobHandle;
	}
```

- `public virtual TrySetPrefab(Game.Prefabs.PrefabBase prefab) : System.Boolean`  

```csharp
public override bool TrySetPrefab(PrefabBase prefab)
	{
		if (prefab is ZonePrefab zonePrefab)
		{
			this.prefab = zonePrefab;
			return true;
		}
		return false;
	}
```

- `private Update(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle Update(JobHandle inputDeps)
	{
		if (GetRaycastResult(out ControlPoint controlPoint, out bool forceUpdate))
		{
			ControlPoint value = m_SnapPoint.value;
			if (m_RaycastPoint.Equals(controlPoint) && !forceUpdate)
			{
				switch (this.mode)
				{
				case Mode.FloodFill:
				case Mode.Paint:
					if (m_State == State.Default || m_StartPoint.Equals(value))
					{
						base.applyMode = ApplyMode.None;
						return inputDeps;
					}
					break;
				case Mode.Marquee:
					base.applyMode = ApplyMode.None;
					return inputDeps;
				}
			}
			else
			{
				m_RaycastPoint = controlPoint;
				inputDeps = SnapPoint(inputDeps);
				JobHandle.ScheduleBatchedJobs();
				inputDeps.Complete();
			}
			if (value.Equals(m_SnapPoint.value) && !forceUpdate)
			{
				switch (this.mode)
				{
				case Mode.FloodFill:
				case Mode.Paint:
					if (m_State == State.Default || m_StartPoint.Equals(value))
					{
						base.applyMode = ApplyMode.None;
						return inputDeps;
					}
					break;
				case Mode.Marquee:
					base.applyMode = ApplyMode.None;
					return inputDeps;
				}
			}
			switch (this.mode)
			{
			case Mode.FloodFill:
			case Mode.Paint:
				if (m_State != State.Default)
				{
					base.applyMode = ApplyMode.Apply;
					m_StartPoint = value;
				}
				else
				{
					base.applyMode = ApplyMode.Clear;
				}
				return UpdateDefinitions(inputDeps);
			case Mode.Marquee:
				base.applyMode = ApplyMode.Clear;
				return UpdateDefinitions(inputDeps);
			}
		}
		else
		{
			if (m_RaycastPoint.Equals(default(ControlPoint)))
			{
				base.applyMode = (forceUpdate ? ApplyMode.Clear : ApplyMode.None);
				return inputDeps;
			}
			m_RaycastPoint = default(ControlPoint);
			Mode mode = this.mode;
			if ((mode == Mode.FloodFill || mode == Mode.Paint) && m_State != State.Default)
			{
				m_StartPoint = m_SnapPoint.value;
				base.applyMode = ApplyMode.Apply;
				inputDeps = SnapPoint(inputDeps);
				return UpdateDefinitions(inputDeps);
			}
		}
		base.applyMode = ApplyMode.Clear;
		inputDeps = SnapPoint(inputDeps);
		return UpdateDefinitions(inputDeps);
	}
```

- `private virtual UpdateActions() : System.Void`  

```csharp
private protected override void UpdateActions()
	{
		using (ProxyAction.DeferStateUpdating())
		{
			switch (m_State)
			{
			case State.Zoning:
				base.applyAction.enabled = base.actionsEnabled;
				base.secondaryApplyAction.enabled = false;
				base.cancelAction.enabled = base.actionsEnabled;
				base.applyActionOverride = m_ApplyZone;
				base.secondaryApplyActionOverride = null;
				base.cancelActionOverride = ((mode == Mode.Marquee) ? m_DiscardZoning : m_DefaultDiscardApply);
				break;
			case State.Dezoning:
				base.applyAction.enabled = false;
				base.secondaryApplyAction.enabled = base.actionsEnabled;
				base.cancelAction.enabled = base.actionsEnabled;
				base.applyActionOverride = null;
				base.secondaryApplyActionOverride = m_RemoveZone;
				base.cancelActionOverride = ((mode == Mode.Marquee) ? m_DiscardDezoning : m_DefaultDiscardRemove);
				break;
			default:
				base.applyAction.enabled = base.actionsEnabled && GetAllowApplyZone();
				base.secondaryApplyAction.enabled = base.actionsEnabled && GetAllowRemoveZone();
				base.cancelAction.enabled = false;
				base.applyActionOverride = m_ApplyZone;
				base.secondaryApplyActionOverride = m_RemoveZone;
				base.cancelActionOverride = null;
				break;
			}
		}
	}
```

- `private UpdateDefinitions(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle UpdateDefinitions(JobHandle inputDeps)
	{
		JobHandle jobHandle = DestroyDefinitions(m_DefinitionGroup, m_ToolOutputBarrier, inputDeps);
		if (!m_RaycastPoint.Equals(default(ControlPoint)))
		{
			Transform transform = Camera.main.transform;
			JobHandle jobHandle2 = IJobExtensions.Schedule(new CreateDefinitionsJob
			{
				m_Prefab = m_PrefabSystem.GetEntity(prefab),
				m_Mode = mode,
				m_State = m_State,
				m_CameraRight = transform.right,
				m_Overwrite = overwrite,
				m_StartPoint = m_StartPoint,
				m_SnapPoint = m_SnapPoint,
				m_TerrainHeightData = m_TerrainSystem.GetHeightData(),
				m_BlockData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Zones_Block_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CommandBuffer = m_ToolOutputBarrier.CreateCommandBuffer()
			}, inputDeps);
			m_ToolOutputBarrier.AddJobHandleForProducer(jobHandle2);
			m_TerrainSystem.AddCPUHeightReader(jobHandle2);
			jobHandle = JobHandle.CombineDependencies(jobHandle, jobHandle2);
		}
		return jobHandle;
	}
```


## Nested types

- `Game.Tools.ZoneToolSystem+Mode`  
- `Game.Tools.ZoneToolSystem+State`  
- `Game.Tools.ZoneToolSystem+SetZoneTypeJob`  
- `Game.Tools.ZoneToolSystem+SnapJob`  
- `Game.Tools.ZoneToolSystem+CreateDefinitionsJob`  
- `Game.Tools.ZoneToolSystem+TypeHandle`  
- `Game.Tools.ZoneToolSystem+<get_toolActions>d__34`  

