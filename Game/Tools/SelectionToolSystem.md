# Game.Tools.SelectionToolSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.Tools.ToolBaseSystem`  
**Implements:** `System.IEquatable<Game.Tools.ToolBaseSystem>`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SelectionToolSystem : Game.Tools.ToolBaseSystem, System.IEquatable<Game.Tools.ToolBaseSystem>
{
    private Game.Tools.SelectionType <selectionType>k__BackingField;
    private Unity.Entities.Entity <selectionOwner>k__BackingField;
    private Game.Areas.SearchSystem m_AreaSearchSystem;
    private Game.Areas.MapTileSystem m_MapTileSystem;
    private Game.Simulation.MapTilePurchaseSystem m_MapTilePurchaseSystem;
    private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
    private Game.Audio.AudioManager m_AudioManager;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Unity.Entities.EntityQuery m_DefinitionGroup;
    private Unity.Entities.EntityQuery m_TempGroup;
    private Unity.Entities.EntityQuery m_SoundQuery;
    private Unity.Entities.Entity m_SelectionEntity;
    private Unity.Entities.Entity m_LastOwner;
    private Game.Tools.SelectionType m_LastType;
    private Unity.Entities.EntityArchetype m_SelectionArchetype;
    private Game.Tools.SelectionToolSystem+State m_State;
    private Game.Tools.ControlPoint m_StartPoint;
    private Game.Tools.ControlPoint m_RaycastPoint;
    private Game.Input.IProxyAction m_SelectArea;
    private Game.Input.IProxyAction m_DeselectArea;
    private Game.Input.IProxyAction m_DiscardSelect;
    private Game.Input.IProxyAction m_DiscardDeselect;
    private System.Boolean m_ApplyBlocked;
    private Game.Tools.SelectionToolSystem+TypeHandle __TypeHandle;
    public static const System.String kToolID;

    public System.String toolID { get; }
    public Game.Tools.SelectionType selectionType { get; set; }
    public Unity.Entities.Entity selectionOwner { get; set; }
    public Game.Tools.SelectionToolSystem+State state { get; }
    private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get; }

    public SelectionToolSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private Unity.Jobs.JobHandle Apply(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly);
    private Unity.Jobs.JobHandle Cancel(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly);
    private Unity.Jobs.JobHandle Clear(Unity.Jobs.JobHandle inputDeps);
    private Unity.Jobs.JobHandle CopySelection(Unity.Jobs.JobHandle inputDeps);
    private Unity.Jobs.JobHandle CopyServiceDistricts(Unity.Jobs.JobHandle inputDeps);
    private Unity.Jobs.JobHandle CopyStartTiles(Unity.Jobs.JobHandle inputDeps);
    private Game.Areas.AreaType GetAreaType(Game.Tools.SelectionType selectionType);
    public virtual Game.Prefabs.PrefabBase GetPrefab();
    protected virtual System.Boolean GetRaycastResult(Game.Tools.ControlPoint& controlPoint);
    protected virtual System.Boolean GetRaycastResult(Game.Tools.ControlPoint& controlPoint, System.Boolean& forceUpdate);
    public System.Boolean GetSelectionQuad(Colossal.Mathematics.Quad3& quad);
    public virtual System.Void InitializeRaycast();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnStartRunning();
    protected virtual System.Void OnStopRunning();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
    private Unity.Jobs.JobHandle ToggleTempEntity(Unity.Jobs.JobHandle inputDeps, System.Boolean select);
    public virtual System.Boolean TrySetPrefab(Game.Prefabs.PrefabBase prefab);
    private Unity.Jobs.JobHandle Update(Unity.Jobs.JobHandle inputDeps);
    private virtual System.Void UpdateActions();
    private Unity.Jobs.JobHandle UpdateDefinitions(Unity.Jobs.JobHandle inputDeps);
    private Unity.Jobs.JobHandle UpdateSelection(Unity.Jobs.JobHandle inputDeps);
    private Unity.Jobs.JobHandle UpdateServiceDistricts(Unity.Jobs.JobHandle inputDeps);
    private Unity.Jobs.JobHandle UpdateStartTiles(Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Game.Tools.SelectionType <selectionType>k__BackingField`  

```csharp
private Game.Tools.SelectionType <selectionType>k__BackingField;
```

- `private Unity.Entities.Entity <selectionOwner>k__BackingField`  

```csharp
private Unity.Entities.Entity <selectionOwner>k__BackingField;
```

- `private Game.Areas.SearchSystem m_AreaSearchSystem`  

```csharp
private Game.Areas.SearchSystem m_AreaSearchSystem;
```

- `private Game.Areas.MapTileSystem m_MapTileSystem`  

```csharp
private Game.Areas.MapTileSystem m_MapTileSystem;
```

- `private Game.Simulation.MapTilePurchaseSystem m_MapTilePurchaseSystem`  

```csharp
private Game.Simulation.MapTilePurchaseSystem m_MapTilePurchaseSystem;
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

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Unity.Entities.EntityQuery m_DefinitionGroup`  

```csharp
private Unity.Entities.EntityQuery m_DefinitionGroup;
```

- `private Unity.Entities.EntityQuery m_TempGroup`  

```csharp
private Unity.Entities.EntityQuery m_TempGroup;
```

- `private Unity.Entities.EntityQuery m_SoundQuery`  

```csharp
private Unity.Entities.EntityQuery m_SoundQuery;
```

- `private Unity.Entities.Entity m_SelectionEntity`  

```csharp
private Unity.Entities.Entity m_SelectionEntity;
```

- `private Unity.Entities.Entity m_LastOwner`  

```csharp
private Unity.Entities.Entity m_LastOwner;
```

- `private Game.Tools.SelectionType m_LastType`  

```csharp
private Game.Tools.SelectionType m_LastType;
```

- `private Unity.Entities.EntityArchetype m_SelectionArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_SelectionArchetype;
```

- `private Game.Tools.SelectionToolSystem+State m_State`  

```csharp
private Game.Tools.SelectionToolSystem+State m_State;
```

- `private Game.Tools.ControlPoint m_StartPoint`  

```csharp
private Game.Tools.ControlPoint m_StartPoint;
```

- `private Game.Tools.ControlPoint m_RaycastPoint`  

```csharp
private Game.Tools.ControlPoint m_RaycastPoint;
```

- `private Game.Input.IProxyAction m_SelectArea`  

```csharp
private Game.Input.IProxyAction m_SelectArea;
```

- `private Game.Input.IProxyAction m_DeselectArea`  

```csharp
private Game.Input.IProxyAction m_DeselectArea;
```

- `private Game.Input.IProxyAction m_DiscardSelect`  

```csharp
private Game.Input.IProxyAction m_DiscardSelect;
```

- `private Game.Input.IProxyAction m_DiscardDeselect`  

```csharp
private Game.Input.IProxyAction m_DiscardDeselect;
```

- `private System.Boolean m_ApplyBlocked`  

```csharp
private System.Boolean m_ApplyBlocked;
```

- `private Game.Tools.SelectionToolSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.SelectionToolSystem+TypeHandle __TypeHandle;
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

- `public Game.Tools.SelectionType selectionType { get; set }`  

```csharp
public Game.Tools.SelectionType selectionType { get; set; }
```

- `public Unity.Entities.Entity selectionOwner { get; set }`  

```csharp
public Unity.Entities.Entity selectionOwner { get; set; }
```

- `public Game.Tools.SelectionToolSystem+State state { get }`  

```csharp
public Game.Tools.SelectionToolSystem+State state { get; }
```

- `private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get }`  

```csharp
private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get; }
```


## Constructors

- `public SelectionToolSystem()`  

```csharp
[Preserve]
	public SelectionToolSystem()
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
		case State.Selecting:
			if (!m_RaycastPoint.Equals(default(ControlPoint)) && GetAllowApply())
			{
				inputDeps = ToggleTempEntity(inputDeps, select: true);
				inputDeps = UpdateSelection(inputDeps);
			}
			if (math.distance(m_StartPoint.m_Position, m_RaycastPoint.m_Position) > 1f)
			{
				m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_AreaMarqueeEndSound);
			}
			m_StartPoint = default(ControlPoint);
			m_State = State.Default;
			GetRaycastResult(out m_RaycastPoint);
			base.applyMode = ApplyMode.Clear;
			return UpdateDefinitions(inputDeps);
		case State.Deselecting:
			if (math.distance(m_StartPoint.m_Position, m_RaycastPoint.m_Position) > 1f)
			{
				m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_AreaMarqueeClearEndSound);
			}
			m_StartPoint = default(ControlPoint);
			m_State = State.Default;
			GetRaycastResult(out m_RaycastPoint);
			base.applyMode = ApplyMode.Clear;
			return UpdateDefinitions(inputDeps);
		default:
			if (!m_RaycastPoint.Equals(default(ControlPoint)))
			{
				if (singleFrameOnly)
				{
					if (GetAllowApply())
					{
						inputDeps = ToggleTempEntity(inputDeps, select: true);
						inputDeps = UpdateSelection(inputDeps);
						GetRaycastResult(out m_RaycastPoint);
						base.applyMode = ApplyMode.Clear;
						return UpdateDefinitions(inputDeps);
					}
				}
				else
				{
					m_StartPoint = m_RaycastPoint;
					m_State = State.Selecting;
				}
				m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_AreaMarqueeStartSound);
			}
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
		case State.Selecting:
			m_StartPoint = default(ControlPoint);
			m_State = State.Default;
			GetRaycastResult(out m_RaycastPoint);
			base.applyMode = ApplyMode.Clear;
			m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_AreaMarqueeEndSound);
			return UpdateDefinitions(inputDeps);
		case State.Deselecting:
			if (!m_RaycastPoint.Equals(default(ControlPoint)) && GetAllowApply())
			{
				inputDeps = ToggleTempEntity(inputDeps, select: false);
				inputDeps = UpdateSelection(inputDeps);
			}
			if (math.distance(m_StartPoint.m_Position, m_RaycastPoint.m_Position) > 1f)
			{
				m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_AreaMarqueeClearEndSound);
			}
			m_StartPoint = default(ControlPoint);
			m_State = State.Default;
			GetRaycastResult(out m_RaycastPoint);
			base.applyMode = ApplyMode.Clear;
			return UpdateDefinitions(inputDeps);
		default:
			if (!m_RaycastPoint.Equals(default(ControlPoint)))
			{
				if (singleFrameOnly)
				{
					if (GetAllowApply())
					{
						inputDeps = ToggleTempEntity(inputDeps, select: false);
						inputDeps = UpdateSelection(inputDeps);
						GetRaycastResult(out m_RaycastPoint);
						base.applyMode = ApplyMode.Clear;
						return UpdateDefinitions(inputDeps);
					}
				}
				else
				{
					m_StartPoint = m_RaycastPoint;
					m_State = State.Deselecting;
				}
				m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_AreaMarqueeClearStartSound);
			}
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

- `private CopySelection(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle CopySelection(JobHandle inputDeps)
	{
		switch (selectionType)
		{
		case SelectionType.ServiceDistrict:
			return CopyServiceDistricts(inputDeps);
		case SelectionType.MapTiles:
			if (m_ToolSystem.actionMode.IsEditor())
			{
				return CopyStartTiles(inputDeps);
			}
			return inputDeps;
		default:
			return inputDeps;
		}
	}
```

- `private CopyServiceDistricts(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle CopyServiceDistricts(JobHandle inputDeps)
	{
		JobHandle jobHandle = IJobExtensions.Schedule(new CopyServiceDistrictsJob
		{
			m_SelectionEntity = m_SelectionEntity,
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ServiceDistricts = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_ServiceDistrict_RO_BufferLookup, ref base.CheckedStateRef),
			m_SelectionElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Tools_SelectionElement_RW_BufferLookup, ref base.CheckedStateRef),
			m_CommandBuffer = m_ToolOutputBarrier.CreateCommandBuffer()
		}, inputDeps);
		m_ToolOutputBarrier.AddJobHandleForProducer(jobHandle);
		return jobHandle;
	}
```

- `private CopyStartTiles(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle CopyStartTiles(JobHandle inputDeps)
	{
		return IJobExtensions.Schedule(new CopyStartTilesJob
		{
			m_SelectionEntity = m_SelectionEntity,
			m_StartTiles = m_MapTileSystem.GetStartTiles(),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SelectionElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Tools_SelectionElement_RW_BufferLookup, ref base.CheckedStateRef)
		}, inputDeps);
	}
```

- `private GetAreaType(Game.Tools.SelectionType selectionType) : Game.Areas.AreaType`  

```csharp
private AreaType GetAreaType(SelectionType selectionType)
	{
		return selectionType switch
		{
			SelectionType.ServiceDistrict => AreaType.District, 
			SelectionType.MapTiles => AreaType.MapTile, 
			_ => AreaType.None, 
		};
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
protected override bool GetRaycastResult(out ControlPoint controlPoint, out bool forceUpdate)
	{
		if (selectionType == SelectionType.MapTiles && m_ToolSystem.actionMode.IsGame() && m_MapTilePurchaseSystem.GetAvailableTiles() == 0)
		{
			controlPoint = default(ControlPoint);
			forceUpdate = false;
			return false;
		}
		return base.GetRaycastResult(out controlPoint, out forceUpdate);
	}
```

- `protected virtual GetRaycastResult(Game.Tools.ControlPoint& controlPoint, System.Boolean& forceUpdate) : System.Boolean`  

```csharp
protected override bool GetRaycastResult(out ControlPoint controlPoint, out bool forceUpdate)
	{
		if (selectionType == SelectionType.MapTiles && m_ToolSystem.actionMode.IsGame() && m_MapTilePurchaseSystem.GetAvailableTiles() == 0)
		{
			controlPoint = default(ControlPoint);
			forceUpdate = false;
			return false;
		}
		return base.GetRaycastResult(out controlPoint, out forceUpdate);
	}
```

- `public GetSelectionQuad(Colossal.Mathematics.Quad3& quad) : System.Boolean`  

```csharp
public bool GetSelectionQuad(out Quad3 quad)
	{
		Camera main = Camera.main;
		if (main == null)
		{
			quad = default(Quad3);
			return false;
		}
		Transform transform = main.transform;
		float3 @float = math.normalizesafe(new float3
		{
			xz = ((float3)transform.right).xz
		});
		float3 float2 = new float3
		{
			xz = MathUtils.Right(@float.xz)
		};
		float3 hitPosition = m_StartPoint.m_HitPosition;
		float3 x = m_RaycastPoint.m_HitPosition - hitPosition;
		float num = math.dot(x, @float);
		float num2 = math.dot(x, float2);
		if (num < 0f)
		{
			@float = -@float;
			num = 0f - num;
		}
		if (num2 < 0f)
		{
			float2 = -float2;
			num2 = 0f - num2;
		}
		quad.a = hitPosition;
		quad.b = hitPosition + float2 * num2;
		quad.c = hitPosition + @float * num + float2 * num2;
		quad.d = hitPosition + @float * num;
		TerrainHeightData terrainData = m_TerrainSystem.GetHeightData();
		JobHandle deps;
		WaterSurfaceData data = m_WaterSystem.GetSurfaceData(out deps);
		deps.Complete();
		quad.a.y = WaterUtils.SampleHeight(ref data, ref terrainData, quad.a);
		quad.b.y = WaterUtils.SampleHeight(ref data, ref terrainData, quad.b);
		quad.c.y = WaterUtils.SampleHeight(ref data, ref terrainData, quad.c);
		quad.d.y = WaterUtils.SampleHeight(ref data, ref terrainData, quad.d);
		if (!m_StartPoint.Equals(default(ControlPoint)))
		{
			return !m_RaycastPoint.Equals(default(ControlPoint));
		}
		return false;
	}
```

- `public virtual InitializeRaycast() : System.Void`  

```csharp
public override void InitializeRaycast()
	{
		base.InitializeRaycast();
		SelectionType selectionType = this.selectionType;
		if ((uint)(selectionType - 1) <= 1u)
		{
			m_ToolRaycastSystem.typeMask = TypeMask.Terrain | TypeMask.Areas | TypeMask.Water;
		}
		else
		{
			m_ToolRaycastSystem.typeMask = TypeMask.None;
		}
		m_ToolRaycastSystem.areaTypeMask = AreaUtils.GetTypeMask(GetAreaType(this.selectionType));
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_AreaSearchSystem = base.World.GetOrCreateSystemManaged<SearchSystem>();
		m_MapTileSystem = base.World.GetOrCreateSystemManaged<MapTileSystem>();
		m_MapTilePurchaseSystem = base.World.GetOrCreateSystemManaged<MapTilePurchaseSystem>();
		m_ToolOutputBarrier = base.World.GetOrCreateSystemManaged<ToolOutputBarrier>();
		m_AudioManager = base.World.GetOrCreateSystemManaged<AudioManager>();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_WaterSystem = base.World.GetOrCreateSystemManaged<WaterSystem>();
		m_DefinitionGroup = GetDefinitionQuery();
		m_TempGroup = GetEntityQuery(ComponentType.ReadOnly<Temp>());
		m_SoundQuery = GetEntityQuery(ComponentType.ReadOnly<ToolUXSoundSettingsData>());
		m_SelectionArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<SelectionInfo>(), ComponentType.ReadWrite<SelectionElement>());
		m_SelectArea = InputManager.instance.toolActionCollection.GetActionState("Select Area", "SelectionToolSystem");
		m_DeselectArea = InputManager.instance.toolActionCollection.GetActionState("Deselect Area", "SelectionToolSystem");
		m_DiscardSelect = InputManager.instance.toolActionCollection.GetActionState("Discard Select", "SelectionToolSystem");
		m_DiscardDeselect = InputManager.instance.toolActionCollection.GetActionState("Discard Deselect", "SelectionToolSystem");
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
		m_State = State.Default;
		m_StartPoint = default(ControlPoint);
		m_ApplyBlocked = false;
	}
```

- `protected virtual OnStopRunning() : System.Void`  

```csharp
[Preserve]
	protected override void OnStopRunning()
	{
		if (m_SelectionEntity != Entity.Null)
		{
			base.EntityManager.DestroyEntity(m_SelectionEntity);
			m_SelectionEntity = Entity.Null;
		}
		base.OnStopRunning();
	}
```

- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
[Preserve]
	protected override JobHandle OnUpdate(JobHandle inputDeps)
	{
		if (m_LastOwner != selectionOwner || m_LastType != selectionType || m_SelectionEntity == Entity.Null)
		{
			if (m_SelectionEntity != Entity.Null)
			{
				base.EntityManager.DestroyEntity(m_SelectionEntity);
			}
			m_SelectionEntity = base.EntityManager.CreateEntity(m_SelectionArchetype);
			SelectionInfo componentData = default(SelectionInfo);
			componentData.m_SelectionType = selectionType;
			componentData.m_AreaType = GetAreaType(selectionType);
			base.EntityManager.SetComponentData(m_SelectionEntity, componentData);
			if (selectionOwner != Entity.Null)
			{
				base.EntityManager.AddComponentData(m_SelectionEntity, new Owner(selectionOwner));
			}
			m_LastOwner = selectionOwner;
			m_LastType = selectionType;
			base.requireAreas = m_ToolRaycastSystem.areaTypeMask;
			inputDeps = CopySelection(inputDeps);
		}
		UpdateActions();
		if (m_State != State.Default && !base.applyAction.enabled && !base.secondaryApplyAction.enabled)
		{
			m_State = State.Default;
		}
		if ((m_ToolRaycastSystem.raycastFlags & (RaycastFlags.DebugDisable | RaycastFlags.UIDisable)) == 0)
		{
			switch (m_State)
			{
			case State.Default:
				if (m_ApplyBlocked)
				{
					if (base.applyAction.WasReleasedThisFrame() || base.secondaryApplyAction.WasReleasedThisFrame())
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
				break;
			case State.Selecting:
				if (base.cancelAction.WasPressedThisFrame())
				{
					m_ApplyBlocked = true;
					return Cancel(inputDeps);
				}
				if (base.applyAction.WasPressedThisFrame() || base.applyAction.WasReleasedThisFrame())
				{
					return Apply(inputDeps);
				}
				break;
			case State.Deselecting:
				if (base.cancelAction.WasPressedThisFrame())
				{
					m_ApplyBlocked = true;
					return Apply(inputDeps);
				}
				if (base.secondaryApplyAction.WasPressedThisFrame() || base.secondaryApplyAction.WasReleasedThisFrame())
				{
					return Cancel(inputDeps);
				}
				break;
			}
			return Update(inputDeps);
		}
		if (m_State != State.Default && (base.applyAction.WasReleasedThisFrame() || base.secondaryApplyAction.WasReleasedThisFrame()))
		{
			m_StartPoint = default(ControlPoint);
			m_State = State.Default;
		}
		return Clear(inputDeps);
	}
```

- `private ToggleTempEntity(Unity.Jobs.JobHandle inputDeps, System.Boolean select) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle ToggleTempEntity(JobHandle inputDeps, bool select)
	{
		if (m_TempGroup.IsEmptyIgnoreFilter)
		{
			return inputDeps;
		}
		return JobChunkExtensions.Schedule(new ToggleEntityJob
		{
			m_SelectionEntity = m_SelectionEntity,
			m_Select = select,
			m_EditorMode = m_ToolSystem.actionMode.IsEditor(),
			m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_NativeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Native_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_MapTileType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Areas_MapTile_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_SelectionElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Tools_SelectionElement_RW_BufferLookup, ref base.CheckedStateRef)
		}, m_TempGroup, inputDeps);
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
		State state = m_State;
		if ((uint)(state - 1) <= 1u)
		{
			if (GetRaycastResult(out ControlPoint controlPoint, out bool forceUpdate) && controlPoint.Equals(m_RaycastPoint) && !forceUpdate)
			{
				base.applyMode = ApplyMode.None;
				return inputDeps;
			}
			m_RaycastPoint = controlPoint;
			base.applyMode = ApplyMode.Clear;
			return UpdateDefinitions(inputDeps);
		}
		if (GetRaycastResult(out ControlPoint controlPoint2, out bool forceUpdate2) && controlPoint2.m_OriginalEntity == m_RaycastPoint.m_OriginalEntity && !forceUpdate2 && !base.EntityManager.HasComponent<Updated>(m_RaycastPoint.m_OriginalEntity))
		{
			m_RaycastPoint = controlPoint2;
			base.applyMode = ApplyMode.None;
			return inputDeps;
		}
		m_RaycastPoint = controlPoint2;
		base.applyMode = ApplyMode.Clear;
		return UpdateDefinitions(inputDeps);
	}
```

- `private virtual UpdateActions() : System.Void`  

```csharp
private protected override void UpdateActions()
	{
		using (ProxyAction.DeferStateUpdating())
		{
			switch (selectionType)
			{
			case SelectionType.MapTiles:
				if (m_ToolSystem.actionMode.IsGame() && m_MapTilePurchaseSystem.GetAvailableTiles() == 0)
				{
					base.applyAction.enabled = false;
					base.applyActionOverride = null;
					base.secondaryApplyAction.enabled = false;
					base.secondaryApplyActionOverride = null;
					base.cancelAction.enabled = false;
					base.cancelActionOverride = null;
					break;
				}
				if (m_TempGroup.CalculateEntityCount() <= 1)
				{
					base.applyAction.enabled = base.actionsEnabled;
					base.applyActionOverride = m_SelectArea;
					base.secondaryApplyAction.enabled = base.actionsEnabled;
					base.secondaryApplyActionOverride = m_DeselectArea;
					base.cancelAction.enabled = false;
					base.cancelActionOverride = null;
					break;
				}
				switch (m_State)
				{
				case State.Default:
					base.applyAction.enabled = base.actionsEnabled;
					base.applyActionOverride = m_SelectArea;
					base.secondaryApplyAction.enabled = base.actionsEnabled;
					base.secondaryApplyActionOverride = m_DeselectArea;
					base.cancelAction.enabled = false;
					base.cancelActionOverride = null;
					break;
				case State.Selecting:
					base.applyAction.enabled = base.actionsEnabled;
					base.applyActionOverride = m_SelectArea;
					base.secondaryApplyAction.enabled = false;
					base.secondaryApplyActionOverride = null;
					base.cancelAction.enabled = base.actionsEnabled;
					base.cancelActionOverride = m_DiscardSelect;
					break;
				case State.Deselecting:
					base.applyAction.enabled = false;
					base.applyActionOverride = null;
					base.secondaryApplyAction.enabled = base.actionsEnabled;
					base.secondaryApplyActionOverride = m_DeselectArea;
					base.cancelAction.enabled = base.actionsEnabled;
					base.cancelActionOverride = m_DiscardDeselect;
					break;
				}
				break;
			case SelectionType.ServiceDistrict:
				switch (m_State)
				{
				case State.Default:
					base.applyAction.enabled = base.actionsEnabled;
					base.applyActionOverride = m_SelectArea;
					base.secondaryApplyAction.enabled = base.actionsEnabled;
					base.secondaryApplyActionOverride = m_DeselectArea;
					base.cancelAction.enabled = false;
					base.cancelActionOverride = null;
					break;
				case State.Selecting:
					base.applyAction.enabled = base.actionsEnabled;
					base.applyActionOverride = m_SelectArea;
					base.secondaryApplyAction.enabled = false;
					base.secondaryApplyActionOverride = null;
					base.cancelAction.enabled = base.actionsEnabled;
					base.cancelActionOverride = m_DiscardSelect;
					break;
				case State.Deselecting:
					base.applyAction.enabled = false;
					base.applyActionOverride = null;
					base.secondaryApplyAction.enabled = base.actionsEnabled;
					base.secondaryApplyActionOverride = m_DeselectArea;
					base.cancelAction.enabled = base.actionsEnabled;
					base.cancelActionOverride = m_DiscardDeselect;
					break;
				}
				break;
			default:
				base.applyAction.enabled = false;
				base.applyActionOverride = null;
				base.secondaryApplyAction.enabled = false;
				base.secondaryApplyActionOverride = null;
				base.cancelAction.enabled = false;
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
		if (m_State != State.Default || m_RaycastPoint.m_OriginalEntity != Entity.Null)
		{
			NativeList<Entity> nativeList = new NativeList<Entity>(Allocator.TempJob);
			GetSelectionQuad(out var quad);
			JobHandle dependencies;
			FindEntitiesJob jobData = new FindEntitiesJob
			{
				m_StartPoint = ((m_State != State.Default) ? m_StartPoint : default(ControlPoint)),
				m_EndPoint = m_RaycastPoint,
				m_AreaSearchTree = m_AreaSearchSystem.GetSearchTree(readOnly: true, out dependencies),
				m_SelectionQuad = quad.xz,
				m_AreaType = GetAreaType(selectionType),
				m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_AreaGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_AreaGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Nodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Node_RO_BufferLookup, ref base.CheckedStateRef),
				m_Triangles = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Triangle_RO_BufferLookup, ref base.CheckedStateRef),
				m_Entities = nativeList
			};
			CreateDefinitionsJob jobData2 = new CreateDefinitionsJob
			{
				m_EditorMode = m_ToolSystem.actionMode.IsEditor(),
				m_NativeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Native_RO_ComponentLookup, ref base.CheckedStateRef),
				m_MapTileData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_MapTile_RO_ComponentLookup, ref base.CheckedStateRef),
				m_AreaNodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Node_RO_BufferLookup, ref base.CheckedStateRef),
				m_Entities = nativeList.AsDeferredJobArray(),
				m_CommandBuffer = m_ToolOutputBarrier.CreateCommandBuffer().AsParallelWriter()
			};
			JobHandle jobHandle2 = IJobExtensions.Schedule(jobData, JobHandle.CombineDependencies(inputDeps, dependencies));
			JobHandle jobHandle3 = jobData2.Schedule(nativeList, 4, jobHandle2);
			nativeList.Dispose(jobHandle3);
			m_AreaSearchSystem.AddSearchTreeReader(jobHandle2);
			m_ToolOutputBarrier.AddJobHandleForProducer(jobHandle3);
			jobHandle = JobHandle.CombineDependencies(jobHandle, jobHandle3);
		}
		return jobHandle;
	}
```

- `private UpdateSelection(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle UpdateSelection(JobHandle inputDeps)
	{
		switch (selectionType)
		{
		case SelectionType.ServiceDistrict:
			return UpdateServiceDistricts(inputDeps);
		case SelectionType.MapTiles:
			if (m_ToolSystem.actionMode.IsEditor())
			{
				return UpdateStartTiles(inputDeps);
			}
			return inputDeps;
		default:
			return inputDeps;
		}
	}
```

- `private UpdateServiceDistricts(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle UpdateServiceDistricts(JobHandle inputDeps)
	{
		JobHandle jobHandle = IJobExtensions.Schedule(new UpdateServiceDistrictsJob
		{
			m_SelectionEntity = m_SelectionEntity,
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SelectionElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Tools_SelectionElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_ServiceDistricts = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_ServiceDistrict_RW_BufferLookup, ref base.CheckedStateRef),
			m_CommandBuffer = m_ToolOutputBarrier.CreateCommandBuffer()
		}, inputDeps);
		m_ToolOutputBarrier.AddJobHandleForProducer(jobHandle);
		return jobHandle;
	}
```

- `private UpdateStartTiles(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle UpdateStartTiles(JobHandle inputDeps)
	{
		JobHandle jobHandle = IJobExtensions.Schedule(new UpdateStartTilesJob
		{
			m_SelectionEntity = m_SelectionEntity,
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SelectionElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Tools_SelectionElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_StartTiles = m_MapTileSystem.GetStartTiles(),
			m_CommandBuffer = m_ToolOutputBarrier.CreateCommandBuffer()
		}, inputDeps);
		m_ToolOutputBarrier.AddJobHandleForProducer(jobHandle);
		return jobHandle;
	}
```


## Nested types

- `Game.Tools.SelectionToolSystem+State`  
- `Game.Tools.SelectionToolSystem+FindEntitiesJob`  
- `Game.Tools.SelectionToolSystem+CreateDefinitionsJob`  
- `Game.Tools.SelectionToolSystem+ToggleEntityJob`  
- `Game.Tools.SelectionToolSystem+CopyStartTilesJob`  
- `Game.Tools.SelectionToolSystem+UpdateStartTilesJob`  
- `Game.Tools.SelectionToolSystem+CopyServiceDistrictsJob`  
- `Game.Tools.SelectionToolSystem+UpdateServiceDistrictsJob`  
- `Game.Tools.SelectionToolSystem+TypeHandle`  
- `Game.Tools.SelectionToolSystem+<get_toolActions>d__37`  

