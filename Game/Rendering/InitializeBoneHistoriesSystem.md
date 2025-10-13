# Game.Rendering.InitializeBoneHistoriesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class InitializeBoneHistoriesSystem : Game.GameSystemBase
{
    private Game.Rendering.PreCullingSystem m_PreCullingSystem;
    private Game.Rendering.InitializeBoneHistoriesSystem+TypeHandle __TypeHandle;

    public InitializeBoneHistoriesSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Rendering.PreCullingSystem m_PreCullingSystem`  

```csharp
private Game.Rendering.PreCullingSystem m_PreCullingSystem;
```

- `private Game.Rendering.InitializeBoneHistoriesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.InitializeBoneHistoriesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public InitializeBoneHistoriesSystem()`  

```csharp
[Preserve]
	public InitializeBoneHistoriesSystem()
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
		JobHandle dependencies;
		InitializeBoneHistoriesJob jobData = new InitializeBoneHistoriesJob
		{
			m_TempData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Skeletons = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_Skeleton_RO_BufferLookup, ref base.CheckedStateRef),
			m_Bones = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_Bone_RO_BufferLookup, ref base.CheckedStateRef),
			m_ProceduralBones = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_ProceduralBone_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubMeshes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubMesh_RO_BufferLookup, ref base.CheckedStateRef),
			m_BoneHistories = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_BoneHistory_RW_BufferLookup, ref base.CheckedStateRef),
			m_CullingData = m_PreCullingSystem.GetUpdatedData(readOnly: true, out dependencies)
		};
		JobHandle jobHandle = jobData.Schedule(jobData.m_CullingData, 4, JobHandle.CombineDependencies(base.Dependency, dependencies));
		m_PreCullingSystem.AddCullingDataReader(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Rendering.InitializeBoneHistoriesSystem+InitializeBoneHistoriesJob`  
- `Game.Rendering.InitializeBoneHistoriesSystem+TypeHandle`  

