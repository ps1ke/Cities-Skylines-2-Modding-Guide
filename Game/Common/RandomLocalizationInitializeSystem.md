# Game.Common.RandomLocalizationInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Common`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class RandomLocalizationInitializeSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_CreatedQuery;
    private Game.Common.RandomLocalizationInitializeSystem+TypeHandle __TypeHandle;

    public RandomLocalizationInitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_CreatedQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedQuery;
```

- `private Game.Common.RandomLocalizationInitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Common.RandomLocalizationInitializeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public RandomLocalizationInitializeSystem()`  

```csharp
[Preserve]
	public RandomLocalizationInitializeSystem()
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
		m_CreatedQuery = GetEntityQuery(ComponentType.ReadOnly<Created>(), ComponentType.ReadWrite<RandomLocalizationIndex>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Game.Objects.OutsideConnection>());
		RequireForUpdate(m_CreatedQuery);
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
		InitializeLocalizationJob jobData = new InitializeLocalizationJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_RandomLocalizationIndexType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Common_RandomLocalizationIndex_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_LocalizationCounts = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_LocalizationCount_RO_BufferLookup, ref base.CheckedStateRef),
			m_SpawnableBuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnableBuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RandomSeed = RandomSeed.Next()
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_CreatedQuery, base.Dependency);
	}
```


## Nested types

- `Game.Common.RandomLocalizationInitializeSystem+InitializeLocalizationJob`  
- `Game.Common.RandomLocalizationInitializeSystem+TypeHandle`  

