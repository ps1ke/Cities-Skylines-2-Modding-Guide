# Game.Buildings.ParkInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ParkInitializeSystem : Game.GameSystemBase
{
    private Game.Simulation.CitySystem m_CitySystem;
    private Unity.Entities.EntityQuery m_ParkQuery;
    private Game.Buildings.ParkInitializeSystem+TypeHandle __TypeHandle;

    public ParkInitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Unity.Entities.EntityQuery m_ParkQuery`  

```csharp
private Unity.Entities.EntityQuery m_ParkQuery;
```

- `private Game.Buildings.ParkInitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Buildings.ParkInitializeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ParkInitializeSystem()`  

```csharp
[Preserve]
	public ParkInitializeSystem()
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
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_ParkQuery = GetEntityQuery(ComponentType.ReadWrite<Park>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.ReadOnly<Created>());
		RequireForUpdate(m_ParkQuery);
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
		JobHandle dependency = JobChunkExtensions.ScheduleParallel(new InitializeParksJob
		{
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ParkType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Park_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ModifiedServiceCoverageType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_ModifiedServiceCoverage_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ParkData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ParkData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CoverageData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_CoverageData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CityModifiers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_CityModifier_RO_BufferLookup, ref base.CheckedStateRef),
			m_City = m_CitySystem.City
		}, m_ParkQuery, base.Dependency);
		base.Dependency = dependency;
	}
```


## Nested types

- `Game.Buildings.ParkInitializeSystem+InitializeParksJob`  
- `Game.Buildings.ParkInitializeSystem+TypeHandle`  

