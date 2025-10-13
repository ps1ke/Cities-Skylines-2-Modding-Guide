# Game.Serialization.LaneObjectSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LaneObjectSystem : Game.GameSystemBase
{
    private Game.Objects.SearchSystem m_ObjectSearchSystem;
    private Unity.Entities.EntityQuery m_Query;
    private Game.Serialization.LaneObjectSystem+TypeHandle __TypeHandle;

    public LaneObjectSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  

```csharp
private Game.Objects.SearchSystem m_ObjectSearchSystem;
```

- `private Unity.Entities.EntityQuery m_Query`  

```csharp
private Unity.Entities.EntityQuery m_Query;
```

- `private Game.Serialization.LaneObjectSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Serialization.LaneObjectSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public LaneObjectSystem()`  

```csharp
[Preserve]
	public LaneObjectSystem()
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
		m_ObjectSearchSystem = base.World.GetOrCreateSystemManaged<Game.Objects.SearchSystem>();
		m_Query = GetEntityQuery(new EntityQueryDesc
		{
			Any = new ComponentType[10]
			{
				ComponentType.ReadOnly<CarCurrentLane>(),
				ComponentType.ReadOnly<CarTrailerLane>(),
				ComponentType.ReadOnly<ParkedCar>(),
				ComponentType.ReadOnly<ParkedTrain>(),
				ComponentType.ReadOnly<WatercraftCurrentLane>(),
				ComponentType.ReadOnly<AircraftCurrentLane>(),
				ComponentType.ReadOnly<TrainCurrentLane>(),
				ComponentType.ReadOnly<HumanCurrentLane>(),
				ComponentType.ReadOnly<AnimalCurrentLane>(),
				ComponentType.ReadOnly<BlockedLane>()
			}
		});
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
		JobHandle dependencies;
		JobHandle jobHandle = JobChunkExtensions.Schedule(new LaneObjectJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_CarCurrentLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_CarCurrentLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CarTrailerLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_CarTrailerLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ParkedCarType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_ParkedCar_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ParkedTrainType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_ParkedTrain_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WatercraftCurrentLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_WatercraftCurrentLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_AircraftCurrentLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_AircraftCurrentLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TrainCurrentLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_TrainCurrentLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_HumanCurrentLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Creatures_HumanCurrentLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_AnimalCurrentLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Creatures_AnimalCurrentLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_BlockedLaneType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Objects_BlockedLane_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LaneObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_LaneObject_RW_BufferLookup, ref base.CheckedStateRef),
			m_SearchTree = m_ObjectSearchSystem.GetMovingSearchTree(readOnly: false, out dependencies)
		}, m_Query, JobHandle.CombineDependencies(base.Dependency, dependencies));
		m_ObjectSearchSystem.AddMovingSearchTreeWriter(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Serialization.LaneObjectSystem+LaneObjectJob`  
- `Game.Serialization.LaneObjectSystem+TypeHandle`  

