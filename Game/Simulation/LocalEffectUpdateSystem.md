# Game.Simulation.LocalEffectUpdateSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LocalEffectUpdateSystem : Game.GameSystemBase
{
    private Game.Buildings.LocalEffectSystem m_LocalEffectSystem;
    private Unity.Entities.EntityQuery m_EffectProviderQuery;
    private Game.Simulation.LocalEffectUpdateSystem+TypeHandle __TypeHandle;

    public LocalEffectUpdateSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Buildings.LocalEffectSystem m_LocalEffectSystem`  

```csharp
private Game.Buildings.LocalEffectSystem m_LocalEffectSystem;
```

- `private Unity.Entities.EntityQuery m_EffectProviderQuery`  

```csharp
private Unity.Entities.EntityQuery m_EffectProviderQuery;
```

- `private Game.Simulation.LocalEffectUpdateSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.LocalEffectUpdateSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public LocalEffectUpdateSystem()`  

```csharp
[Preserve]
	public LocalEffectUpdateSystem()
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

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 256;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_LocalEffectSystem = base.World.GetOrCreateSystemManaged<LocalEffectSystem>();
		m_EffectProviderQuery = GetEntityQuery(ComponentType.ReadOnly<LocalEffectProvider>(), ComponentType.ReadOnly<Efficiency>(), ComponentType.Exclude<Signature>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Destroyed>(), ComponentType.Exclude<Temp>());
		RequireForUpdate(m_EffectProviderQuery);
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
		JobHandle jobHandle = JobChunkExtensions.Schedule(new UpdateLocalEffectsJob
		{
			m_SearchTree = m_LocalEffectSystem.GetSearchTree(readOnly: false, out dependencies),
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_BuildingEfficiencyType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_Efficiency_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_InstalledUpgradeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LocalModifierData = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_LocalModifierData_RO_BufferLookup, ref base.CheckedStateRef)
		}, m_EffectProviderQuery, JobHandle.CombineDependencies(base.Dependency, dependencies));
		m_LocalEffectSystem.AddLocalEffectWriter(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Simulation.LocalEffectUpdateSystem+UpdateLocalEffectsJob`  
- `Game.Simulation.LocalEffectUpdateSystem+TypeHandle`  

