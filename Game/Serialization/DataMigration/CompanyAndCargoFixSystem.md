# Game.Serialization.DataMigration.CompanyAndCargoFixSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization.DataMigration`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CompanyAndCargoFixSystem : Game.GameSystemBase
{
    private Game.Serialization.LoadGameSystem m_LoadGameSystem;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Unity.Entities.EntityQuery m_ProfitabilityCompanyQuery;
    private Game.Serialization.DataMigration.CompanyAndCargoFixSystem+TypeHandle __TypeHandle;

    public CompanyAndCargoFixSystem();

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

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Unity.Entities.EntityQuery m_ProfitabilityCompanyQuery`  

```csharp
private Unity.Entities.EntityQuery m_ProfitabilityCompanyQuery;
```

- `private Game.Serialization.DataMigration.CompanyAndCargoFixSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Serialization.DataMigration.CompanyAndCargoFixSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CompanyAndCargoFixSystem()`  

```csharp
[Preserve]
	public CompanyAndCargoFixSystem()
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
		m_ResourceSystem = base.World.GetOrCreateSystemManaged<ResourceSystem>();
		m_ProfitabilityCompanyQuery = GetEntityQuery(ComponentType.ReadOnly<Profitability>(), ComponentType.Exclude<Created>(), ComponentType.Exclude<Deleted>());
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
		if (!m_LoadGameSystem.context.format.Has(FormatTags.CompanyAndCargoFix) && !m_ProfitabilityCompanyQuery.IsEmptyIgnoreFilter)
		{
			ProfitabilityFixJob jobData = new ProfitabilityFixJob
			{
				m_ProfitabilityType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Companies_Profitability_RW_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_ResourcesBufType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Economy_Resources_RW_BufferTypeHandle, ref base.CheckedStateRef),
				m_OwnedVehicleType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Vehicles_OwnedVehicle_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_ResourceDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ResourceData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_IndustrialProcessDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_IndustrialProcessData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_DeliveryTrucks = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_DeliveryTruck_RO_ComponentLookup, ref base.CheckedStateRef),
				m_LayoutElementBufs = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_LayoutElement_RO_BufferLookup, ref base.CheckedStateRef),
				m_ResourcePrefabs = m_ResourceSystem.GetPrefabs()
			};
			base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_ProfitabilityCompanyQuery, base.Dependency);
		}
	}
```


## Nested types

- `Game.Serialization.DataMigration.CompanyAndCargoFixSystem+ProfitabilityFixJob`  
- `Game.Serialization.DataMigration.CompanyAndCargoFixSystem+TypeHandle`  

