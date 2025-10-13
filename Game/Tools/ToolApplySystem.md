# Game.Tools.ToolApplySystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ToolApplySystem : Game.GameSystemBase
{
    private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
    private Game.Simulation.CitySystem m_CitySystem;
    private Unity.Entities.EntityQuery m_ApplyQuery;
    private Game.Tools.ToolApplySystem+TypeHandle __TypeHandle;

    public ToolApplySystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier`  

```csharp
private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Unity.Entities.EntityQuery m_ApplyQuery`  

```csharp
private Unity.Entities.EntityQuery m_ApplyQuery;
```

- `private Game.Tools.ToolApplySystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.ToolApplySystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ToolApplySystem()`  

```csharp
[Preserve]
	public ToolApplySystem()
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
		m_ToolOutputBarrier = base.World.GetOrCreateSystemManaged<ToolOutputBarrier>();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_ApplyQuery = GetEntityQuery(new EntityQueryDesc
		{
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Temp>(),
				ComponentType.ReadOnly<Warning>(),
				ComponentType.ReadOnly<Override>()
			}
		});
		RequireForUpdate(m_ApplyQuery);
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
		NativeList<ArchetypeChunk> chunks = m_ApplyQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle);
		JobHandle jobHandle = IJobExtensions.Schedule(new ApplyEntitiesJob
		{
			m_Chunks = chunks,
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WarningType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Warning_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_OverrideType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Override_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_City = m_CitySystem.City,
			m_PlayerMoney = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_City_PlayerMoney_RW_ComponentLookup, ref base.CheckedStateRef),
			m_CommandBuffer = m_ToolOutputBarrier.CreateCommandBuffer()
		}, JobHandle.CombineDependencies(base.Dependency, outJobHandle));
		chunks.Dispose(jobHandle);
		m_ToolOutputBarrier.AddJobHandleForProducer(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Tools.ToolApplySystem+ApplyEntitiesJob`  
- `Game.Tools.ToolApplySystem+TypeHandle`  

