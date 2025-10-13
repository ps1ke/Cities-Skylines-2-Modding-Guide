# Game.Tools.TerrainToolSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.Tools.ToolBaseSystem`  
**Implements:** `System.IEquatable<Game.Tools.ToolBaseSystem>`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TerrainToolSystem : Game.Tools.ToolBaseSystem, System.IEquatable<Game.Tools.ToolBaseSystem>
{
    private Game.Prefabs.TerraformingPrefab <prefab>k__BackingField;
    private Game.Audio.AudioManager m_AudioManager;
    private UnityEngine.AudioSource m_AudioSource;
    private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
    private Unity.Entities.EntityQuery m_DefinitionQuery;
    private Unity.Entities.EntityQuery m_BrushQuery;
    private Unity.Entities.EntityQuery m_TempQuery;
    private Unity.Entities.EntityQuery m_SoundQuery;
    private Unity.Entities.EntityQuery m_VisibleQuery;
    private Game.Input.IProxyAction m_EraseMaterial;
    private Game.Input.IProxyAction m_EraseResource;
    private Game.Input.IProxyAction m_FastSoften;
    private Game.Input.IProxyAction m_LevelTerrain;
    private Game.Input.IProxyAction m_LowerTerrain;
    private Game.Input.IProxyAction m_PaintMaterial;
    private Game.Input.IProxyAction m_PaintResource;
    private Game.Input.IProxyAction m_RaiseTerrain;
    private Game.Input.IProxyAction m_SetLevelTarget;
    private Game.Input.IProxyAction m_SetSlopeTarget;
    private Game.Input.IProxyAction m_SlopeTerrain;
    private Game.Input.IProxyAction m_SoftenTerrain;
    private Game.Tools.ControlPoint m_RaycastPoint;
    private Game.Tools.ControlPoint m_StartPoint;
    private Unity.Mathematics.float3 m_TargetPosition;
    private Unity.Mathematics.float3 m_ApplyPosition;
    private System.Boolean m_TargetSet;
    private Game.Tools.TerrainToolSystem+State m_State;
    private Game.Tools.TerrainToolSystem+TypeHandle __TypeHandle;
    public static const System.String kToolID;
    public static const System.String kTerrainToolKeyGroup;

    public System.String toolID { get; }
    public Game.Prefabs.TerraformingPrefab prefab { get; private set; }
    public System.Boolean brushing { get; }
    private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get; }
    public System.Single brushHeight { get; set; }

    public TerrainToolSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private Unity.Jobs.JobHandle Apply(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly);
    private Unity.Jobs.JobHandle Cancel(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly);
    private Unity.Jobs.JobHandle Clear(Unity.Jobs.JobHandle inputDeps);
    public virtual System.Void GetAvailableSnapMask(Game.Tools.Snap& onMask, Game.Tools.Snap& offMask);
    public virtual Game.Prefabs.PrefabBase GetPrefab();
    private System.Boolean HaveBrushSettingsChanged();
    public virtual System.Void InitializeRaycast();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnStartRunning();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
    public System.Void SetDisableFX();
    public System.Void SetPrefab(Game.Prefabs.TerraformingPrefab value);
    public virtual System.Boolean TrySetPrefab(Game.Prefabs.PrefabBase prefab);
    private Unity.Jobs.JobHandle Update(Unity.Jobs.JobHandle inputDeps);
    private virtual System.Void UpdateActions();
    private Unity.Jobs.JobHandle UpdateDefinitions(Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Game.Prefabs.TerraformingPrefab <prefab>k__BackingField`  

```csharp
private Game.Prefabs.TerraformingPrefab <prefab>k__BackingField;
```

- `private Game.Audio.AudioManager m_AudioManager`  

```csharp
private Game.Audio.AudioManager m_AudioManager;
```

- `private UnityEngine.AudioSource m_AudioSource`  

```csharp
private UnityEngine.AudioSource m_AudioSource;
```

- `private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier`  

```csharp
private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
```

- `private Unity.Entities.EntityQuery m_DefinitionQuery`  

```csharp
private Unity.Entities.EntityQuery m_DefinitionQuery;
```

- `private Unity.Entities.EntityQuery m_BrushQuery`  

```csharp
private Unity.Entities.EntityQuery m_BrushQuery;
```

- `private Unity.Entities.EntityQuery m_TempQuery`  

```csharp
private Unity.Entities.EntityQuery m_TempQuery;
```

- `private Unity.Entities.EntityQuery m_SoundQuery`  

```csharp
private Unity.Entities.EntityQuery m_SoundQuery;
```

- `private Unity.Entities.EntityQuery m_VisibleQuery`  

```csharp
private Unity.Entities.EntityQuery m_VisibleQuery;
```

- `private Game.Input.IProxyAction m_EraseMaterial`  

```csharp
private Game.Input.IProxyAction m_EraseMaterial;
```

- `private Game.Input.IProxyAction m_EraseResource`  

```csharp
private Game.Input.IProxyAction m_EraseResource;
```

- `private Game.Input.IProxyAction m_FastSoften`  

```csharp
private Game.Input.IProxyAction m_FastSoften;
```

- `private Game.Input.IProxyAction m_LevelTerrain`  

```csharp
private Game.Input.IProxyAction m_LevelTerrain;
```

- `private Game.Input.IProxyAction m_LowerTerrain`  

```csharp
private Game.Input.IProxyAction m_LowerTerrain;
```

- `private Game.Input.IProxyAction m_PaintMaterial`  

```csharp
private Game.Input.IProxyAction m_PaintMaterial;
```

- `private Game.Input.IProxyAction m_PaintResource`  

```csharp
private Game.Input.IProxyAction m_PaintResource;
```

- `private Game.Input.IProxyAction m_RaiseTerrain`  

```csharp
private Game.Input.IProxyAction m_RaiseTerrain;
```

- `private Game.Input.IProxyAction m_SetLevelTarget`  

```csharp
private Game.Input.IProxyAction m_SetLevelTarget;
```

- `private Game.Input.IProxyAction m_SetSlopeTarget`  

```csharp
private Game.Input.IProxyAction m_SetSlopeTarget;
```

- `private Game.Input.IProxyAction m_SlopeTerrain`  

```csharp
private Game.Input.IProxyAction m_SlopeTerrain;
```

- `private Game.Input.IProxyAction m_SoftenTerrain`  

```csharp
private Game.Input.IProxyAction m_SoftenTerrain;
```

- `private Game.Tools.ControlPoint m_RaycastPoint`  

```csharp
private Game.Tools.ControlPoint m_RaycastPoint;
```

- `private Game.Tools.ControlPoint m_StartPoint`  

```csharp
private Game.Tools.ControlPoint m_StartPoint;
```

- `private Unity.Mathematics.float3 m_TargetPosition`  

```csharp
private Unity.Mathematics.float3 m_TargetPosition;
```

- `private Unity.Mathematics.float3 m_ApplyPosition`  

```csharp
private Unity.Mathematics.float3 m_ApplyPosition;
```

- `private System.Boolean m_TargetSet`  

```csharp
private System.Boolean m_TargetSet;
```

- `private Game.Tools.TerrainToolSystem+State m_State`  

```csharp
private Game.Tools.TerrainToolSystem+State m_State;
```

- `private Game.Tools.TerrainToolSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.TerrainToolSystem+TypeHandle __TypeHandle;
```

- `public static const System.String kToolID`  

```csharp
public static const System.String kToolID;
```

- `public static const System.String kTerrainToolKeyGroup`  

```csharp
public static const System.String kTerrainToolKeyGroup;
```


## Properties

- `public System.String toolID { get }`  

```csharp
public System.String toolID { get; }
```

- `public Game.Prefabs.TerraformingPrefab prefab { get; private set }`  

```csharp
public Game.Prefabs.TerraformingPrefab prefab { get; private set; }
```

- `public System.Boolean brushing { get }`  

```csharp
public System.Boolean brushing { get; }
```

- `private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get }`  

```csharp
private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get; }
```

- `public System.Single brushHeight { get; set }`  

```csharp
public System.Single brushHeight { get; set; }
```


## Constructors

- `public TerrainToolSystem()`  

```csharp
[Preserve]
	public TerrainToolSystem()
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
			base.applyMode = ((prefab.m_Type != TerraformingType.Slope && GetAllowApply()) ? ApplyMode.Apply : ApplyMode.Clear);
			if (!singleFrameOnly)
			{
				m_StartPoint = m_RaycastPoint;
				m_State = State.Adding;
			}
			if (m_AudioSource == null && !m_ToolSystem.actionMode.IsEditor())
			{
				m_AudioSource = m_AudioManager.PlayExclusiveUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_TerraformSound);
			}
			GetRaycastResult(out m_RaycastPoint);
			m_ApplyPosition = m_RaycastPoint.m_HitPosition;
			return UpdateDefinitions(inputDeps);
		}
		if (m_State == State.Adding)
		{
			base.applyMode = (GetAllowApply() ? ApplyMode.Apply : ApplyMode.Clear);
			m_StartPoint = default(ControlPoint);
			m_State = State.Default;
			GetRaycastResult(out m_RaycastPoint);
			SetDisableFX();
			return UpdateDefinitions(inputDeps);
		}
		base.applyMode = ApplyMode.Clear;
		m_StartPoint = default(ControlPoint);
		m_State = State.Default;
		GetRaycastResult(out m_RaycastPoint);
		SetDisableFX();
		return UpdateDefinitions(inputDeps);
	}
```

- `private Cancel(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly = False) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle Cancel(JobHandle inputDeps, bool singleFrameOnly = false)
	{
		if (m_State == State.Default)
		{
			base.applyMode = ((prefab.m_Type != TerraformingType.Slope && GetAllowApply()) ? ApplyMode.Apply : ApplyMode.Clear);
			if (!singleFrameOnly)
			{
				m_StartPoint = m_RaycastPoint;
				m_State = State.Removing;
			}
			if (m_AudioSource == null && !m_ToolSystem.actionMode.IsEditor())
			{
				m_AudioSource = m_AudioManager.PlayExclusiveUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_TerraformSound);
			}
			GetRaycastResult(out m_RaycastPoint);
			m_TargetSet = true;
			m_TargetPosition = m_RaycastPoint.m_HitPosition;
			inputDeps = InvertBrushes(m_TempQuery, inputDeps);
			return UpdateDefinitions(inputDeps);
		}
		if (m_State == State.Removing)
		{
			base.applyMode = (GetAllowApply() ? ApplyMode.Apply : ApplyMode.Clear);
			m_StartPoint = default(ControlPoint);
			m_State = State.Default;
			GetRaycastResult(out m_RaycastPoint);
			SetDisableFX();
			return UpdateDefinitions(inputDeps);
		}
		base.applyMode = ApplyMode.Clear;
		m_StartPoint = default(ControlPoint);
		m_State = State.Default;
		GetRaycastResult(out m_RaycastPoint);
		SetDisableFX();
		return UpdateDefinitions(inputDeps);
	}
```

- `private Clear(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle Clear(JobHandle inputDeps)
	{
		base.applyMode = ApplyMode.Clear;
		SetDisableFX();
		return inputDeps;
	}
```

- `public virtual GetAvailableSnapMask(Game.Tools.Snap& onMask, Game.Tools.Snap& offMask) : System.Void`  

```csharp
public override void GetAvailableSnapMask(out Snap onMask, out Snap offMask)
	{
		base.GetAvailableSnapMask(out onMask, out offMask);
		if (prefab != null && prefab.m_Target == TerraformingTarget.Height)
		{
			onMask |= Snap.ContourLines;
			offMask |= Snap.ContourLines;
		}
	}
```

- `public virtual GetPrefab() : Game.Prefabs.PrefabBase`  

```csharp
public override PrefabBase GetPrefab()
	{
		return prefab;
	}
```

- `private HaveBrushSettingsChanged() : System.Boolean`  

```csharp
private bool HaveBrushSettingsChanged()
	{
		NativeArray<ArchetypeChunk> nativeArray = m_VisibleQuery.ToArchetypeChunkArray(Allocator.TempJob);
		try
		{
			ComponentTypeHandle<Brush> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Brush_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			for (int i = 0; i < nativeArray.Length; i++)
			{
				NativeArray<Brush> nativeArray2 = nativeArray[i].GetNativeArray(ref typeHandle);
				for (int j = 0; j < nativeArray2.Length; j++)
				{
					if (!nativeArray2[j].m_Size.Equals(base.brushSize))
					{
						return true;
					}
				}
			}
			return false;
		}
		finally
		{
			nativeArray.Dispose();
		}
	}
```

- `public virtual InitializeRaycast() : System.Void`  

```csharp
public override void InitializeRaycast()
	{
		base.InitializeRaycast();
		if (prefab != null && base.brushType != null)
		{
			m_ToolRaycastSystem.typeMask = TypeMask.Terrain;
			m_ToolRaycastSystem.raycastFlags |= RaycastFlags.Outside;
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
		m_AudioManager = base.World.GetOrCreateSystemManaged<AudioManager>();
		m_ToolOutputBarrier = base.World.GetOrCreateSystemManaged<ToolOutputBarrier>();
		m_DefinitionQuery = GetDefinitionQuery();
		m_BrushQuery = GetBrushQuery();
		m_VisibleQuery = GetEntityQuery(ComponentType.ReadOnly<Brush>(), ComponentType.Exclude<Hidden>(), ComponentType.Exclude<Deleted>());
		m_TempQuery = GetEntityQuery(ComponentType.ReadOnly<Brush>(), ComponentType.ReadOnly<Temp>());
		m_SoundQuery = GetEntityQuery(ComponentType.ReadOnly<ToolUXSoundSettingsData>());
		m_EraseMaterial = InputManager.instance.toolActionCollection.GetActionState("Erase Material", "TerrainToolSystem");
		m_EraseResource = InputManager.instance.toolActionCollection.GetActionState("Erase Resource", "TerrainToolSystem");
		m_FastSoften = InputManager.instance.toolActionCollection.GetActionState("Fast Soften", "TerrainToolSystem");
		m_LevelTerrain = InputManager.instance.toolActionCollection.GetActionState("Level Terrain", "TerrainToolSystem");
		m_LowerTerrain = InputManager.instance.toolActionCollection.GetActionState("Lower Terrain", "TerrainToolSystem");
		m_PaintMaterial = InputManager.instance.toolActionCollection.GetActionState("Paint Material", "TerrainToolSystem");
		m_PaintResource = InputManager.instance.toolActionCollection.GetActionState("Paint Resource", "TerrainToolSystem");
		m_RaiseTerrain = InputManager.instance.toolActionCollection.GetActionState("Raise Terrain", "TerrainToolSystem");
		m_SetLevelTarget = InputManager.instance.toolActionCollection.GetActionState("Set Level Target", "TerrainToolSystem");
		m_SetSlopeTarget = InputManager.instance.toolActionCollection.GetActionState("Set Slope Target", "TerrainToolSystem");
		m_SlopeTerrain = InputManager.instance.toolActionCollection.GetActionState("Slope Terrain", "TerrainToolSystem");
		m_SoftenTerrain = InputManager.instance.toolActionCollection.GetActionState("Soften Terrain", "TerrainToolSystem");
		base.brushSize = 100f;
		base.brushAngle = 0f;
		base.brushStrength = 0.5f;
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

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		base.OnGameLoaded(serializationContext);
		base.brushType = FindDefaultBrush(m_BrushQuery);
		base.brushSize = 100f;
		base.brushAngle = 0f;
		base.brushStrength = 0.5f;
	}
```

- `protected virtual OnStartRunning() : System.Void`  

```csharp
[Preserve]
	protected override void OnStartRunning()
	{
		base.OnStartRunning();
		m_RaycastPoint = default(ControlPoint);
		m_StartPoint = default(ControlPoint);
		m_State = State.Default;
	}
```

- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
[Preserve]
	protected override JobHandle OnUpdate(JobHandle inputDeps)
	{
		if (base.brushType == null)
		{
			base.brushType = FindDefaultBrush(m_BrushQuery);
		}
		base.requireNet = Layer.Road | Layer.TrainTrack | Layer.Pathway | Layer.TramTrack | Layer.SubwayTrack | Layer.PublicTransportRoad;
		base.requirePipelines = true;
		if (m_FocusChanged)
		{
			return inputDeps;
		}
		if (prefab != null && base.brushType != null && m_HasFocus)
		{
			UpdateInfoview(m_PrefabSystem.GetEntity(prefab));
			GetAvailableSnapMask(out m_SnapOnMask, out m_SnapOffMask);
			if (m_State != State.Default && !base.applyAction.enabled)
			{
				m_State = State.Default;
			}
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
		}
		else
		{
			UpdateInfoview(Entity.Null);
		}
		if (m_State != State.Default && (base.applyAction.WasReleasedThisFrame() || base.secondaryApplyAction.WasReleasedThisFrame() || !m_HasFocus))
		{
			m_StartPoint = default(ControlPoint);
			m_State = State.Default;
		}
		return Clear(inputDeps);
	}
```

- `public SetDisableFX() : System.Void`  

```csharp
public void SetDisableFX()
	{
		if (m_AudioSource != null)
		{
			m_AudioManager.StopExclusiveUISound(m_AudioSource);
			m_AudioSource = null;
		}
	}
```

- `public SetPrefab(Game.Prefabs.TerraformingPrefab value) : System.Void`  

```csharp
public void SetPrefab(TerraformingPrefab value)
	{
		m_TargetSet = false;
		m_TargetPosition = new float3(0f, 0f, 0f);
		m_ApplyPosition = new float3(0f, 0f, 0f);
		prefab = value;
		if (base.Enabled)
		{
			UpdateActions();
		}
	}
```

- `public virtual TrySetPrefab(Game.Prefabs.PrefabBase prefab) : System.Boolean`  

```csharp
public override bool TrySetPrefab(PrefabBase prefab)
	{
		if (prefab is TerraformingPrefab terraformingPrefab)
		{
			SetPrefab(terraformingPrefab);
			return true;
		}
		return false;
	}
```

- `private Update(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle Update(JobHandle inputDeps)
	{
		if (GetRaycastResult(out var controlPoint))
		{
			if (m_State != State.Default)
			{
				base.applyMode = (GetAllowApply() ? ApplyMode.Apply : ApplyMode.Clear);
				m_StartPoint = m_RaycastPoint;
				m_RaycastPoint = controlPoint;
				return UpdateDefinitions(inputDeps);
			}
			if (m_RaycastPoint.Equals(controlPoint))
			{
				if (HaveBrushSettingsChanged())
				{
					base.applyMode = ApplyMode.Clear;
					return UpdateDefinitions(inputDeps);
				}
				base.applyMode = ApplyMode.None;
				return inputDeps;
			}
			base.applyMode = ApplyMode.Clear;
			m_StartPoint = controlPoint;
			m_RaycastPoint = controlPoint;
			return UpdateDefinitions(inputDeps);
		}
		if (m_RaycastPoint.Equals(default(ControlPoint)))
		{
			base.applyMode = ApplyMode.None;
			return inputDeps;
		}
		if (m_State != State.Default)
		{
			base.applyMode = (GetAllowApply() ? ApplyMode.Apply : ApplyMode.Clear);
			m_StartPoint = m_RaycastPoint;
			m_RaycastPoint = default(ControlPoint);
		}
		else
		{
			base.applyMode = ApplyMode.Clear;
			m_StartPoint = default(ControlPoint);
			m_RaycastPoint = default(ControlPoint);
		}
		return UpdateDefinitions(inputDeps);
	}
```

- `private virtual UpdateActions() : System.Void`  

```csharp
private protected override void UpdateActions()
	{
		using (ProxyAction.DeferStateUpdating())
		{
			base.applyAction.enabled = base.actionsEnabled;
			base.secondaryApplyAction.enabled = base.actionsEnabled;
			if (prefab.m_Type == TerraformingType.Shift)
			{
				if (prefab.m_Target == TerraformingTarget.Height)
				{
					base.applyActionOverride = m_RaiseTerrain;
					base.secondaryApplyActionOverride = m_LowerTerrain;
				}
				else if (prefab.m_Target == TerraformingTarget.Material)
				{
					base.applyActionOverride = m_PaintMaterial;
					base.secondaryApplyActionOverride = m_EraseMaterial;
				}
				else
				{
					base.applyActionOverride = m_PaintResource;
					base.secondaryApplyActionOverride = m_EraseResource;
				}
			}
			else if (prefab.m_Type == TerraformingType.Level)
			{
				base.applyActionOverride = m_LevelTerrain;
				base.secondaryApplyActionOverride = m_SetLevelTarget;
			}
			else if (prefab.m_Type == TerraformingType.Slope)
			{
				base.applyActionOverride = m_SlopeTerrain;
				base.secondaryApplyActionOverride = m_SetSlopeTarget;
			}
			else if (prefab.m_Type == TerraformingType.Soften)
			{
				base.applyActionOverride = m_SoftenTerrain;
				base.secondaryApplyActionOverride = m_FastSoften;
			}
			else
			{
				base.applyActionOverride = null;
				base.secondaryApplyActionOverride = null;
			}
		}
	}
```

- `private UpdateDefinitions(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle UpdateDefinitions(JobHandle inputDeps)
	{
		JobHandle jobHandle = DestroyDefinitions(m_DefinitionQuery, m_ToolOutputBarrier, inputDeps);
		if (prefab != null && base.brushType != null)
		{
			JobHandle jobHandle2 = IJobExtensions.Schedule(new CreateDefinitionsJob
			{
				m_Prefab = m_PrefabSystem.GetEntity(prefab),
				m_Brush = m_PrefabSystem.GetEntity(base.brushType),
				m_Size = base.brushSize,
				m_Angle = math.radians(base.brushAngle),
				m_Strength = ((m_State == State.Removing) ? (0f - base.brushStrength) : base.brushStrength),
				m_Time = UnityEngine.Time.deltaTime,
				m_StartPoint = m_StartPoint,
				m_EndPoint = m_RaycastPoint,
				m_Target = (m_TargetSet ? m_TargetPosition : m_RaycastPoint.m_HitPosition),
				m_ApplyStart = m_ApplyPosition,
				m_CommandBuffer = m_ToolOutputBarrier.CreateCommandBuffer()
			}, inputDeps);
			m_ToolOutputBarrier.AddJobHandleForProducer(jobHandle2);
			jobHandle = JobHandle.CombineDependencies(jobHandle, jobHandle2);
			if (base.applyMode == ApplyMode.Apply)
			{
				EnsureCachedBrushData();
			}
		}
		return jobHandle;
	}
```


## Nested types

- `Game.Tools.TerrainToolSystem+State`  
- `Game.Tools.TerrainToolSystem+CreateDefinitionsJob`  
- `Game.Tools.TerrainToolSystem+TypeHandle`  
- `Game.Tools.TerrainToolSystem+<get_toolActions>d__32`  

