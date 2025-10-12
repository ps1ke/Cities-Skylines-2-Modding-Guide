# Game.Simulation.GarbageAccumulationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`, `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Unity.Entities.EntityQuery m_GarbageProducerQuery`  
- `private Unity.Entities.EntityArchetype m_CollectionRequestArchetype`  
- `private Unity.Collections.NativeArray<System.Int64> m_GarbageAccumulation`  
- `private Unity.Jobs.JobHandle m_AccumulationDeps`  
- `private System.Int64 m_Accumulation`  
- `private Game.Simulation.GarbageAccumulationSystem+TypeHandle __TypeHandle`  
- `private Unity.Entities.EntityQuery __query_2138252455_0`  
- `private Unity.Entities.EntityQuery __query_2138252455_1`  
- `public static readonly System.Int32 kUpdatesPerDay`  

## Properties

- `public System.Int64 garbageAccumulation { get }`  

## Constructors

- `public GarbageAccumulationSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public static GetGarbage(Game.Prefabs.ConsumptionData& consumption, Unity.Entities.Entity building, Unity.Entities.Entity prefab, Unity.Entities.BufferLookup<Game.Buildings.Renter> renters, Unity.Entities.BufferLookup<Game.Buildings.Student> students, Unity.Entities.BufferLookup<Game.Buildings.Occupant> occupants, Unity.Entities.ComponentLookup<Game.Citizens.HomelessHousehold> homelessHouseholds, Unity.Entities.BufferLookup<Game.Citizens.HouseholdCitizen> householdCitizens, Unity.Entities.ComponentLookup<Game.Citizens.Citizen> citizens, Unity.Entities.BufferLookup<Game.Companies.Employee> employees, Unity.Entities.BufferLookup<Game.Buildings.Patient> patients, Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> spawnableDatas, Unity.Entities.ComponentLookup<Game.Areas.CurrentDistrict> currentDistricts, Unity.Entities.BufferLookup<Game.Areas.DistrictModifier> districtModifiers, Unity.Entities.ComponentLookup<Game.Prefabs.ZoneData> zoneDatas, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Game.Prefabs.GarbageParameterData& garbageParameter) : System.Void`  
- `public static GetGarbageAccumulation(Unity.Entities.Entity building, Unity.Entities.Entity prefab, Game.Prefabs.ConsumptionData& consumption, Game.Areas.CurrentDistrict currentDistrict, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Unity.Entities.ComponentLookup<Game.Citizens.Citizen> citizens, Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> spawnableDatas, Unity.Entities.ComponentLookup<Game.Prefabs.ZoneData> zoneDatas, Unity.Entities.ComponentLookup<Game.Citizens.HomelessHousehold> homelessHousehold, Unity.Entities.BufferLookup<Game.Citizens.HouseholdCitizen> householdCitizens, Unity.Entities.BufferLookup<Game.Buildings.Renter> renters, Unity.Entities.BufferLookup<Game.Companies.Employee> employees, Unity.Entities.BufferLookup<Game.Buildings.Student> students, Unity.Entities.BufferLookup<Game.Buildings.Occupant> occupants, Unity.Entities.BufferLookup<Game.Buildings.Patient> patients, Unity.Entities.BufferLookup<Game.Areas.DistrictModifier> districtModifiers, Game.Prefabs.GarbageParameterData& garbageParameter) : System.Void`  
- `public static GetGarbageEfficiencyFactor(System.Int32 garbage, Game.Prefabs.GarbageParameterData garbageParameters, System.Single maxPenalty) : System.Single`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  
- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

## Nested types

- `Game.Simulation.GarbageAccumulationSystem+GarbageAccumulationJob`  
- `Game.Simulation.GarbageAccumulationSystem+TypeHandle`  

