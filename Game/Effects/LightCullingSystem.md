# Game.Effects.LightCullingSystem

**Assembly:** `Game`  
**Namespace:** `Game.Effects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LightCullingSystem : Game.GameSystemBase
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Rendering.RenderingSystem m_RenderingSystem;
    private Game.Effects.EffectControlSystem m_EffectControlSystem;
    private Unity.Entities.EntityQuery m_LightEffectPrefabQuery;
    private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Effects.LightCullingSystem+LightEffectCullData> m_LightEffectCullData;
    private Unity.Collections.NativeQueue<Game.Effects.LightCullingSystem+VisibleLightData> m_VisibleLights;
    private Unity.Collections.NativeReference<System.Single> m_LastFrameMaxPunctualLightDistance;
    private Game.Effects.LightCullingSystem+TypeHandle __TypeHandle;
    private static Game.Effects.LightCullingSystem+DefaultLightParams s_DefaultLightParams;
    public static System.Boolean s_enableMinMaxLightCullingOptim;
    public static System.Single s_maxLightDistanceScale;
    public static System.Single s_minLightDistanceScale;

    public LightCullingSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void ComputeLightEffectCullData(Unity.Mathematics.float4 lodParameters);
    private static UnityEngine.Rendering.HighDefinition.GPULightType GetGPULightType(Game.Prefabs.Effects.LightEffect lightEffect);
    private System.Void GetRenderDataFromLigthEffet(UnityEngine.Rendering.HighDefinition.HDLightRenderData& hdLightRenderData, Game.Prefabs.LightEffectData lightEffectData, Game.Prefabs.Effects.LightEffect lightEffect, Unity.Mathematics.float4 lodParameters);
    private UnityEngine.Rendering.HighDefinition.AreaLightShape GetUnityAreaShape(Game.Rendering.AreaLightShape arealightShape);
    private UnityEngine.Rendering.HighDefinition.SpotLightShape GetUnitySpotShape(Game.Rendering.SpotLightShape spotlightShape);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    private System.Void ReadDefaultLightParams();
}
```


## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  

```csharp
private Game.Rendering.RenderingSystem m_RenderingSystem;
```

- `private Game.Effects.EffectControlSystem m_EffectControlSystem`  

```csharp
private Game.Effects.EffectControlSystem m_EffectControlSystem;
```

- `private Unity.Entities.EntityQuery m_LightEffectPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_LightEffectPrefabQuery;
```

- `private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Effects.LightCullingSystem+LightEffectCullData> m_LightEffectCullData`  

```csharp
private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Effects.LightCullingSystem+LightEffectCullData> m_LightEffectCullData;
```

- `private Unity.Collections.NativeQueue<Game.Effects.LightCullingSystem+VisibleLightData> m_VisibleLights`  

```csharp
private Unity.Collections.NativeQueue<Game.Effects.LightCullingSystem+VisibleLightData> m_VisibleLights;
```

- `private Unity.Collections.NativeReference<System.Single> m_LastFrameMaxPunctualLightDistance`  

```csharp
private Unity.Collections.NativeReference<System.Single> m_LastFrameMaxPunctualLightDistance;
```

- `private Game.Effects.LightCullingSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Effects.LightCullingSystem+TypeHandle __TypeHandle;
```

- `private static Game.Effects.LightCullingSystem+DefaultLightParams s_DefaultLightParams`  

```csharp
private static Game.Effects.LightCullingSystem+DefaultLightParams s_DefaultLightParams;
```

- `public static System.Boolean s_enableMinMaxLightCullingOptim`  

```csharp
public static System.Boolean s_enableMinMaxLightCullingOptim;
```

- `public static System.Single s_maxLightDistanceScale`  

```csharp
public static System.Single s_maxLightDistanceScale;
```

- `public static System.Single s_minLightDistanceScale`  

```csharp
public static System.Single s_minLightDistanceScale;
```


## Constructors

- `public LightCullingSystem()`  

```csharp
[Preserve]
	public LightCullingSystem()
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

- `private ComputeLightEffectCullData(Unity.Mathematics.float4 lodParameters) : System.Void`  

```csharp
private void ComputeLightEffectCullData(float4 lodParameters)
	{
		m_LightEffectCullData.Clear();
		NativeArray<ArchetypeChunk> nativeArray = m_LightEffectPrefabQuery.ToArchetypeChunkArray(Allocator.Temp);
		EntityTypeHandle entityTypeHandle = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef);
		ComponentTypeHandle<PrefabData> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
		ComponentTypeHandle<LightEffectData> typeHandle2 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_LightEffectData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
		CompleteDependency();
		int num = m_LightEffectPrefabQuery.CalculateEntityCount();
		float num2 = 1f / lodParameters.x;
		if (!HDRPDotsInputs.s_HdLightRenderData.IsCreated || num + 8 > HDRPDotsInputs.s_HdLightRenderData.Length)
		{
			ArrayExtensions.ResizeArray(ref HDRPDotsInputs.s_HdLightRenderData, num + 8);
		}
		LightEffectCullData item = default(LightEffectCullData);
		for (int i = 0; i < nativeArray.Length; i++)
		{
			ArchetypeChunk archetypeChunk = nativeArray[i];
			NativeArray<Entity> nativeArray2 = archetypeChunk.GetNativeArray(entityTypeHandle);
			NativeArray<PrefabData> nativeArray3 = archetypeChunk.GetNativeArray(ref typeHandle);
			NativeArray<LightEffectData> nativeArray4 = archetypeChunk.GetNativeArray(ref typeHandle2);
			for (int j = 0; j < nativeArray2.Length; j++)
			{
				Entity key = nativeArray2[j];
				PrefabData prefabData = nativeArray3[j];
				LightEffectData lightEffectData = nativeArray4[j];
				LightEffect component = m_PrefabSystem.GetPrefab<EffectPrefab>(prefabData).GetComponent<LightEffect>();
				item.m_LightEffectPrefabDataIndex = HDRPDotsInputs.s_lightEffectPrefabData.Length;
				item.m_lightType = component.m_Type;
				item.m_Range = component.m_Range;
				item.m_SpotAngle = component.m_SpotAngle;
				item.m_InvDistanceFactor = lightEffectData.m_InvDistanceFactor * num2;
				HDRPDotsInputs.s_lightEffectPrefabData.Add(default(HDRPDotsInputs.LightEffectPrefabData));
				HDRPDotsInputs.s_lightEffectPrefabCookies.Add(component.m_Cookie);
				GetRenderDataFromLigthEffet(ref HDRPDotsInputs.s_HdLightRenderData.ElementAt(item.m_LightEffectPrefabDataIndex), lightEffectData, component, lodParameters);
				m_LightEffectCullData.Add(key, item);
			}
		}
	}
```

- `private static GetGPULightType(Game.Prefabs.Effects.LightEffect lightEffect) : UnityEngine.Rendering.HighDefinition.GPULightType`  

```csharp
private static GPULightType GetGPULightType(LightEffect lightEffect)
	{
		if (lightEffect.m_Type == Game.Rendering.LightType.Spot)
		{
			if (lightEffect.m_SpotShape == Game.Rendering.SpotLightShape.Cone)
			{
				return GPULightType.Spot;
			}
			if (lightEffect.m_SpotShape == Game.Rendering.SpotLightShape.Pyramid)
			{
				return GPULightType.ProjectorPyramid;
			}
			if (lightEffect.m_SpotShape == Game.Rendering.SpotLightShape.Box)
			{
				return GPULightType.ProjectorBox;
			}
		}
		else
		{
			if (lightEffect.m_Type == Game.Rendering.LightType.Point)
			{
				return GPULightType.Point;
			}
			if (lightEffect.m_Type == Game.Rendering.LightType.Area)
			{
				if (lightEffect.m_AreaShape == Game.Rendering.AreaLightShape.Rectangle)
				{
					return GPULightType.Rectangle;
				}
				if (lightEffect.m_AreaShape == Game.Rendering.AreaLightShape.Tube)
				{
					return GPULightType.Tube;
				}
			}
		}
		throw new NotImplementedException($"Unsupported light type {lightEffect.m_Type}");
	}
```

- `private GetRenderDataFromLigthEffet(UnityEngine.Rendering.HighDefinition.HDLightRenderData& hdLightRenderData, Game.Prefabs.LightEffectData lightEffectData, Game.Prefabs.Effects.LightEffect lightEffect, Unity.Mathematics.float4 lodParameters) : System.Void`  

```csharp
private void GetRenderDataFromLigthEffet(ref HDLightRenderData hdLightRenderData, LightEffectData lightEffectData, LightEffect lightEffect, float4 lodParameters)
	{
		hdLightRenderData.pointLightType = ((lightEffect.m_Type == Game.Rendering.LightType.Area) ? HDAdditionalLightData.PointLightHDType.Area : HDAdditionalLightData.PointLightHDType.Punctual);
		hdLightRenderData.spotLightShape = GetUnitySpotShape(lightEffect.m_SpotShape);
		hdLightRenderData.areaLightShape = GetUnityAreaShape(lightEffect.m_AreaShape);
		hdLightRenderData.lightLayer = LightLayerEnum.Everything;
		hdLightRenderData.fadeDistance = 100000f;
		hdLightRenderData.distance = lightEffect.m_LuxAtDistance;
		hdLightRenderData.angularDiameter = lightEffect.m_SpotAngle;
		hdLightRenderData.volumetricFadeDistance = lightEffect.m_VolumetricFadeDistance;
		hdLightRenderData.includeForRayTracing = false;
		hdLightRenderData.useScreenSpaceShadows = false;
		hdLightRenderData.useRayTracedShadows = false;
		hdLightRenderData.colorShadow = false;
		hdLightRenderData.lightDimmer = lightEffect.m_LightDimmer;
		hdLightRenderData.volumetricDimmer = lightEffect.m_VolumetricDimmer;
		hdLightRenderData.shapeWidth = lightEffect.m_ShapeWidth;
		hdLightRenderData.shapeHeight = lightEffect.m_ShapeHeight;
		hdLightRenderData.aspectRatio = lightEffect.m_AspectRatio;
		hdLightRenderData.innerSpotPercent = lightEffect.m_InnerSpotPercentage;
		hdLightRenderData.spotIESCutoffPercent = 100f;
		hdLightRenderData.shadowDimmer = 1f;
		hdLightRenderData.volumetricShadowDimmer = 1f;
		hdLightRenderData.shadowFadeDistance = 0f;
		hdLightRenderData.shapeRadius = lightEffect.m_ShapeRadius;
		hdLightRenderData.barnDoorLength = lightEffect.m_BarnDoorLength;
		hdLightRenderData.barnDoorAngle = lightEffect.m_BarnDoorAngle;
		hdLightRenderData.flareSize = 0f;
		hdLightRenderData.flareFalloff = 0f;
		hdLightRenderData.affectVolumetric = lightEffect.m_UseVolumetric;
		hdLightRenderData.affectDiffuse = lightEffect.m_AffectDiffuse;
		hdLightRenderData.affectSpecular = lightEffect.m_AffectSpecular;
		hdLightRenderData.applyRangeAttenuation = lightEffect.m_ApplyRangeAttenuation;
		hdLightRenderData.penumbraTint = false;
		hdLightRenderData.interactsWithSky = false;
		hdLightRenderData.surfaceTint = Color.black;
		hdLightRenderData.shadowTint = Color.black;
		hdLightRenderData.flareTint = Color.black;
	}
```

- `private GetUnityAreaShape(Game.Rendering.AreaLightShape arealightShape) : UnityEngine.Rendering.HighDefinition.AreaLightShape`  

```csharp
private UnityEngine.Rendering.HighDefinition.AreaLightShape GetUnityAreaShape(Game.Rendering.AreaLightShape arealightShape)
	{
		return arealightShape switch
		{
			Game.Rendering.AreaLightShape.Tube => UnityEngine.Rendering.HighDefinition.AreaLightShape.Tube, 
			Game.Rendering.AreaLightShape.Rectangle => UnityEngine.Rendering.HighDefinition.AreaLightShape.Rectangle, 
			_ => UnityEngine.Rendering.HighDefinition.AreaLightShape.Rectangle, 
		};
	}
```

- `private GetUnitySpotShape(Game.Rendering.SpotLightShape spotlightShape) : UnityEngine.Rendering.HighDefinition.SpotLightShape`  

```csharp
private UnityEngine.Rendering.HighDefinition.SpotLightShape GetUnitySpotShape(Game.Rendering.SpotLightShape spotlightShape)
	{
		return spotlightShape switch
		{
			Game.Rendering.SpotLightShape.Pyramid => UnityEngine.Rendering.HighDefinition.SpotLightShape.Pyramid, 
			Game.Rendering.SpotLightShape.Box => UnityEngine.Rendering.HighDefinition.SpotLightShape.Box, 
			Game.Rendering.SpotLightShape.Cone => UnityEngine.Rendering.HighDefinition.SpotLightShape.Cone, 
			_ => UnityEngine.Rendering.HighDefinition.SpotLightShape.Cone, 
		};
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_RenderingSystem = base.World.GetOrCreateSystemManaged<RenderingSystem>();
		m_EffectControlSystem = base.World.GetOrCreateSystemManaged<EffectControlSystem>();
		m_LightEffectPrefabQuery = GetEntityQuery(ComponentType.ReadOnly<LightEffectData>(), ComponentType.ReadOnly<PrefabData>());
		m_LightEffectCullData = new NativeParallelHashMap<Entity, LightEffectCullData>(128, Allocator.Persistent);
		m_VisibleLights = new NativeQueue<VisibleLightData>(Allocator.Persistent);
		m_LastFrameMaxPunctualLightDistance = new NativeReference<float>(Allocator.Persistent);
		m_LastFrameMaxPunctualLightDistance.Value = -1f;
		ReadDefaultLightParams();
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
		HDRPDotsInputs.punctualLightsJobHandle.Complete();
		m_LastFrameMaxPunctualLightDistance.Dispose();
		m_VisibleLights.Dispose();
		m_LightEffectCullData.Dispose();
		HDRPDotsInputs.ClearFrameLightData();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		HDRPDotsInputs.punctualLightsJobHandle.Complete();
		HDRPDotsInputs.MaxPunctualLights = m_RenderingSystem.maxLightCount;
		HDRPDotsInputs.ClearFrameLightData();
		Camera main = Camera.main;
		if (!(main == null))
		{
			m_EffectControlSystem.GetLodParameters(out var lodParameters, out var cameraPosition, out var cameraDirection);
			ComputeLightEffectCullData(lodParameters);
			Plane[] array = GeometryUtility.CalculateFrustumPlanes(main);
			NativeArray<float4> planes = new NativeArray<float4>(6, Allocator.TempJob);
			for (int i = 0; i < array.Length; i++)
			{
				planes[i] = new float4(array[i].normal, array[i].distance);
			}
			if (!s_enableMinMaxLightCullingOptim)
			{
				m_LastFrameMaxPunctualLightDistance.Value = -1f;
			}
			float autoRejectDistance = 1f;
			if (m_LastFrameMaxPunctualLightDistance.Value > 0f)
			{
				autoRejectDistance = m_LastFrameMaxPunctualLightDistance.Value * s_maxLightDistanceScale;
			}
			JobHandle dependencies;
			LightCullingJob jobData = new LightCullingJob
			{
				m_LightEffectCullData = m_LightEffectCullData,
				m_Planes = planes,
				m_EnabledEffectData = m_EffectControlSystem.GetEnabledData(readOnly: true, out dependencies),
				m_LodParameters = lodParameters,
				m_CameraPosition = cameraPosition,
				m_CameraDirection = cameraDirection,
				m_AutoRejectDistance = autoRejectDistance,
				m_VisibleLights = m_VisibleLights.AsParallelWriter()
			};
			JobHandle jobHandle = jobData.Schedule(jobData.m_EnabledEffectData, 16, dependencies);
			m_EffectControlSystem.AddEnabledDataReader(jobHandle);
			HDRPDotsInputs.punctualLightsJobHandle = IJobExtensions.Schedule(new SortAndBuildPunctualLightsJob
			{
				m_maxLights = HDRPDotsInputs.MaxPunctualLights,
				m_minDistanceScale = s_minLightDistanceScale,
				m_PunctualLightsOut = HDRPDotsInputs.s_punctualLightdata,
				m_LightEffectPrefabData = HDRPDotsInputs.s_lightEffectPrefabData,
				m_VisibleLightsOut = HDRPDotsInputs.s_punctualVisibleLights,
				m_LightEffectCullData = m_LightEffectCullData,
				m_VisibleLights = m_VisibleLights,
				m_MaxDistance = m_LastFrameMaxPunctualLightDistance
			}, jobHandle);
		}
	}
```

- `private ReadDefaultLightParams() : System.Void`  

```csharp
private void ReadDefaultLightParams()
	{
		GameObject gameObject = new GameObject("Default LightSource");
		HDAdditionalLightData hDAdditionalLightData = gameObject.AddHDLight(HDLightTypeAndShape.ConeSpot);
		s_DefaultLightParams.shapeWidth = hDAdditionalLightData.shapeWidth;
		s_DefaultLightParams.shapeHeight = hDAdditionalLightData.shapeHeight;
		s_DefaultLightParams.spotIESCutoffPercent01 = hDAdditionalLightData.spotIESCutoffPercent01;
		s_DefaultLightParams.shapeRadius = hDAdditionalLightData.shapeRadius;
		CoreUtils.Destroy(gameObject);
	}
```


## Nested types

- `Game.Effects.LightCullingSystem+DefaultLightParams`  
- `Game.Effects.LightCullingSystem+LightEffectCullData`  
- `Game.Effects.LightCullingSystem+LightCullingJob`  
- `Game.Effects.LightCullingSystem+VisibleLightData`  
- `Game.Effects.LightCullingSystem+SortAndBuildPunctualLightsJob`  
- `Game.Effects.LightCullingSystem+TypeHandle`  

