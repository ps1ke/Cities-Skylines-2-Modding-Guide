# Game.Debug.LandValueDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LandValueDebugSystem : Game.Debug.BaseDebugSystem
{
    private Game.Simulation.LandValueSystem m_LandValueSystem;
    private Colossal.GizmosSystem m_GizmosSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Tools.DefaultToolSystem m_DefaultToolSystem;
    private Unity.Entities.EntityQuery m_LandValueEdgeQuery;
    private Unity.Entities.EntityQuery m_LandValueParameterQuery;
    public Game.Debug.BaseDebugSystem+Option m_LandValueCellOption;
    private Game.Debug.BaseDebugSystem+Option m_EdgeLandValueOption;
    private Game.Debug.LandValueDebugSystem+TypeHandle __TypeHandle;
    private static readonly System.Single heightScale;

    public LandValueDebugSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private static UnityEngine.Color GetColor(UnityEngine.Color a, UnityEngine.Color b, UnityEngine.Color c, System.Single value, System.Single maxValue1, System.Single maxValue2);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    public virtual System.Void OnDisabled(UnityEngine.Rendering.DebugUI+Container container);
    public virtual System.Void OnEnabled(UnityEngine.Rendering.DebugUI+Container container);
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Game.Simulation.LandValueSystem m_LandValueSystem`  

```csharp
private Game.Simulation.LandValueSystem m_LandValueSystem;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Tools.DefaultToolSystem m_DefaultToolSystem`  

```csharp
private Game.Tools.DefaultToolSystem m_DefaultToolSystem;
```

- `private Unity.Entities.EntityQuery m_LandValueEdgeQuery`  

```csharp
private Unity.Entities.EntityQuery m_LandValueEdgeQuery;
```

- `private Unity.Entities.EntityQuery m_LandValueParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_LandValueParameterQuery;
```

- `public Game.Debug.BaseDebugSystem+Option m_LandValueCellOption`  

```csharp
public Game.Debug.BaseDebugSystem+Option m_LandValueCellOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_EdgeLandValueOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_EdgeLandValueOption;
```

- `private Game.Debug.LandValueDebugSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Debug.LandValueDebugSystem+TypeHandle __TypeHandle;
```

- `private static readonly System.Single heightScale`  

```csharp
private static readonly System.Single heightScale;
```


## Constructors

- `public LandValueDebugSystem()`  

```csharp
[Preserve]
	public LandValueDebugSystem()
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

- `private static GetColor(UnityEngine.Color a, UnityEngine.Color b, UnityEngine.Color c, System.Single value, System.Single maxValue1, System.Single maxValue2) : UnityEngine.Color`  

```csharp
private static Color GetColor(Color a, Color b, Color c, float value, float maxValue1, float maxValue2)
	{
		if (value < maxValue1)
		{
			return Color.Lerp(a, b, value / maxValue1);
		}
		return Color.Lerp(b, c, math.saturate((value - maxValue1) / (maxValue2 - maxValue1)));
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_LandValueSystem = base.World.GetOrCreateSystemManaged<LandValueSystem>();
		m_GizmosSystem = base.World.GetOrCreateSystemManaged<GizmosSystem>();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_DefaultToolSystem = base.World.GetOrCreateSystemManaged<DefaultToolSystem>();
		m_LandValueParameterQuery = GetEntityQuery(ComponentType.ReadOnly<LandValueParameterData>());
		m_LandValueEdgeQuery = GetEntityQuery(ComponentType.ReadOnly<Edge>(), ComponentType.ReadOnly<LandValue>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Hidden>());
		m_LandValueCellOption = AddOption("Land value (Cell)", defaultEnabled: true);
		m_EdgeLandValueOption = AddOption("Land value (Edge)", defaultEnabled: true);
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

- `public virtual OnDisabled(UnityEngine.Rendering.DebugUI+Container container) : System.Void`  

```csharp
public override void OnDisabled(DebugUI.Container container)
	{
		base.OnDisabled(container);
		m_DefaultToolSystem.debugLandValue = false;
	}
```

- `public virtual OnEnabled(UnityEngine.Rendering.DebugUI+Container container) : System.Void`  

```csharp
public override void OnEnabled(DebugUI.Container container)
	{
		base.OnEnabled(container);
		m_DefaultToolSystem.debugLandValue = true;
	}
```

- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
[Preserve]
	protected override JobHandle OnUpdate(JobHandle inputDeps)
	{
		if (m_LandValueCellOption.enabled)
		{
			JobHandle dependencies;
			JobHandle dependencies2;
			LandValueGizmoJob jobData = new LandValueGizmoJob
			{
				m_LandValueMap = m_LandValueSystem.GetMap(readOnly: true, out dependencies),
				m_GizmoBatcher = m_GizmosSystem.GetGizmosBatcher(out dependencies2),
				m_TerrainHeightData = m_TerrainSystem.GetHeightData(),
				m_LandValueOption = m_LandValueCellOption.enabled,
				m_LandValueParameterData = m_LandValueParameterQuery.GetSingleton<LandValueParameterData>()
			};
			base.Dependency = IJobExtensions.Schedule(jobData, JobHandle.CombineDependencies(inputDeps, dependencies2, dependencies));
			m_GizmosSystem.AddGizmosBatcherWriter(base.Dependency);
		}
		if (m_EdgeLandValueOption.enabled)
		{
			JobHandle dependencies3;
			LandValueEdgeGizmoJob jobData2 = new LandValueEdgeGizmoJob
			{
				m_EdgeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Edge_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CurveType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Curve_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_LandValues = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_LandValue_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_NodeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Node_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TerrainHeightData = m_TerrainSystem.GetHeightData(),
				m_GizmoBatcher = m_GizmosSystem.GetGizmosBatcher(out dependencies3),
				m_LandValueOption = m_EdgeLandValueOption.enabled
			};
			base.Dependency = JobChunkExtensions.ScheduleParallel(jobData2, m_LandValueEdgeQuery, JobHandle.CombineDependencies(inputDeps, dependencies3));
			m_GizmosSystem.AddGizmosBatcherWriter(base.Dependency);
		}
		m_TerrainSystem.AddCPUHeightReader(base.Dependency);
		return base.Dependency;
	}
```


## Nested types

- `Game.Debug.LandValueDebugSystem+LandValueEdgeGizmoJob`  
- `Game.Debug.LandValueDebugSystem+LandValueGizmoJob`  
- `Game.Debug.LandValueDebugSystem+TypeHandle`  

