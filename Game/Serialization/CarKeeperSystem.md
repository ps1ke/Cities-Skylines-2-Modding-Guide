# Game.Serialization.CarKeeperSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CarKeeperSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_Query;
    private Unity.Entities.EntityQuery m_KeeperQuery;
    private Game.Serialization.CarKeeperSystem+TypeHandle __TypeHandle;

    public CarKeeperSystem();

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

- `private Unity.Entities.EntityQuery m_KeeperQuery`  

```csharp
private Unity.Entities.EntityQuery m_KeeperQuery;
```

- `private Game.Serialization.CarKeeperSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Serialization.CarKeeperSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CarKeeperSystem()`  

```csharp
[Preserve]
	public CarKeeperSystem()
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
		m_Query = GetEntityQuery(ComponentType.ReadOnly<PersonalCar>());
		m_KeeperQuery = GetEntityQuery(ComponentType.ReadOnly<CarKeeper>());
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
		JobHandle dependsOn = JobChunkExtensions.Schedule(new CarKeeperJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_PersonalCarType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_PersonalCar_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CarKeeperData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_CarKeeper_RW_ComponentLookup, ref base.CheckedStateRef)
		}, m_Query, base.Dependency);
		NoCarJob jobData = new NoCarJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_CarKeeperType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_CarKeeper_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PersonalCars = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_PersonalCar_RO_ComponentLookup, ref base.CheckedStateRef)
		};
		base.Dependency = JobChunkExtensions.Schedule(jobData, m_KeeperQuery, dependsOn);
	}
```


## Nested types

- `Game.Serialization.CarKeeperSystem+CarKeeperJob`  
- `Game.Serialization.CarKeeperSystem+NoCarJob`  
- `Game.Serialization.CarKeeperSystem+TypeHandle`  

