# Game.Rendering.CityBoundaryMeshSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CityBoundaryMeshSystem : Game.GameSystemBase, Game.Serialization.IPreDeserialize
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Areas.MapTileSystem m_MapTileSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Areas.SearchSystem m_AreaSearchSystem;
    private Unity.Entities.EntityQuery m_UpdatedQuery;
    private Unity.Entities.EntityQuery m_MapTileQuery;
    private Unity.Entities.EntityQuery m_SettingsQuery;
    private UnityEngine.Mesh m_BoundaryMesh;
    private UnityEngine.Material m_BoundaryMaterial;
    private Unity.Jobs.JobHandle m_MeshDependencies;
    private Unity.Collections.NativeList<Unity.Mathematics.float3> m_Vertices;
    private Unity.Collections.NativeList<Unity.Mathematics.float2> m_UVs;
    private Unity.Collections.NativeList<UnityEngine.Color32> m_Colors;
    private Unity.Collections.NativeList<System.Int32> m_Indices;
    private Colossal.Collections.NativeValue<Colossal.Mathematics.Bounds3> m_Bounds;
    private System.Boolean m_Loaded;
    private Game.Rendering.CityBoundaryMeshSystem+TypeHandle __TypeHandle;

    public CityBoundaryMeshSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void Clear();
    private System.Void DestroyMesh();
    private System.Void DisposeMeshData();
    public System.Boolean GetBoundaryMesh(UnityEngine.Mesh& mesh, UnityEngine.Material& material);
    private System.Boolean GetLoaded();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Areas.MapTileSystem m_MapTileSystem`  

```csharp
private Game.Areas.MapTileSystem m_MapTileSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Areas.SearchSystem m_AreaSearchSystem`  

```csharp
private Game.Areas.SearchSystem m_AreaSearchSystem;
```

- `private Unity.Entities.EntityQuery m_UpdatedQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedQuery;
```

- `private Unity.Entities.EntityQuery m_MapTileQuery`  

```csharp
private Unity.Entities.EntityQuery m_MapTileQuery;
```

- `private Unity.Entities.EntityQuery m_SettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_SettingsQuery;
```

- `private UnityEngine.Mesh m_BoundaryMesh`  

```csharp
private UnityEngine.Mesh m_BoundaryMesh;
```

- `private UnityEngine.Material m_BoundaryMaterial`  

```csharp
private UnityEngine.Material m_BoundaryMaterial;
```

- `private Unity.Jobs.JobHandle m_MeshDependencies`  

```csharp
private Unity.Jobs.JobHandle m_MeshDependencies;
```

- `private Unity.Collections.NativeList<Unity.Mathematics.float3> m_Vertices`  

```csharp
private Unity.Collections.NativeList<Unity.Mathematics.float3> m_Vertices;
```

- `private Unity.Collections.NativeList<Unity.Mathematics.float2> m_UVs`  

```csharp
private Unity.Collections.NativeList<Unity.Mathematics.float2> m_UVs;
```

- `private Unity.Collections.NativeList<UnityEngine.Color32> m_Colors`  

```csharp
private Unity.Collections.NativeList<UnityEngine.Color32> m_Colors;
```

- `private Unity.Collections.NativeList<System.Int32> m_Indices`  

```csharp
private Unity.Collections.NativeList<System.Int32> m_Indices;
```

- `private Colossal.Collections.NativeValue<Colossal.Mathematics.Bounds3> m_Bounds`  

```csharp
private Colossal.Collections.NativeValue<Colossal.Mathematics.Bounds3> m_Bounds;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Rendering.CityBoundaryMeshSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.CityBoundaryMeshSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CityBoundaryMeshSystem()`  

```csharp
[Preserve]
	public CityBoundaryMeshSystem()
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

- `private Clear() : System.Void`  

```csharp
private void Clear()
	{
		DisposeMeshData();
		DestroyMesh();
		m_BoundaryMaterial = null;
	}
```

- `private DestroyMesh() : System.Void`  

```csharp
private void DestroyMesh()
	{
		if (m_BoundaryMesh != null)
		{
			Object.Destroy(m_BoundaryMesh);
			m_BoundaryMesh = null;
		}
	}
```

- `private DisposeMeshData() : System.Void`  

```csharp
private void DisposeMeshData()
	{
		if (m_Vertices.IsCreated)
		{
			m_MeshDependencies.Complete();
			m_MeshDependencies = default(JobHandle);
			m_Vertices.Dispose();
			m_UVs.Dispose();
			m_Colors.Dispose();
			m_Indices.Dispose();
			m_Bounds.Dispose();
		}
	}
```

- `public GetBoundaryMesh(UnityEngine.Mesh& mesh, UnityEngine.Material& material) : System.Boolean`  

```csharp
public bool GetBoundaryMesh(out Mesh mesh, out Material material)
	{
		if (m_Vertices.IsCreated)
		{
			m_MeshDependencies.Complete();
			m_MeshDependencies = default(JobHandle);
			if (m_Vertices.Length != 0)
			{
				if (m_BoundaryMesh == null)
				{
					m_BoundaryMesh = new Mesh();
					m_BoundaryMesh.name = "City boundaries";
				}
				else
				{
					m_BoundaryMesh.Clear();
				}
				m_BoundaryMesh.SetVertices(m_Vertices.AsArray());
				m_BoundaryMesh.SetUVs(0, m_UVs.AsArray());
				m_BoundaryMesh.SetColors(m_Colors.AsArray());
				m_BoundaryMesh.SetIndices(m_Indices.AsArray(), MeshTopology.Triangles, 0, calculateBounds: false);
				float2 heightScaleOffset = m_TerrainSystem.heightScaleOffset;
				Bounds3 value = m_Bounds.value;
				value.min.y = heightScaleOffset.y;
				value.max.y = heightScaleOffset.y + heightScaleOffset.x;
				m_BoundaryMesh.bounds = RenderingUtils.ToBounds(value);
			}
			else
			{
				DestroyMesh();
			}
			m_Vertices.Dispose();
			m_UVs.Dispose();
			m_Colors.Dispose();
			m_Indices.Dispose();
			m_Bounds.Dispose();
		}
		mesh = m_BoundaryMesh;
		material = m_BoundaryMaterial;
		return m_BoundaryMesh != null;
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

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_MapTileSystem = base.World.GetOrCreateSystemManaged<MapTileSystem>();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_AreaSearchSystem = base.World.GetOrCreateSystemManaged<SearchSystem>();
		m_UpdatedQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<MapTile>(),
				ComponentType.ReadOnly<Area>()
			},
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Deleted>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		});
		m_MapTileQuery = GetEntityQuery(ComponentType.ReadOnly<MapTile>(), ComponentType.ReadOnly<Area>(), ComponentType.ReadOnly<Node>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_SettingsQuery = GetEntityQuery(ComponentType.ReadOnly<CityBoundaryData>());
		RequireForUpdate(m_SettingsQuery);
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
		Clear();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (GetLoaded() || !m_UpdatedQuery.IsEmptyIgnoreFilter)
		{
			DisposeMeshData();
			CityBoundaryPrefab prefab = m_PrefabSystem.GetPrefab<CityBoundaryPrefab>(m_SettingsQuery.GetSingletonEntity());
			m_BoundaryMaterial = prefab.m_Material;
			NativeQueue<Boundary> boundaryQueue = new NativeQueue<Boundary>(Allocator.TempJob);
			m_Vertices = new NativeList<float3>(Allocator.TempJob);
			m_UVs = new NativeList<float2>(Allocator.TempJob);
			m_Colors = new NativeList<Color32>(Allocator.TempJob);
			m_Indices = new NativeList<int>(Allocator.TempJob);
			m_Bounds = new NativeValue<Bounds3>(Allocator.TempJob);
			JobHandle dependencies;
			FillBoundaryQueueJob jobData = new FillBoundaryQueueJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_NativeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Native_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_NodeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Areas_Node_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_MapTileData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_MapTile_RO_ComponentLookup, ref base.CheckedStateRef),
				m_NativeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Native_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Nodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Node_RO_BufferLookup, ref base.CheckedStateRef),
				m_Triangles = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Triangle_RO_BufferLookup, ref base.CheckedStateRef),
				m_SearchTree = m_AreaSearchSystem.GetSearchTree(readOnly: true, out dependencies),
				m_StartTiles = m_MapTileSystem.GetStartTiles(),
				m_EditorMode = m_ToolSystem.actionMode.IsEditor(),
				m_CityBorderColor = prefab.m_CityBorderColor.linear,
				m_MapBorderColor = prefab.m_MapBorderColor.linear,
				m_BoundaryQueue = boundaryQueue.AsParallelWriter()
			};
			FillBoundaryMeshDataJob jobData2 = new FillBoundaryMeshDataJob
			{
				m_Width = prefab.m_Width,
				m_TilingLength = prefab.m_TilingLength,
				m_BoundaryQueue = boundaryQueue,
				m_Vertices = m_Vertices,
				m_UVs = m_UVs,
				m_Colors = m_Colors,
				m_Indices = m_Indices,
				m_Bounds = m_Bounds
			};
			JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(jobData, m_MapTileQuery, JobHandle.CombineDependencies(base.Dependency, dependencies));
			JobHandle jobHandle2 = IJobExtensions.Schedule(jobData2, jobHandle);
			boundaryQueue.Dispose(jobHandle2);
			m_AreaSearchSystem.AddSearchTreeReader(jobHandle);
			m_MeshDependencies = jobHandle2;
			base.Dependency = jobHandle;
		}
	}
```

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PreDeserialize(Context context)
	{
		Clear();
		m_Loaded = true;
	}
```


## Nested types

- `Game.Rendering.CityBoundaryMeshSystem+Boundary`  
- `Game.Rendering.CityBoundaryMeshSystem+FillBoundaryQueueJob`  
- `Game.Rendering.CityBoundaryMeshSystem+FillBoundaryMeshDataJob`  
- `Game.Rendering.CityBoundaryMeshSystem+TypeHandle`  

