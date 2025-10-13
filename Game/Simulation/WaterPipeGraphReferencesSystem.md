# Game.Simulation.WaterPipeGraphReferencesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WaterPipeGraphReferencesSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_EdgeGroup;
    private Game.Simulation.WaterPipeGraphReferencesSystem+TypeHandle __TypeHandle;

    public WaterPipeGraphReferencesSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_EdgeGroup`  

```csharp
private Unity.Entities.EntityQuery m_EdgeGroup;
```

- `private Game.Simulation.WaterPipeGraphReferencesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.WaterPipeGraphReferencesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public WaterPipeGraphReferencesSystem()`  

```csharp
[Preserve]
	public WaterPipeGraphReferencesSystem()
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
		m_EdgeGroup = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<WaterPipeEdge>() },
			Any = new ComponentType[1] { ComponentType.ReadOnly<Deleted>() }
		});
		RequireForUpdate(m_EdgeGroup);
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
		UpdateGraphReferencesJob jobData = new UpdateGraphReferencesJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_WaterPipeEdgeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Simulation_WaterPipeEdge_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ConnectedFlowEdges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Simulation_ConnectedFlowEdge_RW_BufferLookup, ref base.CheckedStateRef)
		};
		base.Dependency = JobChunkExtensions.Schedule(jobData, m_EdgeGroup, base.Dependency);
	}
```


## Nested types

- `Game.Simulation.WaterPipeGraphReferencesSystem+UpdateGraphReferencesJob`  
- `Game.Simulation.WaterPipeGraphReferencesSystem+TypeHandle`  

