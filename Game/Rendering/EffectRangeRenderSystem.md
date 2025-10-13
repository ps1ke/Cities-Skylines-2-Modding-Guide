# Game.Rendering.EffectRangeRenderSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class EffectRangeRenderSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_ProviderQuery;
    private Unity.Entities.EntityQuery m_InfomodeQuery;
    private Game.Rendering.OverlayRenderSystem m_OverlayRenderSystem;
    private Game.Rendering.EffectRangeRenderSystem+TypeHandle __TypeHandle;

    public EffectRangeRenderSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_ProviderQuery`  

```csharp
private Unity.Entities.EntityQuery m_ProviderQuery;
```

- `private Unity.Entities.EntityQuery m_InfomodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_InfomodeQuery;
```

- `private Game.Rendering.OverlayRenderSystem m_OverlayRenderSystem`  

```csharp
private Game.Rendering.OverlayRenderSystem m_OverlayRenderSystem;
```

- `private Game.Rendering.EffectRangeRenderSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.EffectRangeRenderSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public EffectRangeRenderSystem()`  

```csharp
[Preserve]
	public EffectRangeRenderSystem()
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
		m_OverlayRenderSystem = base.World.GetOrCreateSystemManaged<OverlayRenderSystem>();
		m_ProviderQuery = GetEntityQuery(ComponentType.ReadOnly<LocalEffectProvider>(), ComponentType.Exclude<Hidden>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Destroyed>());
		m_InfomodeQuery = GetEntityQuery(ComponentType.ReadOnly<InfomodeActive>(), ComponentType.ReadOnly<InfoviewLocalEffectData>());
		RequireForUpdate(m_ProviderQuery);
		RequireForUpdate(m_InfomodeQuery);
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
		JobHandle outJobHandle;
		NativeList<ArchetypeChunk> infomodeChunks = m_InfomodeQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle);
		JobHandle dependencies;
		JobHandle jobHandle = JobChunkExtensions.Schedule(new EffectRangeRenderJob
		{
			m_InfomodeChunks = infomodeChunks,
			m_OverlayBuffer = m_OverlayRenderSystem.GetBuffer(out dependencies),
			m_BuildingEfficiencyType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_Efficiency_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_FirewatchTowerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_FirewatchTower_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_InfoviewLocalEffectType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_InfoviewLocalEffectData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_InstalledUpgradeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_FirewatchTowerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_FirewatchTower_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Efficiencies = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_Efficiency_RO_BufferLookup, ref base.CheckedStateRef),
			m_LocalModifierData = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_LocalModifierData_RO_BufferLookup, ref base.CheckedStateRef)
		}, m_ProviderQuery, JobHandle.CombineDependencies(base.Dependency, outJobHandle, dependencies));
		infomodeChunks.Dispose(jobHandle);
		m_OverlayRenderSystem.AddBufferWriter(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Rendering.EffectRangeRenderSystem+EffectRangeRenderJob`  
- `Game.Rendering.EffectRangeRenderSystem+TypeHandle`  

