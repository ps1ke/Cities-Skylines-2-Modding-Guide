# Game.Simulation.CitizenHappinessSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CitizenHappinessSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private Game.Debug.DebugWatchDistribution m_DebugData;
    private Unity.Collections.NativeQueue<Game.Simulation.CitizenHappinessSystem+FactorItem> m_FactorQueue;
    private Unity.Entities.EntityQuery m_CitizenQuery;
    private Unity.Entities.EntityQuery m_HappinessFactorParameterQuery;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
    private Game.Simulation.AirPollutionSystem m_AirPollutionSystem;
    private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem;
    private Game.Simulation.TelecomCoverageSystem m_TelecomCoverageSystem;
    private Game.Buildings.LocalEffectSystem m_LocalEffectSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Triggers.TriggerSystem m_TriggerSystem;
    private Game.Simulation.TaxSystem m_TaxSystem;
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Unity.Entities.EntityQuery m_HealthcareParameterQuery;
    private Unity.Entities.EntityQuery m_ParkParameterQuery;
    private Unity.Entities.EntityQuery m_EducationParameterQuery;
    private Unity.Entities.EntityQuery m_TelecomParameterQuery;
    private Unity.Entities.EntityQuery m_GarbageParameterQuery;
    private Unity.Entities.EntityQuery m_PoliceParameterQuery;
    private Unity.Entities.EntityQuery m_CitizenHappinessParameterQuery;
    private Unity.Entities.EntityQuery m_TimeSettingQuery;
    private Unity.Entities.EntityQuery m_TimeDataQuery;
    private Unity.Collections.NativeArray<Unity.Mathematics.int4> m_HappinessFactors;
    private Unity.Jobs.JobHandle m_LastDeps;
    private Game.Simulation.CitizenHappinessSystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_429327288_0;

    public CitizenHappinessSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private static System.Void AddCompanyHappinessFactors(Unity.Collections.NativeArray<System.Int32> factors, Unity.Entities.Entity property, Unity.Entities.Entity prefab, Unity.Entities.Entity renter, Unity.Entities.Entity renterPrefab, Game.Prefabs.IndustrialProcessData processData, Game.Companies.ServiceCompanyData serviceCompanyData, System.Boolean commercial, System.Int32 level, Unity.Entities.ComponentLookup`1[[Game.Prefabs.OfficeBuilding, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& officeBuildings, Unity.Entities.ComponentLookup`1[[Game.Companies.WorkProvider, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& workProviders, Unity.Entities.BufferLookup`1[[Game.Companies.Employee, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& employees, Unity.Entities.ComponentLookup`1[[Game.Prefabs.WorkplaceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& workplaceDatas, Unity.Entities.ComponentLookup`1[[Game.Companies.ServiceAvailable, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& serviceAvailables, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas, Unity.Entities.BufferLookup`1[[Game.Buildings.Efficiency, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& efficiencies, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingPropertyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildingPropertyDatas, Unity.Entities.BufferLookup`1[[Game.Net.ResourceAvailability, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& availabilities, Unity.Entities.BufferLookup`1[[Game.Companies.TradeCost, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& tradeCosts, Unity.Collections.NativeArray<System.Int32> taxRates, Game.Buildings.Building building, Game.Prefabs.SpawnableBuildingData spawnableData, Game.Prefabs.BuildingData buildingData, Game.Prefabs.ResourcePrefabs resourcePrefabs, Game.Prefabs.EconomyParameterData& economyParameters);
    public System.Void Deserialize<TReader>(TReader reader);
    public static Unity.Mathematics.int2 GetAirPollutionBonuses(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Objects.Transform, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& transforms, Unity.Collections.NativeArray<Game.Simulation.AirPollution> airPollutionMap, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Game.Prefabs.CitizenHappinessParameterData& data);
    public static System.Single GetApartmentWellbeing(System.Single sizePerResident, System.Int32 level);
    public static System.Void GetBuildingHappinessFactors(Unity.Entities.Entity property, Unity.Collections.NativeArray<System.Int32> factors, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.SpawnableBuildingData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& spawnableBuildings, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingPropertyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildingPropertyDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ConsumptionData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& consumptionDatas, Unity.Entities.BufferLookup`1[[Game.City.CityModifier, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& cityModifiers, Unity.Entities.ComponentLookup`1[[Game.Buildings.Building, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildings, Unity.Entities.ComponentLookup`1[[Game.Buildings.ElectricityConsumer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& electricityConsumers, Unity.Entities.ComponentLookup`1[[Game.Buildings.WaterConsumer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& waterConsumers, Unity.Entities.BufferLookup`1[[Game.Net.ServiceCoverage, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& serviceCoverages, Unity.Entities.ComponentLookup`1[[Game.Prefabs.Locked, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& locked, Unity.Entities.ComponentLookup`1[[Game.Objects.Transform, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& transforms, Unity.Entities.ComponentLookup`1[[Game.Buildings.GarbageProducer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& garbageProducers, Unity.Entities.ComponentLookup`1[[Game.Buildings.CrimeProducer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& crimeProducers, Unity.Entities.ComponentLookup`1[[Game.Buildings.MailProducer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& mailProducers, Unity.Entities.ComponentLookup`1[[Game.Prefabs.OfficeBuilding, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& officeBuildings, Unity.Entities.BufferLookup`1[[Game.Buildings.Renter, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& renters, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizenDatas, Unity.Entities.BufferLookup`1[[Game.Citizens.HouseholdCitizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& householdCitizens, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildingDatas, Unity.Entities.ComponentLookup`1[[Game.Companies.CompanyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& companies, Unity.Entities.ComponentLookup`1[[Game.Prefabs.IndustrialProcessData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& industrialProcessDatas, Unity.Entities.ComponentLookup`1[[Game.Companies.WorkProvider, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& workProviders, Unity.Entities.BufferLookup`1[[Game.Companies.Employee, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& employees, Unity.Entities.ComponentLookup`1[[Game.Prefabs.WorkplaceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& workplaceDatas, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.HealthProblem, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& healthProblems, Unity.Entities.ComponentLookup`1[[Game.Companies.ServiceAvailable, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& serviceAvailables, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ZonePropertiesData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& zonePropertiesDatas, Unity.Entities.BufferLookup`1[[Game.Buildings.Efficiency, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& efficiencies, Unity.Entities.ComponentLookup`1[[Game.Companies.ServiceCompanyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& serviceCompanyDatas, Unity.Entities.BufferLookup`1[[Game.Net.ResourceAvailability, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& availabilities, Unity.Entities.BufferLookup`1[[Game.Companies.TradeCost, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& tradeCosts, Game.Prefabs.CitizenHappinessParameterData citizenHappinessParameters, Game.Prefabs.GarbageParameterData garbageParameters, Game.Prefabs.HealthcareParameterData healthcareParameters, Game.Prefabs.ParkParameterData parkParameters, Game.Prefabs.EducationParameterData educationParameters, Game.Prefabs.TelecomParameterData telecomParameters, Game.Prefabs.EconomyParameterData& economyParameters, Unity.Entities.DynamicBuffer<Game.Prefabs.HappinessFactorParameterData> happinessFactorParameters, Unity.Collections.NativeArray<Game.Simulation.GroundPollution> pollutionMap, Unity.Collections.NativeArray<Game.Simulation.NoisePollution> noisePollutionMap, Unity.Collections.NativeArray<Game.Simulation.AirPollution> airPollutionMap, Game.Simulation.CellMapData<Game.Simulation.TelecomCoverage> telecomCoverage, Unity.Entities.Entity city, Unity.Collections.NativeArray<System.Int32> taxRates, Unity.Collections.NativeArray<Unity.Entities.Entity> processes, Game.Prefabs.ResourcePrefabs resourcePrefabs, System.Single relativeElectricityFee, System.Single relativeWaterFee);
    public static Unity.Mathematics.int2 GetCachedWelfareBonuses(System.Single cachedValue, System.Int32 currentHappiness);
    public static Unity.Mathematics.int2 GetConsumptionBonuses(System.Single dailyConsumption, System.Int32 citizens, Game.Prefabs.CitizenHappinessParameterData& data);
    public static System.Single GetConsumptionHappinessDifferential(System.Single dailyConsumption, System.Int32 citizens);
    public static Unity.Mathematics.int2 GetCrimeBonuses(Game.Citizens.CrimeVictim crimeVictim, Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Buildings.CrimeProducer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& crimes, Unity.Entities.ComponentLookup`1[[Game.Prefabs.Locked, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& locked, Unity.Entities.Entity policeService, Game.Prefabs.CitizenHappinessParameterData& data);
    public static Unity.Mathematics.int2 GetDeathPenalty(Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> householdCitizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.HealthProblem, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& healthProblems, Game.Prefabs.CitizenHappinessParameterData& data);
    public static Unity.Mathematics.int2 GetEducationBonuses(System.Single curvePosition, Unity.Entities.DynamicBuffer<Game.Net.ServiceCoverage> serviceCoverage, Unity.Entities.ComponentLookup`1[[Game.Prefabs.Locked, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& locked, Unity.Entities.Entity educationService, Game.Prefabs.CitizenHappinessParameterData& data, System.Int32 children);
    public static Unity.Mathematics.int2 GetElectricityFeeBonuses(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Buildings.ElectricityConsumer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& electricityConsumers, System.Single relativeFee, Game.Prefabs.CitizenHappinessParameterData& data);
    public static Unity.Mathematics.int2 GetElectricityFeeBonuses(System.Single relativeFee, Game.Prefabs.CitizenHappinessParameterData& data);
    public static System.Int32 GetElectricityFeeHappinessEffect(System.Single relativeFee, Game.Prefabs.CitizenHappinessParameterData& data);
    public static Unity.Mathematics.int2 GetElectricitySupplyBonuses(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Buildings.ElectricityConsumer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& electricityConsumers, Game.Prefabs.CitizenHappinessParameterData& data);
    public static Unity.Mathematics.int2 GetEntertainmentBonuses(System.Single curvePosition, Unity.Entities.DynamicBuffer<Game.Net.ServiceCoverage> serviceCoverage, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Unity.Entities.ComponentLookup`1[[Game.Prefabs.Locked, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& locked, Unity.Entities.Entity entertainmentService, Game.Prefabs.CitizenHappinessParameterData& data);
    private static System.Int32 GetFactor(System.Single profit, System.Single defaultProfit);
    private static System.Int32 GetFactorIndex(Game.Simulation.CitizenHappinessSystem+HappinessFactor factor, System.UInt32 updateFrame);
    public static System.Single GetFreetimeWellbeing(System.Int32 freetime);
    public static System.Single GetFreetimeWellbeingDifferential(System.Int32 freetime);
    public static Unity.Mathematics.int2 GetGarbageBonuses(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Buildings.GarbageProducer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& garbages, Unity.Entities.ComponentLookup`1[[Game.Prefabs.Locked, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& locked, Unity.Entities.Entity garbageService, Game.Prefabs.GarbageParameterData& data);
    public static Unity.Mathematics.int2 GetGroundPollutionBonuses(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Objects.Transform, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& transforms, Unity.Collections.NativeArray<Game.Simulation.GroundPollution> pollutionMap, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Game.Prefabs.CitizenHappinessParameterData& data);
    public Unity.Mathematics.float3 GetHappinessFactor(Game.Simulation.CitizenHappinessSystem+HappinessFactor factor, Unity.Entities.DynamicBuffer<Game.Prefabs.HappinessFactorParameterData> parameters, Unity.Entities.ComponentLookup`1[[Game.Prefabs.Locked, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& locked);
    private static Unity.Mathematics.float3 GetHappinessFactor(Game.Simulation.CitizenHappinessSystem+HappinessFactor factor, Unity.Collections.NativeArray<Unity.Mathematics.int4> happinessFactors, Unity.Entities.DynamicBuffer<Game.Prefabs.HappinessFactorParameterData> parameters, Unity.Entities.ComponentLookup`1[[Game.Prefabs.Locked, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& locked);
    public static Unity.Mathematics.int2 GetHealthcareBonuses(System.Single curvePosition, Unity.Entities.DynamicBuffer<Game.Net.ServiceCoverage> serviceCoverage, Unity.Entities.ComponentLookup`1[[Game.Prefabs.Locked, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& locked, Unity.Entities.Entity healthcareService, Game.Prefabs.CitizenHappinessParameterData& data);
    public static Unity.Mathematics.int2 GetHomelessBonuses(Game.Prefabs.CitizenHappinessParameterData& data);
    public static Unity.Mathematics.int2 GetLeisureBonuses(System.Byte leisureValue);
    public static Unity.Mathematics.int2 GetMailBonuses(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Buildings.MailProducer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& mails, Unity.Entities.ComponentLookup`1[[Game.Prefabs.Locked, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& locked, Unity.Entities.Entity telecomService, Game.Prefabs.CitizenHappinessParameterData& data);
    public static System.Int32 GetMaxHealth(System.Single ageInYears);
    public static Unity.Mathematics.int2 GetNoiseBonuses(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Objects.Transform, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& transforms, Unity.Collections.NativeArray<Game.Simulation.NoisePollution> noiseMap, Game.Prefabs.CitizenHappinessParameterData& data);
    public static Unity.Mathematics.int2 GetSewageBonuses(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Buildings.WaterConsumer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& waterConsumers, Game.Prefabs.CitizenHappinessParameterData& data);
    public static Unity.Mathematics.int2 GetSicknessBonuses(System.Boolean hasHealthProblem, Game.Prefabs.CitizenHappinessParameterData& data);
    public static Unity.Mathematics.int2 GetTaxBonuses(System.Int32 educationLevel, Unity.Collections.NativeArray<System.Int32> taxRates, Game.Prefabs.CitizenHappinessParameterData& data);
    public static Unity.Mathematics.int2 GetTelecomBonuses(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Objects.Transform, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& transforms, Game.Simulation.CellMapData<Game.Simulation.TelecomCoverage> telecomCoverage, Unity.Entities.ComponentLookup`1[[Game.Prefabs.Locked, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& locked, Unity.Entities.Entity telecomService, Game.Prefabs.CitizenHappinessParameterData& data);
    private static Game.Triggers.TriggerType GetTriggerTypeForHappinessFactor(Game.Simulation.CitizenHappinessSystem+HappinessFactor factor);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public static Unity.Mathematics.int2 GetWaterFeeBonuses(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Buildings.WaterConsumer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& waterConsumers, System.Single relativeFee, Game.Prefabs.CitizenHappinessParameterData& data);
    public static Unity.Mathematics.int2 GetWaterFeeBonuses(System.Single relativeFee, Game.Prefabs.CitizenHappinessParameterData& data);
    public static System.Int32 GetWaterFeeHappinessEffect(System.Single relativeFee, Game.Prefabs.CitizenHappinessParameterData& data);
    public static Unity.Mathematics.int2 GetWaterPollutionBonuses(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Buildings.WaterConsumer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& waterConsumers, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Game.Prefabs.CitizenHappinessParameterData& data);
    public static Unity.Mathematics.int2 GetWaterSupplyBonuses(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Buildings.WaterConsumer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& waterConsumers, Game.Prefabs.CitizenHappinessParameterData& data);
    public static System.Single GetWelfareValue(System.Single curvePosition, Unity.Entities.DynamicBuffer<Game.Net.ServiceCoverage> serviceCoverage, Game.Prefabs.CitizenHappinessParameterData& data);
    public static Unity.Mathematics.int2 GetWellfareBonuses(System.Single curvePosition, Unity.Entities.DynamicBuffer<Game.Net.ServiceCoverage> serviceCoverage, Game.Prefabs.CitizenHappinessParameterData& data, System.Int32 currentHappiness);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Game.Debug.DebugWatchDistribution m_DebugData`  

```csharp
private Game.Debug.DebugWatchDistribution m_DebugData;
```

- `private Unity.Collections.NativeQueue<Game.Simulation.CitizenHappinessSystem+FactorItem> m_FactorQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.Simulation.CitizenHappinessSystem+FactorItem> m_FactorQueue;
```

- `private Unity.Entities.EntityQuery m_CitizenQuery`  

```csharp
private Unity.Entities.EntityQuery m_CitizenQuery;
```

- `private Unity.Entities.EntityQuery m_HappinessFactorParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_HappinessFactorParameterQuery;
```

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

- `private Game.Simulation.TelecomCoverageSystem m_TelecomCoverageSystem`  

```csharp
private Game.Simulation.TelecomCoverageSystem m_TelecomCoverageSystem;
```

- `private Game.Buildings.LocalEffectSystem m_LocalEffectSystem`  

```csharp
private Game.Buildings.LocalEffectSystem m_LocalEffectSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Triggers.TriggerSystem m_TriggerSystem`  

```csharp
private Game.Triggers.TriggerSystem m_TriggerSystem;
```

- `private Game.Simulation.TaxSystem m_TaxSystem`  

```csharp
private Game.Simulation.TaxSystem m_TaxSystem;
```

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Unity.Entities.EntityQuery m_HealthcareParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_HealthcareParameterQuery;
```

- `private Unity.Entities.EntityQuery m_ParkParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_ParkParameterQuery;
```

- `private Unity.Entities.EntityQuery m_EducationParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EducationParameterQuery;
```

- `private Unity.Entities.EntityQuery m_TelecomParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_TelecomParameterQuery;
```

- `private Unity.Entities.EntityQuery m_GarbageParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_GarbageParameterQuery;
```

- `private Unity.Entities.EntityQuery m_PoliceParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_PoliceParameterQuery;
```

- `private Unity.Entities.EntityQuery m_CitizenHappinessParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_CitizenHappinessParameterQuery;
```

- `private Unity.Entities.EntityQuery m_TimeSettingQuery`  

```csharp
private Unity.Entities.EntityQuery m_TimeSettingQuery;
```

- `private Unity.Entities.EntityQuery m_TimeDataQuery`  

```csharp
private Unity.Entities.EntityQuery m_TimeDataQuery;
```

- `private Unity.Collections.NativeArray<Unity.Mathematics.int4> m_HappinessFactors`  

```csharp
private Unity.Collections.NativeArray<Unity.Mathematics.int4> m_HappinessFactors;
```

- `private Unity.Jobs.JobHandle m_LastDeps`  

```csharp
private Unity.Jobs.JobHandle m_LastDeps;
```

- `private Game.Simulation.CitizenHappinessSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.CitizenHappinessSystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_429327288_0`  

```csharp
private Unity.Entities.EntityQuery __query_429327288_0;
```


## Constructors

- `public CitizenHappinessSystem()`  

```csharp
public CitizenHappinessSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private static AddCompanyHappinessFactors(Unity.Collections.NativeArray<System.Int32> factors, Unity.Entities.Entity property, Unity.Entities.Entity prefab, Unity.Entities.Entity renter, Unity.Entities.Entity renterPrefab, Game.Prefabs.IndustrialProcessData processData, Game.Companies.ServiceCompanyData serviceCompanyData, System.Boolean commercial, System.Int32 level, Unity.Entities.ComponentLookup`1[[Game.Prefabs.OfficeBuilding, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& officeBuildings, Unity.Entities.ComponentLookup`1[[Game.Companies.WorkProvider, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& workProviders, Unity.Entities.BufferLookup`1[[Game.Companies.Employee, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& employees, Unity.Entities.ComponentLookup`1[[Game.Prefabs.WorkplaceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& workplaceDatas, Unity.Entities.ComponentLookup`1[[Game.Companies.ServiceAvailable, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& serviceAvailables, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas, Unity.Entities.BufferLookup`1[[Game.Buildings.Efficiency, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& efficiencies, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingPropertyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildingPropertyDatas, Unity.Entities.BufferLookup`1[[Game.Net.ResourceAvailability, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& availabilities, Unity.Entities.BufferLookup`1[[Game.Companies.TradeCost, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& tradeCosts, Unity.Collections.NativeArray<System.Int32> taxRates, Game.Buildings.Building building, Game.Prefabs.SpawnableBuildingData spawnableData, Game.Prefabs.BuildingData buildingData, Game.Prefabs.ResourcePrefabs resourcePrefabs, Game.Prefabs.EconomyParameterData& economyParameters) : System.Void`  

```csharp
private static System.Void AddCompanyHappinessFactors(Unity.Collections.NativeArray<System.Int32> factors, Unity.Entities.Entity property, Unity.Entities.Entity prefab, Unity.Entities.Entity renter, Unity.Entities.Entity renterPrefab, Game.Prefabs.IndustrialProcessData processData, Game.Companies.ServiceCompanyData serviceCompanyData, System.Boolean commercial, System.Int32 level, Unity.Entities.ComponentLookup`1[[Game.Prefabs.OfficeBuilding, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& officeBuildings, Unity.Entities.ComponentLookup`1[[Game.Companies.WorkProvider, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& workProviders, Unity.Entities.BufferLookup`1[[Game.Companies.Employee, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& employees, Unity.Entities.ComponentLookup`1[[Game.Prefabs.WorkplaceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& workplaceDatas, Unity.Entities.ComponentLookup`1[[Game.Companies.ServiceAvailable, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& serviceAvailables, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas, Unity.Entities.BufferLookup`1[[Game.Buildings.Efficiency, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& efficiencies, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingPropertyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildingPropertyDatas, Unity.Entities.BufferLookup`1[[Game.Net.ResourceAvailability, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& availabilities, Unity.Entities.BufferLookup`1[[Game.Companies.TradeCost, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& tradeCosts, Unity.Collections.NativeArray<System.Int32> taxRates, Game.Buildings.Building building, Game.Prefabs.SpawnableBuildingData spawnableData, Game.Prefabs.BuildingData buildingData, Game.Prefabs.ResourcePrefabs resourcePrefabs, Game.Prefabs.EconomyParameterData& economyParameters);
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public static GetAirPollutionBonuses(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Objects.Transform, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& transforms, Unity.Collections.NativeArray<Game.Simulation.AirPollution> airPollutionMap, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Game.Prefabs.CitizenHappinessParameterData& data) : Unity.Mathematics.int2`  

```csharp
public static Unity.Mathematics.int2 GetAirPollutionBonuses(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Objects.Transform, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& transforms, Unity.Collections.NativeArray<Game.Simulation.AirPollution> airPollutionMap, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Game.Prefabs.CitizenHappinessParameterData& data);
```

- `public static GetApartmentWellbeing(System.Single sizePerResident, System.Int32 level) : System.Single`  

```csharp
public static System.Single GetApartmentWellbeing(System.Single sizePerResident, System.Int32 level);
```

- `public static GetBuildingHappinessFactors(Unity.Entities.Entity property, Unity.Collections.NativeArray<System.Int32> factors, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.SpawnableBuildingData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& spawnableBuildings, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingPropertyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildingPropertyDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ConsumptionData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& consumptionDatas, Unity.Entities.BufferLookup`1[[Game.City.CityModifier, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& cityModifiers, Unity.Entities.ComponentLookup`1[[Game.Buildings.Building, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildings, Unity.Entities.ComponentLookup`1[[Game.Buildings.ElectricityConsumer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& electricityConsumers, Unity.Entities.ComponentLookup`1[[Game.Buildings.WaterConsumer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& waterConsumers, Unity.Entities.BufferLookup`1[[Game.Net.ServiceCoverage, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& serviceCoverages, Unity.Entities.ComponentLookup`1[[Game.Prefabs.Locked, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& locked, Unity.Entities.ComponentLookup`1[[Game.Objects.Transform, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& transforms, Unity.Entities.ComponentLookup`1[[Game.Buildings.GarbageProducer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& garbageProducers, Unity.Entities.ComponentLookup`1[[Game.Buildings.CrimeProducer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& crimeProducers, Unity.Entities.ComponentLookup`1[[Game.Buildings.MailProducer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& mailProducers, Unity.Entities.ComponentLookup`1[[Game.Prefabs.OfficeBuilding, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& officeBuildings, Unity.Entities.BufferLookup`1[[Game.Buildings.Renter, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& renters, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizenDatas, Unity.Entities.BufferLookup`1[[Game.Citizens.HouseholdCitizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& householdCitizens, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildingDatas, Unity.Entities.ComponentLookup`1[[Game.Companies.CompanyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& companies, Unity.Entities.ComponentLookup`1[[Game.Prefabs.IndustrialProcessData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& industrialProcessDatas, Unity.Entities.ComponentLookup`1[[Game.Companies.WorkProvider, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& workProviders, Unity.Entities.BufferLookup`1[[Game.Companies.Employee, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& employees, Unity.Entities.ComponentLookup`1[[Game.Prefabs.WorkplaceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& workplaceDatas, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.HealthProblem, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& healthProblems, Unity.Entities.ComponentLookup`1[[Game.Companies.ServiceAvailable, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& serviceAvailables, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ZonePropertiesData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& zonePropertiesDatas, Unity.Entities.BufferLookup`1[[Game.Buildings.Efficiency, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& efficiencies, Unity.Entities.ComponentLookup`1[[Game.Companies.ServiceCompanyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& serviceCompanyDatas, Unity.Entities.BufferLookup`1[[Game.Net.ResourceAvailability, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& availabilities, Unity.Entities.BufferLookup`1[[Game.Companies.TradeCost, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& tradeCosts, Game.Prefabs.CitizenHappinessParameterData citizenHappinessParameters, Game.Prefabs.GarbageParameterData garbageParameters, Game.Prefabs.HealthcareParameterData healthcareParameters, Game.Prefabs.ParkParameterData parkParameters, Game.Prefabs.EducationParameterData educationParameters, Game.Prefabs.TelecomParameterData telecomParameters, Game.Prefabs.EconomyParameterData& economyParameters, Unity.Entities.DynamicBuffer<Game.Prefabs.HappinessFactorParameterData> happinessFactorParameters, Unity.Collections.NativeArray<Game.Simulation.GroundPollution> pollutionMap, Unity.Collections.NativeArray<Game.Simulation.NoisePollution> noisePollutionMap, Unity.Collections.NativeArray<Game.Simulation.AirPollution> airPollutionMap, Game.Simulation.CellMapData<Game.Simulation.TelecomCoverage> telecomCoverage, Unity.Entities.Entity city, Unity.Collections.NativeArray<System.Int32> taxRates, Unity.Collections.NativeArray<Unity.Entities.Entity> processes, Game.Prefabs.ResourcePrefabs resourcePrefabs, System.Single relativeElectricityFee, System.Single relativeWaterFee) : System.Void`  

```csharp
public static System.Void GetBuildingHappinessFactors(Unity.Entities.Entity property, Unity.Collections.NativeArray<System.Int32> factors, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.SpawnableBuildingData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& spawnableBuildings, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingPropertyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildingPropertyDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ConsumptionData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& consumptionDatas, Unity.Entities.BufferLookup`1[[Game.City.CityModifier, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& cityModifiers, Unity.Entities.ComponentLookup`1[[Game.Buildings.Building, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildings, Unity.Entities.ComponentLookup`1[[Game.Buildings.ElectricityConsumer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& electricityConsumers, Unity.Entities.ComponentLookup`1[[Game.Buildings.WaterConsumer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& waterConsumers, Unity.Entities.BufferLookup`1[[Game.Net.ServiceCoverage, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& serviceCoverages, Unity.Entities.ComponentLookup`1[[Game.Prefabs.Locked, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& locked, Unity.Entities.ComponentLookup`1[[Game.Objects.Transform, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& transforms, Unity.Entities.ComponentLookup`1[[Game.Buildings.GarbageProducer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& garbageProducers, Unity.Entities.ComponentLookup`1[[Game.Buildings.CrimeProducer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& crimeProducers, Unity.Entities.ComponentLookup`1[[Game.Buildings.MailProducer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& mailProducers, Unity.Entities.ComponentLookup`1[[Game.Prefabs.OfficeBuilding, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& officeBuildings, Unity.Entities.BufferLookup`1[[Game.Buildings.Renter, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& renters, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizenDatas, Unity.Entities.BufferLookup`1[[Game.Citizens.HouseholdCitizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& householdCitizens, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildingDatas, Unity.Entities.ComponentLookup`1[[Game.Companies.CompanyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& companies, Unity.Entities.ComponentLookup`1[[Game.Prefabs.IndustrialProcessData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& industrialProcessDatas, Unity.Entities.ComponentLookup`1[[Game.Companies.WorkProvider, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& workProviders, Unity.Entities.BufferLookup`1[[Game.Companies.Employee, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& employees, Unity.Entities.ComponentLookup`1[[Game.Prefabs.WorkplaceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& workplaceDatas, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.HealthProblem, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& healthProblems, Unity.Entities.ComponentLookup`1[[Game.Companies.ServiceAvailable, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& serviceAvailables, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ZonePropertiesData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& zonePropertiesDatas, Unity.Entities.BufferLookup`1[[Game.Buildings.Efficiency, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& efficiencies, Unity.Entities.ComponentLookup`1[[Game.Companies.ServiceCompanyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& serviceCompanyDatas, Unity.Entities.BufferLookup`1[[Game.Net.ResourceAvailability, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& availabilities, Unity.Entities.BufferLookup`1[[Game.Companies.TradeCost, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& tradeCosts, Game.Prefabs.CitizenHappinessParameterData citizenHappinessParameters, Game.Prefabs.GarbageParameterData garbageParameters, Game.Prefabs.HealthcareParameterData healthcareParameters, Game.Prefabs.ParkParameterData parkParameters, Game.Prefabs.EducationParameterData educationParameters, Game.Prefabs.TelecomParameterData telecomParameters, Game.Prefabs.EconomyParameterData& economyParameters, Unity.Entities.DynamicBuffer<Game.Prefabs.HappinessFactorParameterData> happinessFactorParameters, Unity.Collections.NativeArray<Game.Simulation.GroundPollution> pollutionMap, Unity.Collections.NativeArray<Game.Simulation.NoisePollution> noisePollutionMap, Unity.Collections.NativeArray<Game.Simulation.AirPollution> airPollutionMap, Game.Simulation.CellMapData<Game.Simulation.TelecomCoverage> telecomCoverage, Unity.Entities.Entity city, Unity.Collections.NativeArray<System.Int32> taxRates, Unity.Collections.NativeArray<Unity.Entities.Entity> processes, Game.Prefabs.ResourcePrefabs resourcePrefabs, System.Single relativeElectricityFee, System.Single relativeWaterFee);
```

- `public static GetCachedWelfareBonuses(System.Single cachedValue, System.Int32 currentHappiness) : Unity.Mathematics.int2`  

```csharp
public static Unity.Mathematics.int2 GetCachedWelfareBonuses(System.Single cachedValue, System.Int32 currentHappiness);
```

- `public static GetConsumptionBonuses(System.Single dailyConsumption, System.Int32 citizens, Game.Prefabs.CitizenHappinessParameterData& data) : Unity.Mathematics.int2`  

```csharp
public static Unity.Mathematics.int2 GetConsumptionBonuses(System.Single dailyConsumption, System.Int32 citizens, Game.Prefabs.CitizenHappinessParameterData& data);
```

- `public static GetConsumptionHappinessDifferential(System.Single dailyConsumption, System.Int32 citizens) : System.Single`  

```csharp
public static System.Single GetConsumptionHappinessDifferential(System.Single dailyConsumption, System.Int32 citizens);
```

- `public static GetCrimeBonuses(Game.Citizens.CrimeVictim crimeVictim, Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Buildings.CrimeProducer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& crimes, Unity.Entities.ComponentLookup`1[[Game.Prefabs.Locked, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& locked, Unity.Entities.Entity policeService, Game.Prefabs.CitizenHappinessParameterData& data) : Unity.Mathematics.int2`  

```csharp
public static Unity.Mathematics.int2 GetCrimeBonuses(Game.Citizens.CrimeVictim crimeVictim, Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Buildings.CrimeProducer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& crimes, Unity.Entities.ComponentLookup`1[[Game.Prefabs.Locked, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& locked, Unity.Entities.Entity policeService, Game.Prefabs.CitizenHappinessParameterData& data);
```

- `public static GetDeathPenalty(Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> householdCitizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.HealthProblem, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& healthProblems, Game.Prefabs.CitizenHappinessParameterData& data) : Unity.Mathematics.int2`  

```csharp
public static Unity.Mathematics.int2 GetDeathPenalty(Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> householdCitizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.HealthProblem, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& healthProblems, Game.Prefabs.CitizenHappinessParameterData& data);
```

- `public static GetEducationBonuses(System.Single curvePosition, Unity.Entities.DynamicBuffer<Game.Net.ServiceCoverage> serviceCoverage, Unity.Entities.ComponentLookup`1[[Game.Prefabs.Locked, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& locked, Unity.Entities.Entity educationService, Game.Prefabs.CitizenHappinessParameterData& data, System.Int32 children) : Unity.Mathematics.int2`  

```csharp
public static Unity.Mathematics.int2 GetEducationBonuses(System.Single curvePosition, Unity.Entities.DynamicBuffer<Game.Net.ServiceCoverage> serviceCoverage, Unity.Entities.ComponentLookup`1[[Game.Prefabs.Locked, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& locked, Unity.Entities.Entity educationService, Game.Prefabs.CitizenHappinessParameterData& data, System.Int32 children);
```

- `public static GetElectricityFeeBonuses(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Buildings.ElectricityConsumer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& electricityConsumers, System.Single relativeFee, Game.Prefabs.CitizenHappinessParameterData& data) : Unity.Mathematics.int2`  

```csharp
public static Unity.Mathematics.int2 GetElectricityFeeBonuses(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Buildings.ElectricityConsumer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& electricityConsumers, System.Single relativeFee, Game.Prefabs.CitizenHappinessParameterData& data);
```

- `public static GetElectricityFeeBonuses(System.Single relativeFee, Game.Prefabs.CitizenHappinessParameterData& data) : Unity.Mathematics.int2`  

```csharp
public static Unity.Mathematics.int2 GetElectricityFeeBonuses(System.Single relativeFee, Game.Prefabs.CitizenHappinessParameterData& data);
```

- `public static GetElectricityFeeHappinessEffect(System.Single relativeFee, Game.Prefabs.CitizenHappinessParameterData& data) : System.Int32`  

```csharp
public static System.Int32 GetElectricityFeeHappinessEffect(System.Single relativeFee, Game.Prefabs.CitizenHappinessParameterData& data);
```

- `public static GetElectricitySupplyBonuses(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Buildings.ElectricityConsumer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& electricityConsumers, Game.Prefabs.CitizenHappinessParameterData& data) : Unity.Mathematics.int2`  

```csharp
public static Unity.Mathematics.int2 GetElectricitySupplyBonuses(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Buildings.ElectricityConsumer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& electricityConsumers, Game.Prefabs.CitizenHappinessParameterData& data);
```

- `public static GetEntertainmentBonuses(System.Single curvePosition, Unity.Entities.DynamicBuffer<Game.Net.ServiceCoverage> serviceCoverage, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Unity.Entities.ComponentLookup`1[[Game.Prefabs.Locked, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& locked, Unity.Entities.Entity entertainmentService, Game.Prefabs.CitizenHappinessParameterData& data) : Unity.Mathematics.int2`  

```csharp
public static Unity.Mathematics.int2 GetEntertainmentBonuses(System.Single curvePosition, Unity.Entities.DynamicBuffer<Game.Net.ServiceCoverage> serviceCoverage, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Unity.Entities.ComponentLookup`1[[Game.Prefabs.Locked, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& locked, Unity.Entities.Entity entertainmentService, Game.Prefabs.CitizenHappinessParameterData& data);
```

- `private static GetFactor(System.Single profit, System.Single defaultProfit) : System.Int32`  

```csharp
private static System.Int32 GetFactor(System.Single profit, System.Single defaultProfit);
```

- `private static GetFactorIndex(Game.Simulation.CitizenHappinessSystem+HappinessFactor factor, System.UInt32 updateFrame) : System.Int32`  

```csharp
private static System.Int32 GetFactorIndex(Game.Simulation.CitizenHappinessSystem+HappinessFactor factor, System.UInt32 updateFrame);
```

- `public static GetFreetimeWellbeing(System.Int32 freetime) : System.Single`  

```csharp
public static System.Single GetFreetimeWellbeing(System.Int32 freetime);
```

- `public static GetFreetimeWellbeingDifferential(System.Int32 freetime) : System.Single`  

```csharp
public static System.Single GetFreetimeWellbeingDifferential(System.Int32 freetime);
```

- `public static GetGarbageBonuses(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Buildings.GarbageProducer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& garbages, Unity.Entities.ComponentLookup`1[[Game.Prefabs.Locked, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& locked, Unity.Entities.Entity garbageService, Game.Prefabs.GarbageParameterData& data) : Unity.Mathematics.int2`  

```csharp
public static Unity.Mathematics.int2 GetGarbageBonuses(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Buildings.GarbageProducer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& garbages, Unity.Entities.ComponentLookup`1[[Game.Prefabs.Locked, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& locked, Unity.Entities.Entity garbageService, Game.Prefabs.GarbageParameterData& data);
```

- `public static GetGroundPollutionBonuses(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Objects.Transform, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& transforms, Unity.Collections.NativeArray<Game.Simulation.GroundPollution> pollutionMap, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Game.Prefabs.CitizenHappinessParameterData& data) : Unity.Mathematics.int2`  

```csharp
public static Unity.Mathematics.int2 GetGroundPollutionBonuses(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Objects.Transform, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& transforms, Unity.Collections.NativeArray<Game.Simulation.GroundPollution> pollutionMap, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Game.Prefabs.CitizenHappinessParameterData& data);
```

- `public GetHappinessFactor(Game.Simulation.CitizenHappinessSystem+HappinessFactor factor, Unity.Entities.DynamicBuffer<Game.Prefabs.HappinessFactorParameterData> parameters, Unity.Entities.ComponentLookup`1[[Game.Prefabs.Locked, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& locked) : Unity.Mathematics.float3`  

```csharp
public Unity.Mathematics.float3 GetHappinessFactor(Game.Simulation.CitizenHappinessSystem+HappinessFactor factor, Unity.Entities.DynamicBuffer<Game.Prefabs.HappinessFactorParameterData> parameters, Unity.Entities.ComponentLookup`1[[Game.Prefabs.Locked, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& locked);
```

- `private static GetHappinessFactor(Game.Simulation.CitizenHappinessSystem+HappinessFactor factor, Unity.Collections.NativeArray<Unity.Mathematics.int4> happinessFactors, Unity.Entities.DynamicBuffer<Game.Prefabs.HappinessFactorParameterData> parameters, Unity.Entities.ComponentLookup`1[[Game.Prefabs.Locked, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& locked) : Unity.Mathematics.float3`  

```csharp
private static Unity.Mathematics.float3 GetHappinessFactor(Game.Simulation.CitizenHappinessSystem+HappinessFactor factor, Unity.Collections.NativeArray<Unity.Mathematics.int4> happinessFactors, Unity.Entities.DynamicBuffer<Game.Prefabs.HappinessFactorParameterData> parameters, Unity.Entities.ComponentLookup`1[[Game.Prefabs.Locked, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& locked);
```

- `public static GetHealthcareBonuses(System.Single curvePosition, Unity.Entities.DynamicBuffer<Game.Net.ServiceCoverage> serviceCoverage, Unity.Entities.ComponentLookup`1[[Game.Prefabs.Locked, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& locked, Unity.Entities.Entity healthcareService, Game.Prefabs.CitizenHappinessParameterData& data) : Unity.Mathematics.int2`  

```csharp
public static Unity.Mathematics.int2 GetHealthcareBonuses(System.Single curvePosition, Unity.Entities.DynamicBuffer<Game.Net.ServiceCoverage> serviceCoverage, Unity.Entities.ComponentLookup`1[[Game.Prefabs.Locked, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& locked, Unity.Entities.Entity healthcareService, Game.Prefabs.CitizenHappinessParameterData& data);
```

- `public static GetHomelessBonuses(Game.Prefabs.CitizenHappinessParameterData& data) : Unity.Mathematics.int2`  

```csharp
public static Unity.Mathematics.int2 GetHomelessBonuses(Game.Prefabs.CitizenHappinessParameterData& data);
```

- `public static GetLeisureBonuses(System.Byte leisureValue) : Unity.Mathematics.int2`  

```csharp
public static Unity.Mathematics.int2 GetLeisureBonuses(System.Byte leisureValue);
```

- `public static GetMailBonuses(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Buildings.MailProducer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& mails, Unity.Entities.ComponentLookup`1[[Game.Prefabs.Locked, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& locked, Unity.Entities.Entity telecomService, Game.Prefabs.CitizenHappinessParameterData& data) : Unity.Mathematics.int2`  

```csharp
public static Unity.Mathematics.int2 GetMailBonuses(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Buildings.MailProducer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& mails, Unity.Entities.ComponentLookup`1[[Game.Prefabs.Locked, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& locked, Unity.Entities.Entity telecomService, Game.Prefabs.CitizenHappinessParameterData& data);
```

- `public static GetMaxHealth(System.Single ageInYears) : System.Int32`  

```csharp
public static System.Int32 GetMaxHealth(System.Single ageInYears);
```

- `public static GetNoiseBonuses(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Objects.Transform, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& transforms, Unity.Collections.NativeArray<Game.Simulation.NoisePollution> noiseMap, Game.Prefabs.CitizenHappinessParameterData& data) : Unity.Mathematics.int2`  

```csharp
public static Unity.Mathematics.int2 GetNoiseBonuses(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Objects.Transform, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& transforms, Unity.Collections.NativeArray<Game.Simulation.NoisePollution> noiseMap, Game.Prefabs.CitizenHappinessParameterData& data);
```

- `public static GetSewageBonuses(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Buildings.WaterConsumer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& waterConsumers, Game.Prefabs.CitizenHappinessParameterData& data) : Unity.Mathematics.int2`  

```csharp
public static Unity.Mathematics.int2 GetSewageBonuses(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Buildings.WaterConsumer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& waterConsumers, Game.Prefabs.CitizenHappinessParameterData& data);
```

- `public static GetSicknessBonuses(System.Boolean hasHealthProblem, Game.Prefabs.CitizenHappinessParameterData& data) : Unity.Mathematics.int2`  

```csharp
public static Unity.Mathematics.int2 GetSicknessBonuses(System.Boolean hasHealthProblem, Game.Prefabs.CitizenHappinessParameterData& data);
```

- `public static GetTaxBonuses(System.Int32 educationLevel, Unity.Collections.NativeArray<System.Int32> taxRates, Game.Prefabs.CitizenHappinessParameterData& data) : Unity.Mathematics.int2`  

```csharp
public static Unity.Mathematics.int2 GetTaxBonuses(System.Int32 educationLevel, Unity.Collections.NativeArray<System.Int32> taxRates, Game.Prefabs.CitizenHappinessParameterData& data);
```

- `public static GetTelecomBonuses(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Objects.Transform, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& transforms, Game.Simulation.CellMapData<Game.Simulation.TelecomCoverage> telecomCoverage, Unity.Entities.ComponentLookup`1[[Game.Prefabs.Locked, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& locked, Unity.Entities.Entity telecomService, Game.Prefabs.CitizenHappinessParameterData& data) : Unity.Mathematics.int2`  

```csharp
public static Unity.Mathematics.int2 GetTelecomBonuses(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Objects.Transform, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& transforms, Game.Simulation.CellMapData<Game.Simulation.TelecomCoverage> telecomCoverage, Unity.Entities.ComponentLookup`1[[Game.Prefabs.Locked, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& locked, Unity.Entities.Entity telecomService, Game.Prefabs.CitizenHappinessParameterData& data);
```

- `private static GetTriggerTypeForHappinessFactor(Game.Simulation.CitizenHappinessSystem+HappinessFactor factor) : Game.Triggers.TriggerType`  

```csharp
private static Game.Triggers.TriggerType GetTriggerTypeForHappinessFactor(Game.Simulation.CitizenHappinessSystem+HappinessFactor factor);
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
```

- `public static GetWaterFeeBonuses(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Buildings.WaterConsumer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& waterConsumers, System.Single relativeFee, Game.Prefabs.CitizenHappinessParameterData& data) : Unity.Mathematics.int2`  

```csharp
public static Unity.Mathematics.int2 GetWaterFeeBonuses(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Buildings.WaterConsumer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& waterConsumers, System.Single relativeFee, Game.Prefabs.CitizenHappinessParameterData& data);
```

- `public static GetWaterFeeBonuses(System.Single relativeFee, Game.Prefabs.CitizenHappinessParameterData& data) : Unity.Mathematics.int2`  

```csharp
public static Unity.Mathematics.int2 GetWaterFeeBonuses(System.Single relativeFee, Game.Prefabs.CitizenHappinessParameterData& data);
```

- `public static GetWaterFeeHappinessEffect(System.Single relativeFee, Game.Prefabs.CitizenHappinessParameterData& data) : System.Int32`  

```csharp
public static System.Int32 GetWaterFeeHappinessEffect(System.Single relativeFee, Game.Prefabs.CitizenHappinessParameterData& data);
```

- `public static GetWaterPollutionBonuses(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Buildings.WaterConsumer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& waterConsumers, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Game.Prefabs.CitizenHappinessParameterData& data) : Unity.Mathematics.int2`  

```csharp
public static Unity.Mathematics.int2 GetWaterPollutionBonuses(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Buildings.WaterConsumer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& waterConsumers, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Game.Prefabs.CitizenHappinessParameterData& data);
```

- `public static GetWaterSupplyBonuses(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Buildings.WaterConsumer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& waterConsumers, Game.Prefabs.CitizenHappinessParameterData& data) : Unity.Mathematics.int2`  

```csharp
public static Unity.Mathematics.int2 GetWaterSupplyBonuses(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Buildings.WaterConsumer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& waterConsumers, Game.Prefabs.CitizenHappinessParameterData& data);
```

- `public static GetWelfareValue(System.Single curvePosition, Unity.Entities.DynamicBuffer<Game.Net.ServiceCoverage> serviceCoverage, Game.Prefabs.CitizenHappinessParameterData& data) : System.Single`  

```csharp
public static System.Single GetWelfareValue(System.Single curvePosition, Unity.Entities.DynamicBuffer<Game.Net.ServiceCoverage> serviceCoverage, Game.Prefabs.CitizenHappinessParameterData& data);
```

- `public static GetWellfareBonuses(System.Single curvePosition, Unity.Entities.DynamicBuffer<Game.Net.ServiceCoverage> serviceCoverage, Game.Prefabs.CitizenHappinessParameterData& data, System.Int32 currentHappiness) : Unity.Mathematics.int2`  

```csharp
public static Unity.Mathematics.int2 GetWellfareBonuses(System.Single curvePosition, Unity.Entities.DynamicBuffer<Game.Net.ServiceCoverage> serviceCoverage, Game.Prefabs.CitizenHappinessParameterData& data, System.Int32 currentHappiness);
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

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
```


## Nested types

- `Game.Simulation.CitizenHappinessSystem+HappinessFactor`  
- `Game.Simulation.CitizenHappinessSystem+FactorItem`  
- `Game.Simulation.CitizenHappinessSystem+CitizenHappinessJob`  
- `Game.Simulation.CitizenHappinessSystem+HappinessFactorJob`  
- `Game.Simulation.CitizenHappinessSystem+TypeHandle`  

