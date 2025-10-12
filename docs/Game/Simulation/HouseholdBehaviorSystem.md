# Game.Simulation.HouseholdBehaviorSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_HouseholdGroup`  
- `private Unity.Entities.EntityQuery m_EconomyParameterGroup`  
- `private Unity.Entities.EntityQuery m_GameModeSettingQuery`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  
- `private Game.Simulation.TaxSystem m_TaxSystem`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private System.Single m_ResourceDemandPerCitizenMultiplier`  
- `private Game.Simulation.HouseholdBehaviorSystem+TypeHandle __TypeHandle`  
- `public static readonly System.Int32 kCarAmount`  
- `public static readonly System.Int32 kUpdatesPerDay`  
- `public static readonly System.Int32 kMaxShoppingPossibility`  
- `public static readonly System.Int32 kMaxHouseholdNeedAmount`  
- `public static readonly System.Int32 kCarBuyingMinimumMoney`  
- `public static readonly System.Int32 KMinimumShoppingAmount`  

## Constructors

- `public HouseholdBehaviorSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public static GetAgeWeight(Game.Prefabs.ResourceData resourceData, Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> citizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizenDatas) : System.Int32`  
- `public static GetConsumptionMultiplier(Unity.Mathematics.float2 parameter, System.Int32 householdWealth) : System.Single`  
- `public static GetFreeCar(Unity.Entities.Entity household, Unity.Entities.BufferLookup<Game.Vehicles.OwnedVehicle> ownedVehicles, Unity.Entities.ComponentLookup<Game.Vehicles.PersonalCar> personalCars, Unity.Entities.Entity& car) : System.Boolean`  
- `public static GetHighestEducation(Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> citizenBuffer, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens) : System.Int32`  
- `public static GetLastCommutePerCitizen(Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> householdCitizens, Unity.Entities.ComponentLookup<Game.Citizens.Worker> workers) : System.Single`  
- `public static GetResourceShopWeightWithAge(System.Int32 wealth, Game.Economy.Resource resource, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas, System.Int32 carCount, System.Boolean leisureIncluded, Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> citizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizenDatas) : System.Int32`  
- `public static GetResourceShopWeightWithAge(System.Int32 wealth, Game.Prefabs.ResourceData resourceData, System.Int32 carCount, System.Boolean leisureIncluded, Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> citizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizenDatas) : System.Int32`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `public static GetWeight(System.Int32 wealth, Game.Economy.Resource resource, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas, System.Int32 carCount, System.Boolean leisureIncluded) : System.Int32`  
- `public static GetWeight(System.Int32 wealth, Game.Prefabs.ResourceData resourceData, System.Int32 carCount, System.Boolean leisureIncluded) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.HouseholdBehaviorSystem+HouseholdTickJob`  
- `Game.Simulation.HouseholdBehaviorSystem+TypeHandle`  

