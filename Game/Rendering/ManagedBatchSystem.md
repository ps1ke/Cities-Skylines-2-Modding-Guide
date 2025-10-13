# Game.Rendering.ManagedBatchSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ManagedBatchSystem : Game.GameSystemBase
{
    private System.Int32 <groupCount>k__BackingField;
    private System.Int32 <batchCount>k__BackingField;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Rendering.RenderingSystem m_RenderingSystem;
    private Game.Rendering.BatchMeshSystem m_BatchMeshSystem;
    private Game.Rendering.BatchManagerSystem m_BatchManagerSystem;
    private Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem m_TextureStreamingSystem;
    private System.Collections.Generic.Dictionary<Game.Rendering.ManagedBatchSystem+MaterialKey, UnityEngine.Material> m_Materials;
    private System.Collections.Generic.Dictionary<Game.Rendering.ManagedBatchSystem+GroupKey, Unity.Entities.Entity> m_Groups;
    private System.Collections.Generic.Dictionary<Game.Rendering.ManagedBatchSystem+MeshKey, Unity.Entities.Entity> m_Meshes;
    private System.Collections.Generic.List<Game.Rendering.ManagedBatchSystem+KeywordData> m_CachedKeywords;
    private System.Collections.Generic.List<Game.Rendering.ManagedBatchSystem+TextureData> m_CachedTextures;
    private Game.Rendering.ManagedBatchSystem+MaterialKey m_CachedMaterialKey;
    private Game.Rendering.ManagedBatchSystem+GroupKey m_CachedGroupKey;
    private Colossal.Rendering.VTTextureRequester m_VTTextureRequester;
    private Unity.Jobs.JobHandle m_VTRequestDependencies;
    private Unity.Entities.EntityQuery m_MeshSettingsQuery;
    private System.Boolean m_VTRequestsUpdated;
    private System.Int32 m_TunnelLayer;
    private System.Int32 m_MovingLayer;
    private System.Int32 m_PipelineLayer;
    private System.Int32 m_SubPipelineLayer;
    private System.Int32 m_WaterwayLayer;
    private System.Int32 m_OutlineLayer;
    private System.Int32 m_MarkerLayer;
    private System.Int32 m_DecalLayerMask;
    private System.Int32 m_AnimationTexture;
    private System.Int32 m_UseStack1;
    private System.Int32 m_ImpostorSize;
    private System.Int32 m_ImpostorOffset;
    private System.Int32 m_WorldspaceAlbedo;
    private System.Int32 m_MaskMap;

    public System.Int32 materialCount { get; }
    public System.Int32 groupCount { get; private set; }
    public System.Int32 batchCount { get; private set; }
    public System.Collections.Generic.IReadOnlyDictionary<Game.Rendering.ManagedBatchSystem+MaterialKey, UnityEngine.Material> materials { get; }
    public Colossal.Rendering.VTTextureRequester VTTextureRequester { get; }

    public ManagedBatchSystem();

    public System.Void AddVTRequestWriter(Unity.Jobs.JobHandle dependencies);
    public System.Void CompleteVTRequests();
    private Game.Rendering.CustomBatch CreateBatch(System.Int32 groupIndex, System.Int32 batchIndex, Unity.Entities.Entity sharedMesh, Game.Rendering.GroupData& groupData, Game.Rendering.BatchData& batchData, Game.Rendering.PropertyData& lodFadeData);
    private UnityEngine.Material CreateMaterial(Colossal.IO.AssetDatabase.SurfaceAsset sourceSurface, UnityEngine.Material sourceMaterial, Game.Rendering.ManagedBatchSystem+MaterialKey materialKey);
    private System.Void DisableKeyword(Game.Rendering.ManagedBatchSystem+MaterialKey materialKey, System.String keyword);
    public System.Void EnabledShadersUpdated();
    private System.Void EnableKeyword(Game.Rendering.ManagedBatchSystem+MaterialKey materialKey, System.String keyword);
    public static UnityEngine.Material GetTemplate(Colossal.IO.AssetDatabase.SurfaceAsset surfaceAsset);
    public Unity.Jobs.JobHandle GetVTRequestMaxPixels(Unity.Collections.NativeList`1[[System.Single, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& maxPixels0, Unity.Collections.NativeList`1[[System.Single, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& maxPixels1);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void ReloadVT();
    public System.Void RemoveMesh(Unity.Entities.Entity oldMesh, Unity.Entities.Entity newMesh);
    public System.Void ResetSharedMeshes();
    public System.Void ResetVT(System.Int32 desiredMipBias, UnityEngine.Rendering.VirtualTexturing.FilterMode filterMode);
    private System.Void SetTexture(Game.Rendering.ManagedBatchSystem+MaterialKey materialKey, System.Int32 nameID, UnityEngine.Texture texture);
    public System.Void SetupVT(Game.Prefabs.RenderPrefab meshPrefab, UnityEngine.Material material, System.Int32 materialIndex);
}
```


## Fields

- `private System.Int32 <groupCount>k__BackingField`  

```csharp
private System.Int32 <groupCount>k__BackingField;
```

- `private System.Int32 <batchCount>k__BackingField`  

```csharp
private System.Int32 <batchCount>k__BackingField;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  

```csharp
private Game.Rendering.RenderingSystem m_RenderingSystem;
```

- `private Game.Rendering.BatchMeshSystem m_BatchMeshSystem`  

```csharp
private Game.Rendering.BatchMeshSystem m_BatchMeshSystem;
```

- `private Game.Rendering.BatchManagerSystem m_BatchManagerSystem`  

```csharp
private Game.Rendering.BatchManagerSystem m_BatchManagerSystem;
```

- `private Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem m_TextureStreamingSystem`  

```csharp
private Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem m_TextureStreamingSystem;
```

- `private System.Collections.Generic.Dictionary<Game.Rendering.ManagedBatchSystem+MaterialKey, UnityEngine.Material> m_Materials`  

```csharp
private System.Collections.Generic.Dictionary<Game.Rendering.ManagedBatchSystem+MaterialKey, UnityEngine.Material> m_Materials;
```

- `private System.Collections.Generic.Dictionary<Game.Rendering.ManagedBatchSystem+GroupKey, Unity.Entities.Entity> m_Groups`  

```csharp
private System.Collections.Generic.Dictionary<Game.Rendering.ManagedBatchSystem+GroupKey, Unity.Entities.Entity> m_Groups;
```

- `private System.Collections.Generic.Dictionary<Game.Rendering.ManagedBatchSystem+MeshKey, Unity.Entities.Entity> m_Meshes`  

```csharp
private System.Collections.Generic.Dictionary<Game.Rendering.ManagedBatchSystem+MeshKey, Unity.Entities.Entity> m_Meshes;
```

- `private System.Collections.Generic.List<Game.Rendering.ManagedBatchSystem+KeywordData> m_CachedKeywords`  

```csharp
private System.Collections.Generic.List<Game.Rendering.ManagedBatchSystem+KeywordData> m_CachedKeywords;
```

- `private System.Collections.Generic.List<Game.Rendering.ManagedBatchSystem+TextureData> m_CachedTextures`  

```csharp
private System.Collections.Generic.List<Game.Rendering.ManagedBatchSystem+TextureData> m_CachedTextures;
```

- `private Game.Rendering.ManagedBatchSystem+MaterialKey m_CachedMaterialKey`  

```csharp
private Game.Rendering.ManagedBatchSystem+MaterialKey m_CachedMaterialKey;
```

- `private Game.Rendering.ManagedBatchSystem+GroupKey m_CachedGroupKey`  

```csharp
private Game.Rendering.ManagedBatchSystem+GroupKey m_CachedGroupKey;
```

- `private Colossal.Rendering.VTTextureRequester m_VTTextureRequester`  

```csharp
private Colossal.Rendering.VTTextureRequester m_VTTextureRequester;
```

- `private Unity.Jobs.JobHandle m_VTRequestDependencies`  

```csharp
private Unity.Jobs.JobHandle m_VTRequestDependencies;
```

- `private Unity.Entities.EntityQuery m_MeshSettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_MeshSettingsQuery;
```

- `private System.Boolean m_VTRequestsUpdated`  

```csharp
private System.Boolean m_VTRequestsUpdated;
```

- `private System.Int32 m_TunnelLayer`  

```csharp
private System.Int32 m_TunnelLayer;
```

- `private System.Int32 m_MovingLayer`  

```csharp
private System.Int32 m_MovingLayer;
```

- `private System.Int32 m_PipelineLayer`  

```csharp
private System.Int32 m_PipelineLayer;
```

- `private System.Int32 m_SubPipelineLayer`  

```csharp
private System.Int32 m_SubPipelineLayer;
```

- `private System.Int32 m_WaterwayLayer`  

```csharp
private System.Int32 m_WaterwayLayer;
```

- `private System.Int32 m_OutlineLayer`  

```csharp
private System.Int32 m_OutlineLayer;
```

- `private System.Int32 m_MarkerLayer`  

```csharp
private System.Int32 m_MarkerLayer;
```

- `private System.Int32 m_DecalLayerMask`  

```csharp
private System.Int32 m_DecalLayerMask;
```

- `private System.Int32 m_AnimationTexture`  

```csharp
private System.Int32 m_AnimationTexture;
```

- `private System.Int32 m_UseStack1`  

```csharp
private System.Int32 m_UseStack1;
```

- `private System.Int32 m_ImpostorSize`  

```csharp
private System.Int32 m_ImpostorSize;
```

- `private System.Int32 m_ImpostorOffset`  

```csharp
private System.Int32 m_ImpostorOffset;
```

- `private System.Int32 m_WorldspaceAlbedo`  

```csharp
private System.Int32 m_WorldspaceAlbedo;
```

- `private System.Int32 m_MaskMap`  

```csharp
private System.Int32 m_MaskMap;
```


## Properties

- `public System.Int32 materialCount { get }`  

```csharp
public System.Int32 materialCount { get; }
```

- `public System.Int32 groupCount { get; private set }`  

```csharp
public System.Int32 groupCount { get; private set; }
```

- `public System.Int32 batchCount { get; private set }`  

```csharp
public System.Int32 batchCount { get; private set; }
```

- `public System.Collections.Generic.IReadOnlyDictionary<Game.Rendering.ManagedBatchSystem+MaterialKey, UnityEngine.Material> materials { get }`  

```csharp
public System.Collections.Generic.IReadOnlyDictionary<Game.Rendering.ManagedBatchSystem+MaterialKey, UnityEngine.Material> materials { get; }
```

- `public Colossal.Rendering.VTTextureRequester VTTextureRequester { get }`  

```csharp
public Colossal.Rendering.VTTextureRequester VTTextureRequester { get; }
```


## Constructors

- `public ManagedBatchSystem()`  

```csharp
[Preserve]
	public ManagedBatchSystem()
	{
	}
```


## Methods

- `public AddVTRequestWriter(Unity.Jobs.JobHandle dependencies) : System.Void`  

```csharp
public void AddVTRequestWriter(JobHandle dependencies)
	{
		m_VTRequestDependencies = dependencies;
		m_VTRequestsUpdated = true;
	}
```

- `public CompleteVTRequests() : System.Void`  

```csharp
public void CompleteVTRequests()
	{
		if (m_VTRequestsUpdated)
		{
			m_VTRequestDependencies.Complete();
			m_VTTextureRequester.UpdateTexturesVTRequests();
			m_VTRequestsUpdated = false;
		}
		m_TextureStreamingSystem.UpdateWorkingSetMipBias();
	}
```

- `private CreateBatch(System.Int32 groupIndex, System.Int32 batchIndex, Unity.Entities.Entity sharedMesh, Game.Rendering.GroupData& groupData, Game.Rendering.BatchData& batchData, Game.Rendering.PropertyData& lodFadeData) : Game.Rendering.CustomBatch`  

```csharp
private CustomBatch CreateBatch(int groupIndex, int batchIndex, Entity sharedMesh, ref GroupData groupData, ref BatchData batchData, out PropertyData lodFadeData)
	{
		SurfaceAsset surfaceAsset = null;
		Material material = null;
		Material value = null;
		Material value2 = null;
		Mesh mesh = null;
		MaterialPropertyBlock materialPropertyBlock = null;
		Entity entity = Entity.Null;
		ShadowCastingMode shadowCastingMode = ShadowCastingMode.On;
		bool flag = true;
		BatchFlags batchFlags = (BatchFlags)0;
		GeneratedType generatedType = GeneratedType.None;
		int num = 0;
		int num2 = batchData.m_SubMeshIndex;
		MaterialKey materialKey;
		if (m_CachedMaterialKey != null)
		{
			materialKey = m_CachedMaterialKey;
			m_CachedMaterialKey = null;
		}
		else
		{
			materialKey = new MaterialKey();
		}
		lodFadeData = new PropertyData
		{
			m_DataIndex = -1
		};
		m_CachedKeywords.Clear();
		m_CachedTextures.Clear();
		Entity entity2;
		if (batchData.m_LodMesh != Entity.Null)
		{
			entity = batchData.m_LodMesh;
			entity2 = groupData.m_Mesh;
		}
		else
		{
			entity = groupData.m_Mesh;
			entity2 = Entity.Null;
		}
		if (batchData.m_LodIndex > 0)
		{
			batchFlags |= BatchFlags.Lod;
		}
		if (groupData.m_MeshType == MeshType.Zone)
		{
			material = m_PrefabSystem.GetPrefab<ZoneBlockPrefab>(entity).m_Material;
			materialKey.Initialize(material);
			if (groupData.m_Partition >= 1)
			{
				batchFlags |= BatchFlags.Extended1;
			}
			if (groupData.m_Partition >= 2)
			{
				batchFlags |= BatchFlags.Extended2;
			}
			if (groupData.m_Partition >= 3)
			{
				batchFlags |= BatchFlags.Extended3;
			}
			shadowCastingMode = ShadowCastingMode.Off;
			flag = false;
		}
		else if (groupData.m_MeshType == MeshType.Net)
		{
			NetCompositionMeshData componentData = base.EntityManager.GetComponentData<NetCompositionMeshData>(entity);
			DynamicBuffer<MeshMaterial> buffer = base.EntityManager.GetBuffer<MeshMaterial>(entity, isReadOnly: true);
			DynamicBuffer<NetCompositionPiece> buffer2 = base.EntityManager.GetBuffer<NetCompositionPiece>(entity, isReadOnly: true);
			int materialIndex = buffer[num2].m_MaterialIndex;
			for (int i = 0; i < buffer2.Length; i++)
			{
				NetCompositionPiece netCompositionPiece = buffer2[i];
				if (!base.EntityManager.TryGetBuffer(netCompositionPiece.m_Piece, isReadOnly: true, out DynamicBuffer<MeshMaterial> buffer3))
				{
					continue;
				}
				int num3 = 0;
				while (num3 < buffer3.Length)
				{
					if (buffer3[num3].m_MaterialIndex != materialIndex)
					{
						num3++;
						continue;
					}
					goto IL_01c9;
				}
				continue;
				IL_01c9:
				surfaceAsset = m_PrefabSystem.GetPrefab<RenderPrefab>(netCompositionPiece.m_Piece).GetSurfaceAsset(num3);
				surfaceAsset.LoadProperties(useVT: true);
				materialKey.Initialize(surfaceAsset);
				break;
			}
			materialKey.decalLayerMask = 2;
			lodFadeData = m_BatchManagerSystem.GetPropertyData(((batchData.m_LodIndex & 1) == 0) ? NetProperty.LodFade0 : NetProperty.LodFade1);
			batchFlags |= BatchFlags.InfoviewColor | BatchFlags.LodFade;
			generatedType = GeneratedType.NetComposition;
			sharedMesh = entity;
			if ((componentData.m_Flags.m_General & CompositionFlags.General.Node) != 0)
			{
				batchFlags |= BatchFlags.Node;
			}
			if ((componentData.m_Flags.m_General & CompositionFlags.General.Roundabout) != 0)
			{
				batchFlags |= BatchFlags.Roundabout;
			}
			if ((componentData.m_State & MeshFlags.Default) != 0)
			{
				materialKey.textures.Clear();
				materialKey.textures.Add(m_WorldspaceAlbedo, Texture2D.grayTexture);
			}
			batchData.m_ShadowArea = float.PositiveInfinity;
			batchData.m_ShadowHeight = 1f;
			if ((componentData.m_Flags.m_General & CompositionFlags.General.Elevated) != 0 || (componentData.m_Flags.m_Left & (CompositionFlags.Side.Raised | CompositionFlags.Side.Lowered | CompositionFlags.Side.SoundBarrier)) != 0 || (componentData.m_Flags.m_Right & (CompositionFlags.Side.Raised | CompositionFlags.Side.Lowered | CompositionFlags.Side.SoundBarrier)) != 0 || (componentData.m_State & MeshFlags.Default) != 0)
			{
				batchData.m_ShadowHeight = componentData.m_Width;
			}
		}
		else
		{
			RenderPrefab renderPrefab = m_PrefabSystem.GetPrefab<RenderPrefab>(entity);
			MeshData componentData2 = base.EntityManager.GetComponentData<MeshData>(entity);
			SharedMeshData componentData3 = base.EntityManager.GetComponentData<SharedMeshData>(entity);
			RenderPrefab renderPrefab2 = null;
			if (entity2 != Entity.Null)
			{
				renderPrefab2 = m_PrefabSystem.GetPrefab<RenderPrefab>(entity2);
			}
			if (batchData.m_LodIndex > 0)
			{
				MeshKey key = new MeshKey(renderPrefab, componentData2);
				if (!m_Meshes.TryGetValue(key, out sharedMesh))
				{
					m_Meshes.Add(key, entity);
					sharedMesh = entity;
				}
			}
			componentData3.m_Mesh = sharedMesh;
			base.EntityManager.SetComponentData(entity, componentData3);
			DecalProperties decalProperties = renderPrefab.GetComponent<DecalProperties>();
			AnimationProperties component = renderPrefab.GetComponent<AnimationProperties>();
			ProceduralAnimationProperties component2 = renderPrefab.GetComponent<ProceduralAnimationProperties>();
			EmissiveProperties component3 = renderPrefab.GetComponent<EmissiveProperties>();
			ColorProperties component4 = renderPrefab.GetComponent<ColorProperties>();
			CurveProperties component5 = renderPrefab.GetComponent<CurveProperties>();
			DilationProperties component6 = renderPrefab.GetComponent<DilationProperties>();
			OverlayProperties component7 = renderPrefab.GetComponent<OverlayProperties>();
			BaseProperties component8 = renderPrefab.GetComponent<BaseProperties>();
			if (component3 == null && renderPrefab2 != null)
			{
				component3 = renderPrefab2.GetComponent<EmissiveProperties>();
			}
			if (component4 == null && renderPrefab2 != null)
			{
				component4 = renderPrefab2.GetComponent<ColorProperties>();
			}
			if (component8 == null && renderPrefab2 != null)
			{
				component8 = renderPrefab2.GetComponent<BaseProperties>();
			}
			if (decalProperties != null && groupData.m_Layer == MeshLayer.Outline)
			{
				MeshSettingsData singleton = m_MeshSettingsQuery.GetSingleton<MeshSettingsData>();
				renderPrefab = m_PrefabSystem.GetPrefab<RenderPrefab>(singleton.m_MissingObjectMesh);
				num2 = 0;
				surfaceAsset = renderPrefab.GetSurfaceAsset(num2);
				decalProperties = null;
			}
			else if ((componentData2.m_State & MeshFlags.Base) != 0 && num2 == componentData2.m_SubMeshCount)
			{
				if (component8 != null)
				{
					renderPrefab = component8.m_BaseType;
				}
				else
				{
					MeshSettingsData singleton2 = m_MeshSettingsQuery.GetSingleton<MeshSettingsData>();
					renderPrefab = m_PrefabSystem.GetPrefab<RenderPrefab>(singleton2.m_DefaultBaseMesh);
				}
				num2 = 0;
				surfaceAsset = renderPrefab.GetSurfaceAsset(num2);
				generatedType = GeneratedType.ObjectBase;
				batchFlags |= BatchFlags.Base;
			}
			else
			{
				surfaceAsset = renderPrefab.GetSurfaceAsset(num2);
			}
			if (groupData.m_MeshType == MeshType.Object)
			{
				lodFadeData = m_BatchManagerSystem.GetPropertyData(((batchData.m_LodIndex & 1) == 0) ? ObjectProperty.LodFade0 : ObjectProperty.LodFade1);
			}
			else if (groupData.m_MeshType == MeshType.Lane)
			{
				lodFadeData = m_BatchManagerSystem.GetPropertyData(((batchData.m_LodIndex & 1) == 0) ? LaneProperty.LodFade0 : LaneProperty.LodFade1);
			}
			surfaceAsset.LoadProperties(useVT: true);
			materialKey.Initialize(surfaceAsset);
			Bounds3 bounds = RenderingUtils.SafeBounds(componentData2.m_Bounds);
			float3 @float = MathUtils.Center(bounds);
			float3 float2 = MathUtils.Size(bounds);
			float4 float3 = new float4(float2, @float.y);
			batchData.m_ShadowHeight = float2.y;
			batchData.m_ShadowArea = math.sqrt(float2.x * float2.x + float2.z * float2.z) * batchData.m_ShadowHeight;
			VTAtlassingInfo[] array = surfaceAsset.VTAtlassingInfos;
			if (array == null)
			{
				array = surfaceAsset.PreReservedAtlassingInfos;
			}
			int lod = componentData2.m_MinLod;
			if (groupData.m_MeshType == MeshType.Lane)
			{
				lod = groupData.m_Partition;
			}
			PropertyData propertyData = m_BatchManagerSystem.GetPropertyData(MaterialProperty.TextureArea);
			PropertyData propertyData2 = m_BatchManagerSystem.GetPropertyData(MaterialProperty.MeshSize);
			PropertyData propertyData3 = m_BatchManagerSystem.GetPropertyData(MaterialProperty.LodDistanceFactor);
			PropertyData propertyData4 = m_BatchManagerSystem.GetPropertyData(MaterialProperty.SingleLightsOffset);
			PropertyData propertyData5 = m_BatchManagerSystem.GetPropertyData(MaterialProperty.DilationParams);
			if (decalProperties != null)
			{
				materialKey.renderQueue = materialKey.template.shader.renderQueue + decalProperties.m_RendererPriority;
				if (materialPropertyBlock == null)
				{
					materialPropertyBlock = new MaterialPropertyBlock();
				}
				materialPropertyBlock.SetVector(propertyData.m_NameID, new float4(decalProperties.m_TextureArea.min, decalProperties.m_TextureArea.max));
				materialPropertyBlock.SetVector(propertyData2.m_NameID, float3);
				materialPropertyBlock.SetFloat(propertyData3.m_NameID, RenderingUtils.CalculateDistanceFactor(lod));
				materialKey.decalLayerMask = (int)decalProperties.m_LayerMask;
				if (array != null)
				{
					Bounds2 bounds2 = MathUtils.Bounds(decalProperties.m_TextureArea.min, decalProperties.m_TextureArea.max);
					m_VTRequestDependencies.Complete();
					if (array.Length >= 1 && array[0].indexInStack >= 0)
					{
						batchData.m_VTIndex0 = m_VTTextureRequester.RegisterTexture(0, array[0].stackGlobalIndex, array[0].indexInStack, bounds2);
					}
					if (array.Length >= 2 && array[1].indexInStack >= 0)
					{
						batchData.m_VTIndex1 = m_VTTextureRequester.RegisterTexture(1, array[1].stackGlobalIndex, array[1].indexInStack, bounds2);
					}
					batchData.m_VTSizeFactor = math.cmax(float2);
				}
				if (groupData.m_MeshType == MeshType.Lane)
				{
					materialPropertyBlock.SetFloat(m_BatchManagerSystem.GetPropertyData(MaterialProperty.SmoothingDistance).m_NameID, componentData2.m_SmoothingDistance);
				}
				if (decalProperties.m_EnableInfoviewColor)
				{
					batchFlags |= BatchFlags.InfoviewColor;
				}
			}
			else
			{
				DecalLayers decalLayerMask = ((componentData2.m_DecalLayer != 0) ? componentData2.m_DecalLayer : DecalLayers.Other);
				materialKey.decalLayerMask = (int)decalLayerMask;
				batchFlags |= BatchFlags.InfoviewColor | BatchFlags.LodFade | BatchFlags.SurfaceState;
			}
			bool flag2 = groupData.m_MeshType == MeshType.Object;
			bool flag3 = groupData.m_MeshType == MeshType.Lane;
			if (component != null && component.m_Clips != null && component.m_Clips.Length != 0)
			{
				AnimationProperties.BakedAnimationClip bakedAnimationClip = component.m_Clips[0];
				SetTexture(materialKey, m_AnimationTexture, bakedAnimationClip.animationTexture);
				DisableKeyword(materialKey, "_GPU_ANIMATION_TEXTURE");
				batchFlags |= BatchFlags.MotionVectors | BatchFlags.Animated;
			}
			if (component2 != null && component2.m_Bones != null && component2.m_Bones.Length != 0)
			{
				PropertyData propertyData6 = m_BatchManagerSystem.GetPropertyData(ObjectProperty.BoneParameters);
				if (materialPropertyBlock == null)
				{
					materialPropertyBlock = new MaterialPropertyBlock();
				}
				materialPropertyBlock.SetVector(propertyData6.m_NameID, new Vector2(math.asfloat(0), math.asfloat(component2.m_Bones.Length)));
				EnableKeyword(materialKey, "_GPU_ANIMATION_PROCEDURAL");
				batchFlags |= BatchFlags.MotionVectors | BatchFlags.Bones;
				flag2 = false;
			}
			if (component3 != null && component3.hasAnyLights)
			{
				PropertyData propertyData7 = m_BatchManagerSystem.GetPropertyData(ObjectProperty.LightParameters);
				if (materialPropertyBlock == null)
				{
					materialPropertyBlock = new MaterialPropertyBlock();
				}
				materialPropertyBlock.SetVector(propertyData7.m_NameID, new Vector2(0f, component3.lightsCount));
				materialPropertyBlock.SetFloat(propertyData4.m_NameID, component3.GetSingleLightOffset(batchData.m_SubMeshIndex));
				batchFlags |= BatchFlags.Emissive;
			}
			if (component4 != null && component4.m_ColorVariations != null && component4.m_ColorVariations.Count != 0)
			{
				batchFlags |= BatchFlags.ColorMask;
			}
			if ((componentData2.m_State & MeshFlags.Character) != 0)
			{
				if (materialPropertyBlock == null)
				{
					materialPropertyBlock = new MaterialPropertyBlock();
				}
				m_BatchMeshSystem.SetShapeParameters(materialPropertyBlock, sharedMesh, num2);
				batchFlags |= BatchFlags.Bones | BatchFlags.BlendWeights;
			}
			if (component5 != null)
			{
				if (component5.m_GeometryTiling)
				{
					if (materialPropertyBlock == null)
					{
						materialPropertyBlock = new MaterialPropertyBlock();
					}
					float4 float4 = new float4(0.1f, 10f, 0f, 0f);
					if (componentData2.m_TilingCount != 0 && component5.m_StraightTiling)
					{
						float4.x = 1f / (float)componentData2.m_TilingCount;
						float4.y = 0.01f;
					}
					materialPropertyBlock.SetVector(propertyData5.m_NameID, float4);
					EnableKeyword(materialKey, "COLOSSAL_GEOMETRY_TILING");
					flag3 = false;
				}
				if (component5.m_SubFlow)
				{
					batchFlags |= BatchFlags.InfoviewFlow;
				}
				if (component5.m_HangingSwaying)
				{
					batchFlags |= BatchFlags.Hanging;
					float num4 = batchData.m_ShadowArea / batchData.m_ShadowHeight;
					batchData.m_ShadowHeight += 0.5f;
					batchData.m_ShadowArea = num4 * batchData.m_ShadowHeight;
				}
			}
			if (component6 != null)
			{
				if (materialPropertyBlock == null)
				{
					materialPropertyBlock = new MaterialPropertyBlock();
				}
				float4 float5 = new float4(component6.m_MinSize, 1f / math.max(1E-05f, math.max(float3.x, float3.y)), component6.m_InfoviewFactor * 2.5f, 2.5f);
				if (component6.m_InfoviewOnly)
				{
					float5.x = math.max(float3.x, float3.y);
					float5.w = 0f;
				}
				materialPropertyBlock.SetVector(propertyData5.m_NameID, float5);
				materialPropertyBlock.SetFloat(propertyData3.m_NameID, RenderingUtils.CalculateDistanceFactor(lod));
				EnableKeyword(materialKey, "COLOSSAL_GEOMETRY_DILATED");
				flag3 = false;
				if (surfaceAsset.keywords.Contains("_SURFACE_TYPE_TRANSPARENT"))
				{
					batchFlags &= ~BatchFlags.LodFade;
				}
			}
			if (flag2)
			{
				EnableKeyword(materialKey, "_GPU_ANIMATION_OFF");
			}
			if (flag3)
			{
				EnableKeyword(materialKey, "COLOSSAL_GEOMETRY_DEFAULT");
			}
			if (component7 != null)
			{
				if (materialKey.template.renderQueue == 3000)
				{
					materialKey.renderQueue = 3900;
				}
				if (materialPropertyBlock == null)
				{
					materialPropertyBlock = new MaterialPropertyBlock();
				}
				materialPropertyBlock.SetVector(propertyData.m_NameID, new float4(component7.m_TextureArea.min, component7.m_TextureArea.max));
				materialPropertyBlock.SetVector(propertyData2.m_NameID, float3);
				materialPropertyBlock.SetFloat(propertyData3.m_NameID, RenderingUtils.CalculateDistanceFactor(lod));
				batchFlags &= ~BatchFlags.SurfaceState;
			}
			else if (decalProperties == null && materialKey.template.renderQueue >= 2000 && materialKey.template.renderQueue <= 2500 && math.any(MathUtils.Size(bounds) < new float3(7f, 3f, 7f)))
			{
				materialKey.renderQueue = materialKey.template.renderQueue + 1;
			}
			if (decalProperties != null || component7 != null)
			{
				shadowCastingMode = ShadowCastingMode.Off;
				flag = false;
			}
			if (renderPrefab.isImpostor)
			{
				ImpostorData componentData4 = base.EntityManager.GetComponentData<ImpostorData>(entity);
				surfaceAsset.vectors.TryGetValue("_ImpostorOffset", out var value3);
				componentData4.m_Offset = ((float4)value3).xyz;
				surfaceAsset.floats.TryGetValue("_ImpostorSize", out componentData4.m_Size);
				base.EntityManager.SetComponentData(entity, componentData4);
				if (batchData.m_LodIndex == groupData.m_LodCount)
				{
					groupData.m_SecondarySize = float2 * float2 / (componentData4.m_Size * math.cmax(float2));
					groupData.m_SecondaryCenter = @float - componentData4.m_Offset;
				}
			}
			if ((renderPrefab.manualVTRequired || renderPrefab.isImpostor) && decalProperties == null && array != null)
			{
				Bounds2 bounds3 = MathUtils.Bounds(new float2(0f, 0f), new float2(1f, 1f));
				m_VTRequestDependencies.Complete();
				if (array.Length >= 1 && array[0].indexInStack >= 0)
				{
					batchData.m_VTIndex0 = m_VTTextureRequester.RegisterTexture(0, array[0].stackGlobalIndex, array[0].indexInStack, bounds3);
				}
				if (array.Length >= 2 && array[1].indexInStack >= 0)
				{
					batchData.m_VTIndex1 = m_VTTextureRequester.RegisterTexture(1, array[1].stackGlobalIndex, array[1].indexInStack, bounds3);
				}
				batchData.m_VTSizeFactor = math.cmax(float2) * 2f;
			}
			if ((componentData2.m_State & MeshFlags.Default) != 0)
			{
				batchData.m_ShadowArea = float.PositiveInfinity;
				batchData.m_ShadowHeight = float.PositiveInfinity;
				DisableKeyword(materialKey, "_TANGENTSPACE_OCTO");
				materialKey.textures.Add(m_MaskMap, Texture2D.blackTexture);
			}
			if (array != null)
			{
				if ((componentData2.m_State & MeshFlags.Default) != 0)
				{
					DisableKeyword(materialKey, "ENABLE_VT");
				}
				else
				{
					for (int j = 0; j < 2; j++)
					{
						if (array.Length > j && array[j].indexInStack >= 0)
						{
							if (materialPropertyBlock == null)
							{
								materialPropertyBlock = new MaterialPropertyBlock();
							}
							materialPropertyBlock.SetTextureParamBlock(m_BatchManagerSystem.GetVTTextureParamBlockID(j), m_TextureStreamingSystem.GetTextureParamBlock(array[j]));
							materialKey.vtStacks.Add(array[j].stackGlobalIndex);
							EnableKeyword(materialKey, "ENABLE_VT");
						}
						else
						{
							materialKey.vtStacks.Add(-1);
						}
					}
				}
			}
		}
		mesh = m_BatchMeshSystem.GetDefaultMesh(groupData.m_MeshType, batchFlags, generatedType);
		if ((batchFlags & BatchFlags.Animated) != 0)
		{
			if (!m_Materials.TryGetValue(materialKey, out value))
			{
				value = CreateMaterial(surfaceAsset, material, materialKey);
				m_Materials.Add(materialKey, value);
				materialKey = new MaterialKey(materialKey);
			}
			DisableKeyword(materialKey, "_GPU_ANIMATION_OFF");
			EnableKeyword(materialKey, "_GPU_ANIMATION_TEXTURE");
		}
		if (m_Materials.TryGetValue(materialKey, out value2))
		{
			materialKey.Clear();
			m_CachedMaterialKey = materialKey;
		}
		else
		{
			value2 = CreateMaterial(surfaceAsset, material, materialKey);
			m_Materials.Add(materialKey, value2);
		}
		if (value2.IsKeywordEnabled("_TRANSPARENT_WRITES_MOTION_VEC"))
		{
			batchFlags |= BatchFlags.MotionVectors;
		}
		if (value == null)
		{
			value = value2;
		}
		switch (groupData.m_Layer)
		{
		case MeshLayer.Moving:
			num = m_MovingLayer;
			batchFlags |= BatchFlags.MotionVectors;
			break;
		case MeshLayer.Tunnel:
			num = m_TunnelLayer;
			break;
		case MeshLayer.Pipeline:
			num = m_PipelineLayer;
			shadowCastingMode = ShadowCastingMode.Off;
			flag = false;
			break;
		case MeshLayer.SubPipeline:
			num = m_SubPipelineLayer;
			shadowCastingMode = ShadowCastingMode.Off;
			flag = false;
			break;
		case MeshLayer.Waterway:
			num = m_WaterwayLayer;
			shadowCastingMode = ShadowCastingMode.Off;
			flag = false;
			break;
		case MeshLayer.Outline:
			num = m_OutlineLayer;
			batchFlags &= ~(BatchFlags.MotionVectors | BatchFlags.Emissive | BatchFlags.ColorMask | BatchFlags.InfoviewColor | BatchFlags.LodFade | BatchFlags.InfoviewFlow | BatchFlags.SurfaceState);
			batchFlags |= BatchFlags.Outline;
			shadowCastingMode = ShadowCastingMode.Off;
			flag = false;
			break;
		case MeshLayer.Marker:
			num = m_MarkerLayer;
			shadowCastingMode = ShadowCastingMode.Off;
			break;
		}
		if ((batchFlags & BatchFlags.MotionVectors) != 0)
		{
			batchData.m_RenderFlags |= BatchRenderFlags.MotionVectors;
		}
		if (flag)
		{
			batchData.m_RenderFlags |= BatchRenderFlags.ReceiveShadows;
		}
		if (shadowCastingMode != ShadowCastingMode.Off)
		{
			batchData.m_RenderFlags |= BatchRenderFlags.CastShadows;
		}
		if (m_RenderingSystem.IsShaderEnabled(value2.shader))
		{
			batchData.m_RenderFlags |= BatchRenderFlags.IsEnabled;
		}
		batchData.m_ShadowCastingMode = (byte)shadowCastingMode;
		batchData.m_Layer = (byte)num;
		groupData.m_RenderFlags |= batchData.m_RenderFlags;
		return new CustomBatch(groupIndex, batchIndex, surfaceAsset, material, value, value2, mesh, entity, sharedMesh, batchFlags, generatedType, groupData.m_MeshType, num2, materialPropertyBlock);
	}
```

- `private CreateMaterial(Colossal.IO.AssetDatabase.SurfaceAsset sourceSurface, UnityEngine.Material sourceMaterial, Game.Rendering.ManagedBatchSystem+MaterialKey materialKey) : UnityEngine.Material`  

```csharp
private Material CreateMaterial(SurfaceAsset sourceSurface, Material sourceMaterial, MaterialKey materialKey)
	{
		Material material;
		if (sourceSurface != null)
		{
			material = new Material(materialKey.template)
			{
				name = "Batch (" + sourceSurface.name + ")",
				hideFlags = HideFlags.HideAndDontSave
			};
			foreach (KeyValuePair<string, float> @float in sourceSurface.floats)
			{
				material.SetFloat(@float.Key, @float.Value);
			}
			foreach (KeyValuePair<string, int> @int in sourceSurface.ints)
			{
				material.SetInt(@int.Key, @int.Value);
			}
			foreach (KeyValuePair<string, Vector4> vector in sourceSurface.vectors)
			{
				material.SetVector(vector.Key, vector.Value);
			}
			foreach (KeyValuePair<string, Color> color in sourceSurface.colors)
			{
				material.SetColor(color.Key, color.Value);
			}
			foreach (KeyValuePair<int, object> texture in materialKey.textures)
			{
				if (texture.Value is TextureAsset textureAsset)
				{
					material.SetTexture(texture.Key, textureAsset.Load());
				}
				else
				{
					material.SetTexture(texture.Key, (Texture)texture.Value);
				}
			}
			foreach (string keyword in sourceSurface.keywords)
			{
				material.EnableKeyword(keyword);
			}
			HDMaterial.ValidateMaterial(material);
		}
		else
		{
			material = new Material(sourceMaterial)
			{
				name = "Batch (" + sourceMaterial.name + ")",
				hideFlags = HideFlags.HideAndDontSave
			};
			foreach (TextureData item in m_CachedTextures)
			{
				material.SetTexture(item.nameID, item.texture);
			}
		}
		if (materialKey.decalLayerMask != -1)
		{
			material.SetFloat(m_DecalLayerMask, math.asfloat(materialKey.decalLayerMask));
		}
		if (materialKey.renderQueue != -1)
		{
			material.renderQueue = materialKey.renderQueue;
		}
		foreach (KeywordData item2 in m_CachedKeywords)
		{
			if (item2.remove)
			{
				material.DisableKeyword(item2.name);
			}
			else
			{
				material.EnableKeyword(item2.name);
			}
		}
		for (int i = 0; i < materialKey.vtStacks.Count; i++)
		{
			int num = materialKey.vtStacks[i];
			if (num >= 0)
			{
				VTAtlassingInfo[] array = sourceSurface?.VTAtlassingInfos;
				VTTextureParamBlock textureParams = ((array != null) ? m_TextureStreamingSystem.GetTextureParamBlock(array[i]) : VTTextureParamBlock.Identity);
				m_TextureStreamingSystem.BindMaterial(material, num, i, textureParams);
			}
		}
		return material;
	}
```

- `private DisableKeyword(Game.Rendering.ManagedBatchSystem+MaterialKey materialKey, System.String keyword) : System.Void`  

```csharp
private void DisableKeyword(MaterialKey materialKey, string keyword)
	{
		if (materialKey.keywords.Remove(keyword))
		{
			m_CachedKeywords.Add(new KeywordData(keyword, remove: true));
		}
	}
```

- `public EnabledShadersUpdated() : System.Void`  

```csharp
public void EnabledShadersUpdated()
	{
		JobHandle dependencies;
		NativeBatchGroups<CullingData, GroupData, BatchData, InstanceData> nativeBatchGroups = m_BatchManagerSystem.GetNativeBatchGroups(readOnly: false, out dependencies);
		ManagedBatches<OptionalProperties> managedBatches = m_BatchManagerSystem.GetManagedBatches();
		dependencies.Complete();
		int num = nativeBatchGroups.GetGroupCount();
		for (int i = 0; i < num; i++)
		{
			if (!nativeBatchGroups.IsValidGroup(i))
			{
				continue;
			}
			int num2 = nativeBatchGroups.GetBatchCount(i);
			GroupData groupData = nativeBatchGroups.GetGroupData(i);
			groupData.m_RenderFlags &= ~BatchRenderFlags.IsEnabled;
			for (int j = 0; j < num2; j++)
			{
				int managedBatchIndex = nativeBatchGroups.GetManagedBatchIndex(i, j);
				if (managedBatchIndex >= 0)
				{
					CustomBatch customBatch = (CustomBatch)managedBatches.GetBatch(managedBatchIndex);
					BatchData batchData = nativeBatchGroups.GetBatchData(i, j);
					if (m_RenderingSystem.IsShaderEnabled(customBatch.loadedMaterial.shader))
					{
						groupData.m_RenderFlags |= BatchRenderFlags.IsEnabled;
						batchData.m_RenderFlags |= BatchRenderFlags.IsEnabled;
					}
					else
					{
						batchData.m_RenderFlags &= ~BatchRenderFlags.IsEnabled;
					}
					nativeBatchGroups.SetBatchData(i, j, batchData);
				}
			}
			nativeBatchGroups.SetGroupData(i, groupData);
		}
	}
```

- `private EnableKeyword(Game.Rendering.ManagedBatchSystem+MaterialKey materialKey, System.String keyword) : System.Void`  

```csharp
private void EnableKeyword(MaterialKey materialKey, string keyword)
	{
		if (materialKey.keywords.Add(keyword))
		{
			m_CachedKeywords.Add(new KeywordData(keyword, remove: false));
		}
	}
```

- `public static GetTemplate(Colossal.IO.AssetDatabase.SurfaceAsset surfaceAsset) : UnityEngine.Material`  

```csharp
public static Material GetTemplate(SurfaceAsset surfaceAsset)
	{
		Material material = surfaceAsset.GetTemplateMaterial();
		if (material == null)
		{
			material = SurfaceAsset.kDefaultMaterial;
		}
		return material;
	}
```

- `public GetVTRequestMaxPixels(Unity.Collections.NativeList`1[[System.Single, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& maxPixels0, Unity.Collections.NativeList`1[[System.Single, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& maxPixels1) : Unity.Jobs.JobHandle`  

```csharp
public JobHandle GetVTRequestMaxPixels(out NativeList<float> maxPixels0, out NativeList<float> maxPixels1)
	{
		maxPixels0 = m_VTTextureRequester.TexturesMaxPixels[0];
		maxPixels1 = m_VTTextureRequester.TexturesMaxPixels[1];
		return m_VTRequestDependencies;
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
		m_BatchMeshSystem = base.World.GetOrCreateSystemManaged<BatchMeshSystem>();
		m_BatchManagerSystem = base.World.GetOrCreateSystemManaged<BatchManagerSystem>();
		m_TextureStreamingSystem = base.World.GetOrCreateSystemManaged<TextureStreamingSystem>();
		m_Materials = new Dictionary<MaterialKey, Material>();
		m_Groups = new Dictionary<GroupKey, Entity>();
		m_Meshes = new Dictionary<MeshKey, Entity>();
		m_CachedKeywords = new List<KeywordData>();
		m_CachedTextures = new List<TextureData>();
		m_VTTextureRequester = new VTTextureRequester(m_TextureStreamingSystem);
		m_MeshSettingsQuery = GetEntityQuery(ComponentType.ReadOnly<MeshSettingsData>());
		m_TunnelLayer = LayerMask.NameToLayer("Tunnel");
		m_MovingLayer = LayerMask.NameToLayer("Moving");
		m_PipelineLayer = LayerMask.NameToLayer("Pipeline");
		m_SubPipelineLayer = LayerMask.NameToLayer("SubPipeline");
		m_WaterwayLayer = LayerMask.NameToLayer("Waterway");
		m_OutlineLayer = LayerMask.NameToLayer("Outline");
		m_MarkerLayer = LayerMask.NameToLayer("Marker");
		m_DecalLayerMask = Shader.PropertyToID("colossal_DecalLayerMask");
		m_AnimationTexture = Shader.PropertyToID("_AnimationTexture");
		m_UseStack1 = Shader.PropertyToID("colossal_UseStack1");
		m_ImpostorSize = Shader.PropertyToID("_ImpostorSize");
		m_ImpostorOffset = Shader.PropertyToID("_ImpostorOffset");
		m_WorldspaceAlbedo = Shader.PropertyToID("_WorldspaceAlbedo");
		m_MaskMap = Shader.PropertyToID("_MaskMap");
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		foreach (KeyValuePair<MaterialKey, Material> item in m_Materials)
		{
			CoreUtils.Destroy(item.Value);
		}
		m_VTRequestDependencies.Complete();
		m_VTTextureRequester.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		JobHandle dependencies;
		NativeBatchGroups<CullingData, GroupData, BatchData, InstanceData> nativeBatchGroups = m_BatchManagerSystem.GetNativeBatchGroups(readOnly: false, out dependencies);
		ManagedBatches<OptionalProperties> managedBatches = m_BatchManagerSystem.GetManagedBatches();
		dependencies.Complete();
		UpdatedManagedBatchEnumerator updatedManagedBatches = nativeBatchGroups.GetUpdatedManagedBatches();
		int groupIndex;
		while (updatedManagedBatches.GetNextUpdatedGroup(out groupIndex))
		{
			int num = nativeBatchGroups.GetBatchCount(groupIndex);
			GroupData groupData = nativeBatchGroups.GetGroupData(groupIndex);
			GroupKey groupKey = null;
			Entity value = groupData.m_Mesh;
			if (m_PrefabSystem.TryGetPrefab<RenderPrefab>(groupData.m_Mesh, out var prefab) && prefab != null)
			{
				try
				{
					MeshData componentData = base.EntityManager.GetComponentData<MeshData>(groupData.m_Mesh);
					MeshKey key = new MeshKey(prefab, componentData);
					if (!m_Meshes.TryGetValue(key, out value))
					{
						m_Meshes.Add(key, groupData.m_Mesh);
						value = groupData.m_Mesh;
					}
					if (m_CachedGroupKey != null)
					{
						groupKey = m_CachedGroupKey;
						m_CachedGroupKey = null;
					}
					else
					{
						groupKey = new GroupKey();
					}
					groupKey.Initialize(value, groupData);
				}
				catch (Exception exception)
				{
					COSystemBase.baseLog.ErrorFormat(prefab, exception, "Error when initializing batches for {0}", prefab.name);
				}
			}
			for (int i = 0; i < num; i++)
			{
				int num2 = nativeBatchGroups.GetManagedBatchIndex(groupIndex, i);
				if (num2 < 0)
				{
					try
					{
						BatchData batchData = nativeBatchGroups.GetBatchData(groupIndex, i);
						PropertyData lodFadeData;
						CustomBatch customBatch = CreateBatch(groupIndex, i, value, ref groupData, ref batchData, out lodFadeData);
						nativeBatchGroups.SetBatchData(groupIndex, i, batchData);
						BatchFlags batchFlags = customBatch.sourceFlags;
						if (!m_BatchManagerSystem.IsMotionVectorsEnabled())
						{
							batchFlags &= ~BatchFlags.MotionVectors;
						}
						if (!m_BatchManagerSystem.IsLodFadeEnabled())
						{
							batchFlags &= ~BatchFlags.LodFade;
						}
						OptionalProperties optionalProperties = new OptionalProperties(batchFlags, customBatch.sourceType);
						num2 = managedBatches.AddBatch(customBatch, i, nativeBatchGroups);
						m_BatchMeshSystem.AddBatch(customBatch, num2);
						NativeBatchProperties batchProperties = managedBatches.GetBatchProperties(customBatch.material.shader, optionalProperties);
						nativeBatchGroups.SetBatchProperties(groupIndex, i, batchProperties);
						if (lodFadeData.m_DataIndex >= 0)
						{
							nativeBatchGroups.SetBatchDataIndex(groupIndex, i, lodFadeData.m_NameID, lodFadeData.m_DataIndex);
						}
						WriteableBatchDefaultsAccessor batchDefaultsAccessor = nativeBatchGroups.GetBatchDefaultsAccessor(groupIndex, i);
						if (customBatch.sourceSurface != null)
						{
							managedBatches.SetDefaults(GetTemplate(customBatch.sourceSurface), customBatch.sourceSurface.floats, customBatch.sourceSurface.ints, customBatch.sourceSurface.vectors, customBatch.sourceSurface.colors, customBatch.customProps, batchProperties, batchDefaultsAccessor);
						}
						else
						{
							managedBatches.SetDefaults(customBatch.sourceMaterial, customBatch.customProps, batchProperties, batchDefaultsAccessor);
						}
					}
					catch (Exception exception2)
					{
						if (prefab != null)
						{
							COSystemBase.baseLog.ErrorFormat(prefab, exception2, "Error when initializing batch {0} for {1}", i, prefab.name);
						}
						else
						{
							COSystemBase.baseLog.ErrorFormat(exception2, "Error when initializing batch {0} for {1}", i, groupData.m_Mesh);
						}
						continue;
					}
				}
				groupKey?.batches.Add(new GroupKey.Batch((CustomBatch)managedBatches.GetBatch(num2)));
			}
			nativeBatchGroups.SetGroupData(groupIndex, groupData);
			if (groupKey != null)
			{
				if (m_Groups.TryGetValue(groupKey, out var value2))
				{
					m_BatchManagerSystem.MergeGroups(value2, groupIndex);
					groupKey.Clear();
					m_CachedGroupKey = groupKey;
				}
				else
				{
					m_Groups.Add(groupKey, groupData.m_Mesh);
					groupCount++;
					batchCount += num;
				}
			}
			else
			{
				groupCount++;
				batchCount += num;
			}
		}
		nativeBatchGroups.ClearUpdatedManagedBatches();
	}
```

- `public ReloadVT() : System.Void`  

```csharp
public void ReloadVT()
	{
		m_VTRequestDependencies.Complete();
		m_VTTextureRequester.Clear();
		m_TextureStreamingSystem.Reload();
		m_BatchManagerSystem.VirtualTexturingUpdated();
	}
```

- `public RemoveMesh(Unity.Entities.Entity oldMesh, Unity.Entities.Entity newMesh = null) : System.Void`  

```csharp
public System.Void RemoveMesh(Unity.Entities.Entity oldMesh, Unity.Entities.Entity newMesh);
```

- `public ResetSharedMeshes() : System.Void`  

```csharp
public void ResetSharedMeshes()
	{
		JobHandle dependencies;
		NativeBatchGroups<CullingData, GroupData, BatchData, InstanceData> nativeBatchGroups = m_BatchManagerSystem.GetNativeBatchGroups(readOnly: false, out dependencies);
		ManagedBatches<OptionalProperties> managedBatches = m_BatchManagerSystem.GetManagedBatches();
		dependencies.Complete();
		int num = nativeBatchGroups.GetGroupCount();
		for (int i = 0; i < num; i++)
		{
			if (!nativeBatchGroups.IsValidGroup(i))
			{
				continue;
			}
			int num2 = nativeBatchGroups.GetBatchCount(i);
			GroupData groupData = nativeBatchGroups.GetGroupData(i);
			GroupKey groupKey = null;
			Entity value = groupData.m_Mesh;
			if (m_PrefabSystem.TryGetPrefab<RenderPrefab>(groupData.m_Mesh, out var prefab) && prefab != null)
			{
				try
				{
					MeshData componentData = base.EntityManager.GetComponentData<MeshData>(groupData.m_Mesh);
					MeshKey key = new MeshKey(prefab, componentData);
					if (!m_Meshes.TryGetValue(key, out value))
					{
						m_Meshes.Add(key, groupData.m_Mesh);
						value = groupData.m_Mesh;
					}
					if (m_CachedGroupKey != null)
					{
						groupKey = m_CachedGroupKey;
						m_CachedGroupKey = null;
					}
					else
					{
						groupKey = new GroupKey();
					}
					groupKey.Initialize(value, groupData);
				}
				catch (Exception exception)
				{
					COSystemBase.baseLog.ErrorFormat(prefab, exception, "Error when initializing batches for {0}", prefab.name);
				}
			}
			int num3 = 0;
			while (true)
			{
				if (num3 < num2)
				{
					int managedBatchIndex = nativeBatchGroups.GetManagedBatchIndex(i, num3);
					if (managedBatchIndex >= 0)
					{
						groupKey?.batches.Add(new GroupKey.Batch((CustomBatch)managedBatches.GetBatch(managedBatchIndex)));
						num3++;
						continue;
					}
				}
				else if (groupKey != null && m_Groups.TryAdd(groupKey, groupData.m_Mesh))
				{
					num++;
					batchCount += num2;
					break;
				}
				if (groupKey != null)
				{
					groupKey.Clear();
					m_CachedGroupKey = groupKey;
				}
				break;
			}
		}
	}
```

- `public ResetVT(System.Int32 desiredMipBias, UnityEngine.Rendering.VirtualTexturing.FilterMode filterMode) : System.Void`  

```csharp
public void ResetVT(int desiredMipBias, UnityEngine.Rendering.VirtualTexturing.FilterMode filterMode)
	{
		if (m_TextureStreamingSystem.ShouldResetVT(desiredMipBias, filterMode))
		{
			m_VTRequestDependencies.Complete();
			m_VTTextureRequester.Clear();
			m_TextureStreamingSystem.Initialize(desiredMipBias, filterMode);
			m_BatchManagerSystem.VirtualTexturingUpdated();
		}
	}
```

- `private SetTexture(Game.Rendering.ManagedBatchSystem+MaterialKey materialKey, System.Int32 nameID, UnityEngine.Texture texture) : System.Void`  

```csharp
private void SetTexture(MaterialKey materialKey, int nameID, Texture texture)
	{
		if (materialKey.textures.TryGetValue(nameID, out var value))
		{
			if (texture != value)
			{
				materialKey.textures[nameID] = texture;
				m_CachedTextures.Add(new TextureData(nameID, texture));
			}
		}
		else
		{
			materialKey.textures.Add(nameID, texture);
			m_CachedTextures.Add(new TextureData(nameID, texture));
		}
	}
```

- `public SetupVT(Game.Prefabs.RenderPrefab meshPrefab, UnityEngine.Material material, System.Int32 materialIndex) : System.Void`  

```csharp
public void SetupVT(RenderPrefab meshPrefab, Material material, int materialIndex)
	{
		SurfaceAsset surfaceAsset = meshPrefab.GetSurfaceAsset(materialIndex);
		VTAtlassingInfo[] array = surfaceAsset.VTAtlassingInfos;
		if (array == null)
		{
			array = surfaceAsset.PreReservedAtlassingInfos;
		}
		if (array == null || meshPrefab.Has<DefaultMesh>())
		{
			return;
		}
		for (int i = 0; i < 2; i++)
		{
			if (array.Length > i && array[i].indexInStack >= 0)
			{
				m_TextureStreamingSystem.BindMaterial(material, array[i].stackGlobalIndex, i, m_TextureStreamingSystem.GetTextureParamBlock(array[i]));
			}
		}
	}
```


## Nested types

- `Game.Rendering.ManagedBatchSystem+KeywordData`  
- `Game.Rendering.ManagedBatchSystem+TextureData`  
- `Game.Rendering.ManagedBatchSystem+MaterialKey`  
- `Game.Rendering.ManagedBatchSystem+GroupKey`  
- `Game.Rendering.ManagedBatchSystem+MeshKey`  

