# Game.Tools.DefaultToolSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.Tools.ToolBaseSystem`  
**Implements:** `System.IEquatable<Game.Tools.ToolBaseSystem>`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class DefaultToolSystem : Game.Tools.ToolBaseSystem, System.IEquatable<Game.Tools.ToolBaseSystem>
{
    private System.Boolean <underground>k__BackingField;
    private System.Boolean <ignoreErrors>k__BackingField;
    private System.Boolean <allowManipulation>k__BackingField;
    private System.Boolean <debugSelect>k__BackingField;
    private System.Boolean <debugLandValue>k__BackingField;
    private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
    private Game.Audio.AudioManager m_AudioManager;
    private Game.Rendering.RenderingSystem m_RenderingSystem;
    private Unity.Entities.EntityQuery m_DefinitionQuery;
    private Unity.Entities.EntityQuery m_DragQuery;
    private Unity.Entities.EntityQuery m_TempQuery;
    private Unity.Entities.EntityQuery m_InfomodeQuery;
    private Unity.Entities.EntityQuery m_SoundQuery;
    private Unity.Entities.EntityQuery m_UpdateQuery;
    private Unity.Entities.Entity m_LastRaycastEntity;
    private Unity.Mathematics.float3 m_MouseDownPosition;
    private Game.Tools.DefaultToolSystem+State m_State;
    private Game.Input.IProxyAction m_DefaultToolApply;
    private System.Int32 m_LastSelectedIndex;
    private Game.Tools.DefaultToolSystem+TypeHandle __TypeHandle;
    public static const System.String kToolID;

    public System.String toolID { get; }
    public System.Boolean allowUnderground { get; }
    public System.Boolean underground { get; set; }
    public System.Boolean ignoreErrors { get; set; }
    public System.Boolean allowManipulation { get; set; }
    public System.Boolean debugSelect { get; set; }
    public System.Boolean debugLandValue { get; set; }
    private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get; }

    public DefaultToolSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private Unity.Jobs.JobHandle Apply(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly, System.Boolean toggleSelected);
    private Unity.Jobs.JobHandle Cancel(Unity.Jobs.JobHandle inputDeps);
    private Unity.Jobs.JobHandle Clear(Unity.Jobs.JobHandle inputDeps);
    public virtual System.Void ElevationDown();
    public virtual System.Void ElevationScroll();
    public virtual System.Void ElevationUp();
    public virtual Game.Prefabs.PrefabBase GetPrefab();
    public virtual System.Void InitializeRaycast();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnStartRunning();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
    private System.Void PlaySelectedSound(Unity.Entities.Entity selected, System.Boolean forcePlay);
    private Unity.Jobs.JobHandle SelectTempEntity(Unity.Jobs.JobHandle inputDeps, System.Boolean toggleSelected);
    private System.Void SetInfomodeRaycastSettings();
    private System.Void SetState(Game.Tools.DefaultToolSystem+State state);
    public virtual System.Void SetUnderground(System.Boolean underground);
    private System.Void StartDragging(Game.Common.RaycastHit raycastHit);
    private System.Void StopDragging();
    public virtual System.Boolean TrySetPrefab(Game.Prefabs.PrefabBase prefab);
    private Unity.Jobs.JobHandle Update(Unity.Jobs.JobHandle inputDeps);
    private virtual System.Void UpdateActions();
    private Unity.Jobs.JobHandle UpdateDefinitions(Unity.Jobs.JobHandle inputDeps, Unity.Entities.Entity entity, System.Int32 index, Unity.Mathematics.float3 position, System.Boolean setPosition);
}
```


## Fields

- `private System.Boolean <underground>k__BackingField`  

```csharp
private System.Boolean <underground>k__BackingField;
```

- `private System.Boolean <ignoreErrors>k__BackingField`  

```csharp
private System.Boolean <ignoreErrors>k__BackingField;
```

- `private System.Boolean <allowManipulation>k__BackingField`  

```csharp
private System.Boolean <allowManipulation>k__BackingField;
```

- `private System.Boolean <debugSelect>k__BackingField`  

```csharp
private System.Boolean <debugSelect>k__BackingField;
```

- `private System.Boolean <debugLandValue>k__BackingField`  

```csharp
private System.Boolean <debugLandValue>k__BackingField;
```

- `private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier`  

```csharp
private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
```

- `private Game.Audio.AudioManager m_AudioManager`  

```csharp
private Game.Audio.AudioManager m_AudioManager;
```

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  

```csharp
private Game.Rendering.RenderingSystem m_RenderingSystem;
```

- `private Unity.Entities.EntityQuery m_DefinitionQuery`  

```csharp
private Unity.Entities.EntityQuery m_DefinitionQuery;
```

- `private Unity.Entities.EntityQuery m_DragQuery`  

```csharp
private Unity.Entities.EntityQuery m_DragQuery;
```

- `private Unity.Entities.EntityQuery m_TempQuery`  

```csharp
private Unity.Entities.EntityQuery m_TempQuery;
```

- `private Unity.Entities.EntityQuery m_InfomodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_InfomodeQuery;
```

- `private Unity.Entities.EntityQuery m_SoundQuery`  

```csharp
private Unity.Entities.EntityQuery m_SoundQuery;
```

- `private Unity.Entities.EntityQuery m_UpdateQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdateQuery;
```

- `private Unity.Entities.Entity m_LastRaycastEntity`  

```csharp
private Unity.Entities.Entity m_LastRaycastEntity;
```

- `private Unity.Mathematics.float3 m_MouseDownPosition`  

```csharp
private Unity.Mathematics.float3 m_MouseDownPosition;
```

- `private Game.Tools.DefaultToolSystem+State m_State`  

```csharp
private Game.Tools.DefaultToolSystem+State m_State;
```

- `private Game.Input.IProxyAction m_DefaultToolApply`  

```csharp
private Game.Input.IProxyAction m_DefaultToolApply;
```

- `private System.Int32 m_LastSelectedIndex`  

```csharp
private System.Int32 m_LastSelectedIndex;
```

- `private Game.Tools.DefaultToolSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.DefaultToolSystem+TypeHandle __TypeHandle;
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

- `public System.Boolean allowUnderground { get }`  

```csharp
public System.Boolean allowUnderground { get; }
```

- `public System.Boolean underground { get; set }`  

```csharp
public System.Boolean underground { get; set; }
```

- `public System.Boolean ignoreErrors { get; set }`  

```csharp
public System.Boolean ignoreErrors { get; set; }
```

- `public System.Boolean allowManipulation { get; set }`  

```csharp
public System.Boolean allowManipulation { get; set; }
```

- `public System.Boolean debugSelect { get; set }`  

```csharp
public System.Boolean debugSelect { get; set; }
```

- `public System.Boolean debugLandValue { get; set }`  

```csharp
public System.Boolean debugLandValue { get; set; }
```

- `private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get }`  

```csharp
private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get; }
```


## Constructors

- `public DefaultToolSystem()`  

```csharp
[Preserve]
	public DefaultToolSystem()
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

- `private Apply(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly = False, System.Boolean toggleSelected = False) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle Apply(JobHandle inputDeps, bool singleFrameOnly = false, bool toggleSelected = false)
	{
		switch (m_State)
		{
		case State.Default:
			if (!singleFrameOnly)
			{
				SetState(State.MouseDownPrepare);
			}
			base.applyMode = ApplyMode.None;
			return SelectTempEntity(inputDeps, toggleSelected);
		case State.Dragging:
			StopDragging();
			base.applyMode = ApplyMode.Apply;
			return inputDeps;
		default:
			SetState(State.Default);
			base.applyMode = ApplyMode.None;
			return inputDeps;
		}
	}
```

- `private Cancel(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle Cancel(JobHandle inputDeps)
	{
		switch (m_State)
		{
		case State.Dragging:
			StopDragging();
			base.applyMode = ApplyMode.None;
			return inputDeps;
		case State.Default:
			base.applyMode = ApplyMode.None;
			m_ToolSystem.selected = Entity.Null;
			return inputDeps;
		default:
			SetState(State.Default);
			base.applyMode = ApplyMode.None;
			return inputDeps;
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
		return null;
	}
```

- `public virtual InitializeRaycast() : System.Void`  

```csharp
public override void InitializeRaycast()
	{
		base.InitializeRaycast();
		if (underground)
		{
			m_ToolRaycastSystem.collisionMask = CollisionMask.Underground;
		}
		else
		{
			m_ToolRaycastSystem.collisionMask = CollisionMask.OnGround | CollisionMask.Overground;
		}
		if (m_State != State.Default)
		{
			m_ToolRaycastSystem.typeMask = TypeMask.Terrain | TypeMask.Net;
			m_ToolRaycastSystem.netLayerMask = Layer.Road;
			m_ToolRaycastSystem.areaTypeMask = AreaTypeMask.None;
			m_ToolRaycastSystem.iconLayerMask = IconLayerMask.None;
		}
		else
		{
			m_ToolRaycastSystem.typeMask = TypeMask.StaticObjects | TypeMask.MovingObjects | TypeMask.Labels | TypeMask.Icons;
			m_ToolRaycastSystem.raycastFlags |= RaycastFlags.OutsideConnections | RaycastFlags.Decals | RaycastFlags.BuildingLots;
			m_ToolRaycastSystem.netLayerMask = Layer.None;
			m_ToolRaycastSystem.areaTypeMask = AreaTypeMask.None;
			m_ToolRaycastSystem.iconLayerMask = IconLayerMask.Default;
			if (!underground)
			{
				m_ToolRaycastSystem.typeMask |= TypeMask.Areas;
				m_ToolRaycastSystem.areaTypeMask |= AreaTypeMask.Lots;
			}
			if (debugSelect)
			{
				m_ToolRaycastSystem.typeMask |= TypeMask.Net;
				m_ToolRaycastSystem.raycastFlags |= RaycastFlags.SubElements;
				m_ToolRaycastSystem.netLayerMask |= Layer.All;
				if (m_RenderingSystem.markersVisible)
				{
					m_ToolRaycastSystem.raycastFlags |= RaycastFlags.Markers;
				}
			}
			else if (debugLandValue)
			{
				m_ToolRaycastSystem.typeMask |= TypeMask.Terrain;
			}
			if (!m_InfomodeQuery.IsEmptyIgnoreFilter)
			{
				SetInfomodeRaycastSettings();
			}
		}
		if (m_ToolSystem.actionMode.IsEditor())
		{
			m_ToolRaycastSystem.raycastFlags |= RaycastFlags.SubElements | RaycastFlags.Placeholders | RaycastFlags.Markers | RaycastFlags.UpgradeIsMain | RaycastFlags.EditorContainers;
		}
		else
		{
			m_ToolRaycastSystem.raycastFlags |= RaycastFlags.SubBuildings;
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
		m_RenderingSystem = base.World.GetOrCreateSystemManaged<RenderingSystem>();
		m_DefinitionQuery = GetDefinitionQuery();
		m_DragQuery = GetEntityQuery(ComponentType.ReadOnly<Temp>(), ComponentType.Exclude<Owner>());
		m_TempQuery = GetEntityQuery(ComponentType.ReadOnly<Temp>());
		m_InfomodeQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<InfomodeActive>() },
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<InfoviewRouteData>(),
				ComponentType.ReadOnly<InfoviewNetStatusData>(),
				ComponentType.ReadOnly<InfoviewHeatmapData>()
			}
		});
		m_SoundQuery = GetEntityQuery(ComponentType.ReadOnly<ToolUXSoundSettingsData>());
		m_UpdateQuery = GetEntityQuery(ComponentType.ReadOnly<ColorUpdated>());
		m_DefaultToolApply = InputManager.instance.toolActionCollection.GetActionState("Default Tool", GetType().Name);
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
		m_LastRaycastEntity = Entity.Null;
		SetState(State.Default);
		base.applyMode = ApplyMode.None;
		base.requireUnderground = false;
	}
```

- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
[Preserve]
	protected override JobHandle OnUpdate(JobHandle inputDeps)
	{
		base.requireUnderground = underground;
		m_ForceUpdate |= !m_UpdateQuery.IsEmptyIgnoreFilter;
		if ((m_ToolRaycastSystem.raycastFlags & (RaycastFlags.DebugDisable | RaycastFlags.UIDisable)) == 0)
		{
			JobHandle result = ((m_State == State.Default && base.applyAction.WasPressedThisFrame()) ? Apply(inputDeps, base.applyAction.WasReleasedThisFrame(), base.cancelAction.WasPressedThisFrame()) : ((m_State != State.Default && base.applyAction.WasReleasedThisFrame()) ? Apply(inputDeps) : ((!base.cancelAction.IsInProgress()) ? Update(inputDeps) : Cancel(inputDeps))));
			UpdateActions();
			return result;
		}
		if (m_State == State.Default)
		{
			m_LastRaycastEntity = Entity.Null;
		}
		else if (base.applyAction.WasReleasedThisFrame())
		{
			m_LastRaycastEntity = Entity.Null;
			SetState(State.Default);
		}
		UpdateActions();
		return Clear(inputDeps);
	}
```

- `private PlaySelectedSound(Unity.Entities.Entity selected, System.Boolean forcePlay = False) : System.Void`  

```csharp
private void PlaySelectedSound(Entity selected, bool forcePlay = false)
	{
		Game.Creatures.Resident component;
		Citizen component2;
		PrefabRef component3;
		PrefabRef component4;
		SelectedSoundData component5;
		Entity clipEntity = ((base.EntityManager.TryGetComponent<Game.Creatures.Resident>(selected, out component) && base.EntityManager.TryGetComponent<Citizen>(component.m_Citizen, out component2) && base.EntityManager.TryGetComponent<PrefabRef>(component.m_Citizen, out component3)) ? CitizenUtils.GetCitizenSelectedSound(base.EntityManager, component.m_Citizen, component2, component3.m_Prefab) : ((!base.EntityManager.TryGetComponent<PrefabRef>(selected, out component4) || !base.EntityManager.TryGetComponent<SelectedSoundData>(component4.m_Prefab, out component5)) ? m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_SelectEntitySound : component5.m_selectedSound));
		if (forcePlay)
		{
			m_AudioManager.PlayUISound(clipEntity);
		}
		else
		{
			m_AudioManager.PlayUISoundIfNotPlaying(clipEntity);
		}
	}
```

- `private SelectTempEntity(Unity.Jobs.JobHandle inputDeps, System.Boolean toggleSelected) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle SelectTempEntity(JobHandle inputDeps, bool toggleSelected)
	{
		if (m_TempQuery.IsEmptyIgnoreFilter)
		{
			m_ToolSystem.selected = Entity.Null;
			return inputDeps;
		}
		JobHandle outJobHandle;
		NativeList<ArchetypeChunk> chunks = m_TempQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle);
		NativeReference<Entity> selected = new NativeReference<Entity>(Allocator.TempJob);
		JobHandle jobHandle = IJobExtensions.Schedule(new SelectEntityJob
		{
			m_Chunks = chunks,
			m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_AttachmentType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Attachment_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ControllerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_Controller_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EntityLookup = InternalCompilerInterface.GetEntityStorageInfoLookup(ref __TypeHandle.__EntityStorageInfoLookup, ref base.CheckedStateRef),
			m_TempData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TargetData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Target_RO_ComponentLookup, ref base.CheckedStateRef),
			m_DebugData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Debug_RO_ComponentLookup, ref base.CheckedStateRef),
			m_IconData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Notifications_Icon_RO_ComponentLookup, ref base.CheckedStateRef),
			m_VehicleData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Vehicle_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentLookup, ref base.CheckedStateRef),
			m_DebugSelect = debugSelect,
			m_Selected = selected,
			m_CommandBuffer = m_ToolOutputBarrier.CreateCommandBuffer()
		}, JobHandle.CombineDependencies(inputDeps, outJobHandle));
		chunks.Dispose(jobHandle);
		m_ToolOutputBarrier.AddJobHandleForProducer(jobHandle);
		jobHandle.Complete();
		if (!base.EntityManager.HasBuffer<AggregateElement>(selected.Value))
		{
			m_LastSelectedIndex = -1;
		}
		if (m_ToolSystem.selected != selected.Value || m_ToolSystem.selectedIndex != m_LastSelectedIndex)
		{
			m_ToolSystem.selected = selected.Value;
			m_ToolSystem.selectedIndex = m_LastSelectedIndex;
			PlaySelectedSound(selected.Value, forcePlay: true);
		}
		else if (toggleSelected)
		{
			m_ToolSystem.selected = Entity.Null;
		}
		else
		{
			PlaySelectedSound(selected.Value);
		}
		selected.Dispose();
		return jobHandle;
	}
```

- `private SetInfomodeRaycastSettings() : System.Void`  

```csharp
private void SetInfomodeRaycastSettings()
	{
		NativeArray<Entity> nativeArray = m_InfomodeQuery.ToEntityArray(Allocator.TempJob);
		try
		{
			for (int i = 0; i < nativeArray.Length; i++)
			{
				Entity entity = nativeArray[i];
				if (base.EntityManager.TryGetComponent<InfoviewRouteData>(entity, out var component))
				{
					m_ToolRaycastSystem.typeMask |= TypeMask.RouteWaypoints | TypeMask.RouteSegments;
					m_ToolRaycastSystem.routeType = component.m_Type;
				}
				if (base.EntityManager.TryGetComponent<InfoviewNetStatusData>(entity, out var component2))
				{
					switch (component2.m_Type)
					{
					case NetStatusType.LowVoltageFlow:
						m_ToolRaycastSystem.typeMask |= TypeMask.Lanes;
						m_ToolRaycastSystem.utilityTypeMask |= UtilityTypes.LowVoltageLine;
						break;
					case NetStatusType.HighVoltageFlow:
						m_ToolRaycastSystem.typeMask |= TypeMask.Lanes;
						m_ToolRaycastSystem.utilityTypeMask |= UtilityTypes.HighVoltageLine;
						break;
					case NetStatusType.PipeWaterFlow:
						m_ToolRaycastSystem.typeMask |= TypeMask.Lanes;
						m_ToolRaycastSystem.utilityTypeMask |= UtilityTypes.WaterPipe;
						break;
					case NetStatusType.PipeSewageFlow:
						m_ToolRaycastSystem.typeMask |= TypeMask.Lanes;
						m_ToolRaycastSystem.utilityTypeMask |= UtilityTypes.SewagePipe;
						break;
					}
				}
			}
		}
		finally
		{
			nativeArray.Dispose();
		}
	}
```

- `private SetState(Game.Tools.DefaultToolSystem+State state) : System.Void`  

```csharp
private void SetState(State state)
	{
		m_State = state;
	}
```

- `public virtual SetUnderground(System.Boolean underground) : System.Void`  

```csharp
public override void SetUnderground(bool underground)
	{
		this.underground = underground;
	}
```

- `private StartDragging(Game.Common.RaycastHit raycastHit) : System.Void`  

```csharp
private void StartDragging(RaycastHit raycastHit)
	{
		Entity entity = Entity.Null;
		Temp component = default(Temp);
		Transform component2 = default(Transform);
		bool flag = false;
		if (allowManipulation && !m_DragQuery.IsEmptyIgnoreFilter)
		{
			NativeArray<ArchetypeChunk> nativeArray = m_DragQuery.ToArchetypeChunkArray(Allocator.TempJob);
			try
			{
				entity = nativeArray[0].GetNativeArray(GetEntityTypeHandle())[0];
				ComponentTypeHandle<Temp> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef);
				component = nativeArray[0].GetNativeArray(ref typeHandle)[0];
				ComponentTypeHandle<Transform> typeHandle2 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef);
				NativeArray<Transform> nativeArray2 = nativeArray[0].GetNativeArray(ref typeHandle2);
				if (nativeArray2.Length != 0)
				{
					component2 = nativeArray2[0];
					flag = base.EntityManager.HasComponent<Moving>(entity) || base.EntityManager.HasComponent<Game.Objects.Marker>(entity);
				}
				else
				{
					flag = false;
				}
			}
			finally
			{
				nativeArray.Dispose();
			}
		}
		if (flag)
		{
			EntityCommandBuffer entityCommandBuffer = m_ToolOutputBarrier.CreateCommandBuffer();
			component.m_Flags |= TempFlags.Dragging;
			component2.m_Position = raycastHit.m_HitPosition;
			entityCommandBuffer.SetComponent(entity, component);
			entityCommandBuffer.SetComponent(entity, component2);
			entityCommandBuffer.AddComponent(entity, default(Updated));
			SetState(State.Dragging);
		}
		else
		{
			SetState(State.Default);
		}
	}
```

- `private StopDragging() : System.Void`  

```csharp
private void StopDragging()
	{
		if (!m_DragQuery.IsEmptyIgnoreFilter)
		{
			NativeArray<ArchetypeChunk> nativeArray = m_DragQuery.ToArchetypeChunkArray(Allocator.TempJob);
			Entity e = nativeArray[0].GetNativeArray(GetEntityTypeHandle())[0];
			ComponentTypeHandle<Temp> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			Temp component = nativeArray[0].GetNativeArray(ref typeHandle)[0];
			nativeArray.Dispose();
			EntityCommandBuffer entityCommandBuffer = m_ToolOutputBarrier.CreateCommandBuffer();
			component.m_Flags &= ~TempFlags.Dragging;
			entityCommandBuffer.SetComponent(e, component);
			entityCommandBuffer.AddComponent(e, default(Updated));
		}
		SetState(State.Default);
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
		switch (m_State)
		{
		case State.Default:
		{
			if (GetRaycastResult(out var entity2, out var hit2, out var forceUpdate) && entity2 == m_LastRaycastEntity && !forceUpdate)
			{
				base.applyMode = ApplyMode.None;
				return inputDeps;
			}
			m_LastRaycastEntity = entity2;
			base.applyMode = ApplyMode.Clear;
			return UpdateDefinitions(inputDeps, entity2, hit2.m_CellIndex.x, default(float3), setPosition: false);
		}
		case State.MouseDownPrepare:
		{
			if (GetRaycastResult(out Entity _, out RaycastHit hit4))
			{
				m_MouseDownPosition = hit4.m_HitPosition;
				SetState(State.MouseDown);
			}
			base.applyMode = ApplyMode.None;
			return inputDeps;
		}
		case State.MouseDown:
		{
			if (GetRaycastResult(out Entity _, out RaycastHit hit3) && math.distance(hit3.m_HitPosition, m_MouseDownPosition) > 1f)
			{
				StartDragging(hit3);
			}
			base.applyMode = ApplyMode.None;
			return inputDeps;
		}
		case State.Dragging:
		{
			if (GetRaycastResult(out Entity _, out RaycastHit hit))
			{
				if (!m_DragQuery.IsEmptyIgnoreFilter)
				{
					NativeArray<ArchetypeChunk> nativeArray = m_DragQuery.ToArchetypeChunkArray(Allocator.TempJob);
					Entity e = nativeArray[0].GetNativeArray(GetEntityTypeHandle())[0];
					ComponentTypeHandle<Transform> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef);
					Transform component = nativeArray[0].GetNativeArray(ref typeHandle)[0];
					nativeArray.Dispose();
					EntityCommandBuffer entityCommandBuffer = m_ToolOutputBarrier.CreateCommandBuffer();
					component.m_Position = hit.m_HitPosition;
					entityCommandBuffer.SetComponent(e, component);
				}
				else if (base.EntityManager.Exists(m_LastRaycastEntity))
				{
					return UpdateDefinitions(inputDeps, m_LastRaycastEntity, hit.m_CellIndex.x, hit.m_HitPosition, setPosition: true);
				}
			}
			base.applyMode = ApplyMode.None;
			return inputDeps;
		}
		default:
			base.applyMode = ApplyMode.None;
			return inputDeps;
		}
	}
```

- `private virtual UpdateActions() : System.Void`  

```csharp
private protected override void UpdateActions()
	{
		using (ProxyAction.DeferStateUpdating())
		{
			base.applyActionOverride = ((m_LastRaycastEntity != Entity.Null) ? m_DefaultToolApply : m_MouseApply);
			base.applyAction.enabled = base.actionsEnabled;
			base.cancelActionOverride = m_MouseCancel;
			base.cancelAction.enabled = base.actionsEnabled;
		}
	}
```

- `private UpdateDefinitions(Unity.Jobs.JobHandle inputDeps, Unity.Entities.Entity entity, System.Int32 index, Unity.Mathematics.float3 position, System.Boolean setPosition) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle UpdateDefinitions(JobHandle inputDeps, Entity entity, int index, float3 position, bool setPosition)
	{
		JobHandle jobHandle = DestroyDefinitions(m_DefinitionQuery, m_ToolOutputBarrier, inputDeps);
		if (entity != Entity.Null)
		{
			JobHandle jobHandle2 = IJobExtensions.Schedule(new CreateDefinitionsJob
			{
				m_Entity = entity,
				m_Position = position,
				m_SetPosition = setPosition,
				m_Edges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedEdge_RO_BufferLookup, ref base.CheckedStateRef),
				m_InstalledUpgrades = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferLookup, ref base.CheckedStateRef),
				m_LocalTransformCacheData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_LocalTransformCache_RO_ComponentLookup, ref base.CheckedStateRef),
				m_EdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
				m_NodeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Node_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
				m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
				m_EditorContainerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_EditorContainer_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ElevationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Elevation_RO_ComponentLookup, ref base.CheckedStateRef),
				m_AttachedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Attached_RO_ComponentLookup, ref base.CheckedStateRef),
				m_AttachmentData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Attachment_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ServiceUpgradeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_ServiceUpgrade_RO_ComponentLookup, ref base.CheckedStateRef),
				m_LotData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_Lot_RO_ComponentLookup, ref base.CheckedStateRef),
				m_RoutePositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Position_RO_ComponentLookup, ref base.CheckedStateRef),
				m_RouteConnectedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Connected_RO_ComponentLookup, ref base.CheckedStateRef),
				m_IconData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Notifications_Icon_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_AreaNodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Node_RO_BufferLookup, ref base.CheckedStateRef),
				m_SubAreas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_SubArea_RO_BufferLookup, ref base.CheckedStateRef),
				m_RouteWaypoints = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_RouteWaypoint_RO_BufferLookup, ref base.CheckedStateRef),
				m_AggregateElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_AggregateElement_RO_BufferLookup, ref base.CheckedStateRef),
				m_CommandBuffer = m_ToolOutputBarrier.CreateCommandBuffer()
			}, inputDeps);
			m_ToolOutputBarrier.AddJobHandleForProducer(jobHandle2);
			jobHandle = JobHandle.CombineDependencies(jobHandle, jobHandle2);
			m_LastSelectedIndex = index;
		}
		return jobHandle;
	}
```


## Nested types

- `Game.Tools.DefaultToolSystem+State`  
- `Game.Tools.DefaultToolSystem+CreateDefinitionsJob`  
- `Game.Tools.DefaultToolSystem+SelectEntityJob`  
- `Game.Tools.DefaultToolSystem+TypeHandle`  
- `Game.Tools.DefaultToolSystem+<get_toolActions>d__41`  

