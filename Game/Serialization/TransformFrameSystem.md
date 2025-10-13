# Game.Serialization.TransformFrameSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TransformFrameSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Unity.Entities.EntityQuery m_Query;
    private Game.Serialization.TransformFrameSystem+TypeHandle __TypeHandle;

    public TransformFrameSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Unity.Entities.EntityQuery m_Query`  

```csharp
private Unity.Entities.EntityQuery m_Query;
```

- `private Game.Serialization.TransformFrameSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Serialization.TransformFrameSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TransformFrameSystem()`  

```csharp
[Preserve]
	public TransformFrameSystem()
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
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_Query = GetEntityQuery(ComponentType.ReadWrite<TransformFrame>(), ComponentType.ReadWrite<InterpolatedTransform>(), ComponentType.ReadOnly<Transform>());
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
		TransformFrameJob jobData = new TransformFrameJob
		{
			m_UpdateFrameType = InternalCompilerInterface.GetSharedComponentTypeHandle(ref __TypeHandle.__Game_Simulation_UpdateFrame_SharedComponentTypeHandle, ref base.CheckedStateRef),
			m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_MovingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Moving_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_HumanNavigationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Creatures_HumanNavigation_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_AnimalNavigationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Creatures_AnimalNavigation_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TrainType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_Train_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_InterpolatedTransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Rendering_InterpolatedTransform_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TransformFrameType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Objects_TransformFrame_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_SimulationFrameIndex = m_SimulationSystem.frameIndex
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_Query, base.Dependency);
	}
```


## Nested types

- `Game.Serialization.TransformFrameSystem+TransformFrameJob`  
- `Game.Serialization.TransformFrameSystem+TypeHandle`  

