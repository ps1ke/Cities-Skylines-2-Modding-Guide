# Game.Objects.ObjectEmergeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ObjectEmergeSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier4B m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_DeletedBuildingQuery;
    private Unity.Entities.EntityQuery m_DeletedVehicleQuery;
    private Unity.Entities.EntityQuery m_EmergeObjectQuery;
    private Unity.Entities.EntityQuery m_CreaturePrefabQuery;
    private Unity.Entities.ComponentTypeSet m_TripSourceRemoveTypes;
    private Unity.Entities.ComponentTypeSet m_CurrentVehicleRemoveTypes;
    private Unity.Entities.ComponentTypeSet m_CurrentVehicleHumanAddTypes;
    private Unity.Entities.ComponentTypeSet m_CurrentVehicleAnimalAddTypes;
    private Unity.Entities.ComponentTypeSet m_HumanSpawnTypes;
    private Unity.Entities.ComponentTypeSet m_AnimalSpawnTypes;
    private Game.Objects.ObjectEmergeSystem+TypeHandle __TypeHandle;

    public ObjectEmergeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    public static Unity.Entities.Entity SelectAnimalPrefab(Unity.Mathematics.Random& random, Game.Prefabs.PetType petType, Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> chunks, Unity.Entities.EntityTypeHandle entityType, Unity.Entities.ComponentTypeHandle<Game.Prefabs.PetData> petDataType, Game.Common.PseudoRandomSeed& randomSeed);
    private static System.Boolean SelectItem(Unity.Mathematics.Random& random, System.Int32 probability, System.Int32& totalProbability);
    public static Unity.Entities.Entity SelectResidentPrefab(Game.Citizens.Citizen citizenData, Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> chunks, Unity.Entities.EntityTypeHandle entityType, Unity.Entities.ComponentTypeHandle`1[[Game.Prefabs.CreatureData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& creatureType, Unity.Entities.ComponentTypeHandle`1[[Game.Prefabs.ResidentData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& residentType, Game.Prefabs.CreatureData& creatureData, Game.Common.PseudoRandomSeed& randomSeed);
}
```


## Fields

- `private Game.Common.ModificationBarrier4B m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier4B m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_DeletedBuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeletedBuildingQuery;
```

- `private Unity.Entities.EntityQuery m_DeletedVehicleQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeletedVehicleQuery;
```

- `private Unity.Entities.EntityQuery m_EmergeObjectQuery`  

```csharp
private Unity.Entities.EntityQuery m_EmergeObjectQuery;
```

- `private Unity.Entities.EntityQuery m_CreaturePrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreaturePrefabQuery;
```

- `private Unity.Entities.ComponentTypeSet m_TripSourceRemoveTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_TripSourceRemoveTypes;
```

- `private Unity.Entities.ComponentTypeSet m_CurrentVehicleRemoveTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_CurrentVehicleRemoveTypes;
```

- `private Unity.Entities.ComponentTypeSet m_CurrentVehicleHumanAddTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_CurrentVehicleHumanAddTypes;
```

- `private Unity.Entities.ComponentTypeSet m_CurrentVehicleAnimalAddTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_CurrentVehicleAnimalAddTypes;
```

- `private Unity.Entities.ComponentTypeSet m_HumanSpawnTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_HumanSpawnTypes;
```

- `private Unity.Entities.ComponentTypeSet m_AnimalSpawnTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_AnimalSpawnTypes;
```

- `private Game.Objects.ObjectEmergeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Objects.ObjectEmergeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ObjectEmergeSystem()`  

```csharp
[Preserve]
	public ObjectEmergeSystem()
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
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier4B>();
		m_DeletedBuildingQuery = GetEntityQuery(ComponentType.ReadOnly<Deleted>(), ComponentType.ReadOnly<Building>(), ComponentType.Exclude<Temp>());
		m_DeletedVehicleQuery = GetEntityQuery(ComponentType.ReadOnly<Deleted>(), ComponentType.ReadOnly<Passenger>(), ComponentType.Exclude<Temp>());
		m_EmergeObjectQuery = GetEntityQuery(new EntityQueryDesc
		{
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<CurrentBuilding>(),
				ComponentType.ReadOnly<TripSource>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_CreaturePrefabQuery = GetEntityQuery(ComponentType.ReadOnly<CreatureData>(), ComponentType.ReadOnly<PrefabData>());
		m_TripSourceRemoveTypes = new ComponentTypeSet(ComponentType.ReadWrite<TripSource>(), ComponentType.ReadWrite<Unspawned>());
		m_CurrentVehicleRemoveTypes = new ComponentTypeSet(ComponentType.ReadWrite<CurrentVehicle>(), ComponentType.ReadWrite<Relative>(), ComponentType.ReadWrite<Unspawned>());
		m_CurrentVehicleHumanAddTypes = new ComponentTypeSet(new ComponentType[7]
		{
			ComponentType.ReadWrite<Moving>(),
			ComponentType.ReadWrite<TransformFrame>(),
			ComponentType.ReadWrite<InterpolatedTransform>(),
			ComponentType.ReadWrite<HumanNavigation>(),
			ComponentType.ReadWrite<HumanCurrentLane>(),
			ComponentType.ReadWrite<Blocker>(),
			ComponentType.ReadWrite<Updated>()
		});
		m_CurrentVehicleAnimalAddTypes = new ComponentTypeSet(new ComponentType[7]
		{
			ComponentType.ReadWrite<Moving>(),
			ComponentType.ReadWrite<TransformFrame>(),
			ComponentType.ReadWrite<InterpolatedTransform>(),
			ComponentType.ReadWrite<AnimalNavigation>(),
			ComponentType.ReadWrite<AnimalCurrentLane>(),
			ComponentType.ReadWrite<Blocker>(),
			ComponentType.ReadWrite<Updated>()
		});
		m_HumanSpawnTypes = new ComponentTypeSet(ComponentType.ReadWrite<HumanCurrentLane>(), ComponentType.ReadWrite<TripSource>(), ComponentType.ReadWrite<Unspawned>(), ComponentType.ReadWrite<Divert>());
		m_AnimalSpawnTypes = new ComponentTypeSet(ComponentType.ReadWrite<AnimalCurrentLane>(), ComponentType.ReadWrite<TripSource>(), ComponentType.ReadWrite<Unspawned>());
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
		bool flag = !m_DeletedBuildingQuery.IsEmptyIgnoreFilter;
		bool flag2 = !m_DeletedVehicleQuery.IsEmptyIgnoreFilter;
		if (!flag && !flag2)
		{
			return;
		}
		NativeQueue<Entity> emergeQueue = new NativeQueue<Entity>(Allocator.TempJob);
		NativeQueue<Entity>.ParallelWriter emergeQueue2 = emergeQueue.AsParallelWriter();
		if (flag)
		{
			NativeArray<ArchetypeChunk> nativeArray = m_DeletedBuildingQuery.ToArchetypeChunkArray(Allocator.TempJob);
			try
			{
				EntityTypeHandle entityTypeHandle = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef);
				for (int i = 0; i < nativeArray.Length; i++)
				{
					NativeArray<Entity> nativeArray2 = nativeArray[i].GetNativeArray(entityTypeHandle);
					for (int j = 0; j < nativeArray2.Length; j++)
					{
						FindObjectsInBuildingJob jobData = new FindObjectsInBuildingJob
						{
							m_Building = nativeArray2[j],
							m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
							m_CurrentBuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_CurrentBuilding_RO_ComponentTypeHandle, ref base.CheckedStateRef),
							m_TripSourceType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_TripSource_RO_ComponentTypeHandle, ref base.CheckedStateRef),
							m_EmergeQueue = emergeQueue2
						};
						base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_EmergeObjectQuery, base.Dependency);
					}
				}
			}
			finally
			{
				nativeArray.Dispose();
			}
		}
		if (flag2)
		{
			FindObjectsInVehiclesJob jobData2 = new FindObjectsInVehiclesJob
			{
				m_PassengerType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Vehicles_Passenger_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_EmergeQueue = emergeQueue2
			};
			base.Dependency = JobChunkExtensions.ScheduleParallel(jobData2, m_DeletedVehicleQuery, base.Dependency);
		}
		JobHandle outJobHandle;
		NativeList<ArchetypeChunk> creaturePrefabChunks = m_CreaturePrefabQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle);
		JobHandle jobHandle = IJobExtensions.Schedule(new EmergeObjectsJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_CreatureDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_CreatureData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PetDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PetData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ResidentDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_ResidentData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_UpdatedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Updated_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TripSourceData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_TripSource_RO_ComponentLookup, ref base.CheckedStateRef),
			m_UnspawnedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Unspawned_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CitizenData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Citizen_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HouseholdPetData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HouseholdPet_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HouseholdMembers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HouseholdMember_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurrentBuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_CurrentBuilding_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurrentTransportData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_CurrentTransport_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HealthProblemData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HealthProblem_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurrentVehicleData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_CurrentVehicle_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HumanData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_Human_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AnimalData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_Animal_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ResidentData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_Resident_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HumanCurrentLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_HumanCurrentLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AnimalCurrentLane = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_AnimalCurrentLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabHouseholdPetData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_HouseholdPetData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HomelessHouseholds = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HomelessHousehold_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PropertyRenters = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_PropertyRenter_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Deleteds = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RandomSeed = RandomSeed.Next(),
			m_TripSourceRemoveTypes = m_TripSourceRemoveTypes,
			m_CurrentVehicleRemoveTypes = m_CurrentVehicleRemoveTypes,
			m_CurrentVehicleHumanAddTypes = m_CurrentVehicleHumanAddTypes,
			m_CurrentVehicleAnimalAddTypes = m_CurrentVehicleAnimalAddTypes,
			m_HumanSpawnTypes = m_HumanSpawnTypes,
			m_AnimalSpawnTypes = m_AnimalSpawnTypes,
			m_CreaturePrefabChunks = creaturePrefabChunks,
			m_EmergeQueue = emergeQueue,
			m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer()
		}, JobHandle.CombineDependencies(base.Dependency, outJobHandle));
		emergeQueue.Dispose(jobHandle);
		creaturePrefabChunks.Dispose(jobHandle);
		m_ModificationBarrier.AddJobHandleForProducer(jobHandle);
		base.Dependency = jobHandle;
	}
```

- `public static SelectAnimalPrefab(Unity.Mathematics.Random& random, Game.Prefabs.PetType petType, Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> chunks, Unity.Entities.EntityTypeHandle entityType, Unity.Entities.ComponentTypeHandle<Game.Prefabs.PetData> petDataType, Game.Common.PseudoRandomSeed& randomSeed) : Unity.Entities.Entity`  

```csharp
public static Entity SelectAnimalPrefab(ref Random random, PetType petType, NativeList<ArchetypeChunk> chunks, EntityTypeHandle entityType, ComponentTypeHandle<PetData> petDataType, out PseudoRandomSeed randomSeed)
	{
		int totalProbability = 0;
		Entity result = Entity.Null;
		for (int i = 0; i < chunks.Length; i++)
		{
			ArchetypeChunk archetypeChunk = chunks[i];
			NativeArray<Entity> nativeArray = archetypeChunk.GetNativeArray(entityType);
			NativeArray<PetData> nativeArray2 = archetypeChunk.GetNativeArray(ref petDataType);
			for (int j = 0; j < nativeArray2.Length; j++)
			{
				if (nativeArray2[j].m_Type == petType && SelectItem(ref random, 100, ref totalProbability))
				{
					result = nativeArray[j];
				}
			}
		}
		randomSeed = new PseudoRandomSeed(ref random);
		return result;
	}
```

- `private static SelectItem(Unity.Mathematics.Random& random, System.Int32 probability, System.Int32& totalProbability) : System.Boolean`  

```csharp
private static bool SelectItem(ref Random random, int probability, ref int totalProbability)
	{
		totalProbability += probability;
		return random.NextInt(totalProbability) < probability;
	}
```

- `public static SelectResidentPrefab(Game.Citizens.Citizen citizenData, Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> chunks, Unity.Entities.EntityTypeHandle entityType, Unity.Entities.ComponentTypeHandle`1[[Game.Prefabs.CreatureData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& creatureType, Unity.Entities.ComponentTypeHandle`1[[Game.Prefabs.ResidentData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& residentType, Game.Prefabs.CreatureData& creatureData, Game.Common.PseudoRandomSeed& randomSeed) : Unity.Entities.Entity`  

```csharp
public static Entity SelectResidentPrefab(Citizen citizenData, NativeList<ArchetypeChunk> chunks, EntityTypeHandle entityType, ref ComponentTypeHandle<CreatureData> creatureType, ref ComponentTypeHandle<ResidentData> residentType, out CreatureData creatureData, out PseudoRandomSeed randomSeed)
	{
		Random random = citizenData.GetPseudoRandom(CitizenPseudoRandom.SpawnResident);
		GenderMask genderMask = (((citizenData.m_State & CitizenFlags.Male) == 0) ? GenderMask.Female : GenderMask.Male);
		Game.Prefabs.AgeMask ageMask = citizenData.GetAge() switch
		{
			CitizenAge.Child => Game.Prefabs.AgeMask.Child, 
			CitizenAge.Teen => Game.Prefabs.AgeMask.Teen, 
			CitizenAge.Adult => Game.Prefabs.AgeMask.Adult, 
			CitizenAge.Elderly => Game.Prefabs.AgeMask.Elderly, 
			_ => (Game.Prefabs.AgeMask)0, 
		};
		Entity result = Entity.Null;
		int totalProbability = 0;
		creatureData = default(CreatureData);
		randomSeed = new PseudoRandomSeed(ref random);
		for (int i = 0; i < chunks.Length; i++)
		{
			ArchetypeChunk archetypeChunk = chunks[i];
			NativeArray<Entity> nativeArray = archetypeChunk.GetNativeArray(entityType);
			NativeArray<CreatureData> nativeArray2 = archetypeChunk.GetNativeArray(ref creatureType);
			NativeArray<ResidentData> nativeArray3 = archetypeChunk.GetNativeArray(ref residentType);
			for (int j = 0; j < nativeArray3.Length; j++)
			{
				CreatureData creatureData2 = nativeArray2[j];
				ResidentData residentData = nativeArray3[j];
				if ((creatureData2.m_Gender & genderMask) == genderMask && (residentData.m_Age & ageMask) == ageMask)
				{
					int probability = 100;
					if (SelectItem(ref random, probability, ref totalProbability))
					{
						result = nativeArray[j];
						creatureData = creatureData2;
					}
				}
			}
		}
		return result;
	}
```


## Nested types

- `Game.Objects.ObjectEmergeSystem+FindObjectsInBuildingJob`  
- `Game.Objects.ObjectEmergeSystem+FindObjectsInVehiclesJob`  
- `Game.Objects.ObjectEmergeSystem+EmergeObjectsJob`  
- `Game.Objects.ObjectEmergeSystem+TypeHandle`  

