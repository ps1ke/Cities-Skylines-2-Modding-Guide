# Game.Rendering.InitializeBonesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class InitializeBonesSystem : Game.GameSystemBase
{
    private Game.Rendering.ProceduralSkeletonSystem m_ProceduralSkeletonSystem;
    private Game.Rendering.PreCullingSystem m_PreCullingSystem;
    private Game.Rendering.InitializeBonesSystem+TypeHandle __TypeHandle;

    public InitializeBonesSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Rendering.ProceduralSkeletonSystem m_ProceduralSkeletonSystem`  

```csharp
private Game.Rendering.ProceduralSkeletonSystem m_ProceduralSkeletonSystem;
```

- `private Game.Rendering.PreCullingSystem m_PreCullingSystem`  

```csharp
private Game.Rendering.PreCullingSystem m_PreCullingSystem;
```

- `private Game.Rendering.InitializeBonesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.InitializeBonesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public InitializeBonesSystem()`  

```csharp
[Preserve]
	public InitializeBonesSystem()
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

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ProceduralSkeletonSystem = base.World.GetOrCreateSystemManaged<ProceduralSkeletonSystem>();
		m_PreCullingSystem = base.World.GetOrCreateSystemManaged<PreCullingSystem>();
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

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		NativeReference<ProceduralSkeletonSystem.AllocationInfo> allocationInfo;
		NativeQueue<ProceduralSkeletonSystem.AllocationRemove> allocationRemoves;
		int currentTime;
		JobHandle dependencies;
		NativeHeapAllocator heapAllocator = m_ProceduralSkeletonSystem.GetHeapAllocator(out allocationInfo, out allocationRemoves, out currentTime, out dependencies);
		JobHandle dependencies2;
		JobHandle jobHandle = IJobExtensions.Schedule(new InitializeBonesJob
		{
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ProceduralBones = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_ProceduralBone_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubMeshes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubMesh_RO_BufferLookup, ref base.CheckedStateRef),
			m_Skeletons = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_Skeleton_RW_BufferLookup, ref base.CheckedStateRef),
			m_Bones = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_Bone_RW_BufferLookup, ref base.CheckedStateRef),
			m_Momentums = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_Momentum_RW_BufferLookup, ref base.CheckedStateRef),
			m_CurrentTime = currentTime,
			m_CullingData = m_PreCullingSystem.GetUpdatedData(readOnly: true, out dependencies2),
			m_HeapAllocator = heapAllocator,
			m_AllocationInfo = allocationInfo,
			m_AllocationRemoves = allocationRemoves
		}, JobHandle.CombineDependencies(base.Dependency, dependencies2, dependencies));
		m_ProceduralSkeletonSystem.AddHeapWriter(jobHandle);
		m_PreCullingSystem.AddCullingDataReader(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Rendering.InitializeBonesSystem+InitializeBonesJob`  
- `Game.Rendering.InitializeBonesSystem+TypeHandle`  

