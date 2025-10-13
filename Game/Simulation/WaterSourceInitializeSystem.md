# Game.Simulation.WaterSourceInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WaterSourceInitializeSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_WaterSourceQuery;
    private Game.Simulation.WaterSourceInitializeSystem+TypeHandle __TypeHandle;

    public WaterSourceInitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_WaterSourceQuery`  

```csharp
private Unity.Entities.EntityQuery m_WaterSourceQuery;
```

- `private Game.Simulation.WaterSourceInitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.WaterSourceInitializeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public WaterSourceInitializeSystem()`  

```csharp
[Preserve]
	public WaterSourceInitializeSystem()
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
		m_WaterSourceQuery = GetEntityQuery(ComponentType.ReadOnly<WaterSourceData>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.ReadOnly<Created>(), ComponentType.Exclude<Temp>());
		RequireForUpdate(m_WaterSourceQuery);
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
		InitializeWaterSourcesJob jobData = new InitializeWaterSourcesJob
		{
			m_SourceType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Simulation_WaterSourceData_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabSourceDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_WaterSourceData_RO_ComponentLookup, ref base.CheckedStateRef)
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_WaterSourceQuery, base.Dependency);
	}
```


## Nested types

- `Game.Simulation.WaterSourceInitializeSystem+InitializeWaterSourcesJob`  
- `Game.Simulation.WaterSourceInitializeSystem+TypeHandle`  

