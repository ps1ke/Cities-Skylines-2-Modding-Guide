# Game.Areas.ServiceDistrictSystem

**Assembly:** `Game`  
**Namespace:** `Game.Areas`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ServiceDistrictSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_DeletedDistrictQuery;
    private Unity.Entities.EntityQuery m_ServiceDistrictQuery;
    private Game.Areas.ServiceDistrictSystem+TypeHandle __TypeHandle;

    public ServiceDistrictSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_DeletedDistrictQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeletedDistrictQuery;
```

- `private Unity.Entities.EntityQuery m_ServiceDistrictQuery`  

```csharp
private Unity.Entities.EntityQuery m_ServiceDistrictQuery;
```

- `private Game.Areas.ServiceDistrictSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Areas.ServiceDistrictSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ServiceDistrictSystem()`  

```csharp
[Preserve]
	public ServiceDistrictSystem()
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
		m_DeletedDistrictQuery = GetEntityQuery(ComponentType.ReadOnly<Deleted>(), ComponentType.ReadOnly<District>(), ComponentType.Exclude<Temp>());
		m_ServiceDistrictQuery = GetEntityQuery(ComponentType.ReadOnly<ServiceDistrict>(), ComponentType.Exclude<Deleted>());
		RequireForUpdate(m_DeletedDistrictQuery);
		RequireForUpdate(m_ServiceDistrictQuery);
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
		NativeList<Entity> deletedDistricts = m_DeletedDistrictQuery.ToEntityListAsync(Allocator.TempJob, out outJobHandle);
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new RemoveServiceDistrictsJob
		{
			m_DeletedDistricts = deletedDistricts,
			m_ServiceDistrictType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Areas_ServiceDistrict_RW_BufferTypeHandle, ref base.CheckedStateRef)
		}, m_ServiceDistrictQuery, JobHandle.CombineDependencies(base.Dependency, outJobHandle));
		deletedDistricts.Dispose(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Areas.ServiceDistrictSystem+RemoveServiceDistrictsJob`  
- `Game.Areas.ServiceDistrictSystem+TypeHandle`  

