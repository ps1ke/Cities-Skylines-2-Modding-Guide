# Game.Rendering.BatchDataSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class BatchDataSystem : Game.GameSystemBase, Game.Serialization.IPostDeserialize
{
    private Game.Rendering.RenderingSystem m_RenderingSystem;
    private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
    private Game.Rendering.BatchManagerSystem m_BatchManagerSystem;
    private Game.Rendering.BatchMeshSystem m_BatchMeshSystem;
    private Game.Rendering.ManagedBatchSystem m_ManagedBatchSystem;
    private Game.Rendering.PreCullingSystem m_PreCullingSystem;
    private Game.Rendering.LightingSystem m_LightingSystem;
    private Game.Rendering.MeshColorSystem m_MeshColorSystem;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.CitizenPresenceSystem m_CitizenPresenceSystem;
    private Game.Simulation.TreeGrowthSystem m_TreeGrowthSystem;
    private Game.Simulation.WetnessSystem m_WetnessSystem;
    private Game.Simulation.WindSystem m_WindSystem;
    private Game.Simulation.DirtynessSystem m_DirtynessSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Unity.Entities.EntityQuery m_RenderingSettingsQuery;
    private Colossal.Collections.NativeAccumulator<Game.Rendering.BatchDataSystem+SmoothingNeeded> m_SmoothingNeeded;
    private System.Int32 m_SHCoefficients;
    private System.Int32 m_LodParameters;
    private System.Boolean m_UpdateAll;
    private System.Single m_LastLightFactor;
    private System.Single m_LodFadeTimer;
    private Unity.Mathematics.float4 m_LastBuildingStateOverride;
    private System.UInt32 m_LastCitizenPresenceVersion;
    private System.UInt32 m_LastTreeGrowthVersion;
    private System.UInt32 m_LastWetnessVersion;
    private System.UInt32 m_LastDirtynessVersion;
    private System.UInt32 m_LastFireDamageVersion;
    private System.UInt32 m_LastWaterDamageVersion;
    private System.UInt32 m_LastWeatherDamageVersion;
    private System.UInt32 m_LastLaneConditionFrame;
    private System.UInt32 m_LastDamagedFrame;
    private Game.Rendering.BatchDataSystem+TypeHandle __TypeHandle;
    public static const System.Single LOD_FADE_DURATION;
    public static const System.Single DEBUG_FADE_DURATION;

    public BatchDataSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Single CalculateLightFactor();
    private System.Void GetDataQuery(Game.Rendering.PreCullingFlags& cullingFlags, Game.Rendering.BatchDataSystem+UpdateMasks& updateMasks);
    public System.Single GetLevelOfDetail(System.Single levelOfDetail, Game.Rendering.IGameCameraController cameraController);
    public System.Void InstancePropertiesUpdated();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
    private System.Void UpdateGlobalValues(Colossal.Rendering.NativeBatchInstances<Game.Rendering.CullingData, Game.Rendering.GroupData, Game.Rendering.BatchData, Game.Rendering.InstanceData> nativeBatchInstances);
}
```


## Fields

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  

```csharp
private Game.Rendering.RenderingSystem m_RenderingSystem;
```

- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  

```csharp
private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
```

- `private Game.Rendering.BatchManagerSystem m_BatchManagerSystem`  

```csharp
private Game.Rendering.BatchManagerSystem m_BatchManagerSystem;
```

- `private Game.Rendering.BatchMeshSystem m_BatchMeshSystem`  

```csharp
private Game.Rendering.BatchMeshSystem m_BatchMeshSystem;
```

- `private Game.Rendering.ManagedBatchSystem m_ManagedBatchSystem`  

```csharp
private Game.Rendering.ManagedBatchSystem m_ManagedBatchSystem;
```

- `private Game.Rendering.PreCullingSystem m_PreCullingSystem`  

```csharp
private Game.Rendering.PreCullingSystem m_PreCullingSystem;
```

- `private Game.Rendering.LightingSystem m_LightingSystem`  

```csharp
private Game.Rendering.LightingSystem m_LightingSystem;
```

- `private Game.Rendering.MeshColorSystem m_MeshColorSystem`  

```csharp
private Game.Rendering.MeshColorSystem m_MeshColorSystem;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.CitizenPresenceSystem m_CitizenPresenceSystem`  

```csharp
private Game.Simulation.CitizenPresenceSystem m_CitizenPresenceSystem;
```

- `private Game.Simulation.TreeGrowthSystem m_TreeGrowthSystem`  

```csharp
private Game.Simulation.TreeGrowthSystem m_TreeGrowthSystem;
```

- `private Game.Simulation.WetnessSystem m_WetnessSystem`  

```csharp
private Game.Simulation.WetnessSystem m_WetnessSystem;
```

- `private Game.Simulation.WindSystem m_WindSystem`  

```csharp
private Game.Simulation.WindSystem m_WindSystem;
```

- `private Game.Simulation.DirtynessSystem m_DirtynessSystem`  

```csharp
private Game.Simulation.DirtynessSystem m_DirtynessSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Unity.Entities.EntityQuery m_RenderingSettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_RenderingSettingsQuery;
```

- `private Colossal.Collections.NativeAccumulator<Game.Rendering.BatchDataSystem+SmoothingNeeded> m_SmoothingNeeded`  

```csharp
private Colossal.Collections.NativeAccumulator<Game.Rendering.BatchDataSystem+SmoothingNeeded> m_SmoothingNeeded;
```

- `private System.Int32 m_SHCoefficients`  

```csharp
private System.Int32 m_SHCoefficients;
```

- `private System.Int32 m_LodParameters`  

```csharp
private System.Int32 m_LodParameters;
```

- `private System.Boolean m_UpdateAll`  

```csharp
private System.Boolean m_UpdateAll;
```

- `private System.Single m_LastLightFactor`  

```csharp
private System.Single m_LastLightFactor;
```

- `private System.Single m_LodFadeTimer`  

```csharp
private System.Single m_LodFadeTimer;
```

- `private Unity.Mathematics.float4 m_LastBuildingStateOverride`  

```csharp
private Unity.Mathematics.float4 m_LastBuildingStateOverride;
```

- `private System.UInt32 m_LastCitizenPresenceVersion`  

```csharp
private System.UInt32 m_LastCitizenPresenceVersion;
```

- `private System.UInt32 m_LastTreeGrowthVersion`  

```csharp
private System.UInt32 m_LastTreeGrowthVersion;
```

- `private System.UInt32 m_LastWetnessVersion`  

```csharp
private System.UInt32 m_LastWetnessVersion;
```

- `private System.UInt32 m_LastDirtynessVersion`  

```csharp
private System.UInt32 m_LastDirtynessVersion;
```

- `private System.UInt32 m_LastFireDamageVersion`  

```csharp
private System.UInt32 m_LastFireDamageVersion;
```

- `private System.UInt32 m_LastWaterDamageVersion`  

```csharp
private System.UInt32 m_LastWaterDamageVersion;
```

- `private System.UInt32 m_LastWeatherDamageVersion`  

```csharp
private System.UInt32 m_LastWeatherDamageVersion;
```

- `private System.UInt32 m_LastLaneConditionFrame`  

```csharp
private System.UInt32 m_LastLaneConditionFrame;
```

- `private System.UInt32 m_LastDamagedFrame`  

```csharp
private System.UInt32 m_LastDamagedFrame;
```

- `private Game.Rendering.BatchDataSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.BatchDataSystem+TypeHandle __TypeHandle;
```

- `public static const System.Single LOD_FADE_DURATION`  

```csharp
public static const System.Single LOD_FADE_DURATION;
```

- `public static const System.Single DEBUG_FADE_DURATION`  

```csharp
public static const System.Single DEBUG_FADE_DURATION;
```


## Constructors

- `public BatchDataSystem()`  

```csharp
[Preserve]
	public BatchDataSystem()
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

- `private CalculateLightFactor() : System.Single`  

```csharp
private float CalculateLightFactor()
	{
		float dayLightBrightness = m_LightingSystem.dayLightBrightness;
		return math.saturate(1f - math.round(dayLightBrightness * 100f) * 0.01f);
	}
```

- `private GetDataQuery(Game.Rendering.PreCullingFlags& cullingFlags, Game.Rendering.BatchDataSystem+UpdateMasks& updateMasks) : System.Void`  

```csharp
private void GetDataQuery(out PreCullingFlags cullingFlags, out UpdateMasks updateMasks)
	{
		cullingFlags = PreCullingFlags.NearCameraUpdated | PreCullingFlags.Updated | PreCullingFlags.BatchesUpdated | PreCullingFlags.FadeContainer | PreCullingFlags.InterpolatedTransform | PreCullingFlags.Animated | PreCullingFlags.ColorsUpdated;
		updateMasks = default(UpdateMasks);
		if (!m_RenderingSystem.editorBuildingStateOverride.Equals(m_LastBuildingStateOverride))
		{
			m_LastBuildingStateOverride = m_RenderingSystem.editorBuildingStateOverride;
			m_LastCitizenPresenceVersion--;
		}
		uint lastSystemVersion = m_CitizenPresenceSystem.LastSystemVersion;
		uint lastSystemVersion2 = m_TreeGrowthSystem.LastSystemVersion;
		uint lastSystemVersion3 = m_WetnessSystem.LastSystemVersion;
		uint lastSystemVersion4 = m_DirtynessSystem.LastSystemVersion;
		uint num = ((m_RenderingSystem.frameIndex >= m_LastLaneConditionFrame + 128) ? m_RenderingSystem.frameIndex : m_LastLaneConditionFrame);
		uint num2 = ((m_RenderingSystem.frameIndex >= m_LastDamagedFrame + 128) ? m_RenderingSystem.frameIndex : m_LastDamagedFrame);
		float num3 = CalculateLightFactor();
		if (m_UpdateAll)
		{
			cullingFlags |= PreCullingFlags.NearCamera | PreCullingFlags.InfoviewColor | PreCullingFlags.BuildingState | PreCullingFlags.TreeGrowth | PreCullingFlags.LaneCondition | PreCullingFlags.SurfaceState | PreCullingFlags.SurfaceDamage | PreCullingFlags.SmoothColor;
			updateMasks.UpdateAll();
			m_UpdateAll = false;
		}
		else
		{
			SmoothingNeeded result = m_SmoothingNeeded.GetResult();
			if (m_ToolSystem.activeInfoview != null)
			{
				cullingFlags |= PreCullingFlags.InfoviewColor;
				updateMasks.m_ObjectMask.UpdateProperty(ObjectProperty.InfoviewColor);
				updateMasks.m_NetMask.UpdateProperty(NetProperty.InfoviewColor);
				updateMasks.m_LaneMask.UpdateProperty(LaneProperty.InfoviewColor);
				updateMasks.m_LaneMask.UpdateProperty(LaneProperty.FlowMatrix);
			}
			if (lastSystemVersion != m_LastCitizenPresenceVersion || num3 != m_LastLightFactor)
			{
				cullingFlags |= PreCullingFlags.BuildingState;
				updateMasks.m_ObjectMask.UpdateProperty(ObjectProperty.BuildingState);
			}
			if (lastSystemVersion2 != m_LastTreeGrowthVersion)
			{
				cullingFlags |= PreCullingFlags.TreeGrowth;
			}
			if (lastSystemVersion3 != m_LastWetnessVersion || result.IsNeeded(SmoothingType.SurfaceWetness))
			{
				cullingFlags |= PreCullingFlags.SurfaceState;
				updateMasks.m_ObjectMask.UpdateProperty(ObjectProperty.SurfaceWetness);
			}
			if (lastSystemVersion4 != m_LastDirtynessVersion || result.IsNeeded(SmoothingType.SurfaceDirtyness))
			{
				updateMasks.m_ObjectMask.UpdateProperty(ObjectProperty.SurfaceDamage);
			}
			if (num != m_LastLaneConditionFrame)
			{
				cullingFlags |= PreCullingFlags.LaneCondition;
				updateMasks.m_LaneMask.UpdateProperty(LaneProperty.CurveDeterioration);
			}
			if (num2 != m_LastDamagedFrame || result.IsNeeded(SmoothingType.SurfaceDamage))
			{
				updateMasks.m_ObjectMask.UpdateProperty(ObjectProperty.SurfaceDamage);
			}
			if (m_MeshColorSystem.smoothColorsUpdated || result.IsNeeded(SmoothingType.ColorMask))
			{
				cullingFlags |= PreCullingFlags.SmoothColor;
				updateMasks.m_ObjectMask.UpdateProperty(ObjectProperty.ColorMask1);
				updateMasks.m_ObjectMask.UpdateProperty(ObjectProperty.ColorMask2);
				updateMasks.m_ObjectMask.UpdateProperty(ObjectProperty.ColorMask3);
				updateMasks.m_LaneMask.UpdateProperty(LaneProperty.ColorMask1);
				updateMasks.m_LaneMask.UpdateProperty(LaneProperty.ColorMask2);
				updateMasks.m_LaneMask.UpdateProperty(LaneProperty.ColorMask3);
			}
		}
		m_SmoothingNeeded.Clear();
		m_LastCitizenPresenceVersion = lastSystemVersion;
		m_LastTreeGrowthVersion = lastSystemVersion2;
		m_LastWetnessVersion = lastSystemVersion3;
		m_LastDirtynessVersion = lastSystemVersion4;
		m_LastLightFactor = num3;
		m_LastLaneConditionFrame = num;
		m_LastDamagedFrame = num2;
	}
```

- `public GetLevelOfDetail(System.Single levelOfDetail, Game.Rendering.IGameCameraController cameraController) : System.Single`  

```csharp
public float GetLevelOfDetail(float levelOfDetail, IGameCameraController cameraController)
	{
		if (cameraController != null)
		{
			levelOfDetail *= 1f - 1f / (2f + 0.01f * cameraController.zoom);
		}
		return levelOfDetail;
	}
```

- `public InstancePropertiesUpdated() : System.Void`  

```csharp
public void InstancePropertiesUpdated()
	{
		m_UpdateAll = true;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_RenderingSystem = base.World.GetOrCreateSystemManaged<RenderingSystem>();
		m_CameraUpdateSystem = base.World.GetOrCreateSystemManaged<CameraUpdateSystem>();
		m_BatchManagerSystem = base.World.GetOrCreateSystemManaged<BatchManagerSystem>();
		m_BatchMeshSystem = base.World.GetOrCreateSystemManaged<BatchMeshSystem>();
		m_ManagedBatchSystem = base.World.GetOrCreateSystemManaged<ManagedBatchSystem>();
		m_PreCullingSystem = base.World.GetOrCreateSystemManaged<PreCullingSystem>();
		m_LightingSystem = base.World.GetOrCreateSystemManaged<LightingSystem>();
		m_MeshColorSystem = base.World.GetOrCreateSystemManaged<MeshColorSystem>();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_CitizenPresenceSystem = base.World.GetOrCreateSystemManaged<CitizenPresenceSystem>();
		m_TreeGrowthSystem = base.World.GetOrCreateSystemManaged<TreeGrowthSystem>();
		m_WindSystem = base.World.GetOrCreateSystemManaged<WindSystem>();
		m_WetnessSystem = base.World.GetOrCreateSystemManaged<WetnessSystem>();
		m_DirtynessSystem = base.World.GetOrCreateSystemManaged<DirtynessSystem>();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_RenderingSettingsQuery = GetEntityQuery(ComponentType.ReadOnly<RenderingSettingsData>());
		m_SmoothingNeeded = new NativeAccumulator<SmoothingNeeded>(Allocator.Persistent);
		m_SHCoefficients = Shader.PropertyToID("unity_SHCoefficients");
		m_LodParameters = Shader.PropertyToID("colossal_LodParameters");
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
		m_SmoothingNeeded.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		float4 lodParameters = 1f;
		float3 cameraPosition = 0f;
		float3 cameraDirection = 0f;
		float pixelSizeFactor = 1f;
		if (m_CameraUpdateSystem.TryGetLODParameters(out var lodParameters2))
		{
			IGameCameraController activeCameraController = m_CameraUpdateSystem.activeCameraController;
			lodParameters = RenderingUtils.CalculateLodParameters(GetLevelOfDetail(m_RenderingSystem.frameLod, activeCameraController), lodParameters2);
			cameraPosition = lodParameters2.cameraPosition;
			cameraDirection = m_CameraUpdateSystem.activeViewer.forward;
			pixelSizeFactor = (float)lodParameters2.cameraPixelHeight / math.radians(lodParameters2.fieldOfView);
		}
		Shader.SetGlobalVector(m_LodParameters, new Vector4(lodParameters.x, lodParameters.y, 0f, 0f));
		bool flag = m_BatchManagerSystem.IsLodFadeEnabled();
		int lodFadeDelta = 0;
		if (flag)
		{
			m_LodFadeTimer += UnityEngine.Time.deltaTime * (m_RenderingSystem.debugCrossFade ? 102f : 1020f);
			lodFadeDelta = Mathf.FloorToInt(m_LodFadeTimer);
			m_LodFadeTimer -= lodFadeDelta;
			lodFadeDelta = math.clamp(lodFadeDelta, 0, 255);
		}
		m_BatchMeshSystem.UpdateMeshes();
		JobHandle dependencies;
		NativeBatchGroups<CullingData, GroupData, BatchData, InstanceData> nativeBatchGroups = m_BatchManagerSystem.GetNativeBatchGroups(readOnly: true, out dependencies);
		JobHandle dependencies2;
		NativeBatchInstances<CullingData, GroupData, BatchData, InstanceData> nativeBatchInstances = m_BatchManagerSystem.GetNativeBatchInstances(readOnly: false, out dependencies2);
		GetDataQuery(out var cullingFlags, out var updateMasks);
		dependencies2.Complete();
		UpdateGlobalValues(nativeBatchInstances);
		int activeGroupCount = nativeBatchInstances.GetActiveGroupCount();
		NativeBatchInstances<CullingData, GroupData, BatchData, InstanceData>.CullingWriter cullingWriter = nativeBatchInstances.BeginCulling(Allocator.TempJob);
		JobHandle dependencies3;
		JobHandle dependencies4;
		BatchDataJob jobData = new BatchDataJob
		{
			m_CullingInfoData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Rendering_CullingInfo_RO_ComponentLookup, ref base.CheckedStateRef),
			m_DestroyedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Destroyed_RO_ComponentLookup, ref base.CheckedStateRef),
			m_InterpolatedTransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Rendering_InterpolatedTransform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PseudoRandomSeedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_PseudoRandomSeed_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ErrorData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Error_RO_ComponentLookup, ref base.CheckedStateRef),
			m_WarningData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Warning_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OverrideData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Override_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HiddenData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Hidden_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TempData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentLookup, ref base.CheckedStateRef),
			m_MeshBatches = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_MeshBatch_RO_BufferLookup, ref base.CheckedStateRef),
			m_FadeBatches = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_FadeBatch_RO_BufferLookup, ref base.CheckedStateRef),
			m_MeshColors = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_MeshColor_RO_BufferLookup, ref base.CheckedStateRef),
			m_MeshGroups = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_MeshGroup_RO_BufferLookup, ref base.CheckedStateRef),
			m_Animateds = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_Animated_RO_BufferLookup, ref base.CheckedStateRef),
			m_Skeletons = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_Skeleton_RO_BufferLookup, ref base.CheckedStateRef),
			m_Emissives = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_Emissive_RO_BufferLookup, ref base.CheckedStateRef),
			m_TreeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Tree_RO_ComponentLookup, ref base.CheckedStateRef),
			m_StackData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Stack_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ObjectTransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ObjectColorData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Color_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ObjectElevationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Elevation_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ObjectSurfaceData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Surface_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ObjectDamagedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Damaged_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CitizenPresenceData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_CitizenPresence_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingAbandonedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Abandoned_RO_ComponentLookup, ref base.CheckedStateRef),
			m_VehicleData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Vehicle_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PublicTransportData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_PublicTransport_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OnFireData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Events_OnFire_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Passengers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_Passenger_RO_BufferLookup, ref base.CheckedStateRef),
			m_NodeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Node_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CompositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Composition_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OrphanData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Orphan_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NodeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_NodeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EdgeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_EdgeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
			m_StartNodeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_StartNodeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EndNodeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_EndNodeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NodeLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_NodeLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EdgeLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_EdgeLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NetElevationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Elevation_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LaneColorData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_LaneColor_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LaneConditionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_LaneCondition_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HangingLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_HangingLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NetEdgeColorData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_EdgeColor_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NetNodeColorData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_NodeColor_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SubFlows = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubFlow_RO_BufferLookup, ref base.CheckedStateRef),
			m_CutRanges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_CutRange_RO_BufferLookup, ref base.CheckedStateRef),
			m_ZoneBlockData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Zones_Block_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ZoneCells = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Zones_Cell_RO_BufferLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabGrowthScaleData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_GrowthScaleData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabStackData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_StackData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabPublicTransportVehicleData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PublicTransportVehicleData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabMeshData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_MeshData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabNetLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabCompositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetCompositionData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabUtilityLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_UtilityLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabSubMeshes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubMesh_RO_BufferLookup, ref base.CheckedStateRef),
			m_PrefabSubMeshGroups = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubMeshGroup_RO_BufferLookup, ref base.CheckedStateRef),
			m_PrefabAnimationClips = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_AnimationClip_RO_BufferLookup, ref base.CheckedStateRef),
			m_EditorMode = m_ToolSystem.actionMode.IsEditor(),
			m_LightFactor = m_LastLightFactor,
			m_FrameDelta = m_RenderingSystem.frameDelta,
			m_SmoothnessDelta = m_RenderingSystem.frameDelta * 0.0016666667f,
			m_BuildingStateOverride = m_LastBuildingStateOverride,
			m_CullingFlags = cullingFlags,
			m_UpdateMasks = updateMasks,
			m_NativeBatchGroups = nativeBatchGroups,
			m_CullingData = m_PreCullingSystem.GetCullingData(readOnly: true, out dependencies3),
			m_WindData = m_WindSystem.GetData(readOnly: true, out dependencies4),
			m_NativeBatchInstances = nativeBatchInstances.AsParallelInstanceWriter(),
			m_SmoothingNeeded = m_SmoothingNeeded.AsParallelWriter()
		};
		JobHandle dependencies5;
		JobHandle dependencies6;
		BatchLodJob jobData2 = new BatchLodJob
		{
			m_DisableLods = m_RenderingSystem.disableLodModels,
			m_UseLodFade = flag,
			m_LodParameters = lodParameters,
			m_CameraPosition = cameraPosition,
			m_CameraDirection = cameraDirection,
			m_PixelSizeFactor = pixelSizeFactor,
			m_LodFadeDelta = lodFadeDelta,
			m_LoadingState = m_BatchMeshSystem.GetLoadingState(out dependencies5),
			m_NativeBatchGroups = nativeBatchGroups,
			m_NativeBatchInstances = cullingWriter.AsParallel(),
			m_BatchPriority = m_BatchMeshSystem.GetBatchPriority(out dependencies6)
		};
		if (!m_RenderingSettingsQuery.IsEmptyIgnoreFilter)
		{
			jobData.m_RenderingSettingsData = m_RenderingSettingsQuery.GetSingleton<RenderingSettingsData>();
		}
		JobHandle vTRequestMaxPixels = m_ManagedBatchSystem.GetVTRequestMaxPixels(out jobData2.m_VTRequestsMaxPixels0, out jobData2.m_VTRequestsMaxPixels1);
		JobHandle jobHandle = jobData.Schedule(jobData.m_CullingData, 16, JobUtils.CombineDependencies(base.Dependency, dependencies3, dependencies4, dependencies));
		JobHandle jobHandle2 = IJobParallelForExtensions.Schedule(jobData2, activeGroupCount, 1, JobUtils.CombineDependencies(jobHandle, vTRequestMaxPixels, dependencies6, dependencies5));
		JobHandle jobHandle3 = nativeBatchInstances.EndCulling(cullingWriter, jobHandle2);
		m_BatchManagerSystem.AddNativeBatchGroupsReader(jobHandle2);
		m_BatchManagerSystem.AddNativeBatchInstancesWriter(jobHandle3);
		m_BatchMeshSystem.AddBatchPriorityWriter(jobHandle2);
		m_BatchMeshSystem.AddLoadingStateReader(jobHandle2);
		m_ManagedBatchSystem.AddVTRequestWriter(jobHandle2);
		m_PreCullingSystem.AddCullingDataReader(jobHandle);
		m_WindSystem.AddReader(jobHandle);
		m_BatchMeshSystem.UpdateBatchPriorities();
		base.Dependency = jobHandle;
	}
```

- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PostDeserialize(Context context)
	{
		m_LastLaneConditionFrame = m_SimulationSystem.frameIndex;
		m_LastDamagedFrame = m_SimulationSystem.frameIndex;
	}
```

- `private UpdateGlobalValues(Colossal.Rendering.NativeBatchInstances<Game.Rendering.CullingData, Game.Rendering.GroupData, Game.Rendering.BatchData, Game.Rendering.InstanceData> nativeBatchInstances) : System.Void`  

```csharp
private void UpdateGlobalValues(NativeBatchInstances<CullingData, GroupData, BatchData, InstanceData> nativeBatchInstances)
	{
		SHCoefficients value = new SHCoefficients(RenderSettings.ambientProbe);
		nativeBatchInstances.SetGlobalValue(value, m_SHCoefficients);
	}
```


## Nested types

- `Game.Rendering.BatchDataSystem+UpdateMask`  
- `Game.Rendering.BatchDataSystem+UpdateMasks`  
- `Game.Rendering.BatchDataSystem+SmoothingType`  
- `Game.Rendering.BatchDataSystem+SmoothingNeeded`  
- `Game.Rendering.BatchDataSystem+CellTypes`  
- `Game.Rendering.BatchDataSystem+BatchDataJob`  
- `Game.Rendering.BatchDataSystem+BatchLodJob`  
- `Game.Rendering.BatchDataSystem+TypeHandle`  

