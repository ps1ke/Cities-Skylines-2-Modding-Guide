# Game.Serialization.DataMigration.TradeCostFixSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization.DataMigration`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TradeCostFixSystem : Game.GameSystemBase
{
    private Game.Serialization.LoadGameSystem m_LoadGameSystem;
    private Game.Simulation.TradeSystem m_TradeSystem;
    private Unity.Entities.EntityQuery m_TradeCostQuery;
    private Game.Serialization.DataMigration.TradeCostFixSystem+TypeHandle __TypeHandle;

    public TradeCostFixSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Serialization.LoadGameSystem m_LoadGameSystem`  

```csharp
private Game.Serialization.LoadGameSystem m_LoadGameSystem;
```

- `private Game.Simulation.TradeSystem m_TradeSystem`  

```csharp
private Game.Simulation.TradeSystem m_TradeSystem;
```

- `private Unity.Entities.EntityQuery m_TradeCostQuery`  

```csharp
private Unity.Entities.EntityQuery m_TradeCostQuery;
```

- `private Game.Serialization.DataMigration.TradeCostFixSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Serialization.DataMigration.TradeCostFixSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TradeCostFixSystem()`  

```csharp
[Preserve]
	public TradeCostFixSystem()
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
		m_LoadGameSystem = base.World.GetOrCreateSystemManaged<LoadGameSystem>();
		m_TradeSystem = base.World.GetOrCreateSystemManaged<TradeSystem>();
		m_TradeCostQuery = GetEntityQuery(ComponentType.ReadOnly<TradeCost>(), ComponentType.Exclude<Created>(), ComponentType.Exclude<Deleted>());
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
		if (!m_LoadGameSystem.context.format.Has(FormatTags.TradeCostFix))
		{
			if (!m_TradeCostQuery.IsEmptyIgnoreFilter)
			{
				TradeCostFixJob jobData = new TradeCostFixJob
				{
					m_TradeCostBufType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Companies_TradeCost_RW_BufferTypeHandle, ref base.CheckedStateRef),
					m_ResourcesBufType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Economy_Resources_RW_BufferTypeHandle, ref base.CheckedStateRef),
					m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_StorageLimitDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_StorageLimitData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_StorageCompanyDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_StorageCompanyData_RO_ComponentLookup, ref base.CheckedStateRef)
				};
				base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_TradeCostQuery, base.Dependency);
			}
			m_TradeSystem.SetDefaults();
		}
	}
```


## Nested types

- `Game.Serialization.DataMigration.TradeCostFixSystem+TradeCostFixJob`  
- `Game.Serialization.DataMigration.TradeCostFixSystem+TypeHandle`  

