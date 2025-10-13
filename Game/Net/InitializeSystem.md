# Game.Net.InitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class InitializeSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_CreatedEdgesQuery;
    private Game.Net.InitializeSystem+TypeHandle __TypeHandle;

    public InitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_CreatedEdgesQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedEdgesQuery;
```

- `private Game.Net.InitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Net.InitializeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public InitializeSystem()`  

```csharp
[Preserve]
	public InitializeSystem()
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
		m_CreatedEdgesQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Created>() },
			Any = new ComponentType[3]
			{
				ComponentType.ReadWrite<ServiceCoverage>(),
				ComponentType.ReadWrite<ResourceAvailability>(),
				ComponentType.ReadWrite<WaterPipeConnection>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		});
		RequireForUpdate(m_CreatedEdgesQuery);
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
		InitializeEdgesJob jobData = new InitializeEdgesJob
		{
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WaterPipeConnectionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_WaterPipeConnectionData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ServiceCoverageType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_ServiceCoverage_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_ResourceAvailabilityType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_ResourceAvailability_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_WaterPipeConnectionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_WaterPipeConnection_RW_ComponentTypeHandle, ref base.CheckedStateRef)
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_CreatedEdgesQuery, base.Dependency);
	}
```


## Nested types

- `Game.Net.InitializeSystem+InitializeEdgesJob`  
- `Game.Net.InitializeSystem+TypeHandle`  

