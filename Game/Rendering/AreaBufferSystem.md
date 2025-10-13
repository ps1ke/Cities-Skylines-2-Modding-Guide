# Game.Rendering.AreaBufferSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AreaBufferSystem : Game.GameSystemBase, Game.Serialization.IPreDeserialize
{
    private Unity.Entities.EntityQuery m_SettingsQuery;
    private Game.Rendering.RenderingSystem m_RenderingSystem;
    private Game.Rendering.OverlayRenderSystem m_OverlayRenderSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.UI.NameSystem m_NameSystem;
    private Game.Rendering.AreaBufferSystem+AreaTypeData[] m_AreaTypeData;
    private Game.Areas.AreaType m_LastSelectionAreaType;
    private Unity.Entities.EntityQuery m_SelectionQuery;
    private System.Boolean m_Loaded;
    private System.Int32 m_AreaParameters;
    private System.Collections.Generic.Dictionary<Unity.Entities.Entity, System.String> m_CachedLabels;
    private Game.Rendering.AreaBufferSystem+TypeHandle __TypeHandle;

    public AreaBufferSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Boolean GetAreaBuffer(Game.Areas.AreaType type, UnityEngine.ComputeBuffer& buffer, UnityEngine.Material& material, UnityEngine.Bounds& bounds);
    private System.Boolean GetLoaded();
    public System.Boolean GetNameMaterial(Game.Areas.AreaType type, System.Int32 subMeshIndex, UnityEngine.Material& material);
    public System.Boolean GetNameMesh(Game.Areas.AreaType type, UnityEngine.Mesh& mesh, System.Int32& subMeshCount);
    private Game.Rendering.AreaBufferSystem+AreaTypeData InitializeAreaData<T>();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    private System.Void OnDictionaryChanged();
    protected virtual System.Void OnUpdate();
    public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
    private System.Void UpdateLabelVertices(Game.Rendering.AreaBufferSystem+AreaTypeData data, System.Boolean isLoaded);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_SettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_SettingsQuery;
```

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  

```csharp
private Game.Rendering.RenderingSystem m_RenderingSystem;
```

- `private Game.Rendering.OverlayRenderSystem m_OverlayRenderSystem`  

```csharp
private Game.Rendering.OverlayRenderSystem m_OverlayRenderSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.UI.NameSystem m_NameSystem`  

```csharp
private Game.UI.NameSystem m_NameSystem;
```

- `private Game.Rendering.AreaBufferSystem+AreaTypeData[] m_AreaTypeData`  

```csharp
private Game.Rendering.AreaBufferSystem+AreaTypeData[] m_AreaTypeData;
```

- `private Game.Areas.AreaType m_LastSelectionAreaType`  

```csharp
private Game.Areas.AreaType m_LastSelectionAreaType;
```

- `private Unity.Entities.EntityQuery m_SelectionQuery`  

```csharp
private Unity.Entities.EntityQuery m_SelectionQuery;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private System.Int32 m_AreaParameters`  

```csharp
private System.Int32 m_AreaParameters;
```

- `private System.Collections.Generic.Dictionary<Unity.Entities.Entity, System.String> m_CachedLabels`  

```csharp
private System.Collections.Generic.Dictionary<Unity.Entities.Entity, System.String> m_CachedLabels;
```

- `private Game.Rendering.AreaBufferSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.AreaBufferSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public AreaBufferSystem()`  

```csharp
[Preserve]
	public AreaBufferSystem()
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

- `public GetAreaBuffer(Game.Areas.AreaType type, UnityEngine.ComputeBuffer& buffer, UnityEngine.Material& material, UnityEngine.Bounds& bounds) : System.Boolean`  

```csharp
public unsafe bool GetAreaBuffer(AreaType type, out ComputeBuffer buffer, out Material material, out Bounds bounds)
	{
		AreaTypeData areaTypeData = m_AreaTypeData[(int)type];
		if (areaTypeData.m_BufferDirty)
		{
			areaTypeData.m_BufferDirty = false;
			areaTypeData.m_DataDependencies.Complete();
			areaTypeData.m_DataDependencies = default(JobHandle);
			if (areaTypeData.m_BufferData.IsCreated)
			{
				if (areaTypeData.m_Buffer != null && areaTypeData.m_Buffer.count != areaTypeData.m_BufferData.Length)
				{
					areaTypeData.m_Buffer.Release();
					areaTypeData.m_Buffer = null;
				}
				if (areaTypeData.m_BufferData.Length > 0)
				{
					if (areaTypeData.m_Buffer == null)
					{
						areaTypeData.m_Buffer = new ComputeBuffer(areaTypeData.m_BufferData.Length, sizeof(AreaTriangleData));
					}
					areaTypeData.m_Buffer.SetData(areaTypeData.m_BufferData.AsArray());
				}
				areaTypeData.m_BufferData.Dispose();
			}
		}
		buffer = areaTypeData.m_Buffer;
		material = areaTypeData.m_Material;
		if (areaTypeData.m_Bounds.IsCreated)
		{
			bounds = RenderingUtils.ToBounds(areaTypeData.m_Bounds.value);
		}
		else
		{
			bounds = default(Bounds);
		}
		if (areaTypeData.m_Buffer != null)
		{
			return areaTypeData.m_Buffer.count != 0;
		}
		return false;
	}
```

- `private GetLoaded() : System.Boolean`  

```csharp
private bool GetLoaded()
	{
		if (m_Loaded)
		{
			m_Loaded = false;
			return true;
		}
		return false;
	}
```

- `public GetNameMaterial(Game.Areas.AreaType type, System.Int32 subMeshIndex, UnityEngine.Material& material) : System.Boolean`  

```csharp
public bool GetNameMaterial(AreaType type, int subMeshIndex, out Material material)
	{
		MaterialData materialData = m_AreaTypeData[(int)type].m_NameMaterials[subMeshIndex];
		material = materialData.m_Material;
		return materialData.m_HasMesh;
	}
```

- `public GetNameMesh(Game.Areas.AreaType type, UnityEngine.Mesh& mesh, System.Int32& subMeshCount) : System.Boolean`  

```csharp
public bool GetNameMesh(AreaType type, out Mesh mesh, out int subMeshCount)
	{
		AreaTypeData areaTypeData = m_AreaTypeData[(int)type];
		if (areaTypeData.m_NameMaterials != null)
		{
			subMeshCount = areaTypeData.m_NameMaterials.Count;
		}
		else
		{
			subMeshCount = 0;
		}
		if (areaTypeData.m_HasNameMeshData)
		{
			areaTypeData.m_HasNameMeshData = false;
			areaTypeData.m_DataDependencies.Complete();
			areaTypeData.m_DataDependencies = default(JobHandle);
			if (areaTypeData.m_NameMesh == null)
			{
				areaTypeData.m_NameMesh = new Mesh();
				areaTypeData.m_NameMesh.name = $"Area names ({type})";
			}
			Mesh.ApplyAndDisposeWritableMeshData(areaTypeData.m_NameMeshData, areaTypeData.m_NameMesh, MeshUpdateFlags.DontValidateIndices | MeshUpdateFlags.DontRecalculateBounds);
			if (areaTypeData.m_Bounds.IsCreated && math.all(areaTypeData.m_Bounds.value.max >= areaTypeData.m_Bounds.value.min))
			{
				areaTypeData.m_NameMesh.bounds = RenderingUtils.ToBounds(areaTypeData.m_Bounds.value);
			}
			else
			{
				areaTypeData.m_NameMesh.RecalculateBounds();
			}
			areaTypeData.m_HasNameMesh = false;
			for (int i = 0; i < subMeshCount; i++)
			{
				MaterialData value = areaTypeData.m_NameMaterials[i];
				value.m_HasMesh = areaTypeData.m_NameMesh.GetSubMesh(i).vertexCount > 0;
				areaTypeData.m_HasNameMesh |= value.m_HasMesh;
				areaTypeData.m_NameMaterials[i] = value;
			}
		}
		mesh = areaTypeData.m_NameMesh;
		return areaTypeData.m_HasNameMesh;
	}
```

- `private InitializeAreaData<T>() : Game.Rendering.AreaBufferSystem+AreaTypeData`  

```csharp
private Game.Rendering.AreaBufferSystem+AreaTypeData InitializeAreaData<T>();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_RenderingSystem = base.World.GetOrCreateSystemManaged<RenderingSystem>();
		m_OverlayRenderSystem = base.World.GetOrCreateSystemManaged<OverlayRenderSystem>();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_NameSystem = base.World.GetOrCreateSystemManaged<NameSystem>();
		m_AreaTypeData = new AreaTypeData[5];
		m_AreaTypeData[0] = InitializeAreaData<Lot>();
		m_AreaTypeData[1] = InitializeAreaData<District>();
		m_AreaTypeData[2] = InitializeAreaData<MapTile>();
		m_AreaTypeData[3] = InitializeAreaData<Game.Areas.Space>();
		m_AreaTypeData[4] = InitializeAreaData<Surface>();
		m_SettingsQuery = GetEntityQuery(ComponentType.ReadOnly<Created>(), ComponentType.ReadOnly<Game.Prefabs.AreaTypeData>());
		m_SelectionQuery = GetEntityQuery(ComponentType.ReadOnly<SelectionInfo>(), ComponentType.ReadOnly<SelectionElement>());
		m_AreaParameters = Shader.PropertyToID("colossal_AreaParameters");
		GameManager.instance.localizationManager.onActiveDictionaryChanged += OnDictionaryChanged;
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
		for (int i = 0; i < m_AreaTypeData.Length; i++)
		{
			AreaTypeData areaTypeData = m_AreaTypeData[i];
			if (areaTypeData.m_NameMaterials != null)
			{
				for (int j = 0; j < areaTypeData.m_NameMaterials.Count; j++)
				{
					MaterialData materialData = areaTypeData.m_NameMaterials[j];
					if (materialData.m_Material != null)
					{
						Object.Destroy(materialData.m_Material);
					}
				}
			}
			if (areaTypeData.m_BufferData.IsCreated)
			{
				areaTypeData.m_BufferData.Dispose();
			}
			if (areaTypeData.m_Bounds.IsCreated)
			{
				areaTypeData.m_Bounds.Dispose();
			}
			if (areaTypeData.m_Material != null)
			{
				Object.Destroy(areaTypeData.m_Material);
			}
			if (areaTypeData.m_NameMesh != null)
			{
				Object.Destroy(areaTypeData.m_NameMesh);
			}
			if (areaTypeData.m_Buffer != null)
			{
				areaTypeData.m_Buffer.Release();
			}
			if (areaTypeData.m_HasNameMeshData)
			{
				areaTypeData.m_NameMeshData.Dispose();
			}
		}
		GameManager.instance.localizationManager.onActiveDictionaryChanged -= OnDictionaryChanged;
		base.OnDestroy();
	}
```

- `private OnDictionaryChanged() : System.Void`  

```csharp
private void OnDictionaryChanged()
	{
		base.EntityManager.AddComponent<Updated>(m_AreaTypeData[1].m_AreaQuery);
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		bool loaded = GetLoaded();
		if (!m_SettingsQuery.IsEmptyIgnoreFilter)
		{
			NativeArray<ArchetypeChunk> nativeArray = m_SettingsQuery.ToArchetypeChunkArray(Allocator.TempJob);
			ComponentTypeHandle<PrefabData> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			for (int i = 0; i < nativeArray.Length; i++)
			{
				NativeArray<PrefabData> nativeArray2 = nativeArray[i].GetNativeArray(ref typeHandle);
				for (int j = 0; j < nativeArray2.Length; j++)
				{
					AreaTypePrefab prefab = m_PrefabSystem.GetPrefab<AreaTypePrefab>(nativeArray2[j]);
					AreaTypeData areaTypeData = m_AreaTypeData[(int)prefab.m_Type];
					float minNodeDistance = AreaUtils.GetMinNodeDistance(prefab.m_Type);
					if (areaTypeData.m_Material != null)
					{
						Object.Destroy(areaTypeData.m_Material);
					}
					areaTypeData.m_Material = new Material(prefab.m_Material);
					areaTypeData.m_Material.name = "Area buffer (" + prefab.m_Material.name + ")";
					areaTypeData.m_Material.SetVector(m_AreaParameters, new Vector4(minNodeDistance * (1f / 32f), minNodeDistance * 0.25f, minNodeDistance * 2f, 0f));
					if (areaTypeData.m_NameMaterials != null)
					{
						for (int k = 0; k < areaTypeData.m_NameMaterials.Count; k++)
						{
							MaterialData materialData = areaTypeData.m_NameMaterials[k];
							if (materialData.m_Material != null)
							{
								Object.Destroy(materialData.m_Material);
							}
						}
						areaTypeData.m_NameMaterials = null;
					}
					areaTypeData.m_OriginalNameMaterial = prefab.m_NameMaterial;
					if (prefab.m_NameMaterial != null)
					{
						areaTypeData.m_NameMaterials = new List<MaterialData>(1);
					}
				}
			}
			nativeArray.Dispose();
		}
		JobHandle jobHandle = default(JobHandle);
		AreaType areaType = AreaType.None;
		Entity entity = Entity.Null;
		if (!m_SelectionQuery.IsEmptyIgnoreFilter)
		{
			entity = m_SelectionQuery.GetSingletonEntity();
			areaType = base.EntityManager.GetComponentData<SelectionInfo>(entity).m_AreaType;
		}
		if (m_LastSelectionAreaType != AreaType.None)
		{
			m_AreaTypeData[(int)m_LastSelectionAreaType].m_BufferDataDirty = true;
		}
		if (areaType != AreaType.None)
		{
			m_AreaTypeData[(int)areaType].m_BufferDataDirty = true;
		}
		m_LastSelectionAreaType = areaType;
		for (int l = 0; l < m_AreaTypeData.Length; l++)
		{
			AreaTypeData areaTypeData2 = m_AreaTypeData[l];
			EntityQuery entityQuery = (loaded ? areaTypeData2.m_AreaQuery : areaTypeData2.m_UpdatedQuery);
			if (!areaTypeData2.m_BufferDataDirty && entityQuery.IsEmptyIgnoreFilter)
			{
				continue;
			}
			if (areaTypeData2.m_AreaQuery.IsEmptyIgnoreFilter)
			{
				areaTypeData2.m_BufferDataDirty = false;
				areaTypeData2.m_BufferDirty = false;
				if (areaTypeData2.m_Buffer != null)
				{
					areaTypeData2.m_Buffer.Release();
					areaTypeData2.m_Buffer = null;
				}
				if (areaTypeData2.m_NameMesh != null)
				{
					Object.Destroy(areaTypeData2.m_NameMesh);
					areaTypeData2.m_NameMesh = null;
				}
			}
			else
			{
				areaTypeData2.m_BufferDataDirty = true;
			}
			if (areaTypeData2.m_NameMaterials != null && !entityQuery.IsEmptyIgnoreFilter)
			{
				UpdateLabelVertices(areaTypeData2, loaded);
			}
		}
		if (!m_RenderingSystem.hideOverlay)
		{
			for (int m = 0; m < m_AreaTypeData.Length; m++)
			{
				AreaTypeData areaTypeData3 = m_AreaTypeData[m];
				if (!areaTypeData3.m_BufferDataDirty || (areaTypeData3.m_NameMaterials == null && (m_ToolSystem.activeTool == null || ((uint)m_ToolSystem.activeTool.requireAreas & (uint)(1 << m)) == 0)))
				{
					continue;
				}
				areaTypeData3.m_BufferDataDirty = false;
				areaTypeData3.m_BufferDirty = true;
				JobHandle outJobHandle;
				NativeList<ArchetypeChunk> nativeList = areaTypeData3.m_AreaQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle);
				NativeList<ChunkData> chunkData = new NativeList<ChunkData>(0, Allocator.TempJob);
				if (!areaTypeData3.m_BufferData.IsCreated)
				{
					areaTypeData3.m_BufferData = new NativeList<AreaTriangleData>(Allocator.Persistent);
				}
				if (!areaTypeData3.m_Bounds.IsCreated)
				{
					areaTypeData3.m_Bounds = new NativeValue<Bounds3>(Allocator.Persistent);
				}
				ResetChunkDataJob jobData = new ResetChunkDataJob
				{
					m_Chunks = nativeList,
					m_AreaType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Areas_Area_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_HiddenType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Hidden_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_TriangleType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Areas_Triangle_RO_BufferTypeHandle, ref base.CheckedStateRef),
					m_ChunkData = chunkData,
					m_AreaTriangleData = areaTypeData3.m_BufferData
				};
				FillMeshDataJob jobData2 = new FillMeshDataJob
				{
					m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
					m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_HiddenType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Hidden_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_AreaType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Areas_Area_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_NativeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Native_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_NodeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Areas_Node_RO_BufferTypeHandle, ref base.CheckedStateRef),
					m_TriangleType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Areas_Triangle_RO_BufferTypeHandle, ref base.CheckedStateRef),
					m_GeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_AreaGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_ColorData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_AreaColorData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_SelectionElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Tools_SelectionElement_RO_BufferLookup, ref base.CheckedStateRef),
					m_SelectionEntity = entity,
					m_EditorMode = m_ToolSystem.actionMode.IsEditor(),
					m_Chunks = nativeList.AsDeferredJobArray(),
					m_ChunkData = chunkData,
					m_AreaTriangleData = areaTypeData3.m_BufferData
				};
				CalculateBoundsJob jobData3 = new CalculateBoundsJob
				{
					m_ChunkData = chunkData,
					m_Bounds = areaTypeData3.m_Bounds
				};
				JobHandle dependsOn = JobHandle.CombineDependencies(base.Dependency, outJobHandle);
				JobHandle jobHandle2 = IJobParallelForDeferExtensions.Schedule(dependsOn: IJobExtensions.Schedule(jobData, dependsOn), jobData: jobData2, list: nativeList, innerloopBatchCount: 1);
				JobHandle jobHandle3 = IJobExtensions.Schedule(jobData3, jobHandle2);
				chunkData.Dispose(jobHandle3);
				if (areaTypeData3.m_NameMaterials != null)
				{
					if (!areaTypeData3.m_HasNameMeshData)
					{
						areaTypeData3.m_HasNameMeshData = true;
						areaTypeData3.m_NameMeshData = Mesh.AllocateWritableMeshData(1);
					}
					JobHandle job = IJobExtensions.Schedule(new FillNameDataJob
					{
						m_GeometryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Areas_Geometry_RO_ComponentTypeHandle, ref base.CheckedStateRef),
						m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
						m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
						m_HiddenType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Hidden_RO_ComponentTypeHandle, ref base.CheckedStateRef),
						m_LabelVertexType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Areas_LabelVertex_RO_BufferTypeHandle, ref base.CheckedStateRef),
						m_AreaNameData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_AreaNameData_RO_ComponentLookup, ref base.CheckedStateRef),
						m_Chunks = nativeList,
						m_SubMeshCount = areaTypeData3.m_NameMaterials.Count,
						m_NameMeshData = areaTypeData3.m_NameMeshData
					}, dependsOn);
					nativeList.Dispose(JobHandle.CombineDependencies(jobHandle2, job));
					areaTypeData3.m_DataDependencies = JobHandle.CombineDependencies(jobHandle3, job);
				}
				else
				{
					nativeList.Dispose(jobHandle2);
					areaTypeData3.m_DataDependencies = jobHandle3;
				}
				jobHandle = JobHandle.CombineDependencies(jobHandle, areaTypeData3.m_DataDependencies);
			}
		}
		base.Dependency = jobHandle;
	}
```

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PreDeserialize(Context context)
	{
		for (int i = 0; i < m_AreaTypeData.Length; i++)
		{
			AreaTypeData areaTypeData = m_AreaTypeData[i];
			if (areaTypeData.m_BufferData.IsCreated)
			{
				areaTypeData.m_BufferData.Dispose();
				areaTypeData.m_BufferData = default(NativeList<AreaTriangleData>);
			}
			if (areaTypeData.m_Buffer != null)
			{
				areaTypeData.m_Buffer.Release();
				areaTypeData.m_Buffer = null;
			}
			if (areaTypeData.m_NameMesh != null)
			{
				Object.Destroy(areaTypeData.m_NameMesh);
				areaTypeData.m_NameMesh = null;
			}
			if (areaTypeData.m_HasNameMeshData)
			{
				areaTypeData.m_NameMeshData.Dispose();
				areaTypeData.m_HasNameMeshData = false;
			}
		}
		if (m_CachedLabels != null)
		{
			m_CachedLabels.Clear();
		}
		m_Loaded = true;
	}
```

- `private UpdateLabelVertices(Game.Rendering.AreaBufferSystem+AreaTypeData data, System.Boolean isLoaded) : System.Void`  

```csharp
private void UpdateLabelVertices(AreaTypeData data, bool isLoaded)
	{
		NativeArray<ArchetypeChunk> nativeArray = (isLoaded ? data.m_AreaQuery : data.m_UpdatedQuery).ToArchetypeChunkArray(Allocator.TempJob);
		try
		{
			TextMeshPro textMesh = m_OverlayRenderSystem.GetTextMesh();
			textMesh.rectTransform.sizeDelta = new Vector2(250f, 100f);
			textMesh.fontSize = 200f;
			textMesh.alignment = TextAlignmentOptions.Center;
			EntityTypeHandle entityTypeHandle = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<Updated> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Updated_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<BatchesUpdated> typeHandle2 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_BatchesUpdated_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<Temp> typeHandle3 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			BufferTypeHandle<LabelExtents> bufferTypeHandle = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Areas_LabelExtents_RW_BufferTypeHandle, ref base.CheckedStateRef);
			BufferTypeHandle<LabelVertex> bufferTypeHandle2 = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Areas_LabelVertex_RW_BufferTypeHandle, ref base.CheckedStateRef);
			LabelVertex value2 = default(LabelVertex);
			for (int i = 0; i < nativeArray.Length; i++)
			{
				ArchetypeChunk archetypeChunk = nativeArray[i];
				if (isLoaded || archetypeChunk.Has(ref typeHandle) || archetypeChunk.Has(ref typeHandle2))
				{
					NativeArray<Entity> nativeArray2 = archetypeChunk.GetNativeArray(entityTypeHandle);
					NativeArray<Temp> nativeArray3 = archetypeChunk.GetNativeArray(ref typeHandle3);
					BufferAccessor<LabelExtents> bufferAccessor = archetypeChunk.GetBufferAccessor(ref bufferTypeHandle);
					BufferAccessor<LabelVertex> bufferAccessor2 = archetypeChunk.GetBufferAccessor(ref bufferTypeHandle2);
					for (int j = 0; j < nativeArray2.Length; j++)
					{
						Entity entity = nativeArray2[j];
						DynamicBuffer<LabelExtents> dynamicBuffer = bufferAccessor[j];
						DynamicBuffer<LabelVertex> dynamicBuffer2 = bufferAccessor2[j];
						string renderedLabelName;
						if (nativeArray3.Length != 0)
						{
							Temp temp = nativeArray3[j];
							if (!(temp.m_Original != Entity.Null))
							{
								if (m_CachedLabels != null && m_CachedLabels.ContainsKey(entity))
								{
									m_CachedLabels.Remove(entity);
								}
								dynamicBuffer2.Clear();
								continue;
							}
							renderedLabelName = m_NameSystem.GetRenderedLabelName(temp.m_Original);
						}
						else
						{
							renderedLabelName = m_NameSystem.GetRenderedLabelName(entity);
						}
						if (m_CachedLabels != null)
						{
							if (m_CachedLabels.TryGetValue(entity, out var value))
							{
								if (value == renderedLabelName)
								{
									continue;
								}
								m_CachedLabels[entity] = renderedLabelName;
							}
							else
							{
								m_CachedLabels.Add(entity, renderedLabelName);
							}
						}
						else
						{
							m_CachedLabels = new Dictionary<Entity, string>();
							m_CachedLabels.Add(entity, renderedLabelName);
						}
						TMP_TextInfo textInfo = textMesh.GetTextInfo(renderedLabelName);
						int num = 0;
						for (int k = 0; k < textInfo.meshInfo.Length; k++)
						{
							TMP_MeshInfo tMP_MeshInfo = textInfo.meshInfo[k];
							num += tMP_MeshInfo.vertexCount;
						}
						dynamicBuffer2.ResizeUninitialized(num);
						num = 0;
						for (int l = 0; l < textInfo.meshInfo.Length; l++)
						{
							TMP_MeshInfo tMP_MeshInfo2 = textInfo.meshInfo[l];
							if (tMP_MeshInfo2.vertexCount == 0)
							{
								continue;
							}
							Texture mainTexture = tMP_MeshInfo2.material.mainTexture;
							int num2 = -1;
							for (int m = 0; m < data.m_NameMaterials.Count; m++)
							{
								if (data.m_NameMaterials[m].m_Material.mainTexture == mainTexture)
								{
									num2 = m;
									break;
								}
							}
							if (num2 == -1)
							{
								MaterialData item = new MaterialData
								{
									m_Material = new Material(data.m_OriginalNameMaterial)
								};
								m_OverlayRenderSystem.CopyFontAtlasParameters(tMP_MeshInfo2.material, item.m_Material);
								num2 = data.m_NameMaterials.Count;
								data.m_NameMaterials.Add(item);
								item.m_Material.name = $"Area names {num2} ({data.m_OriginalNameMaterial.name})";
							}
							Vector3[] vertices = tMP_MeshInfo2.vertices;
							Vector2[] uvs = tMP_MeshInfo2.uvs0;
							Vector2[] uvs2 = tMP_MeshInfo2.uvs2;
							Color32[] colors = tMP_MeshInfo2.colors32;
							for (int n = 0; n < tMP_MeshInfo2.vertexCount; n++)
							{
								value2.m_Position = vertices[n];
								value2.m_Color = colors[n];
								value2.m_UV0 = uvs[n];
								value2.m_UV1 = uvs2[n];
								value2.m_Material = num2;
								dynamicBuffer2[num + n] = value2;
							}
							num += tMP_MeshInfo2.vertexCount;
						}
						dynamicBuffer.ResizeUninitialized(textInfo.lineCount);
						for (int num3 = 0; num3 < textInfo.lineCount; num3++)
						{
							Extents lineExtents = textInfo.lineInfo[num3].lineExtents;
							dynamicBuffer[num3] = new LabelExtents(lineExtents.min, lineExtents.max);
						}
					}
				}
				else if (m_CachedLabels != null)
				{
					NativeArray<Entity> nativeArray4 = archetypeChunk.GetNativeArray(entityTypeHandle);
					for (int num4 = 0; num4 < nativeArray4.Length; num4++)
					{
						Entity key = nativeArray4[num4];
						m_CachedLabels.Remove(key);
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


## Nested types

- `Game.Rendering.AreaBufferSystem+AreaTriangleData`  
- `Game.Rendering.AreaBufferSystem+MaterialData`  
- `Game.Rendering.AreaBufferSystem+AreaTypeData`  
- `Game.Rendering.AreaBufferSystem+ChunkData`  
- `Game.Rendering.AreaBufferSystem+ResetChunkDataJob`  
- `Game.Rendering.AreaBufferSystem+FillMeshDataJob`  
- `Game.Rendering.AreaBufferSystem+CalculateBoundsJob`  
- `Game.Rendering.AreaBufferSystem+LabelVertexData`  
- `Game.Rendering.AreaBufferSystem+FillNameDataJob`  
- `Game.Rendering.AreaBufferSystem+TypeHandle`  

