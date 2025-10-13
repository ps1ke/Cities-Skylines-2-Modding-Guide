# Game.Simulation.BuildingPollutionAddSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class BuildingPollutionAddSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
    private Game.Simulation.AirPollutionSystem m_AirPollutionSystem;
    private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Unity.Entities.EntityQuery m_PolluterQuery;
    private Unity.Collections.NativeArray<System.Single> m_GroundWeightCache;
    private Unity.Collections.NativeArray<System.Single> m_AirWeightCache;
    private Unity.Collections.NativeArray<System.Single> m_NoiseWeightCache;
    private Unity.Collections.NativeArray<System.Single> m_DistanceWeightCache;
    private Unity.Collections.NativeQueue<Game.Simulation.BuildingPollutionAddSystem+PollutionItem> m_GroundPollutionQueue;
    private Unity.Collections.NativeQueue<Game.Simulation.BuildingPollutionAddSystem+PollutionItem> m_AirPollutionQueue;
    private Unity.Collections.NativeQueue<Game.Simulation.BuildingPollutionAddSystem+PollutionItem> m_NoisePollutionQueue;
    private Game.Simulation.BuildingPollutionAddSystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_985639355_0;
    public static readonly System.Int32 kUpdatesPerDay;

    public BuildingPollutionAddSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private static System.Void CountRenters(System.Int32& count, System.Int32& education, Unity.Entities.DynamicBuffer<Game.Buildings.Renter> renters, Unity.Entities.BufferLookup`1[[Game.Companies.Employee, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& employees, Unity.Entities.BufferLookup`1[[Game.Citizens.HouseholdCitizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& householdCitizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens, System.Boolean ignoreEmployees);
    public static Game.Prefabs.PollutionData GetBuildingPollution(Unity.Entities.Entity prefab, System.Boolean destroyed, System.Boolean abandoned, System.Boolean isPark, System.Single efficiency, Unity.Entities.DynamicBuffer<Game.Buildings.Renter> renters, Unity.Entities.DynamicBuffer<Game.Buildings.InstalledUpgrade> installedUpgrades, Game.Prefabs.PollutionParameterData pollutionParameters, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildingDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.SpawnableBuildingData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& spawnableDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PollutionData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& pollutionDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PollutionModifierData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& pollutionModifierDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ZoneData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& zoneDatas, Unity.Entities.BufferLookup`1[[Game.Companies.Employee, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& employees, Unity.Entities.BufferLookup`1[[Game.Citizens.HouseholdCitizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& householdCitizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    private static System.Single GetWeight(System.Single distance, System.Single exponent);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem`  

```csharp
private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
```

- `private Game.Simulation.AirPollutionSystem m_AirPollutionSystem`  

```csharp
private Game.Simulation.AirPollutionSystem m_AirPollutionSystem;
```

- `private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem`  

```csharp
private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Unity.Entities.EntityQuery m_PolluterQuery`  

```csharp
private Unity.Entities.EntityQuery m_PolluterQuery;
```

- `private Unity.Collections.NativeArray<System.Single> m_GroundWeightCache`  

```csharp
private Unity.Collections.NativeArray<System.Single> m_GroundWeightCache;
```

- `private Unity.Collections.NativeArray<System.Single> m_AirWeightCache`  

```csharp
private Unity.Collections.NativeArray<System.Single> m_AirWeightCache;
```

- `private Unity.Collections.NativeArray<System.Single> m_NoiseWeightCache`  

```csharp
private Unity.Collections.NativeArray<System.Single> m_NoiseWeightCache;
```

- `private Unity.Collections.NativeArray<System.Single> m_DistanceWeightCache`  

```csharp
private Unity.Collections.NativeArray<System.Single> m_DistanceWeightCache;
```

- `private Unity.Collections.NativeQueue<Game.Simulation.BuildingPollutionAddSystem+PollutionItem> m_GroundPollutionQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.Simulation.BuildingPollutionAddSystem+PollutionItem> m_GroundPollutionQueue;
```

- `private Unity.Collections.NativeQueue<Game.Simulation.BuildingPollutionAddSystem+PollutionItem> m_AirPollutionQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.Simulation.BuildingPollutionAddSystem+PollutionItem> m_AirPollutionQueue;
```

- `private Unity.Collections.NativeQueue<Game.Simulation.BuildingPollutionAddSystem+PollutionItem> m_NoisePollutionQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.Simulation.BuildingPollutionAddSystem+PollutionItem> m_NoisePollutionQueue;
```

- `private Game.Simulation.BuildingPollutionAddSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.BuildingPollutionAddSystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_985639355_0`  

```csharp
private Unity.Entities.EntityQuery __query_985639355_0;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```


## Constructors

- `public BuildingPollutionAddSystem()`  

```csharp
public BuildingPollutionAddSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private static CountRenters(System.Int32& count, System.Int32& education, Unity.Entities.DynamicBuffer<Game.Buildings.Renter> renters, Unity.Entities.BufferLookup`1[[Game.Companies.Employee, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& employees, Unity.Entities.BufferLookup`1[[Game.Citizens.HouseholdCitizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& householdCitizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens, System.Boolean ignoreEmployees) : System.Void`  

```csharp
private static System.Void CountRenters(System.Int32& count, System.Int32& education, Unity.Entities.DynamicBuffer<Game.Buildings.Renter> renters, Unity.Entities.BufferLookup`1[[Game.Companies.Employee, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& employees, Unity.Entities.BufferLookup`1[[Game.Citizens.HouseholdCitizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& householdCitizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens, System.Boolean ignoreEmployees);
```

- `public static GetBuildingPollution(Unity.Entities.Entity prefab, System.Boolean destroyed, System.Boolean abandoned, System.Boolean isPark, System.Single efficiency, Unity.Entities.DynamicBuffer<Game.Buildings.Renter> renters, Unity.Entities.DynamicBuffer<Game.Buildings.InstalledUpgrade> installedUpgrades, Game.Prefabs.PollutionParameterData pollutionParameters, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildingDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.SpawnableBuildingData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& spawnableDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PollutionData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& pollutionDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PollutionModifierData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& pollutionModifierDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ZoneData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& zoneDatas, Unity.Entities.BufferLookup`1[[Game.Companies.Employee, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& employees, Unity.Entities.BufferLookup`1[[Game.Citizens.HouseholdCitizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& householdCitizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens) : Game.Prefabs.PollutionData`  

```csharp
public static Game.Prefabs.PollutionData GetBuildingPollution(Unity.Entities.Entity prefab, System.Boolean destroyed, System.Boolean abandoned, System.Boolean isPark, System.Single efficiency, Unity.Entities.DynamicBuffer<Game.Buildings.Renter> renters, Unity.Entities.DynamicBuffer<Game.Buildings.InstalledUpgrade> installedUpgrades, Game.Prefabs.PollutionParameterData pollutionParameters, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildingDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.SpawnableBuildingData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& spawnableDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PollutionData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& pollutionDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PollutionModifierData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& pollutionModifierDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ZoneData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& zoneDatas, Unity.Entities.BufferLookup`1[[Game.Companies.Employee, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& employees, Unity.Entities.BufferLookup`1[[Game.Citizens.HouseholdCitizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& householdCitizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens);
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
```

- `private static GetWeight(System.Single distance, System.Single exponent) : System.Single`  

```csharp
private static System.Single GetWeight(System.Single distance, System.Single exponent);
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


## Nested types

- `Game.Simulation.BuildingPollutionAddSystem+PollutionItem`  
- `Game.Simulation.BuildingPollutionAddSystem+ApplyBuildingPollutionJob<T>`  
- `Game.Simulation.BuildingPollutionAddSystem+BuildingPolluteJob`  
- `Game.Simulation.BuildingPollutionAddSystem+TypeHandle`  

