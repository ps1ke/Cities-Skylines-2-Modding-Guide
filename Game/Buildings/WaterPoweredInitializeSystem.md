# Game.Buildings.WaterPoweredInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WaterPoweredInitializeSystem : Game.GameSystemBase
{
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Unity.Entities.EntityQuery m_WaterPoweredQuery;
    private Game.Buildings.WaterPoweredInitializeSystem+TypeHandle __TypeHandle;

    public WaterPoweredInitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Unity.Entities.EntityQuery m_WaterPoweredQuery`  

```csharp
private Unity.Entities.EntityQuery m_WaterPoweredQuery;
```

- `private Game.Buildings.WaterPoweredInitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Buildings.WaterPoweredInitializeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public WaterPoweredInitializeSystem()`  

```csharp
[Preserve]
	public WaterPoweredInitializeSystem()
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
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_WaterSystem = base.World.GetOrCreateSystemManaged<WaterSystem>();
		m_WaterPoweredQuery = GetEntityQuery(ComponentType.ReadOnly<Updated>(), ComponentType.ReadOnly<WaterPowered>(), ComponentType.Exclude<ServiceUpgrade>(), ComponentType.Exclude<Deleted>());
		RequireForUpdate(m_WaterPoweredQuery);
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
		JobHandle deps;
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new WaterPoweredInitializeJob
		{
			m_CreatedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Created_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_SubnetType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_SubNet_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_WaterPoweredType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_WaterPowered_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CompositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Composition_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PlaceableNetData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PlaceableNetData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NetCompositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetCompositionData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TerrainCompositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TerrainComposition_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TerrainHeightData = m_TerrainSystem.GetHeightData(),
			m_WaterSurfaceData = m_WaterSystem.GetVelocitiesSurfaceData(out deps)
		}, m_WaterPoweredQuery, JobHandle.CombineDependencies(base.Dependency, deps));
		m_TerrainSystem.AddCPUHeightReader(jobHandle);
		m_WaterSystem.AddSurfaceReader(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Buildings.WaterPoweredInitializeSystem+WaterPoweredInitializeJob`  
- `Game.Buildings.WaterPoweredInitializeSystem+TypeHandle`  

