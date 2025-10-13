# Game.Serialization.ServiceCoverageSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ServiceCoverageSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_Query;
    private Game.Serialization.ServiceCoverageSystem+TypeHandle __TypeHandle;

    public ServiceCoverageSystem();

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

- `private Game.Serialization.ServiceCoverageSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Serialization.ServiceCoverageSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ServiceCoverageSystem()`  

```csharp
[Preserve]
	public ServiceCoverageSystem()
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
		m_Query = GetEntityQuery(ComponentType.ReadOnly<ServiceCoverage>());
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
		ServiceCoverageJob jobData = new ServiceCoverageJob
		{
			m_CoverageType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_ServiceCoverage_RW_BufferTypeHandle, ref base.CheckedStateRef)
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_Query, base.Dependency);
	}
```


## Nested types

- `Game.Serialization.ServiceCoverageSystem+ServiceCoverageJob`  
- `Game.Serialization.ServiceCoverageSystem+TypeHandle`  

