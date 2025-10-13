# Game.Rendering.InitializeLightsSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class InitializeLightsSystem : Game.GameSystemBase
{
    private Game.Rendering.ProceduralEmissiveSystem m_ProceduralEmissiveSystem;
    private Game.Rendering.PreCullingSystem m_PreCullingSystem;
    private Game.Rendering.InitializeLightsSystem+TypeHandle __TypeHandle;

    public InitializeLightsSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Rendering.ProceduralEmissiveSystem m_ProceduralEmissiveSystem`  

```csharp
private Game.Rendering.ProceduralEmissiveSystem m_ProceduralEmissiveSystem;
```

- `private Game.Rendering.PreCullingSystem m_PreCullingSystem`  

```csharp
private Game.Rendering.PreCullingSystem m_PreCullingSystem;
```

- `private Game.Rendering.InitializeLightsSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.InitializeLightsSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public InitializeLightsSystem()`  

```csharp
[Preserve]
	public InitializeLightsSystem()
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
		m_ProceduralEmissiveSystem = base.World.GetOrCreateSystemManaged<ProceduralEmissiveSystem>();
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
		NativeReference<ProceduralEmissiveSystem.AllocationInfo> allocationInfo;
		NativeQueue<ProceduralEmissiveSystem.AllocationRemove> allocationRemoves;
		int currentTime;
		JobHandle dependencies;
		NativeHeapAllocator heapAllocator = m_ProceduralEmissiveSystem.GetHeapAllocator(out allocationInfo, out allocationRemoves, out currentTime, out dependencies);
		JobHandle dependencies2;
		JobHandle jobHandle = IJobExtensions.Schedule(new ProceduralInitializeJob
		{
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ProceduralLights = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_ProceduralLight_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubMeshes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubMesh_RO_BufferLookup, ref base.CheckedStateRef),
			m_Emissives = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_Emissive_RW_BufferLookup, ref base.CheckedStateRef),
			m_Lights = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_LightState_RW_BufferLookup, ref base.CheckedStateRef),
			m_CurrentTime = currentTime,
			m_CullingData = m_PreCullingSystem.GetUpdatedData(readOnly: true, out dependencies2),
			m_HeapAllocator = heapAllocator,
			m_AllocationInfo = allocationInfo,
			m_AllocationRemoves = allocationRemoves
		}, JobHandle.CombineDependencies(base.Dependency, dependencies2, dependencies));
		m_ProceduralEmissiveSystem.AddHeapWriter(jobHandle);
		m_PreCullingSystem.AddCullingDataReader(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Rendering.InitializeLightsSystem+ProceduralInitializeJob`  
- `Game.Rendering.InitializeLightsSystem+TypeHandle`  

