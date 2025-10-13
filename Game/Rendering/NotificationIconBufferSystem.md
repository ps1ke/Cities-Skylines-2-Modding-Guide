# Game.Rendering.NotificationIconBufferSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class NotificationIconBufferSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_IconQuery;
    private Unity.Entities.EntityQuery m_ConfigurationQuery;
    private Game.Notifications.IconClusterSystem m_IconClusterSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Unity.Collections.NativeList<Game.Rendering.NotificationIconBufferSystem+InstanceData> m_InstanceData;
    private Colossal.Collections.NativeValue<Colossal.Mathematics.Bounds3> m_IconBounds;
    private Unity.Jobs.JobHandle m_InstanceDataDeps;
    private Game.Rendering.NotificationIconBufferSystem+TypeHandle __TypeHandle;

    public NotificationIconBufferSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public Game.Rendering.NotificationIconBufferSystem+IconData GetIconData();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_IconQuery`  

```csharp
private Unity.Entities.EntityQuery m_IconQuery;
```

- `private Unity.Entities.EntityQuery m_ConfigurationQuery`  

```csharp
private Unity.Entities.EntityQuery m_ConfigurationQuery;
```

- `private Game.Notifications.IconClusterSystem m_IconClusterSystem`  

```csharp
private Game.Notifications.IconClusterSystem m_IconClusterSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Unity.Collections.NativeList<Game.Rendering.NotificationIconBufferSystem+InstanceData> m_InstanceData`  

```csharp
private Unity.Collections.NativeList<Game.Rendering.NotificationIconBufferSystem+InstanceData> m_InstanceData;
```

- `private Colossal.Collections.NativeValue<Colossal.Mathematics.Bounds3> m_IconBounds`  

```csharp
private Colossal.Collections.NativeValue<Colossal.Mathematics.Bounds3> m_IconBounds;
```

- `private Unity.Jobs.JobHandle m_InstanceDataDeps`  

```csharp
private Unity.Jobs.JobHandle m_InstanceDataDeps;
```

- `private Game.Rendering.NotificationIconBufferSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.NotificationIconBufferSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public NotificationIconBufferSystem()`  

```csharp
[Preserve]
	public NotificationIconBufferSystem()
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

- `public GetIconData() : Game.Rendering.NotificationIconBufferSystem+IconData`  

```csharp
public IconData GetIconData()
	{
		m_InstanceDataDeps.Complete();
		m_InstanceDataDeps = default(JobHandle);
		if (m_InstanceData.IsCreated)
		{
			return new IconData
			{
				m_InstanceData = m_InstanceData.AsArray(),
				m_IconBounds = m_IconBounds
			};
		}
		return default(IconData);
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_IconClusterSystem = base.World.GetOrCreateSystemManaged<IconClusterSystem>();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_IconQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Icon>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<DisallowCluster>(),
				ComponentType.ReadOnly<Game.Notifications.Animation>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Hidden>()
			}
		});
		m_ConfigurationQuery = GetEntityQuery(ComponentType.ReadOnly<IconConfigurationData>());
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
		if (m_InstanceData.IsCreated)
		{
			m_InstanceDataDeps.Complete();
			m_InstanceData.Dispose();
			m_IconBounds.Dispose();
		}
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		Camera main = Camera.main;
		if (!(main == null) && !m_ConfigurationQuery.IsEmptyIgnoreFilter)
		{
			if (!m_InstanceData.IsCreated)
			{
				m_InstanceData = new NativeList<InstanceData>(64, Allocator.Persistent);
				m_IconBounds = new NativeValue<Bounds3>(Allocator.Persistent);
			}
			UnityEngine.Transform transform = main.transform;
			uint categoryMask = uint.MaxValue;
			if (m_ToolSystem.activeInfoview != null)
			{
				categoryMask = m_PrefabSystem.GetComponentData<InfoviewData>(m_ToolSystem.activeInfoview).m_NotificationMask;
				categoryMask |= 0x80000000u;
			}
			m_InstanceDataDeps.Complete();
			JobHandle outJobHandle;
			NativeList<ArchetypeChunk> chunks = m_IconQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle);
			JobHandle dependencies;
			NotificationIconBufferJob jobData = new NotificationIconBufferJob
			{
				m_IconType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Notifications_Icon_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_AnimationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Notifications_Animation_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_HiddenType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Hidden_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_IconDisplayData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NotificationIconDisplayData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
				m_DeletedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentLookup, ref base.CheckedStateRef),
				m_IconData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Notifications_Icon_RO_ComponentLookup, ref base.CheckedStateRef),
				m_AnimationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Notifications_Animation_RO_ComponentLookup, ref base.CheckedStateRef),
				m_DisallowClusterData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Notifications_DisallowCluster_RO_ComponentLookup, ref base.CheckedStateRef),
				m_HiddenData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Hidden_RO_ComponentLookup, ref base.CheckedStateRef),
				m_InterpolatedTransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Rendering_InterpolatedTransform_RO_ComponentLookup, ref base.CheckedStateRef),
				m_IconAnimations = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_IconAnimationElement_RO_BufferLookup, ref base.CheckedStateRef),
				m_Chunks = chunks,
				m_CameraPosition = transform.position,
				m_CameraUp = transform.up,
				m_CameraRight = transform.right,
				m_ConfigurationEntity = m_ConfigurationQuery.GetSingletonEntity(),
				m_CategoryMask = categoryMask,
				m_ClusterData = m_IconClusterSystem.GetIconClusterData(readOnly: false, out dependencies),
				m_InstanceData = m_InstanceData,
				m_IconBounds = m_IconBounds
			};
			NotificationIconSortJob jobData2 = new NotificationIconSortJob
			{
				m_InstanceData = m_InstanceData
			};
			JobHandle jobHandle = IJobExtensions.Schedule(jobData, JobHandle.CombineDependencies(base.Dependency, outJobHandle, dependencies));
			JobHandle instanceDataDeps = IJobExtensions.Schedule(jobData2, jobHandle);
			chunks.Dispose(jobHandle);
			m_IconClusterSystem.AddIconClusterWriter(jobHandle);
			m_InstanceDataDeps = instanceDataDeps;
			base.Dependency = jobHandle;
		}
	}
```


## Nested types

- `Game.Rendering.NotificationIconBufferSystem+IconData`  
- `Game.Rendering.NotificationIconBufferSystem+InstanceData`  
- `Game.Rendering.NotificationIconBufferSystem+HiddenPositionData`  
- `Game.Rendering.NotificationIconBufferSystem+NotificationIconBufferJob`  
- `Game.Rendering.NotificationIconBufferSystem+NotificationIconSortJob`  
- `Game.Rendering.NotificationIconBufferSystem+TypeHandle`  

