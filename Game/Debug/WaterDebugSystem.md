# Game.Debug.WaterDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WaterDebugSystem : Game.Debug.BaseDebugSystem
{
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Colossal.GizmosSystem m_GizmosSystem;
    private Unity.Entities.EntityQuery m_WaterSourceGroup;
    private Game.Debug.BaseDebugSystem+Option m_ShowCulling;
    private Game.Debug.BaseDebugSystem+Option m_showSurface;
    private Game.Debug.WaterDebugSystem+TypeHandle __TypeHandle;

    public WaterDebugSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private Unity.Entities.EntityQuery m_WaterSourceGroup`  

```csharp
private Unity.Entities.EntityQuery m_WaterSourceGroup;
```

- `private Game.Debug.BaseDebugSystem+Option m_ShowCulling`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_ShowCulling;
```

- `private Game.Debug.BaseDebugSystem+Option m_showSurface`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_showSurface;
```

- `private Game.Debug.WaterDebugSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Debug.WaterDebugSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public WaterDebugSystem()`  

```csharp
[Preserve]
	public WaterDebugSystem()
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
		m_GizmosSystem = base.World.GetOrCreateSystemManaged<GizmosSystem>();
		m_WaterSystem = base.World.GetOrCreateSystemManaged<WaterSystem>();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_showSurface = AddOption("Show Surface Boxes", defaultEnabled: true);
		m_ShowCulling = AddOption("Show Culling Boxes", defaultEnabled: false);
		m_WaterSourceGroup = GetEntityQuery(ComponentType.ReadOnly<WaterSourceData>());
		base.Enabled = false;
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
		JobHandle deps;
		JobHandle dependencies;
		WaterGizmoJob jobData = new WaterGizmoJob
		{
			m_WaterSources = m_WaterSourceGroup.ToEntityListAsync(Allocator.TempJob, out outJobHandle),
			m_SourceDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_WaterSourceData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Transforms = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_WaterActive = m_WaterSystem.GetActive(),
			m_WaterDepths = m_WaterSystem.GetDepths(out deps),
			m_GizmoBatcher = m_GizmosSystem.GetGizmosBatcher(out dependencies),
			m_GridCellInMeters = (float)m_WaterSystem.GridSize * m_WaterSystem.CellSize,
			m_CellInMeters = m_WaterSystem.CellSize,
			m_MapSize = m_WaterSystem.MapSize,
			m_PositionOffset = m_TerrainSystem.positionOffset,
			m_ShowCulling = m_ShowCulling.enabled,
			m_showSurface = m_showSurface.enabled
		};
		base.Dependency = IJobExtensions.Schedule(jobData, JobUtils.CombineDependencies(base.Dependency, deps, dependencies, outJobHandle));
		jobData.m_WaterSources.Dispose(base.Dependency);
		m_WaterSystem.AddSurfaceReader(base.Dependency);
		m_WaterSystem.AddActiveReader(base.Dependency);
		m_GizmosSystem.AddGizmosBatcherWriter(base.Dependency);
	}
```


## Nested types

- `Game.Debug.WaterDebugSystem+WaterGizmoJob`  
- `Game.Debug.WaterDebugSystem+TypeHandle`  

