# Game.Serialization.RandomLocalizationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class RandomLocalizationSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_Query;
    private Game.Serialization.RandomLocalizationSystem+TypeHandle __TypeHandle;

    public RandomLocalizationSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_Query`  

```csharp
private Unity.Entities.EntityQuery m_Query;
```

- `private Game.Serialization.RandomLocalizationSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Serialization.RandomLocalizationSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public RandomLocalizationSystem()`  

```csharp
[Preserve]
	public RandomLocalizationSystem()
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
		m_Query = GetEntityQuery(ComponentType.ReadOnly<RandomLocalizationIndex>(), ComponentType.ReadOnly<PrefabRef>());
		RequireForUpdate(m_Query);
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
		EnsureLocalizationJob jobData = new EnsureLocalizationJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_RandomLocalizationType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Common_RandomLocalizationIndex_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_LocalizationCounts = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_LocalizationCount_RO_BufferLookup, ref base.CheckedStateRef),
			m_SpawnableBuildingDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnableBuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RandomSeed = RandomSeed.Next()
		};
		base.Dependency = JobChunkExtensions.Schedule(jobData, m_Query, base.Dependency);
	}
```


## Nested types

- `Game.Serialization.RandomLocalizationSystem+EnsureLocalizationJob`  
- `Game.Serialization.RandomLocalizationSystem+TypeHandle`  

