# Game.Rendering.AggregateMeshSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AggregateMeshSystem : Game.GameSystemBase, Game.Serialization.IPreDeserialize
{
    private Unity.Entities.EntityQuery m_CreatedPrefabQuery;
    private Unity.Entities.EntityQuery m_UpdatedLabelQuery;
    private Unity.Entities.EntityQuery m_LabelQuery;
    private Unity.Entities.EntityQuery m_UpdatedArrowQuery;
    private Unity.Entities.EntityQuery m_ArrowQuery;
    private Unity.Entities.EntityQuery m_TempAggregatedQuery;
    private Game.Rendering.OverlayRenderSystem m_OverlayRenderSystem;
    private Game.Rendering.UndergroundViewSystem m_UndergroundViewSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.UI.NameSystem m_NameSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private System.Collections.Generic.List<Game.Rendering.AggregateMeshSystem+MeshData> m_LabelData;
    private System.Collections.Generic.List<Game.Rendering.AggregateMeshSystem+MeshData> m_ArrowData;
    private System.Collections.Generic.Dictionary<Unity.Entities.Entity, System.String> m_CachedLabels;
    private System.Int32 m_FaceColor;
    private System.Boolean m_TunnelSelectOn;
    private System.Boolean m_Loaded;
    private Game.Rendering.AggregateMeshSystem+TypeHandle __TypeHandle;

    public AggregateMeshSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void ClearMeshData(System.Collections.Generic.List<Game.Rendering.AggregateMeshSystem+MeshData> meshData);
    private System.Void DestroyMeshData(System.Collections.Generic.List<Game.Rendering.AggregateMeshSystem+MeshData> meshData);
    private Unity.Jobs.JobHandle FillArrowMeshData(Unity.Jobs.JobHandle inputDeps);
    private Unity.Jobs.JobHandle FillNameMeshData(Unity.Jobs.JobHandle inputDeps);
    public System.Boolean GetArrowMaterial(System.Int32 index, System.Int32 subMeshIndex, UnityEngine.Material& material);
    public System.Int32 GetArrowMaterialCount();
    public System.Boolean GetArrowMesh(System.Int32 index, UnityEngine.Mesh& mesh, System.Int32& subMeshCount);
    private System.Boolean GetLoaded();
    private System.Boolean GetMaterialData(System.Collections.Generic.List<Game.Rendering.AggregateMeshSystem+MeshData> meshData, System.Int32 index, System.Int32 subMeshIndex, UnityEngine.Material& material);
    private System.Boolean GetMeshData(System.Collections.Generic.List<Game.Rendering.AggregateMeshSystem+MeshData> meshData, System.Int32 index, UnityEngine.Mesh& mesh, System.Int32& subMeshCount);
    public System.Boolean GetNameMaterial(System.Int32 index, System.Int32 subMeshIndex, UnityEngine.Material& material);
    public System.Int32 GetNameMaterialCount();
    public System.Boolean GetNameMesh(System.Int32 index, UnityEngine.Mesh& mesh, System.Int32& subMeshCount);
    private System.Void InitializePrefabs();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    private System.Void OnDictionaryChanged();
    protected virtual System.Void OnUpdate();
    public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
    private System.Void UpdateArrowMaterials(System.Boolean isLoaded);
    private Unity.Jobs.JobHandle UpdateArrowPositions(Unity.Jobs.JobHandle inputDeps, System.Boolean isLoaded);
    private Unity.Jobs.JobHandle UpdateLabelPositions(Unity.Jobs.JobHandle inputDeps, System.Boolean isLoaded);
    private System.Void UpdateLabelVertices(System.Boolean isLoaded);
    private System.Void UpdateUndergroundState(System.Collections.Generic.List<Game.Rendering.AggregateMeshSystem+MeshData> meshData, System.Boolean undergroundOn);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_CreatedPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedPrefabQuery;
```

- `private Unity.Entities.EntityQuery m_UpdatedLabelQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedLabelQuery;
```

- `private Unity.Entities.EntityQuery m_LabelQuery`  

```csharp
private Unity.Entities.EntityQuery m_LabelQuery;
```

- `private Unity.Entities.EntityQuery m_UpdatedArrowQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedArrowQuery;
```

- `private Unity.Entities.EntityQuery m_ArrowQuery`  

```csharp
private Unity.Entities.EntityQuery m_ArrowQuery;
```

- `private Unity.Entities.EntityQuery m_TempAggregatedQuery`  

```csharp
private Unity.Entities.EntityQuery m_TempAggregatedQuery;
```

- `private Game.Rendering.OverlayRenderSystem m_OverlayRenderSystem`  

```csharp
private Game.Rendering.OverlayRenderSystem m_OverlayRenderSystem;
```

- `private Game.Rendering.UndergroundViewSystem m_UndergroundViewSystem`  

```csharp
private Game.Rendering.UndergroundViewSystem m_UndergroundViewSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.UI.NameSystem m_NameSystem`  

```csharp
private Game.UI.NameSystem m_NameSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private System.Collections.Generic.List<Game.Rendering.AggregateMeshSystem+MeshData> m_LabelData`  

```csharp
private System.Collections.Generic.List<Game.Rendering.AggregateMeshSystem+MeshData> m_LabelData;
```

- `private System.Collections.Generic.List<Game.Rendering.AggregateMeshSystem+MeshData> m_ArrowData`  

```csharp
private System.Collections.Generic.List<Game.Rendering.AggregateMeshSystem+MeshData> m_ArrowData;
```

- `private System.Collections.Generic.Dictionary<Unity.Entities.Entity, System.String> m_CachedLabels`  

```csharp
private System.Collections.Generic.Dictionary<Unity.Entities.Entity, System.String> m_CachedLabels;
```

- `private System.Int32 m_FaceColor`  

```csharp
private System.Int32 m_FaceColor;
```

- `private System.Boolean m_TunnelSelectOn`  

```csharp
private System.Boolean m_TunnelSelectOn;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Rendering.AggregateMeshSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.AggregateMeshSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public AggregateMeshSystem()`  

```csharp
[Preserve]
	public AggregateMeshSystem()
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

- `private ClearMeshData(System.Collections.Generic.List<Game.Rendering.AggregateMeshSystem+MeshData> meshData) : System.Void`  

```csharp
private void ClearMeshData(List<MeshData> meshData)
	{
		if (meshData == null)
		{
			return;
		}
		for (int i = 0; i < meshData.Count; i++)
		{
			MeshData meshData2 = meshData[i];
			if (meshData2.m_Materials != null)
			{
				for (int j = 0; j < meshData2.m_Materials.Count; j++)
				{
					MaterialData value = meshData2.m_Materials[j];
					value.m_HasMesh = false;
					meshData2.m_Materials[j] = value;
				}
			}
			if (meshData2.m_Mesh != null)
			{
				Object.Destroy(meshData2.m_Mesh);
				meshData2.m_Mesh = null;
			}
			if (meshData2.m_HasMeshData)
			{
				meshData2.m_MeshData.Dispose();
				meshData2.m_HasMeshData = false;
			}
			meshData2.m_HasMesh = false;
		}
	}
```

- `private DestroyMeshData(System.Collections.Generic.List<Game.Rendering.AggregateMeshSystem+MeshData> meshData) : System.Void`  

```csharp
private void DestroyMeshData(List<MeshData> meshData)
	{
		if (meshData == null)
		{
			return;
		}
		for (int i = 0; i < meshData.Count; i++)
		{
			MeshData meshData2 = meshData[i];
			if (meshData2.m_Materials != null)
			{
				for (int j = 0; j < meshData2.m_Materials.Count; j++)
				{
					MaterialData materialData = meshData2.m_Materials[j];
					if (materialData.m_Material != null)
					{
						Object.Destroy(materialData.m_Material);
					}
				}
			}
			if (meshData2.m_Mesh != null)
			{
				Object.Destroy(meshData2.m_Mesh);
			}
			if (meshData2.m_HasMeshData)
			{
				meshData2.m_MeshData.Dispose();
			}
		}
		meshData.Clear();
	}
```

- `private FillArrowMeshData(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle FillArrowMeshData(JobHandle inputDeps)
	{
		JobHandle jobHandle = inputDeps;
		if (m_ArrowData != null)
		{
			for (int i = 0; i < m_ArrowData.Count; i++)
			{
				MeshData meshData = m_ArrowData[i];
				if (!meshData.m_MeshDirty)
				{
					continue;
				}
				meshData.m_MeshDirty = false;
				m_ArrowQuery.ResetFilter();
				m_ArrowQuery.SetSharedComponentFilter(new ArrowMaterial
				{
					m_Index = i
				});
				if (m_ArrowQuery.IsEmptyIgnoreFilter)
				{
					if (meshData.m_Materials != null)
					{
						for (int j = 0; j < meshData.m_Materials.Count; j++)
						{
							MaterialData value = meshData.m_Materials[j];
							value.m_HasMesh = false;
							meshData.m_Materials[j] = value;
						}
					}
					if (meshData.m_Mesh != null)
					{
						Object.Destroy(meshData.m_Mesh);
						meshData.m_Mesh = null;
					}
					if (meshData.m_HasMeshData)
					{
						meshData.m_HasMeshData = false;
						meshData.m_MeshData.Dispose();
					}
					meshData.m_HasMesh = false;
				}
				else
				{
					JobHandle outJobHandle;
					NativeList<ArchetypeChunk> chunks = m_ArrowQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle);
					if (!meshData.m_HasMeshData)
					{
						meshData.m_HasMeshData = true;
						meshData.m_MeshData = Mesh.AllocateWritableMeshData(1);
					}
					JobHandle jobHandle2 = IJobExtensions.Schedule(new FillArrowDataJob
					{
						m_HiddenType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Hidden_RO_ComponentTypeHandle, ref base.CheckedStateRef),
						m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
						m_ArrowPositionType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_ArrowPosition_RO_BufferTypeHandle, ref base.CheckedStateRef),
						m_NetArrowData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetArrowData_RO_ComponentLookup, ref base.CheckedStateRef),
						m_Chunks = chunks,
						m_ArrowMeshData = meshData.m_MeshData
					}, JobHandle.CombineDependencies(outJobHandle, inputDeps));
					chunks.Dispose(jobHandle2);
					meshData.m_DataDependencies = jobHandle2;
					jobHandle = JobHandle.CombineDependencies(jobHandle, jobHandle2);
				}
			}
		}
		return jobHandle;
	}
```

- `private FillNameMeshData(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle FillNameMeshData(JobHandle inputDeps)
	{
		JobHandle jobHandle = inputDeps;
		if (m_LabelData != null)
		{
			for (int i = 0; i < m_LabelData.Count; i++)
			{
				MeshData meshData = m_LabelData[i];
				if (!meshData.m_MeshDirty)
				{
					continue;
				}
				meshData.m_MeshDirty = false;
				m_LabelQuery.ResetFilter();
				m_LabelQuery.SetSharedComponentFilter(new LabelMaterial
				{
					m_Index = i
				});
				if (m_LabelQuery.IsEmptyIgnoreFilter)
				{
					if (meshData.m_Materials != null)
					{
						for (int j = 0; j < meshData.m_Materials.Count; j++)
						{
							MaterialData value = meshData.m_Materials[j];
							value.m_HasMesh = false;
							meshData.m_Materials[j] = value;
						}
					}
					if (meshData.m_Mesh != null)
					{
						Object.Destroy(meshData.m_Mesh);
						meshData.m_Mesh = null;
					}
					if (meshData.m_HasMeshData)
					{
						meshData.m_HasMeshData = false;
						meshData.m_MeshData.Dispose();
					}
					meshData.m_HasMesh = false;
					continue;
				}
				JobHandle outJobHandle;
				NativeList<ArchetypeChunk> chunks = m_LabelQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle);
				if (!meshData.m_HasMeshData)
				{
					meshData.m_HasMeshData = true;
					meshData.m_MeshData = Mesh.AllocateWritableMeshData(1);
				}
				JobHandle jobHandle2 = IJobExtensions.Schedule(new FillNameDataJob
				{
					m_LabelExtentsType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_LabelExtents_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_HiddenType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Hidden_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_LabelPositionType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_LabelPosition_RO_BufferTypeHandle, ref base.CheckedStateRef),
					m_LabelVertexType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_LabelVertex_RO_BufferTypeHandle, ref base.CheckedStateRef),
					m_NetNameData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetNameData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_Chunks = chunks,
					m_SubMeshCount = meshData.m_Materials.Count,
					m_NameMeshData = meshData.m_MeshData
				}, JobHandle.CombineDependencies(outJobHandle, inputDeps));
				chunks.Dispose(jobHandle2);
				meshData.m_DataDependencies = jobHandle2;
				jobHandle = JobHandle.CombineDependencies(jobHandle, jobHandle2);
			}
		}
		return jobHandle;
	}
```

- `public GetArrowMaterial(System.Int32 index, System.Int32 subMeshIndex, UnityEngine.Material& material) : System.Boolean`  

```csharp
public bool GetArrowMaterial(int index, int subMeshIndex, out Material material)
	{
		return GetMaterialData(m_ArrowData, index, subMeshIndex, out material);
	}
```

- `public GetArrowMaterialCount() : System.Int32`  

```csharp
public int GetArrowMaterialCount()
	{
		if (m_ArrowData != null)
		{
			return m_ArrowData.Count;
		}
		return 0;
	}
```

- `public GetArrowMesh(System.Int32 index, UnityEngine.Mesh& mesh, System.Int32& subMeshCount) : System.Boolean`  

```csharp
public bool GetArrowMesh(int index, out Mesh mesh, out int subMeshCount)
	{
		return GetMeshData(m_ArrowData, index, out mesh, out subMeshCount);
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

- `private GetMaterialData(System.Collections.Generic.List<Game.Rendering.AggregateMeshSystem+MeshData> meshData, System.Int32 index, System.Int32 subMeshIndex, UnityEngine.Material& material) : System.Boolean`  

```csharp
private bool GetMaterialData(List<MeshData> meshData, int index, int subMeshIndex, out Material material)
	{
		MaterialData materialData = meshData[index].m_Materials[subMeshIndex];
		material = materialData.m_Material;
		return materialData.m_HasMesh;
	}
```

- `private GetMeshData(System.Collections.Generic.List<Game.Rendering.AggregateMeshSystem+MeshData> meshData, System.Int32 index, UnityEngine.Mesh& mesh, System.Int32& subMeshCount) : System.Boolean`  

```csharp
private bool GetMeshData(List<MeshData> meshData, int index, out Mesh mesh, out int subMeshCount)
	{
		MeshData meshData2 = meshData[index];
		subMeshCount = meshData2.m_Materials.Count;
		if (meshData2.m_HasMeshData)
		{
			meshData2.m_HasMeshData = false;
			meshData2.m_DataDependencies.Complete();
			meshData2.m_DataDependencies = default(JobHandle);
			if (meshData2.m_Mesh == null)
			{
				meshData2.m_Mesh = new Mesh();
				if (meshData2.m_OriginalMaterial != null)
				{
					meshData2.m_Mesh.name = $"Aggregates ({meshData2.m_OriginalMaterial})";
				}
			}
			Mesh.ApplyAndDisposeWritableMeshData(meshData2.m_MeshData, meshData2.m_Mesh, MeshUpdateFlags.DontValidateIndices | MeshUpdateFlags.DontRecalculateBounds);
			Bounds bounds = default(Bounds);
			meshData2.m_HasMesh = false;
			for (int i = 0; i < subMeshCount; i++)
			{
				MaterialData value = meshData2.m_Materials[i];
				SubMeshDescriptor subMesh = meshData2.m_Mesh.GetSubMesh(i);
				value.m_HasMesh = subMesh.vertexCount > 0;
				if (value.m_HasMesh)
				{
					if (meshData2.m_HasMesh)
					{
						bounds.Encapsulate(subMesh.bounds);
					}
					else
					{
						bounds = subMesh.bounds;
						meshData2.m_HasMesh = true;
					}
				}
				meshData2.m_Materials[i] = value;
			}
			meshData2.m_Mesh.bounds = bounds;
		}
		mesh = meshData2.m_Mesh;
		return meshData2.m_HasMesh;
	}
```

- `public GetNameMaterial(System.Int32 index, System.Int32 subMeshIndex, UnityEngine.Material& material) : System.Boolean`  

```csharp
public bool GetNameMaterial(int index, int subMeshIndex, out Material material)
	{
		return GetMaterialData(m_LabelData, index, subMeshIndex, out material);
	}
```

- `public GetNameMaterialCount() : System.Int32`  

```csharp
public int GetNameMaterialCount()
	{
		if (m_LabelData != null)
		{
			return m_LabelData.Count;
		}
		return 0;
	}
```

- `public GetNameMesh(System.Int32 index, UnityEngine.Mesh& mesh, System.Int32& subMeshCount) : System.Boolean`  

```csharp
public bool GetNameMesh(int index, out Mesh mesh, out int subMeshCount)
	{
		return GetMeshData(m_LabelData, index, out mesh, out subMeshCount);
	}
```

- `private InitializePrefabs() : System.Void`  

```csharp
private void InitializePrefabs()
	{
		NativeArray<ArchetypeChunk> nativeArray = m_CreatedPrefabQuery.ToArchetypeChunkArray(Allocator.TempJob);
		try
		{
			bool flag = m_UndergroundViewSystem.undergroundOn && m_UndergroundViewSystem.tunnelsOn;
			ComponentTypeHandle<PrefabData> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<NetNameData> typeHandle2 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_NetNameData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<NetArrowData> typeHandle3 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_NetArrowData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
			for (int i = 0; i < nativeArray.Length; i++)
			{
				ArchetypeChunk archetypeChunk = nativeArray[i];
				NativeArray<PrefabData> nativeArray2 = archetypeChunk.GetNativeArray(ref typeHandle);
				NativeArray<NetNameData> nativeArray3 = archetypeChunk.GetNativeArray(ref typeHandle2);
				NativeArray<NetArrowData> nativeArray4 = archetypeChunk.GetNativeArray(ref typeHandle3);
				for (int j = 0; j < nativeArray2.Length; j++)
				{
					AggregateNetPrefab prefab = m_PrefabSystem.GetPrefab<AggregateNetPrefab>(nativeArray2[j]);
					NetLabel component = prefab.GetComponent<NetLabel>();
					NetArrow component2 = prefab.GetComponent<NetArrow>();
					NetNameData value;
					int num;
					if (component != null && component.m_NameMaterial != null)
					{
						value = nativeArray3[j];
						if (m_LabelData != null)
						{
							num = 0;
							while (num < m_LabelData.Count)
							{
								if (!(m_LabelData[num].m_OriginalMaterial == component.m_NameMaterial))
								{
									num++;
									continue;
								}
								goto IL_012f;
							}
						}
						MeshData meshData = new MeshData();
						meshData.m_OriginalMaterial = component.m_NameMaterial;
						meshData.m_Materials = new List<MaterialData>(2);
						if (m_LabelData == null)
						{
							m_LabelData = new List<MeshData>();
						}
						value.m_MaterialIndex = m_LabelData.Count;
						nativeArray3[j] = value;
						m_LabelData.Add(meshData);
					}
					goto IL_01b9;
					IL_01b9:
					if (!(component2 != null) || !(component2.m_ArrowMaterial != null))
					{
						continue;
					}
					NetArrowData value2 = nativeArray4[j];
					int num2;
					if (m_ArrowData != null)
					{
						num2 = 0;
						while (num2 < m_ArrowData.Count)
						{
							if (!(m_ArrowData[num2].m_OriginalMaterial == component2.m_ArrowMaterial))
							{
								num2++;
								continue;
							}
							goto IL_0210;
						}
					}
					MeshData meshData2 = new MeshData();
					meshData2.m_OriginalMaterial = component2.m_ArrowMaterial;
					meshData2.m_Materials = new List<MaterialData>(2);
					MaterialData item = default(MaterialData);
					item.m_Material = new Material(component2.m_ArrowMaterial);
					item.m_Material.name = "Aggregate arrows (" + prefab.name + ")";
					item.m_Material.SetColor(m_FaceColor, new Color(1f, 1f, 1f, flag ? 0.25f : 1f));
					meshData2.m_Materials.Add(item);
					MaterialData item2 = default(MaterialData);
					item2.m_Material = new Material(component2.m_ArrowMaterial);
					item2.m_Material.name = "Aggregate underground arrows (" + prefab.name + ")";
					item2.m_Material.SetColor(m_FaceColor, new Color(1f, 1f, 1f, 1f));
					item2.m_IsUnderground = true;
					meshData2.m_Materials.Add(item2);
					if (m_ArrowData == null)
					{
						m_ArrowData = new List<MeshData>();
					}
					value2.m_MaterialIndex = m_ArrowData.Count;
					nativeArray4[j] = value2;
					m_ArrowData.Add(meshData2);
					continue;
					IL_012f:
					value.m_MaterialIndex = num;
					nativeArray3[j] = value;
					goto IL_01b9;
					IL_0210:
					value2.m_MaterialIndex = num2;
					nativeArray4[j] = value2;
				}
			}
		}
		finally
		{
			nativeArray.Dispose();
		}
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_OverlayRenderSystem = base.World.GetOrCreateSystemManaged<OverlayRenderSystem>();
		m_UndergroundViewSystem = base.World.GetOrCreateSystemManaged<UndergroundViewSystem>();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_NameSystem = base.World.GetOrCreateSystemManaged<NameSystem>();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_CreatedPrefabQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<AggregateNetData>()
			},
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<NetNameData>(),
				ComponentType.ReadOnly<NetArrowData>()
			}
		});
		m_UpdatedLabelQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Aggregate>(),
				ComponentType.ReadOnly<LabelMaterial>()
			},
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<BatchesUpdated>(),
				ComponentType.ReadOnly<Deleted>()
			}
		});
		m_LabelQuery = GetEntityQuery(ComponentType.ReadOnly<Aggregate>(), ComponentType.ReadOnly<LabelMaterial>(), ComponentType.Exclude<Deleted>());
		m_UpdatedArrowQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Aggregate>(),
				ComponentType.ReadOnly<ArrowMaterial>()
			},
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<BatchesUpdated>(),
				ComponentType.ReadOnly<Deleted>()
			}
		});
		m_ArrowQuery = GetEntityQuery(ComponentType.ReadOnly<Aggregate>(), ComponentType.ReadOnly<ArrowMaterial>(), ComponentType.Exclude<Deleted>());
		m_TempAggregatedQuery = GetEntityQuery(ComponentType.ReadOnly<Aggregated>(), ComponentType.ReadOnly<Temp>(), ComponentType.Exclude<Deleted>());
		m_FaceColor = Shader.PropertyToID("_FaceColor");
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
		DestroyMeshData(m_LabelData);
		DestroyMeshData(m_ArrowData);
		GameManager.instance.localizationManager.onActiveDictionaryChanged -= OnDictionaryChanged;
		base.OnDestroy();
	}
```

- `private OnDictionaryChanged() : System.Void`  

```csharp
private void OnDictionaryChanged()
	{
		base.EntityManager.AddComponent<Updated>(m_LabelQuery);
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		bool loaded = GetLoaded();
		if (!m_CreatedPrefabQuery.IsEmptyIgnoreFilter)
		{
			InitializePrefabs();
		}
		EntityQuery entityQuery = (loaded ? m_LabelQuery : m_UpdatedLabelQuery);
		EntityQuery entityQuery2 = (loaded ? m_ArrowQuery : m_UpdatedArrowQuery);
		bool flag = m_UndergroundViewSystem.undergroundOn && m_UndergroundViewSystem.tunnelsOn;
		bool flag2 = !entityQuery.IsEmptyIgnoreFilter;
		bool flag3 = !entityQuery2.IsEmptyIgnoreFilter;
		if (flag != m_TunnelSelectOn)
		{
			UpdateUndergroundState(m_LabelData, flag);
			UpdateUndergroundState(m_ArrowData, flag);
			m_TunnelSelectOn = flag;
		}
		if (flag2 || flag3)
		{
			JobHandle dependency = base.Dependency;
			JobHandle jobHandle = default(JobHandle);
			if (flag2)
			{
				UpdateLabelVertices(loaded);
				JobHandle inputDeps = UpdateLabelPositions(dependency, loaded);
				jobHandle = JobHandle.CombineDependencies(jobHandle, FillNameMeshData(inputDeps));
			}
			if (flag3)
			{
				UpdateArrowMaterials(loaded);
				JobHandle inputDeps2 = UpdateArrowPositions(dependency, loaded);
				jobHandle = JobHandle.CombineDependencies(jobHandle, FillArrowMeshData(inputDeps2));
			}
			base.Dependency = jobHandle;
		}
	}
```

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PreDeserialize(Context context)
	{
		ClearMeshData(m_LabelData);
		ClearMeshData(m_ArrowData);
		if (m_CachedLabels != null)
		{
			m_CachedLabels.Clear();
		}
		m_Loaded = true;
	}
```

- `private UpdateArrowMaterials(System.Boolean isLoaded) : System.Void`  

```csharp
private void UpdateArrowMaterials(bool isLoaded)
	{
		List<MaterialUpdate> list = null;
		NativeArray<ArchetypeChunk> nativeArray = (isLoaded ? m_ArrowQuery : m_UpdatedArrowQuery).ToArchetypeChunkArray(Allocator.TempJob);
		try
		{
			EntityTypeHandle entityTypeHandle = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<Updated> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Updated_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<PrefabRef> typeHandle2 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			SharedComponentTypeHandle<ArrowMaterial> sharedComponentTypeHandle = InternalCompilerInterface.GetSharedComponentTypeHandle(ref __TypeHandle.__Game_Net_ArrowMaterial_SharedComponentTypeHandle, ref base.CheckedStateRef);
			for (int i = 0; i < nativeArray.Length; i++)
			{
				ArchetypeChunk archetypeChunk = nativeArray[i];
				ArrowMaterial sharedComponent = archetypeChunk.GetSharedComponent(sharedComponentTypeHandle, base.EntityManager);
				if (isLoaded || archetypeChunk.Has(ref typeHandle))
				{
					NativeArray<Entity> nativeArray2 = archetypeChunk.GetNativeArray(entityTypeHandle);
					NativeArray<PrefabRef> nativeArray3 = archetypeChunk.GetNativeArray(ref typeHandle2);
					for (int j = 0; j < nativeArray2.Length; j++)
					{
						Entity entity = nativeArray2[j];
						PrefabRef prefabRef = nativeArray3[j];
						NetArrowData componentData = base.EntityManager.GetComponentData<NetArrowData>(prefabRef.m_Prefab);
						m_ArrowData[componentData.m_MaterialIndex].m_MeshDirty = true;
						if (componentData.m_MaterialIndex != sharedComponent.m_Index)
						{
							if (list == null)
							{
								list = new List<MaterialUpdate>();
							}
							list.Add(new MaterialUpdate
							{
								m_Entity = entity,
								m_Material = componentData.m_MaterialIndex
							});
						}
					}
				}
				else
				{
					NativeArray<Entity> nativeArray4 = archetypeChunk.GetNativeArray(entityTypeHandle);
					NativeArray<PrefabRef> nativeArray5 = archetypeChunk.GetNativeArray(ref typeHandle2);
					for (int k = 0; k < nativeArray4.Length; k++)
					{
						_ = nativeArray4[k];
						PrefabRef prefabRef2 = nativeArray5[k];
						NetArrowData componentData2 = base.EntityManager.GetComponentData<NetArrowData>(prefabRef2.m_Prefab);
						m_ArrowData[componentData2.m_MaterialIndex].m_MeshDirty = true;
					}
				}
			}
		}
		finally
		{
			nativeArray.Dispose();
		}
		if (list != null)
		{
			for (int l = 0; l < list.Count; l++)
			{
				MaterialUpdate materialUpdate = list[l];
				base.EntityManager.SetSharedComponent(materialUpdate.m_Entity, new ArrowMaterial
				{
					m_Index = materialUpdate.m_Material
				});
			}
		}
	}
```

- `private UpdateArrowPositions(Unity.Jobs.JobHandle inputDeps, System.Boolean isLoaded) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle UpdateArrowPositions(JobHandle inputDeps, bool isLoaded)
	{
		EntityQuery query = (isLoaded ? m_ArrowQuery : m_UpdatedArrowQuery);
		NativeParallelMultiHashMap<Entity, TempValue> tempMap = new NativeParallelMultiHashMap<Entity, TempValue>(32, Allocator.TempJob);
		FillTempMapJob jobData = new FillTempMapJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_AggregatedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Aggregated_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TempMap = tempMap
		};
		UpdateArrowPositionsJob jobData2 = new UpdateArrowPositionsJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_AggregateElementType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_AggregateElement_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_ArrowPositionType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_ArrowPosition_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_EdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CompositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Composition_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NetCompositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetCompositionData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ConnectedEdges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedEdge_RO_BufferLookup, ref base.CheckedStateRef),
			m_NetCompositionCarriageways = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_NetCompositionCarriageway_RO_BufferLookup, ref base.CheckedStateRef),
			m_EditorMode = m_ToolSystem.actionMode.IsEditor(),
			m_TempMap = tempMap
		};
		JobHandle dependsOn = JobChunkExtensions.Schedule(jobData, m_TempAggregatedQuery, inputDeps);
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(jobData2, query, dependsOn);
		tempMap.Dispose(jobHandle);
		return jobHandle;
	}
```

- `private UpdateLabelPositions(Unity.Jobs.JobHandle inputDeps, System.Boolean isLoaded) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle UpdateLabelPositions(JobHandle inputDeps, bool isLoaded)
	{
		EntityQuery query = (isLoaded ? m_LabelQuery : m_UpdatedLabelQuery);
		return JobChunkExtensions.ScheduleParallel(new UpdateLabelPositionsJob
		{
			m_LabelExtentsType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_LabelExtents_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_AggregateElementType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_AggregateElement_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_LabelPositionType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_LabelPosition_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_EdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CompositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Composition_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NetCompositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetCompositionData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ConnectedEdges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedEdge_RO_BufferLookup, ref base.CheckedStateRef)
		}, query, inputDeps);
	}
```

- `private UpdateLabelVertices(System.Boolean isLoaded) : System.Void`  

```csharp
private void UpdateLabelVertices(bool isLoaded)
	{
		List<MaterialUpdate> list = null;
		NativeArray<ArchetypeChunk> nativeArray = (isLoaded ? m_LabelQuery : m_UpdatedLabelQuery).ToArchetypeChunkArray(Allocator.TempJob);
		try
		{
			TextMeshPro textMesh = m_OverlayRenderSystem.GetTextMesh();
			textMesh.rectTransform.sizeDelta = new Vector2(250f, 100f);
			textMesh.fontSize = 200f;
			textMesh.alignment = TextAlignmentOptions.Center;
			bool flag = m_UndergroundViewSystem.undergroundOn && m_UndergroundViewSystem.tunnelsOn;
			EntityTypeHandle entityTypeHandle = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<Updated> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Updated_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<BatchesUpdated> typeHandle2 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_BatchesUpdated_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<Temp> typeHandle3 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<PrefabRef> typeHandle4 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<LabelExtents> typeHandle5 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_LabelExtents_RW_ComponentTypeHandle, ref base.CheckedStateRef);
			SharedComponentTypeHandle<LabelMaterial> sharedComponentTypeHandle = InternalCompilerInterface.GetSharedComponentTypeHandle(ref __TypeHandle.__Game_Net_LabelMaterial_SharedComponentTypeHandle, ref base.CheckedStateRef);
			BufferTypeHandle<LabelVertex> bufferTypeHandle = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_LabelVertex_RW_BufferTypeHandle, ref base.CheckedStateRef);
			LabelVertex value2 = default(LabelVertex);
			for (int i = 0; i < nativeArray.Length; i++)
			{
				ArchetypeChunk archetypeChunk = nativeArray[i];
				LabelMaterial sharedComponent = archetypeChunk.GetSharedComponent(sharedComponentTypeHandle, base.EntityManager);
				if (isLoaded || archetypeChunk.Has(ref typeHandle) || archetypeChunk.Has(ref typeHandle2))
				{
					NativeArray<Entity> nativeArray2 = archetypeChunk.GetNativeArray(entityTypeHandle);
					NativeArray<Temp> nativeArray3 = archetypeChunk.GetNativeArray(ref typeHandle3);
					NativeArray<PrefabRef> nativeArray4 = archetypeChunk.GetNativeArray(ref typeHandle4);
					NativeArray<LabelExtents> nativeArray5 = archetypeChunk.GetNativeArray(ref typeHandle5);
					BufferAccessor<LabelVertex> bufferAccessor = archetypeChunk.GetBufferAccessor(ref bufferTypeHandle);
					for (int j = 0; j < nativeArray2.Length; j++)
					{
						Entity entity = nativeArray2[j];
						PrefabRef prefabRef = nativeArray4[j];
						DynamicBuffer<LabelVertex> dynamicBuffer = bufferAccessor[j];
						NetNameData componentData = base.EntityManager.GetComponentData<NetNameData>(prefabRef.m_Prefab);
						MeshData meshData = m_LabelData[componentData.m_MaterialIndex];
						meshData.m_MeshDirty = true;
						if (componentData.m_MaterialIndex != sharedComponent.m_Index)
						{
							if (list == null)
							{
								list = new List<MaterialUpdate>();
							}
							list.Add(new MaterialUpdate
							{
								m_Entity = entity,
								m_Material = componentData.m_MaterialIndex
							});
						}
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
								dynamicBuffer.Clear();
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
						dynamicBuffer.ResizeUninitialized(num);
						num = 0;
						for (int l = 0; l < textInfo.meshInfo.Length; l++)
						{
							TMP_MeshInfo tMP_MeshInfo2 = textInfo.meshInfo[l];
							if (tMP_MeshInfo2.vertexCount == 0)
							{
								continue;
							}
							Texture mainTexture = tMP_MeshInfo2.material.mainTexture;
							int2 material = -1;
							for (int m = 0; m < meshData.m_Materials.Count; m++)
							{
								MaterialData materialData = meshData.m_Materials[m];
								if (materialData.m_Material.mainTexture == mainTexture)
								{
									if (materialData.m_IsUnderground)
									{
										material.y = m;
									}
									else
									{
										material.x = m;
									}
								}
							}
							if (material.x == -1)
							{
								MaterialData item = default(MaterialData);
								item.m_Material = new Material(meshData.m_OriginalMaterial);
								item.m_Material.SetColor(m_FaceColor, new Color(1f, 1f, 1f, flag ? 0.25f : 1f));
								m_OverlayRenderSystem.CopyFontAtlasParameters(tMP_MeshInfo2.material, item.m_Material);
								material.x = meshData.m_Materials.Count;
								meshData.m_Materials.Add(item);
								item.m_Material.name = $"Aggregate names {material.x} ({meshData.m_OriginalMaterial.name})";
							}
							if (material.y == -1)
							{
								MaterialData item2 = default(MaterialData);
								item2.m_Material = new Material(meshData.m_OriginalMaterial);
								item2.m_Material.SetColor(m_FaceColor, new Color(1f, 1f, 1f, 1f));
								m_OverlayRenderSystem.CopyFontAtlasParameters(tMP_MeshInfo2.material, item2.m_Material);
								item2.m_IsUnderground = true;
								material.y = meshData.m_Materials.Count;
								meshData.m_Materials.Add(item2);
								item2.m_Material.name = $"Aggregate underground names {material.y} ({meshData.m_OriginalMaterial.name})";
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
								value2.m_Material = material;
								dynamicBuffer[num + n] = value2;
							}
							num += tMP_MeshInfo2.vertexCount;
						}
						LabelExtents value3 = default(LabelExtents);
						for (int num2 = 0; num2 < textInfo.lineCount; num2++)
						{
							Extents lineExtents = textInfo.lineInfo[num2].lineExtents;
							value3.m_Bounds |= new Bounds2(lineExtents.min, lineExtents.max);
						}
						nativeArray5[j] = value3;
					}
					continue;
				}
				NativeArray<Entity> nativeArray6 = archetypeChunk.GetNativeArray(entityTypeHandle);
				NativeArray<PrefabRef> nativeArray7 = archetypeChunk.GetNativeArray(ref typeHandle4);
				for (int num3 = 0; num3 < nativeArray6.Length; num3++)
				{
					Entity key = nativeArray6[num3];
					PrefabRef prefabRef2 = nativeArray7[num3];
					NetNameData componentData2 = base.EntityManager.GetComponentData<NetNameData>(prefabRef2.m_Prefab);
					m_LabelData[componentData2.m_MaterialIndex].m_MeshDirty = true;
					if (m_CachedLabels != null)
					{
						m_CachedLabels.Remove(key);
					}
				}
			}
		}
		finally
		{
			nativeArray.Dispose();
		}
		if (list != null)
		{
			for (int num4 = 0; num4 < list.Count; num4++)
			{
				MaterialUpdate materialUpdate = list[num4];
				base.EntityManager.SetSharedComponent(materialUpdate.m_Entity, new LabelMaterial
				{
					m_Index = materialUpdate.m_Material
				});
			}
		}
	}
```

- `private UpdateUndergroundState(System.Collections.Generic.List<Game.Rendering.AggregateMeshSystem+MeshData> meshData, System.Boolean undergroundOn) : System.Void`  

```csharp
private void UpdateUndergroundState(List<MeshData> meshData, bool undergroundOn)
	{
		if (meshData == null)
		{
			return;
		}
		for (int i = 0; i < meshData.Count; i++)
		{
			MeshData meshData2 = meshData[i];
			if (meshData2.m_Materials == null)
			{
				continue;
			}
			for (int j = 0; j < meshData2.m_Materials.Count; j++)
			{
				MaterialData materialData = meshData2.m_Materials[j];
				if (!materialData.m_IsUnderground && materialData.m_Material != null)
				{
					materialData.m_Material.SetColor(m_FaceColor, new Color(1f, 1f, 1f, undergroundOn ? 0.25f : 1f));
				}
			}
		}
	}
```


## Nested types

- `Game.Rendering.AggregateMeshSystem+MaterialData`  
- `Game.Rendering.AggregateMeshSystem+MeshData`  
- `Game.Rendering.AggregateMeshSystem+MaterialUpdate`  
- `Game.Rendering.AggregateMeshSystem+UpdateLabelPositionsJob`  
- `Game.Rendering.AggregateMeshSystem+FillTempMapJob`  
- `Game.Rendering.AggregateMeshSystem+TempValue`  
- `Game.Rendering.AggregateMeshSystem+UpdateArrowPositionsJob`  
- `Game.Rendering.AggregateMeshSystem+LabelVertexData`  
- `Game.Rendering.AggregateMeshSystem+SubMeshData`  
- `Game.Rendering.AggregateMeshSystem+FillNameDataJob`  
- `Game.Rendering.AggregateMeshSystem+ArrowVertexData`  
- `Game.Rendering.AggregateMeshSystem+FillArrowDataJob`  
- `Game.Rendering.AggregateMeshSystem+TypeHandle`  

