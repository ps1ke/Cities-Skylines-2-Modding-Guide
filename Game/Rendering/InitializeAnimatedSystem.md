# Game.Rendering.InitializeAnimatedSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class InitializeAnimatedSystem : Game.GameSystemBase
{
    private Game.Rendering.AnimatedSystem m_AnimatedSystem;
    private Game.Rendering.PreCullingSystem m_PreCullingSystem;
    private Game.Rendering.InitializeAnimatedSystem+TypeHandle __TypeHandle;

    public InitializeAnimatedSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Rendering.AnimatedSystem m_AnimatedSystem`  

```csharp
private Game.Rendering.AnimatedSystem m_AnimatedSystem;
```

- `private Game.Rendering.PreCullingSystem m_PreCullingSystem`  

```csharp
private Game.Rendering.PreCullingSystem m_PreCullingSystem;
```

- `private Game.Rendering.InitializeAnimatedSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.InitializeAnimatedSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public InitializeAnimatedSystem()`  

```csharp
[Preserve]
	public InitializeAnimatedSystem()
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
		m_AnimatedSystem = base.World.GetOrCreateSystemManaged<AnimatedSystem>();
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
		JobHandle dependencies2;
		JobHandle jobHandle = IJobExtensions.Schedule(new InitializeAnimatedJob
		{
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CharacterStyleData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_CharacterStyleData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_MeshGroups = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_MeshGroup_RO_BufferLookup, ref base.CheckedStateRef),
			m_MeshColors = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_MeshColor_RO_BufferLookup, ref base.CheckedStateRef),
			m_AnimationClips = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_AnimationClip_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubMeshes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubMesh_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubMeshGroups = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubMeshGroup_RO_BufferLookup, ref base.CheckedStateRef),
			m_CharacterElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_CharacterElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_OverlayElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_OverlayElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_Animateds = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_Animated_RW_BufferLookup, ref base.CheckedStateRef),
			m_CullingData = m_PreCullingSystem.GetUpdatedData(readOnly: true, out dependencies),
			m_AllocationData = m_AnimatedSystem.GetAllocationData(out dependencies2)
		}, JobHandle.CombineDependencies(base.Dependency, dependencies, dependencies2));
		m_AnimatedSystem.AddAllocationWriter(jobHandle);
		m_PreCullingSystem.AddCullingDataReader(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Rendering.InitializeAnimatedSystem+InitializeAnimatedJob`  
- `Game.Rendering.InitializeAnimatedSystem+OverlayIndex`  
- `Game.Rendering.InitializeAnimatedSystem+TypeHandle`  

