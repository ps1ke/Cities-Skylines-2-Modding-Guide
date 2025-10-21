# Game.Simulation.HouseholdBehaviorSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class HouseholdBehaviorSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_HouseholdGroup;
    private Unity.Entities.EntityQuery m_EconomyParameterGroup;
    private Unity.Entities.EntityQuery m_GameModeSettingQuery;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Simulation.TaxSystem m_TaxSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private System.Single m_ResourceDemandPerCitizenMultiplier;
    private Game.Simulation.HouseholdBehaviorSystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kCarAmount;
    public static readonly System.Int32 kUpdatesPerDay;
    public static readonly System.Int32 kMaxShoppingPossibility;
    public static readonly System.Int32 kMaxHouseholdNeedAmount;
    public static readonly System.Int32 kCarBuyingMinimumMoney;
    public static readonly System.Int32 KMinimumShoppingAmount;

    public HouseholdBehaviorSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static System.Int32 GetAgeWeight(Game.Prefabs.ResourceData resourceData, Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> citizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizenDatas);
    public static System.Single GetConsumptionMultiplier(Unity.Mathematics.float2 parameter, System.Int32 householdWealth);
    public static System.Boolean GetFreeCar(Unity.Entities.Entity household, Unity.Entities.BufferLookup<Game.Vehicles.OwnedVehicle> ownedVehicles, Unity.Entities.ComponentLookup<Game.Vehicles.PersonalCar> personalCars, Unity.Entities.Entity& car);
    public static System.Int32 GetHighestEducation(Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> citizenBuffer, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens);
    public static System.Single GetLastCommutePerCitizen(Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> householdCitizens, Unity.Entities.ComponentLookup<Game.Citizens.Worker> workers);
    public static System.Int32 GetResourceShopWeightWithAge(System.Int32 wealth, Game.Economy.Resource resource, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas, System.Int32 carCount, System.Boolean leisureIncluded, Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> citizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizenDatas);
    public static System.Int32 GetResourceShopWeightWithAge(System.Int32 wealth, Game.Prefabs.ResourceData resourceData, System.Int32 carCount, System.Boolean leisureIncluded, Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> citizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizenDatas);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public static System.Int32 GetWeight(System.Int32 wealth, Game.Economy.Resource resource, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas, System.Int32 carCount, System.Boolean leisureIncluded);
    public static System.Int32 GetWeight(System.Int32 wealth, Game.Prefabs.ResourceData resourceData, System.Int32 carCount, System.Boolean leisureIncluded);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_HouseholdGroup`  

```csharp
private Unity.Entities.EntityQuery m_HouseholdGroup;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterGroup`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterGroup;
```

- `private Unity.Entities.EntityQuery m_GameModeSettingQuery`  

```csharp
private Unity.Entities.EntityQuery m_GameModeSettingQuery;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Simulation.TaxSystem m_TaxSystem`  

```csharp
private Game.Simulation.TaxSystem m_TaxSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private System.Single m_ResourceDemandPerCitizenMultiplier`  

```csharp
private System.Single m_ResourceDemandPerCitizenMultiplier;
```

- `private Game.Simulation.HouseholdBehaviorSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.HouseholdBehaviorSystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Int32 kCarAmount`  

```csharp
public static readonly System.Int32 kCarAmount;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```

- `public static readonly System.Int32 kMaxShoppingPossibility`  

```csharp
public static readonly System.Int32 kMaxShoppingPossibility;
```

- `public static readonly System.Int32 kMaxHouseholdNeedAmount`  

```csharp
public static readonly System.Int32 kMaxHouseholdNeedAmount;
```

- `public static readonly System.Int32 kCarBuyingMinimumMoney`  

```csharp
public static readonly System.Int32 kCarBuyingMinimumMoney;
```

- `public static readonly System.Int32 KMinimumShoppingAmount`  

```csharp
public static readonly System.Int32 KMinimumShoppingAmount;
```


## Constructors

- `public HouseholdBehaviorSystem()`  

```csharp
public HouseholdBehaviorSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public static GetAgeWeight(Game.Prefabs.ResourceData resourceData, Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> citizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizenDatas) : System.Int32`  

```csharp
public static System.Int32 GetAgeWeight(Game.Prefabs.ResourceData resourceData, Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> citizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizenDatas);
```

- `public static GetConsumptionMultiplier(Unity.Mathematics.float2 parameter, System.Int32 householdWealth) : System.Single`  

```csharp
public static System.Single GetConsumptionMultiplier(Unity.Mathematics.float2 parameter, System.Int32 householdWealth);
```

- `public static GetFreeCar(Unity.Entities.Entity household, Unity.Entities.BufferLookup<Game.Vehicles.OwnedVehicle> ownedVehicles, Unity.Entities.ComponentLookup<Game.Vehicles.PersonalCar> personalCars, Unity.Entities.Entity& car) : System.Boolean`  

```csharp
public static System.Boolean GetFreeCar(Unity.Entities.Entity household, Unity.Entities.BufferLookup<Game.Vehicles.OwnedVehicle> ownedVehicles, Unity.Entities.ComponentLookup<Game.Vehicles.PersonalCar> personalCars, Unity.Entities.Entity& car);
```

- `public static GetHighestEducation(Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> citizenBuffer, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens) : System.Int32`  

```csharp
public static System.Int32 GetHighestEducation(Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> citizenBuffer, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens);
```

- `public static GetLastCommutePerCitizen(Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> householdCitizens, Unity.Entities.ComponentLookup<Game.Citizens.Worker> workers) : System.Single`  

```csharp
public static System.Single GetLastCommutePerCitizen(Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> householdCitizens, Unity.Entities.ComponentLookup<Game.Citizens.Worker> workers);
```

- `public static GetResourceShopWeightWithAge(System.Int32 wealth, Game.Economy.Resource resource, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas, System.Int32 carCount, System.Boolean leisureIncluded, Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> citizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizenDatas) : System.Int32`  

```csharp
public static System.Int32 GetResourceShopWeightWithAge(System.Int32 wealth, Game.Economy.Resource resource, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas, System.Int32 carCount, System.Boolean leisureIncluded, Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> citizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizenDatas);
```

- `public static GetResourceShopWeightWithAge(System.Int32 wealth, Game.Prefabs.ResourceData resourceData, System.Int32 carCount, System.Boolean leisureIncluded, Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> citizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizenDatas) : System.Int32`  

```csharp
public static System.Int32 GetResourceShopWeightWithAge(System.Int32 wealth, Game.Prefabs.ResourceData resourceData, System.Int32 carCount, System.Boolean leisureIncluded, Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> citizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizenDatas);
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
```

- `public static GetWeight(System.Int32 wealth, Game.Economy.Resource resource, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas, System.Int32 carCount, System.Boolean leisureIncluded) : System.Int32`  

```csharp
public static System.Int32 GetWeight(System.Int32 wealth, Game.Economy.Resource resource, Game.Prefabs.ResourcePrefabs resourcePrefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas, System.Int32 carCount, System.Boolean leisureIncluded);
```

- `public static GetWeight(System.Int32 wealth, Game.Prefabs.ResourceData resourceData, System.Int32 carCount, System.Boolean leisureIncluded) : System.Int32`  

```csharp
public static System.Int32 GetWeight(System.Int32 wealth, Game.Prefabs.ResourceData resourceData, System.Int32 carCount, System.Boolean leisureIncluded);
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

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Simulation.HouseholdBehaviorSystem+HouseholdTickJob`  
- `Game.Simulation.HouseholdBehaviorSystem+TypeHandle`  

