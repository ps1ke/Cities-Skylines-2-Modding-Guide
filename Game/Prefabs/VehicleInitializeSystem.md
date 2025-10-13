# Game.Prefabs.VehicleInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class VehicleInitializeSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_PrefabQuery;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Prefabs.VehicleInitializeSystem+TypeHandle __TypeHandle;

    public VehicleInitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_PrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrefabQuery;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Prefabs.VehicleInitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Prefabs.VehicleInitializeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public VehicleInitializeSystem()`  

```csharp
[Preserve]
	public VehicleInitializeSystem()
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
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_PrefabQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<PrefabData>()
			},
			Any = new ComponentType[4]
			{
				ComponentType.ReadWrite<CarData>(),
				ComponentType.ReadWrite<TrainData>(),
				ComponentType.ReadWrite<CarTractorData>(),
				ComponentType.ReadWrite<CarTrailerData>()
			}
		});
		RequireForUpdate(m_PrefabQuery);
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
		NativeArray<ArchetypeChunk> chunks = m_PrefabQuery.ToArchetypeChunkArray(Allocator.TempJob);
		ComponentTypeHandle<PrefabData> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
		ComponentTypeHandle<ObjectGeometryData> typeHandle2 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
		ComponentTypeHandle<MultipleUnitTrainData> componentTypeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_MultipleUnitTrainData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
		ComponentTypeHandle<TrainData> typeHandle3 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_TrainData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
		ComponentTypeHandle<CarData> typeHandle4 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_CarData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
		ComponentTypeHandle<SwayingData> typeHandle5 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_SwayingData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
		ComponentTypeHandle<VehicleData> componentTypeHandle2 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_VehicleData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
		ComponentTypeHandle<CarTractorData> typeHandle6 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_CarTractorData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
		ComponentTypeHandle<CarTrailerData> typeHandle7 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_CarTrailerData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
		BufferTypeHandle<SubMesh> bufferTypeHandle = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_SubMesh_RO_BufferTypeHandle, ref base.CheckedStateRef);
		CompleteDependency();
		for (int i = 0; i < chunks.Length; i++)
		{
			ArchetypeChunk archetypeChunk = chunks[i];
			NativeArray<PrefabData> nativeArray = archetypeChunk.GetNativeArray(ref typeHandle);
			NativeArray<ObjectGeometryData> nativeArray2 = archetypeChunk.GetNativeArray(ref typeHandle2);
			NativeArray<TrainData> nativeArray3 = archetypeChunk.GetNativeArray(ref typeHandle3);
			NativeArray<CarData> nativeArray4 = archetypeChunk.GetNativeArray(ref typeHandle4);
			NativeArray<SwayingData> nativeArray5 = archetypeChunk.GetNativeArray(ref typeHandle5);
			NativeArray<CarTractorData> nativeArray6 = archetypeChunk.GetNativeArray(ref typeHandle6);
			NativeArray<CarTrailerData> nativeArray7 = archetypeChunk.GetNativeArray(ref typeHandle7);
			for (int j = 0; j < nativeArray3.Length; j++)
			{
				TrainPrefab prefab = m_PrefabSystem.GetPrefab<TrainPrefab>(nativeArray[j]);
				ObjectGeometryData objectGeometryData = nativeArray2[j];
				TrainData value = nativeArray3[j];
				float2 @float = new float2(objectGeometryData.m_Bounds.max.z, 0f - objectGeometryData.m_Bounds.min.z);
				value.m_TrackType = prefab.m_TrackType;
				value.m_EnergyType = prefab.m_EnergyType;
				value.m_MaxSpeed = prefab.m_MaxSpeed / 3.6f;
				value.m_Acceleration = prefab.m_Acceleration;
				value.m_Braking = prefab.m_Braking;
				value.m_Turning = math.radians(prefab.m_Turning);
				value.m_BogieOffsets = prefab.m_BogieOffset;
				value.m_AttachOffsets = @float - prefab.m_AttachOffset;
				nativeArray3[j] = value;
			}
			for (int k = 0; k < nativeArray4.Length; k++)
			{
				CarBasePrefab prefab2 = m_PrefabSystem.GetPrefab<CarBasePrefab>(nativeArray[k]);
				CarData value2 = nativeArray4[k];
				SwayingData value3 = nativeArray5[k];
				value2.m_SizeClass = prefab2.m_SizeClass;
				value2.m_EnergyType = prefab2.m_EnergyType;
				value2.m_MaxSpeed = prefab2.m_MaxSpeed / 3.6f;
				value2.m_Acceleration = prefab2.m_Acceleration;
				value2.m_Braking = prefab2.m_Braking;
				value2.m_Turning = math.radians(prefab2.m_Turning);
				value3.m_SpringFactors = prefab2.m_Stiffness;
				nativeArray4[k] = value2;
				nativeArray5[k] = value3;
			}
			for (int l = 0; l < nativeArray6.Length; l++)
			{
				CarTractor component = m_PrefabSystem.GetPrefab<VehiclePrefab>(nativeArray[l]).GetComponent<CarTractor>();
				ObjectGeometryData objectGeometryData2 = nativeArray2[l];
				CarTractorData value4 = nativeArray6[l];
				value4.m_TrailerType = component.m_TrailerType;
				value4.m_AttachPosition.xy = component.m_AttachOffset.xy;
				value4.m_AttachPosition.z = objectGeometryData2.m_Bounds.min.z + component.m_AttachOffset.z;
				if (component.m_FixedTrailer != null)
				{
					value4.m_FixedTrailer = m_PrefabSystem.GetEntity(component.m_FixedTrailer);
				}
				nativeArray6[l] = value4;
			}
			for (int m = 0; m < nativeArray7.Length; m++)
			{
				CarTrailerPrefab prefab3 = m_PrefabSystem.GetPrefab<CarTrailerPrefab>(nativeArray[m]);
				ObjectGeometryData objectGeometryData3 = nativeArray2[m];
				CarTrailerData value5 = nativeArray7[m];
				value5.m_TrailerType = prefab3.m_TrailerType;
				value5.m_MovementType = prefab3.m_MovementType;
				value5.m_AttachPosition.xy = prefab3.m_AttachOffset.xy;
				value5.m_AttachPosition.z = objectGeometryData3.m_Bounds.max.z - prefab3.m_AttachOffset.z;
				if (prefab3.m_FixedTractor != null)
				{
					value5.m_FixedTractor = m_PrefabSystem.GetEntity(prefab3.m_FixedTractor);
				}
				nativeArray7[m] = value5;
			}
		}
		JobHandle dependency = IJobParallelForExtensions.Schedule(new InitializeVehiclesJob
		{
			m_ObjectGeometryType = typeHandle2,
			m_CarTrailerType = typeHandle7,
			m_MultipleUnitTrainType = componentTypeHandle,
			m_SubmeshType = bufferTypeHandle,
			m_CarType = typeHandle4,
			m_TrainType = typeHandle3,
			m_SwayingType = typeHandle5,
			m_VehicleType = componentTypeHandle2,
			m_ProceduralBones = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_ProceduralBone_RO_BufferLookup, ref base.CheckedStateRef),
			m_Chunks = chunks
		}, chunks.Length, 1, base.Dependency);
		base.Dependency = dependency;
	}
```


## Nested types

- `Game.Prefabs.VehicleInitializeSystem+InitializeVehiclesJob`  
- `Game.Prefabs.VehicleInitializeSystem+TypeHandle`  

