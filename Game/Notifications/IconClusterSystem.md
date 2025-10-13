# Game.Notifications.IconClusterSystem

**Assembly:** `Game`  
**Namespace:** `Game.Notifications`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class IconClusterSystem : Game.GameSystemBase, Game.Serialization.IPreDeserialize
{
    private Unity.Entities.EntityQuery m_IconQuery;
    private Unity.Entities.EntityQuery m_ModifiedQuery;
    private Unity.Entities.EntityQuery m_ModifiedAndTempQuery;
    private Colossal.Collections.NativeQuadTree<System.Int32, Game.Notifications.IconClusterSystem+TreeBounds> m_ClusterTree;
    private Colossal.Collections.NativeHeapAllocator m_IconAllocator;
    private Unity.Collections.NativeList<Game.Notifications.IconClusterSystem+IconCluster> m_IconClusters;
    private Unity.Collections.NativeList<Game.Notifications.IconClusterSystem+ClusterIcon> m_ClusterIcons;
    private Unity.Collections.NativeList<System.Int32> m_RootClusters;
    private Unity.Collections.NativeList<System.Int32> m_FreeClusterIndices;
    private Unity.Jobs.JobHandle m_ClusterReadDeps;
    private Unity.Jobs.JobHandle m_ClusterWriteDeps;
    private System.Boolean m_Loaded;
    private Game.Notifications.IconClusterSystem+TypeHandle __TypeHandle;

    public IconClusterSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddIconClusterReader(Unity.Jobs.JobHandle jobHandle);
    public System.Void AddIconClusterWriter(Unity.Jobs.JobHandle jobHandle);
    private System.Void ClearData();
    public Game.Notifications.IconClusterSystem+ClusterData GetIconClusterData(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies);
    private System.Boolean GetLoaded();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
    public System.Void RecalculateClusters();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_IconQuery`  

```csharp
private Unity.Entities.EntityQuery m_IconQuery;
```

- `private Unity.Entities.EntityQuery m_ModifiedQuery`  

```csharp
private Unity.Entities.EntityQuery m_ModifiedQuery;
```

- `private Unity.Entities.EntityQuery m_ModifiedAndTempQuery`  

```csharp
private Unity.Entities.EntityQuery m_ModifiedAndTempQuery;
```

- `private Colossal.Collections.NativeQuadTree<System.Int32, Game.Notifications.IconClusterSystem+TreeBounds> m_ClusterTree`  

```csharp
private Colossal.Collections.NativeQuadTree<System.Int32, Game.Notifications.IconClusterSystem+TreeBounds> m_ClusterTree;
```

- `private Colossal.Collections.NativeHeapAllocator m_IconAllocator`  

```csharp
private Colossal.Collections.NativeHeapAllocator m_IconAllocator;
```

- `private Unity.Collections.NativeList<Game.Notifications.IconClusterSystem+IconCluster> m_IconClusters`  

```csharp
private Unity.Collections.NativeList<Game.Notifications.IconClusterSystem+IconCluster> m_IconClusters;
```

- `private Unity.Collections.NativeList<Game.Notifications.IconClusterSystem+ClusterIcon> m_ClusterIcons`  

```csharp
private Unity.Collections.NativeList<Game.Notifications.IconClusterSystem+ClusterIcon> m_ClusterIcons;
```

- `private Unity.Collections.NativeList<System.Int32> m_RootClusters`  

```csharp
private Unity.Collections.NativeList<System.Int32> m_RootClusters;
```

- `private Unity.Collections.NativeList<System.Int32> m_FreeClusterIndices`  

```csharp
private Unity.Collections.NativeList<System.Int32> m_FreeClusterIndices;
```

- `private Unity.Jobs.JobHandle m_ClusterReadDeps`  

```csharp
private Unity.Jobs.JobHandle m_ClusterReadDeps;
```

- `private Unity.Jobs.JobHandle m_ClusterWriteDeps`  

```csharp
private Unity.Jobs.JobHandle m_ClusterWriteDeps;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Notifications.IconClusterSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Notifications.IconClusterSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public IconClusterSystem()`  

```csharp
[Preserve]
	public IconClusterSystem()
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

- `public AddIconClusterReader(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public void AddIconClusterReader(JobHandle jobHandle)
	{
		m_ClusterReadDeps = JobHandle.CombineDependencies(m_ClusterReadDeps, jobHandle);
	}
```

- `public AddIconClusterWriter(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public void AddIconClusterWriter(JobHandle jobHandle)
	{
		m_ClusterWriteDeps = jobHandle;
	}
```

- `private ClearData() : System.Void`  

```csharp
private void ClearData()
	{
		if (m_IconClusters.IsCreated)
		{
			m_ClusterReadDeps.Complete();
			m_ClusterWriteDeps.Complete();
			m_ClusterReadDeps = default(JobHandle);
			m_ClusterWriteDeps = default(JobHandle);
			m_ClusterTree.Clear();
			m_IconAllocator.Clear();
			m_IconClusters.Clear();
			m_ClusterIcons.Clear();
			m_RootClusters.Clear();
			m_FreeClusterIndices.Clear();
			m_IconClusters.Add(default(IconCluster));
			m_ClusterIcons.ResizeUninitialized((int)m_IconAllocator.Size);
		}
	}
```

- `public GetIconClusterData(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies) : Game.Notifications.IconClusterSystem+ClusterData`  

```csharp
public ClusterData GetIconClusterData(bool readOnly, out JobHandle dependencies)
	{
		dependencies = (readOnly ? m_ClusterWriteDeps : JobHandle.CombineDependencies(m_ClusterReadDeps, m_ClusterWriteDeps));
		return new ClusterData(m_IconClusters, m_ClusterIcons, m_RootClusters);
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
		m_IconQuery = GetEntityQuery(ComponentType.ReadOnly<Icon>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<DisallowCluster>(), ComponentType.Exclude<Animation>());
		m_ModifiedQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Icon>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Deleted>()
			}
		});
		m_ModifiedAndTempQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Icon>() },
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Temp>(),
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Deleted>()
			}
		});
		m_ClusterTree = new NativeQuadTree<int, TreeBounds>(1f, Allocator.Persistent);
		m_IconAllocator = new NativeHeapAllocator(1024u, 1u, Allocator.Persistent);
		m_IconClusters = new NativeList<IconCluster>(1024, Allocator.Persistent);
		m_ClusterIcons = new NativeList<ClusterIcon>(1024, Allocator.Persistent);
		m_RootClusters = new NativeList<int>(8, Allocator.Persistent);
		m_FreeClusterIndices = new NativeList<int>(128, Allocator.Persistent);
		m_IconClusters.Add(default(IconCluster));
		m_ClusterIcons.ResizeUninitialized((int)m_IconAllocator.Size);
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
		if (m_IconClusters.IsCreated)
		{
			m_ClusterReadDeps.Complete();
			m_ClusterWriteDeps.Complete();
			m_ClusterTree.Dispose();
			m_IconAllocator.Dispose();
			m_IconClusters.Dispose();
			m_ClusterIcons.Dispose();
			m_RootClusters.Dispose();
			m_FreeClusterIndices.Dispose();
		}
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		bool loaded = GetLoaded();
		if (!(loaded ? m_IconQuery : m_ModifiedQuery).IsEmptyIgnoreFilter)
		{
			if (loaded)
			{
				ClearData();
			}
			NativeList<UnsafeHashSet<int>> orphans = new NativeList<UnsafeHashSet<int>>(64, Allocator.TempJob);
			NativeList<TempIconCluster> tempBuffer = new NativeList<TempIconCluster>(100, Allocator.TempJob);
			IconData iconData = new IconData
			{
				m_ClusterTree = m_ClusterTree,
				m_IconAllocator = m_IconAllocator,
				m_IconClusters = m_IconClusters,
				m_ClusterIcons = m_ClusterIcons,
				m_RootClusters = m_RootClusters,
				m_FreeClusterIndices = m_FreeClusterIndices
			};
			JobHandle outJobHandle;
			IconChunkJob jobData = new IconChunkJob
			{
				m_Chunks = (loaded ? m_IconQuery : m_ModifiedAndTempQuery).ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle),
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_DeletedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_DisallowClusterType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Notifications_DisallowCluster_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_AnimationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Notifications_Animation_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_IconDisplayData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NotificationIconDisplayData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_MovingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Moving_RO_ComponentLookup, ref base.CheckedStateRef),
				m_IconType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Notifications_Icon_RW_ComponentTypeHandle, ref base.CheckedStateRef),
				m_IconData = iconData,
				m_Orphans = orphans,
				m_TempBuffer = tempBuffer
			};
			IconClusterJob jobData2 = new IconClusterJob
			{
				m_IconData = iconData,
				m_Orphans = orphans,
				m_TempBuffer = tempBuffer
			};
			JobHandle jobHandle = IJobExtensions.Schedule(jobData, JobHandle.CombineDependencies(outJobHandle, m_ClusterReadDeps, m_ClusterWriteDeps));
			JobHandle jobHandle2 = IJobExtensions.Schedule(jobData2, jobHandle);
			jobData.m_Chunks.Dispose(jobHandle);
			orphans.Dispose(jobHandle2);
			tempBuffer.Dispose(jobHandle2);
			m_ClusterWriteDeps = jobHandle2;
			m_ClusterReadDeps = default(JobHandle);
			base.Dependency = jobHandle;
		}
	}
```

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PreDeserialize(Context context)
	{
		ClearData();
		m_Loaded = true;
	}
```

- `public RecalculateClusters() : System.Void`  

```csharp
public void RecalculateClusters()
	{
		m_Loaded = true;
	}
```


## Nested types

- `Game.Notifications.IconClusterSystem+ClusterData`  
- `Game.Notifications.IconClusterSystem+IconCluster`  
- `Game.Notifications.IconClusterSystem+ClusterIcon`  
- `Game.Notifications.IconClusterSystem+TempIconCluster`  
- `Game.Notifications.IconClusterSystem+TreeBounds`  
- `Game.Notifications.IconClusterSystem+IconChunkJob`  
- `Game.Notifications.IconClusterSystem+IconClusterJob`  
- `Game.Notifications.IconClusterSystem+IconData`  
- `Game.Notifications.IconClusterSystem+TypeHandle`  

