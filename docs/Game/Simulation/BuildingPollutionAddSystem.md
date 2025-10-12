# Game.Simulation.BuildingPollutionAddSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem`  
- `private Game.Simulation.AirPollutionSystem m_AirPollutionSystem`  
- `private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Unity.Entities.EntityQuery m_PolluterQuery`  
- `private Unity.Collections.NativeArray<System.Single> m_GroundWeightCache`  
- `private Unity.Collections.NativeArray<System.Single> m_AirWeightCache`  
- `private Unity.Collections.NativeArray<System.Single> m_NoiseWeightCache`  
- `private Unity.Collections.NativeArray<System.Single> m_DistanceWeightCache`  
- `private Unity.Collections.NativeQueue<Game.Simulation.BuildingPollutionAddSystem+PollutionItem> m_GroundPollutionQueue`  
- `private Unity.Collections.NativeQueue<Game.Simulation.BuildingPollutionAddSystem+PollutionItem> m_AirPollutionQueue`  
- `private Unity.Collections.NativeQueue<Game.Simulation.BuildingPollutionAddSystem+PollutionItem> m_NoisePollutionQueue`  
- `private Game.Simulation.BuildingPollutionAddSystem+TypeHandle __TypeHandle`  
- `private Unity.Entities.EntityQuery __query_985639355_0`  
- `public static readonly System.Int32 kUpdatesPerDay`  

## Constructors

- `public BuildingPollutionAddSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private static CountRenters(System.Int32& count, System.Int32& education, Unity.Entities.DynamicBuffer<Game.Buildings.Renter> renters, Unity.Entities.BufferLookup`1[[Game.Companies.Employee, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& employees, Unity.Entities.BufferLookup`1[[Game.Citizens.HouseholdCitizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& householdCitizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens, System.Boolean ignoreEmployees) : System.Void`  
- `public static GetBuildingPollution(Unity.Entities.Entity prefab, System.Boolean destroyed, System.Boolean abandoned, System.Boolean isPark, System.Single efficiency, Unity.Entities.DynamicBuffer<Game.Buildings.Renter> renters, Unity.Entities.DynamicBuffer<Game.Buildings.InstalledUpgrade> installedUpgrades, Game.Prefabs.PollutionParameterData pollutionParameters, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildingDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.SpawnableBuildingData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& spawnableDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PollutionData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& pollutionDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PollutionModifierData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& pollutionModifierDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ZoneData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& zoneDatas, Unity.Entities.BufferLookup`1[[Game.Companies.Employee, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& employees, Unity.Entities.BufferLookup`1[[Game.Citizens.HouseholdCitizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& householdCitizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens) : Game.Prefabs.PollutionData`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `private static GetWeight(System.Single distance, System.Single exponent) : System.Single`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.BuildingPollutionAddSystem+PollutionItem`  
- `Game.Simulation.BuildingPollutionAddSystem+ApplyBuildingPollutionJob<T>`  
- `Game.Simulation.BuildingPollutionAddSystem+BuildingPolluteJob`  
- `Game.Simulation.BuildingPollutionAddSystem+TypeHandle`  

