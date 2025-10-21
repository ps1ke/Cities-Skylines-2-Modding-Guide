# Game.Simulation.GarbageAccumulationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`, `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class GarbageAccumulationSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable, Game.Serialization.IPreDeserialize
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_GarbageProducerQuery;
    private Unity.Entities.EntityArchetype m_CollectionRequestArchetype;
    private Unity.Collections.NativeArray<System.Int64> m_GarbageAccumulation;
    private Unity.Jobs.JobHandle m_AccumulationDeps;
    private System.Int64 m_Accumulation;
    private Game.Simulation.GarbageAccumulationSystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_2138252455_0;
    private Unity.Entities.EntityQuery __query_2138252455_1;
    public static readonly System.Int32 kUpdatesPerDay;

    public System.Int64 garbageAccumulation { get; }

    public GarbageAccumulationSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void Deserialize<TReader>(TReader reader);
    public static System.Void GetGarbage(Game.Prefabs.ConsumptionData& consumption, Unity.Entities.Entity building, Unity.Entities.Entity prefab, Unity.Entities.BufferLookup<Game.Buildings.Renter> renters, Unity.Entities.BufferLookup<Game.Buildings.Student> students, Unity.Entities.BufferLookup<Game.Buildings.Occupant> occupants, Unity.Entities.ComponentLookup<Game.Citizens.HomelessHousehold> homelessHouseholds, Unity.Entities.BufferLookup<Game.Citizens.HouseholdCitizen> householdCitizens, Unity.Entities.ComponentLookup<Game.Citizens.Citizen> citizens, Unity.Entities.BufferLookup<Game.Companies.Employee> employees, Unity.Entities.BufferLookup<Game.Buildings.Patient> patients, Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> spawnableDatas, Unity.Entities.ComponentLookup<Game.Areas.CurrentDistrict> currentDistricts, Unity.Entities.BufferLookup<Game.Areas.DistrictModifier> districtModifiers, Unity.Entities.ComponentLookup<Game.Prefabs.ZoneData> zoneDatas, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Game.Prefabs.GarbageParameterData& garbageParameter);
    public static System.Void GetGarbageAccumulation(Unity.Entities.Entity building, Unity.Entities.Entity prefab, Game.Prefabs.ConsumptionData& consumption, Game.Areas.CurrentDistrict currentDistrict, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Unity.Entities.ComponentLookup<Game.Citizens.Citizen> citizens, Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> spawnableDatas, Unity.Entities.ComponentLookup<Game.Prefabs.ZoneData> zoneDatas, Unity.Entities.ComponentLookup<Game.Citizens.HomelessHousehold> homelessHousehold, Unity.Entities.BufferLookup<Game.Citizens.HouseholdCitizen> householdCitizens, Unity.Entities.BufferLookup<Game.Buildings.Renter> renters, Unity.Entities.BufferLookup<Game.Companies.Employee> employees, Unity.Entities.BufferLookup<Game.Buildings.Student> students, Unity.Entities.BufferLookup<Game.Buildings.Occupant> occupants, Unity.Entities.BufferLookup<Game.Buildings.Patient> patients, Unity.Entities.BufferLookup<Game.Areas.DistrictModifier> districtModifiers, Game.Prefabs.GarbageParameterData& garbageParameter);
    public static System.Single GetGarbageEfficiencyFactor(System.Int32 garbage, Game.Prefabs.GarbageParameterData garbageParameters, System.Single maxPenalty);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_GarbageProducerQuery`  

```csharp
private Unity.Entities.EntityQuery m_GarbageProducerQuery;
```

- `private Unity.Entities.EntityArchetype m_CollectionRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_CollectionRequestArchetype;
```

- `private Unity.Collections.NativeArray<System.Int64> m_GarbageAccumulation`  

```csharp
private Unity.Collections.NativeArray<System.Int64> m_GarbageAccumulation;
```

- `private Unity.Jobs.JobHandle m_AccumulationDeps`  

```csharp
private Unity.Jobs.JobHandle m_AccumulationDeps;
```

- `private System.Int64 m_Accumulation`  

```csharp
private System.Int64 m_Accumulation;
```

- `private Game.Simulation.GarbageAccumulationSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.GarbageAccumulationSystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_2138252455_0`  

```csharp
private Unity.Entities.EntityQuery __query_2138252455_0;
```

- `private Unity.Entities.EntityQuery __query_2138252455_1`  

```csharp
private Unity.Entities.EntityQuery __query_2138252455_1;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```


## Properties

- `public System.Int64 garbageAccumulation { get }`  

```csharp
public System.Int64 garbageAccumulation { get; }
```


## Constructors

- `public GarbageAccumulationSystem()`  

```csharp
public GarbageAccumulationSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public static GetGarbage(Game.Prefabs.ConsumptionData& consumption, Unity.Entities.Entity building, Unity.Entities.Entity prefab, Unity.Entities.BufferLookup<Game.Buildings.Renter> renters, Unity.Entities.BufferLookup<Game.Buildings.Student> students, Unity.Entities.BufferLookup<Game.Buildings.Occupant> occupants, Unity.Entities.ComponentLookup<Game.Citizens.HomelessHousehold> homelessHouseholds, Unity.Entities.BufferLookup<Game.Citizens.HouseholdCitizen> householdCitizens, Unity.Entities.ComponentLookup<Game.Citizens.Citizen> citizens, Unity.Entities.BufferLookup<Game.Companies.Employee> employees, Unity.Entities.BufferLookup<Game.Buildings.Patient> patients, Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> spawnableDatas, Unity.Entities.ComponentLookup<Game.Areas.CurrentDistrict> currentDistricts, Unity.Entities.BufferLookup<Game.Areas.DistrictModifier> districtModifiers, Unity.Entities.ComponentLookup<Game.Prefabs.ZoneData> zoneDatas, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Game.Prefabs.GarbageParameterData& garbageParameter) : System.Void`  

```csharp
public static System.Void GetGarbage(Game.Prefabs.ConsumptionData& consumption, Unity.Entities.Entity building, Unity.Entities.Entity prefab, Unity.Entities.BufferLookup<Game.Buildings.Renter> renters, Unity.Entities.BufferLookup<Game.Buildings.Student> students, Unity.Entities.BufferLookup<Game.Buildings.Occupant> occupants, Unity.Entities.ComponentLookup<Game.Citizens.HomelessHousehold> homelessHouseholds, Unity.Entities.BufferLookup<Game.Citizens.HouseholdCitizen> householdCitizens, Unity.Entities.ComponentLookup<Game.Citizens.Citizen> citizens, Unity.Entities.BufferLookup<Game.Companies.Employee> employees, Unity.Entities.BufferLookup<Game.Buildings.Patient> patients, Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> spawnableDatas, Unity.Entities.ComponentLookup<Game.Areas.CurrentDistrict> currentDistricts, Unity.Entities.BufferLookup<Game.Areas.DistrictModifier> districtModifiers, Unity.Entities.ComponentLookup<Game.Prefabs.ZoneData> zoneDatas, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Game.Prefabs.GarbageParameterData& garbageParameter);
```

- `public static GetGarbageAccumulation(Unity.Entities.Entity building, Unity.Entities.Entity prefab, Game.Prefabs.ConsumptionData& consumption, Game.Areas.CurrentDistrict currentDistrict, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Unity.Entities.ComponentLookup<Game.Citizens.Citizen> citizens, Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> spawnableDatas, Unity.Entities.ComponentLookup<Game.Prefabs.ZoneData> zoneDatas, Unity.Entities.ComponentLookup<Game.Citizens.HomelessHousehold> homelessHousehold, Unity.Entities.BufferLookup<Game.Citizens.HouseholdCitizen> householdCitizens, Unity.Entities.BufferLookup<Game.Buildings.Renter> renters, Unity.Entities.BufferLookup<Game.Companies.Employee> employees, Unity.Entities.BufferLookup<Game.Buildings.Student> students, Unity.Entities.BufferLookup<Game.Buildings.Occupant> occupants, Unity.Entities.BufferLookup<Game.Buildings.Patient> patients, Unity.Entities.BufferLookup<Game.Areas.DistrictModifier> districtModifiers, Game.Prefabs.GarbageParameterData& garbageParameter) : System.Void`  

```csharp
public static System.Void GetGarbageAccumulation(Unity.Entities.Entity building, Unity.Entities.Entity prefab, Game.Prefabs.ConsumptionData& consumption, Game.Areas.CurrentDistrict currentDistrict, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Unity.Entities.ComponentLookup<Game.Citizens.Citizen> citizens, Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> spawnableDatas, Unity.Entities.ComponentLookup<Game.Prefabs.ZoneData> zoneDatas, Unity.Entities.ComponentLookup<Game.Citizens.HomelessHousehold> homelessHousehold, Unity.Entities.BufferLookup<Game.Citizens.HouseholdCitizen> householdCitizens, Unity.Entities.BufferLookup<Game.Buildings.Renter> renters, Unity.Entities.BufferLookup<Game.Companies.Employee> employees, Unity.Entities.BufferLookup<Game.Buildings.Student> students, Unity.Entities.BufferLookup<Game.Buildings.Occupant> occupants, Unity.Entities.BufferLookup<Game.Buildings.Patient> patients, Unity.Entities.BufferLookup<Game.Areas.DistrictModifier> districtModifiers, Game.Prefabs.GarbageParameterData& garbageParameter);
```

- `public static GetGarbageEfficiencyFactor(System.Int32 garbage, Game.Prefabs.GarbageParameterData garbageParameters, System.Single maxPenalty) : System.Single`  

```csharp
public static System.Single GetGarbageEfficiencyFactor(System.Int32 garbage, Game.Prefabs.GarbageParameterData garbageParameters, System.Single maxPenalty);
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
```


## Nested types

- `Game.Simulation.GarbageAccumulationSystem+GarbageAccumulationJob`  
- `Game.Simulation.GarbageAccumulationSystem+TypeHandle`  

