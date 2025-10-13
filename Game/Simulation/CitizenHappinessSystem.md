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
[Preserve]
	public CitizenHappinessSystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		EntityQueryBuilder entityQueryBuilder = new EntityQueryBuilder(Allocator.Temp);
		EntityQueryBuilder entityQueryBuilder2 = entityQueryBuilder.WithAll<ServiceFeeParameterData>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_429327288_0 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder.Dispose();
	}
```

- `private static AddCompanyHappinessFactors(Unity.Collections.NativeArray<System.Int32> factors, Unity.Entities.Entity property, Unity.Entities.Entity prefab, Unity.Entities.Entity renter, Unity.Entities.Entity renterPrefab, Game.Prefabs.IndustrialProcessData processData, Game.Companies.ServiceCompanyData serviceCompanyData, System.Boolean commercial, System.Int32 level, Unity.Entities.ComponentLookup`1[[Game.Prefabs.OfficeBuilding, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& officeBuildings, Unity.Entities.ComponentLookup`1[[Game.Companies.WorkProvider, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& workProviders, Unity.Entities.BufferLookup`1[[Game.Companies.Employee, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& employees, Unity.Entities.ComponentLookup`1[[Game.Prefabs.WorkplaceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& workplaceDatas, Unity.Entities.ComponentLookup`1[[Game.Companies.ServiceAvailable, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& serviceAvailables, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas, Unity.Entities.BufferLookup`1[[Game.Buildings.Efficiency, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& efficiencies, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingPropertyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildingPropertyDatas, Unity.Entities.BufferLookup`1[[Game.Net.ResourceAvailability, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& availabilities, Unity.Entities.BufferLookup`1[[Game.Companies.TradeCost, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& tradeCosts, Unity.Collections.NativeArray<System.Int32> taxRates, Game.Buildings.Building building, Game.Prefabs.SpawnableBuildingData spawnableData, Game.Prefabs.BuildingData buildingData, Game.Prefabs.ResourcePrefabs resourcePrefabs, Game.Prefabs.EconomyParameterData& economyParameters) : System.Void`  

```csharp
private static void AddCompanyHappinessFactors(NativeArray<int> factors, Entity property, Entity prefab, Entity renter, Entity renterPrefab, IndustrialProcessData processData, ServiceCompanyData serviceCompanyData, bool commercial, int level, ref ComponentLookup<OfficeBuilding> officeBuildings, ref ComponentLookup<WorkProvider> workProviders, ref BufferLookup<Employee> employees, ref ComponentLookup<WorkplaceData> workplaceDatas, ref ComponentLookup<ServiceAvailable> serviceAvailables, ref ComponentLookup<ResourceData> resourceDatas, ref BufferLookup<Efficiency> efficiencies, ref ComponentLookup<BuildingPropertyData> buildingPropertyDatas, ref BufferLookup<ResourceAvailability> availabilities, ref BufferLookup<TradeCost> tradeCosts, NativeArray<int> taxRates, Building building, SpawnableBuildingData spawnableData, BuildingData buildingData, ResourcePrefabs resourcePrefabs, ref EconomyParameterData economyParameters)
	{
	}
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public static GetAirPollutionBonuses(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Objects.Transform, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& transforms, Unity.Collections.NativeArray<Game.Simulation.AirPollution> airPollutionMap, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Game.Prefabs.CitizenHappinessParameterData& data) : Unity.Mathematics.int2`  

```csharp
public static int2 GetAirPollutionBonuses(Entity building, ref ComponentLookup<Game.Objects.Transform> transforms, NativeArray<AirPollution> airPollutionMap, DynamicBuffer<CityModifier> cityModifiers, in CitizenHappinessParameterData data)
	{
		int2 result = default(int2);
		if (transforms.HasComponent(building))
		{
			short y = (short)(AirPollutionSystem.GetPollution(transforms[building].m_Position, airPollutionMap).m_Pollution / data.m_PollutionBonusDivisor);
			float value = 1f;
			CityUtils.ApplyModifier(ref value, cityModifiers, CityModifierType.PollutionHealthAffect);
			result.x = (int)((float)(-math.min(data.m_MaxAirAndGroundPollutionBonus, y)) * value);
		}
		return result;
	}
```

- `public static GetApartmentWellbeing(System.Single sizePerResident, System.Int32 level) : System.Single`  

```csharp
public static float GetApartmentWellbeing(float sizePerResident, int level)
	{
		return 0.8f * (4f * (float)(level - 1) + (24.55531f + -70.21f / math.pow(1f + math.pow(sizePerResident / 0.03690514f, 25.2376f), 0.01494523f)));
	}
```

- `public static GetBuildingHappinessFactors(Unity.Entities.Entity property, Unity.Collections.NativeArray<System.Int32> factors, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.SpawnableBuildingData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& spawnableBuildings, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingPropertyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildingPropertyDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ConsumptionData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& consumptionDatas, Unity.Entities.BufferLookup`1[[Game.City.CityModifier, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& cityModifiers, Unity.Entities.ComponentLookup`1[[Game.Buildings.Building, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildings, Unity.Entities.ComponentLookup`1[[Game.Buildings.ElectricityConsumer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& electricityConsumers, Unity.Entities.ComponentLookup`1[[Game.Buildings.WaterConsumer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& waterConsumers, Unity.Entities.BufferLookup`1[[Game.Net.ServiceCoverage, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& serviceCoverages, Unity.Entities.ComponentLookup`1[[Game.Prefabs.Locked, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& locked, Unity.Entities.ComponentLookup`1[[Game.Objects.Transform, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& transforms, Unity.Entities.ComponentLookup`1[[Game.Buildings.GarbageProducer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& garbageProducers, Unity.Entities.ComponentLookup`1[[Game.Buildings.CrimeProducer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& crimeProducers, Unity.Entities.ComponentLookup`1[[Game.Buildings.MailProducer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& mailProducers, Unity.Entities.ComponentLookup`1[[Game.Prefabs.OfficeBuilding, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& officeBuildings, Unity.Entities.BufferLookup`1[[Game.Buildings.Renter, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& renters, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizenDatas, Unity.Entities.BufferLookup`1[[Game.Citizens.HouseholdCitizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& householdCitizens, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildingDatas, Unity.Entities.ComponentLookup`1[[Game.Companies.CompanyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& companies, Unity.Entities.ComponentLookup`1[[Game.Prefabs.IndustrialProcessData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& industrialProcessDatas, Unity.Entities.ComponentLookup`1[[Game.Companies.WorkProvider, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& workProviders, Unity.Entities.BufferLookup`1[[Game.Companies.Employee, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& employees, Unity.Entities.ComponentLookup`1[[Game.Prefabs.WorkplaceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& workplaceDatas, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.HealthProblem, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& healthProblems, Unity.Entities.ComponentLookup`1[[Game.Companies.ServiceAvailable, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& serviceAvailables, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ResourceData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourceDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ZonePropertiesData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& zonePropertiesDatas, Unity.Entities.BufferLookup`1[[Game.Buildings.Efficiency, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& efficiencies, Unity.Entities.ComponentLookup`1[[Game.Companies.ServiceCompanyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& serviceCompanyDatas, Unity.Entities.BufferLookup`1[[Game.Net.ResourceAvailability, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& availabilities, Unity.Entities.BufferLookup`1[[Game.Companies.TradeCost, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& tradeCosts, Game.Prefabs.CitizenHappinessParameterData citizenHappinessParameters, Game.Prefabs.GarbageParameterData garbageParameters, Game.Prefabs.HealthcareParameterData healthcareParameters, Game.Prefabs.ParkParameterData parkParameters, Game.Prefabs.EducationParameterData educationParameters, Game.Prefabs.TelecomParameterData telecomParameters, Game.Prefabs.EconomyParameterData& economyParameters, Unity.Entities.DynamicBuffer<Game.Prefabs.HappinessFactorParameterData> happinessFactorParameters, Unity.Collections.NativeArray<Game.Simulation.GroundPollution> pollutionMap, Unity.Collections.NativeArray<Game.Simulation.NoisePollution> noisePollutionMap, Unity.Collections.NativeArray<Game.Simulation.AirPollution> airPollutionMap, Game.Simulation.CellMapData<Game.Simulation.TelecomCoverage> telecomCoverage, Unity.Entities.Entity city, Unity.Collections.NativeArray<System.Int32> taxRates, Unity.Collections.NativeArray<Unity.Entities.Entity> processes, Game.Prefabs.ResourcePrefabs resourcePrefabs, System.Single relativeElectricityFee, System.Single relativeWaterFee) : System.Void`  

```csharp
public static void GetBuildingHappinessFactors(Entity property, NativeArray<int> factors, ref ComponentLookup<PrefabRef> prefabs, ref ComponentLookup<SpawnableBuildingData> spawnableBuildings, ref ComponentLookup<BuildingPropertyData> buildingPropertyDatas, ref ComponentLookup<ConsumptionData> consumptionDatas, ref BufferLookup<CityModifier> cityModifiers, ref ComponentLookup<Building> buildings, ref ComponentLookup<ElectricityConsumer> electricityConsumers, ref ComponentLookup<WaterConsumer> waterConsumers, ref BufferLookup<Game.Net.ServiceCoverage> serviceCoverages, ref ComponentLookup<Locked> locked, ref ComponentLookup<Game.Objects.Transform> transforms, ref ComponentLookup<GarbageProducer> garbageProducers, ref ComponentLookup<CrimeProducer> crimeProducers, ref ComponentLookup<MailProducer> mailProducers, ref ComponentLookup<OfficeBuilding> officeBuildings, ref BufferLookup<Renter> renters, ref ComponentLookup<Citizen> citizenDatas, ref BufferLookup<HouseholdCitizen> householdCitizens, ref ComponentLookup<BuildingData> buildingDatas, ref ComponentLookup<CompanyData> companies, ref ComponentLookup<IndustrialProcessData> industrialProcessDatas, ref ComponentLookup<WorkProvider> workProviders, ref BufferLookup<Employee> employees, ref ComponentLookup<WorkplaceData> workplaceDatas, ref ComponentLookup<Citizen> citizens, ref ComponentLookup<HealthProblem> healthProblems, ref ComponentLookup<ServiceAvailable> serviceAvailables, ref ComponentLookup<ResourceData> resourceDatas, ref ComponentLookup<ZonePropertiesData> zonePropertiesDatas, ref BufferLookup<Efficiency> efficiencies, ref ComponentLookup<ServiceCompanyData> serviceCompanyDatas, ref BufferLookup<ResourceAvailability> availabilities, ref BufferLookup<TradeCost> tradeCosts, CitizenHappinessParameterData citizenHappinessParameters, GarbageParameterData garbageParameters, HealthcareParameterData healthcareParameters, ParkParameterData parkParameters, EducationParameterData educationParameters, TelecomParameterData telecomParameters, ref EconomyParameterData economyParameters, DynamicBuffer<HappinessFactorParameterData> happinessFactorParameters, NativeArray<GroundPollution> pollutionMap, NativeArray<NoisePollution> noisePollutionMap, NativeArray<AirPollution> airPollutionMap, CellMapData<TelecomCoverage> telecomCoverage, Entity city, NativeArray<int> taxRates, NativeArray<Entity> processes, ResourcePrefabs resourcePrefabs, float relativeElectricityFee, float relativeWaterFee)
	{
		for (int i = 0; i < factors.Length; i++)
		{
			factors[i] = 0;
		}
		if (!prefabs.HasComponent(property))
		{
			return;
		}
		Entity prefab = prefabs[property].m_Prefab;
		if (!spawnableBuildings.HasComponent(prefab) || !buildingDatas.HasComponent(prefab))
		{
			return;
		}
		BuildingPropertyData buildingPropertyData = buildingPropertyDatas[prefab];
		DynamicBuffer<CityModifier> cityModifiers2 = cityModifiers[city];
		BuildingData buildingData = buildingDatas[prefab];
		float num = buildingData.m_LotSize.x * buildingData.m_LotSize.y;
		Entity entity = Entity.Null;
		float curvePosition = 0f;
		SpawnableBuildingData spawnableData = spawnableBuildings[prefab];
		int level = spawnableData.m_Level;
		Building building = default(Building);
		if (buildings.HasComponent(property))
		{
			building = buildings[property];
			entity = building.m_RoadEdge;
			curvePosition = building.m_CurvePosition;
		}
		bool flag = false;
		Entity entity2 = default(Entity);
		Entity entity3 = default(Entity);
		IndustrialProcessData processData = default(IndustrialProcessData);
		ServiceCompanyData serviceCompanyData = default(ServiceCompanyData);
		Resource resource = buildingPropertyData.m_AllowedManufactured | buildingPropertyData.m_AllowedSold;
		if (resource != Resource.NoResource)
		{
			if (renters.HasBuffer(property))
			{
				DynamicBuffer<Renter> dynamicBuffer = renters[property];
				for (int j = 0; j < dynamicBuffer.Length; j++)
				{
					entity2 = dynamicBuffer[j].m_Renter;
					if (!companies.HasComponent(entity2) || !prefabs.HasComponent(entity2))
					{
						continue;
					}
					entity3 = prefabs[entity2].m_Prefab;
					if (industrialProcessDatas.HasComponent(entity3))
					{
						if (serviceCompanyDatas.HasComponent(entity3))
						{
							serviceCompanyData = serviceCompanyDatas[entity3];
						}
						processData = industrialProcessDatas[entity3];
						flag = true;
						break;
					}
				}
			}
			int num2 = 0;
			if (flag)
			{
				AddCompanyHappinessFactors(factors, property, prefab, entity2, entity3, processData, serviceCompanyData, buildingPropertyData.m_AllowedSold != Resource.NoResource, level, ref officeBuildings, ref workProviders, ref employees, ref workplaceDatas, ref serviceAvailables, ref resourceDatas, ref efficiencies, ref buildingPropertyDatas, ref availabilities, ref tradeCosts, taxRates, building, spawnableData, buildingData, resourcePrefabs, ref economyParameters);
				num2++;
			}
			else
			{
				for (int k = 0; k < processes.Length; k++)
				{
					processData = industrialProcessDatas[processes[k]];
					bool num3 = buildingPropertyData.m_AllowedSold != Resource.NoResource;
					if (num3 && serviceCompanyDatas.HasComponent(processes[k]))
					{
						serviceCompanyData = serviceCompanyDatas[processes[k]];
					}
					if ((!num3 || serviceCompanyDatas.HasComponent(processes[k])) && (resource & processData.m_Output.m_Resource) != Resource.NoResource)
					{
						AddCompanyHappinessFactors(factors, property, prefab, entity2, entity3, processData, serviceCompanyData, buildingPropertyData.m_AllowedSold != Resource.NoResource, level, ref officeBuildings, ref workProviders, ref employees, ref workplaceDatas, ref serviceAvailables, ref resourceDatas, ref efficiencies, ref buildingPropertyDatas, ref availabilities, ref tradeCosts, taxRates, building, spawnableData, buildingData, resourcePrefabs, ref economyParameters);
						num2++;
					}
				}
			}
			for (int l = 0; l < factors.Length; l++)
			{
				factors[l] /= num2;
			}
		}
		if (buildingPropertyData.m_ResidentialProperties <= 0)
		{
			return;
		}
		for (int m = 0; m < factors.Length; m++)
		{
			factors[m] = Mathf.RoundToInt((float)factors[m] / (1f - economyParameters.m_MixedBuildingCompanyRentPercentage));
		}
		num /= (float)buildingPropertyData.m_ResidentialProperties;
		float num4 = 1f;
		int currentHappiness = 50;
		int num5 = 128;
		float num6 = 0.3f;
		float num7 = 0.25f;
		float num8 = 0.25f;
		float num9 = 0.15f;
		float num10 = 0.05f;
		float num11 = 2f;
		if (renters.HasBuffer(property))
		{
			num6 = 0f;
			num7 = 0f;
			num8 = 0f;
			num9 = 0f;
			num10 = 0f;
			int2 @int = default(int2);
			int2 int2 = default(int2);
			int num12 = 0;
			int num13 = 0;
			DynamicBuffer<Renter> dynamicBuffer2 = renters[property];
			for (int n = 0; n < dynamicBuffer2.Length; n++)
			{
				Entity renter = dynamicBuffer2[n].m_Renter;
				if (!householdCitizens.HasBuffer(renter))
				{
					continue;
				}
				num13++;
				DynamicBuffer<HouseholdCitizen> dynamicBuffer3 = householdCitizens[renter];
				for (int num14 = 0; num14 < dynamicBuffer3.Length; num14++)
				{
					Entity citizen = dynamicBuffer3[num14].m_Citizen;
					if (citizenDatas.HasComponent(citizen))
					{
						Citizen citizen2 = citizenDatas[citizen];
						int2.x += citizen2.Happiness;
						int2.y++;
						num12 += citizen2.m_LeisureCounter;
						switch (citizen2.GetEducationLevel())
						{
						case 0:
							num6 += 1f;
							break;
						case 1:
							num7 += 1f;
							break;
						case 2:
							num8 += 1f;
							break;
						case 3:
							num9 += 1f;
							break;
						case 4:
							num10 += 1f;
							break;
						}
						if (citizen2.GetAge() == CitizenAge.Child)
						{
							@int.x++;
						}
					}
				}
				@int.y++;
			}
			if (@int.y > 0)
			{
				num4 = @int.x / @int.y;
			}
			if (int2.y > 0)
			{
				currentHappiness = Mathf.RoundToInt(int2.x / int2.y);
				num5 = Mathf.RoundToInt(num12 / int2.y);
				num6 /= (float)int2.y;
				num7 /= (float)int2.y;
				num8 /= (float)int2.y;
				num9 /= (float)int2.y;
				num10 /= (float)int2.y;
				num11 = (float)int2.y / (float)num13;
			}
		}
		Entity healthcareServicePrefab = healthcareParameters.m_HealthcareServicePrefab;
		Entity parkServicePrefab = parkParameters.m_ParkServicePrefab;
		Entity educationServicePrefab = educationParameters.m_EducationServicePrefab;
		Entity telecomServicePrefab = telecomParameters.m_TelecomServicePrefab;
		if (!locked.HasEnabledComponent(happinessFactorParameters[4].m_LockedEntity))
		{
			int2 electricitySupplyBonuses = GetElectricitySupplyBonuses(property, ref electricityConsumers, in citizenHappinessParameters);
			factors[3] = (electricitySupplyBonuses.x + electricitySupplyBonuses.y) / 2 - happinessFactorParameters[4].m_BaseLevel;
		}
		if (!locked.HasEnabledComponent(happinessFactorParameters[23].m_LockedEntity))
		{
			int2 electricityFeeBonuses = GetElectricityFeeBonuses(property, ref electricityConsumers, relativeElectricityFee, in citizenHappinessParameters);
			factors[26] = (electricityFeeBonuses.x + electricityFeeBonuses.y) / 2 - happinessFactorParameters[23].m_BaseLevel;
		}
		if (!locked.HasEnabledComponent(happinessFactorParameters[8].m_LockedEntity))
		{
			int2 waterSupplyBonuses = GetWaterSupplyBonuses(property, ref waterConsumers, in citizenHappinessParameters);
			factors[7] = (waterSupplyBonuses.x + waterSupplyBonuses.y) / 2 - happinessFactorParameters[8].m_BaseLevel;
		}
		if (!locked.HasEnabledComponent(happinessFactorParameters[24].m_LockedEntity))
		{
			int2 waterFeeBonuses = GetWaterFeeBonuses(property, ref waterConsumers, relativeWaterFee, in citizenHappinessParameters);
			factors[27] = (waterFeeBonuses.x + waterFeeBonuses.y) / 2 - happinessFactorParameters[24].m_BaseLevel;
		}
		if (!locked.HasEnabledComponent(happinessFactorParameters[9].m_LockedEntity))
		{
			int2 waterPollutionBonuses = GetWaterPollutionBonuses(property, ref waterConsumers, cityModifiers2, in citizenHappinessParameters);
			factors[8] = (waterPollutionBonuses.x + waterPollutionBonuses.y) / 2 - happinessFactorParameters[9].m_BaseLevel;
		}
		if (!locked.HasEnabledComponent(happinessFactorParameters[10].m_LockedEntity))
		{
			int2 sewageBonuses = GetSewageBonuses(property, ref waterConsumers, in citizenHappinessParameters);
			factors[9] = (sewageBonuses.x + sewageBonuses.y) / 2 - happinessFactorParameters[10].m_BaseLevel;
		}
		if (serviceCoverages.HasBuffer(entity))
		{
			DynamicBuffer<Game.Net.ServiceCoverage> serviceCoverage = serviceCoverages[entity];
			if (!locked.HasEnabledComponent(happinessFactorParameters[5].m_LockedEntity))
			{
				int2 healthcareBonuses = GetHealthcareBonuses(curvePosition, serviceCoverage, ref locked, healthcareServicePrefab, in citizenHappinessParameters);
				factors[4] = (healthcareBonuses.x + healthcareBonuses.y) / 2 - happinessFactorParameters[5].m_BaseLevel;
			}
			if (!locked.HasEnabledComponent(happinessFactorParameters[12].m_LockedEntity))
			{
				int2 entertainmentBonuses = GetEntertainmentBonuses(curvePosition, serviceCoverage, cityModifiers2, ref locked, parkServicePrefab, in citizenHappinessParameters);
				factors[11] = (entertainmentBonuses.x + entertainmentBonuses.y) / 2 - happinessFactorParameters[12].m_BaseLevel;
			}
			if (!locked.HasEnabledComponent(happinessFactorParameters[13].m_LockedEntity))
			{
				int2 educationBonuses = GetEducationBonuses(curvePosition, serviceCoverage, ref locked, educationServicePrefab, in citizenHappinessParameters, 1);
				factors[12] = Mathf.RoundToInt(num4 * (float)(educationBonuses.x + educationBonuses.y) / 2f) - happinessFactorParameters[13].m_BaseLevel;
			}
			if (!locked.HasEnabledComponent(happinessFactorParameters[15].m_LockedEntity))
			{
				int2 wellfareBonuses = GetWellfareBonuses(curvePosition, serviceCoverage, in citizenHappinessParameters, currentHappiness);
				factors[14] = (wellfareBonuses.x + wellfareBonuses.y) / 2 - happinessFactorParameters[15].m_BaseLevel;
			}
		}
		if (!locked.HasEnabledComponent(happinessFactorParameters[6].m_LockedEntity))
		{
			int2 groundPollutionBonuses = GetGroundPollutionBonuses(property, ref transforms, pollutionMap, cityModifiers2, in citizenHappinessParameters);
			factors[5] = (groundPollutionBonuses.x + groundPollutionBonuses.y) / 2 - happinessFactorParameters[6].m_BaseLevel;
		}
		if (!locked.HasEnabledComponent(happinessFactorParameters[2].m_LockedEntity))
		{
			int2 airPollutionBonuses = GetAirPollutionBonuses(property, ref transforms, airPollutionMap, cityModifiers2, in citizenHappinessParameters);
			factors[2] = (airPollutionBonuses.x + airPollutionBonuses.y) / 2 - happinessFactorParameters[2].m_BaseLevel;
		}
		if (!locked.HasEnabledComponent(happinessFactorParameters[7].m_LockedEntity))
		{
			int2 noiseBonuses = GetNoiseBonuses(property, ref transforms, noisePollutionMap, in citizenHappinessParameters);
			factors[6] = (noiseBonuses.x + noiseBonuses.y) / 2 - happinessFactorParameters[7].m_BaseLevel;
		}
		if (!locked.HasEnabledComponent(happinessFactorParameters[11].m_LockedEntity))
		{
			int2 garbageBonuses = GetGarbageBonuses(property, ref garbageProducers, ref locked, happinessFactorParameters[11].m_LockedEntity, in garbageParameters);
			factors[10] = (garbageBonuses.x + garbageBonuses.y) / 2 - happinessFactorParameters[11].m_BaseLevel;
		}
		if (!locked.HasEnabledComponent(happinessFactorParameters[1].m_LockedEntity))
		{
			int2 crimeBonuses = GetCrimeBonuses(default(CrimeVictim), property, ref crimeProducers, ref locked, happinessFactorParameters[1].m_LockedEntity, in citizenHappinessParameters);
			factors[1] = (crimeBonuses.x + crimeBonuses.y) / 2 - happinessFactorParameters[1].m_BaseLevel;
		}
		if (!locked.HasEnabledComponent(happinessFactorParameters[14].m_LockedEntity))
		{
			int2 mailBonuses = GetMailBonuses(property, ref mailProducers, ref locked, telecomServicePrefab, in citizenHappinessParameters);
			factors[13] = (mailBonuses.x + mailBonuses.y) / 2 - happinessFactorParameters[14].m_BaseLevel;
		}
		if (!locked.HasEnabledComponent(happinessFactorParameters[0].m_LockedEntity))
		{
			int2 telecomBonuses = GetTelecomBonuses(property, ref transforms, telecomCoverage, ref locked, telecomServicePrefab, in citizenHappinessParameters);
			factors[0] = (telecomBonuses.x + telecomBonuses.y) / 2 - happinessFactorParameters[0].m_BaseLevel;
		}
		if (!locked.HasEnabledComponent(happinessFactorParameters[16].m_LockedEntity))
		{
			int2 leisureBonuses = GetLeisureBonuses((byte)num5);
			factors[15] = (leisureBonuses.x + leisureBonuses.y) / 2 - happinessFactorParameters[16].m_BaseLevel;
		}
		if (!locked.HasEnabledComponent(happinessFactorParameters[17].m_LockedEntity))
		{
			float2 @float = new float2(num6, num6) * GetTaxBonuses(0, taxRates, in citizenHappinessParameters) + new float2(num7, num7) * GetTaxBonuses(1, taxRates, in citizenHappinessParameters) + new float2(num8, num8) * GetTaxBonuses(2, taxRates, in citizenHappinessParameters) + new float2(num9, num9) * GetTaxBonuses(3, taxRates, in citizenHappinessParameters) + new float2(num10, num10) * GetTaxBonuses(4, taxRates, in citizenHappinessParameters);
			factors[16] = Mathf.RoundToInt(@float.x + @float.y) / 2 - happinessFactorParameters[17].m_BaseLevel;
		}
		if (!locked.HasEnabledComponent(happinessFactorParameters[3].m_LockedEntity))
		{
			float2 float2 = GetApartmentWellbeing(buildingPropertyData.m_SpaceMultiplier * num / num11, level);
			factors[21] = Mathf.RoundToInt(float2.x + float2.y) / 2 - happinessFactorParameters[3].m_BaseLevel;
		}
		if (resource != Resource.NoResource)
		{
			for (int num15 = 0; num15 < factors.Length; num15++)
			{
				factors[num15] = Mathf.RoundToInt((float)factors[num15] * (1f - economyParameters.m_MixedBuildingCompanyRentPercentage));
			}
		}
	}
```

- `public static GetCachedWelfareBonuses(System.Single cachedValue, System.Int32 currentHappiness) : Unity.Mathematics.int2`  

```csharp
public static int2 GetCachedWelfareBonuses(float cachedValue, int currentHappiness)
	{
		return new int2
		{
			y = Mathf.RoundToInt(cachedValue * (float)math.max(0, (50 - currentHappiness) / 50))
		};
	}
```

- `public static GetConsumptionBonuses(System.Single dailyConsumption, System.Int32 citizens, Game.Prefabs.CitizenHappinessParameterData& data) : Unity.Mathematics.int2`  

```csharp
public static int2 GetConsumptionBonuses(float dailyConsumption, int citizens, in CitizenHappinessParameterData data)
	{
		float num = dailyConsumption / math.max(1f, citizens);
		float f = 20f * math.log(1f + 0.2f * num) + 12500f / (2f * num + 190f) - 112f;
		return new int2(0, math.clamp(Mathf.RoundToInt(f), -40, 40));
	}
```

- `public static GetConsumptionHappinessDifferential(System.Single dailyConsumption, System.Int32 citizens) : System.Single`  

```csharp
public static float GetConsumptionHappinessDifferential(float dailyConsumption, int citizens)
	{
		if (dailyConsumption <= 0f)
		{
			return 100f;
		}
		float num = dailyConsumption / math.max(1f, citizens);
		return 8f / (1f + 0.2f * num) - 50000f * math.pow(2f * num + 190f, -2f);
	}
```

- `public static GetCrimeBonuses(Game.Citizens.CrimeVictim crimeVictim, Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Buildings.CrimeProducer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& crimes, Unity.Entities.ComponentLookup`1[[Game.Prefabs.Locked, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& locked, Unity.Entities.Entity policeService, Game.Prefabs.CitizenHappinessParameterData& data) : Unity.Mathematics.int2`  

```csharp
public static int2 GetCrimeBonuses(CrimeVictim crimeVictim, Entity building, ref ComponentLookup<CrimeProducer> crimes, ref ComponentLookup<Locked> locked, Entity policeService, in CitizenHappinessParameterData data)
	{
		if (locked.HasEnabledComponent(policeService))
		{
			return new int2(0, 0);
		}
		int2 result = default(int2);
		if (crimes.HasComponent(building))
		{
			int y = Mathf.RoundToInt(math.max(0f, (crimes[building].m_Crime - (float)data.m_NegligibleCrime) * data.m_CrimeMultiplier));
			result.x = 0;
			result.y = -math.min(data.m_MaxCrimePenalty, y);
		}
		result.y -= crimeVictim.m_Effect;
		return result;
	}
```

- `public static GetDeathPenalty(Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> householdCitizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.HealthProblem, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& healthProblems, Game.Prefabs.CitizenHappinessParameterData& data) : Unity.Mathematics.int2`  

```csharp
public static int2 GetDeathPenalty(DynamicBuffer<HouseholdCitizen> householdCitizens, ref ComponentLookup<HealthProblem> healthProblems, in CitizenHappinessParameterData data)
	{
		bool flag = false;
		foreach (HouseholdCitizen item in householdCitizens)
		{
			if (CitizenUtils.IsDead(item.m_Citizen, ref healthProblems))
			{
				flag = true;
				break;
			}
		}
		if (flag)
		{
			return new int2(-data.m_DeathHealthPenalty, -data.m_DeathWellbeingPenalty);
		}
		return default(int2);
	}
```

- `public static GetEducationBonuses(System.Single curvePosition, Unity.Entities.DynamicBuffer<Game.Net.ServiceCoverage> serviceCoverage, Unity.Entities.ComponentLookup`1[[Game.Prefabs.Locked, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& locked, Unity.Entities.Entity educationService, Game.Prefabs.CitizenHappinessParameterData& data, System.Int32 children) : Unity.Mathematics.int2`  

```csharp
public static int2 GetEducationBonuses(float curvePosition, DynamicBuffer<Game.Net.ServiceCoverage> serviceCoverage, ref ComponentLookup<Locked> locked, Entity educationService, in CitizenHappinessParameterData data, int children)
	{
		if (locked.HasEnabledComponent(educationService))
		{
			return new int2(0, 0);
		}
		int2 result = default(int2);
		float f = math.sqrt(children) * data.m_EducationWellbeingMultiplier * (NetUtils.GetServiceCoverage(serviceCoverage, CoverageService.Education, curvePosition) - data.m_NeutralEducation);
		result.y = Mathf.RoundToInt(f);
		return result;
	}
```

- `public static GetElectricityFeeBonuses(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Buildings.ElectricityConsumer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& electricityConsumers, System.Single relativeFee, Game.Prefabs.CitizenHappinessParameterData& data) : Unity.Mathematics.int2`  

```csharp
public static int2 GetElectricityFeeBonuses(float relativeFee, in CitizenHappinessParameterData data)
	{
		return new int2
		{
			y = (int)math.round(data.m_ElectricityFeeWellbeingEffect.Evaluate(relativeFee))
		};
	}
```

- `public static GetElectricityFeeBonuses(System.Single relativeFee, Game.Prefabs.CitizenHappinessParameterData& data) : Unity.Mathematics.int2`  

```csharp
public static int2 GetElectricityFeeBonuses(float relativeFee, in CitizenHappinessParameterData data)
	{
		return new int2
		{
			y = (int)math.round(data.m_ElectricityFeeWellbeingEffect.Evaluate(relativeFee))
		};
	}
```

- `public static GetElectricityFeeHappinessEffect(System.Single relativeFee, Game.Prefabs.CitizenHappinessParameterData& data) : System.Int32`  

```csharp
public static int GetElectricityFeeHappinessEffect(float relativeFee, in CitizenHappinessParameterData data)
	{
		return (int)math.round((float)math.csum(GetElectricityFeeBonuses(relativeFee, in data)) / 2f);
	}
```

- `public static GetElectricitySupplyBonuses(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Buildings.ElectricityConsumer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& electricityConsumers, Game.Prefabs.CitizenHappinessParameterData& data) : Unity.Mathematics.int2`  

```csharp
public static int2 GetElectricitySupplyBonuses(Entity building, ref ComponentLookup<ElectricityConsumer> electricityConsumers, in CitizenHappinessParameterData data)
	{
		if (electricityConsumers.TryGetComponent(building, out var componentData))
		{
			float num = math.saturate((float)componentData.m_CooldownCounter / data.m_ElectricityPenaltyDelay);
			return new int2
			{
				y = (int)math.round((0f - data.m_ElectricityWellbeingPenalty) * num)
			};
		}
		return default(int2);
	}
```

- `public static GetEntertainmentBonuses(System.Single curvePosition, Unity.Entities.DynamicBuffer<Game.Net.ServiceCoverage> serviceCoverage, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Unity.Entities.ComponentLookup`1[[Game.Prefabs.Locked, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& locked, Unity.Entities.Entity entertainmentService, Game.Prefabs.CitizenHappinessParameterData& data) : Unity.Mathematics.int2`  

```csharp
public static int2 GetEntertainmentBonuses(float curvePosition, DynamicBuffer<Game.Net.ServiceCoverage> serviceCoverage, DynamicBuffer<CityModifier> cityModifiers, ref ComponentLookup<Locked> locked, Entity entertainmentService, in CitizenHappinessParameterData data)
	{
		if (locked.HasEnabledComponent(entertainmentService))
		{
			return new int2(0, 0);
		}
		int2 result = default(int2);
		float value = NetUtils.GetServiceCoverage(serviceCoverage, CoverageService.Park, curvePosition);
		CityUtils.ApplyModifier(ref value, cityModifiers, CityModifierType.Entertainment);
		value = data.m_EntertainmentWellbeingMultiplier * math.min(1f, math.sqrt(value / 1.5f));
		result.x = 0;
		result.y = Mathf.RoundToInt(value);
		return result;
	}
```

- `private static GetFactor(System.Single profit, System.Single defaultProfit) : System.Int32`  

```csharp
private static int GetFactor(float profit, float defaultProfit)
	{
		return Mathf.RoundToInt(10f * (profit / defaultProfit - 1f));
	}
```

- `private static GetFactorIndex(Game.Simulation.CitizenHappinessSystem+HappinessFactor factor, System.UInt32 updateFrame) : System.Int32`  

```csharp
private static int GetFactorIndex(HappinessFactor factor, uint updateFrame)
	{
		return (int)factor + (int)(25 * updateFrame);
	}
```

- `public static GetFreetimeWellbeing(System.Int32 freetime) : System.Single`  

```csharp
public static float GetFreetimeWellbeing(int freetime)
	{
		return 4f * math.log(math.max(1, freetime)) - 25f;
	}
```

- `public static GetFreetimeWellbeingDifferential(System.Int32 freetime) : System.Single`  

```csharp
public static float GetFreetimeWellbeingDifferential(int freetime)
	{
		return 4f / (float)freetime;
	}
```

- `public static GetGarbageBonuses(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Buildings.GarbageProducer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& garbages, Unity.Entities.ComponentLookup`1[[Game.Prefabs.Locked, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& locked, Unity.Entities.Entity garbageService, Game.Prefabs.GarbageParameterData& data) : Unity.Mathematics.int2`  

```csharp
public static int2 GetGarbageBonuses(Entity building, ref ComponentLookup<GarbageProducer> garbages, ref ComponentLookup<Locked> locked, Entity garbageService, in GarbageParameterData data)
	{
		if (locked.HasEnabledComponent(garbageService))
		{
			return new int2(0, 0);
		}
		int2 result = default(int2);
		if (garbages.HasComponent(building))
		{
			int y = math.max(0, (garbages[building].m_Garbage - data.m_HappinessEffectBaseline) / data.m_HappinessEffectStep);
			result.x = -math.min(10, y);
			result.y = -math.min(10, y);
		}
		return result;
	}
```

- `public static GetGroundPollutionBonuses(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Objects.Transform, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& transforms, Unity.Collections.NativeArray<Game.Simulation.GroundPollution> pollutionMap, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Game.Prefabs.CitizenHappinessParameterData& data) : Unity.Mathematics.int2`  

```csharp
public static int2 GetGroundPollutionBonuses(Entity building, ref ComponentLookup<Game.Objects.Transform> transforms, NativeArray<GroundPollution> pollutionMap, DynamicBuffer<CityModifier> cityModifiers, in CitizenHappinessParameterData data)
	{
		int2 result = default(int2);
		if (transforms.HasComponent(building))
		{
			short y = (short)(GroundPollutionSystem.GetPollution(transforms[building].m_Position, pollutionMap).m_Pollution / data.m_PollutionBonusDivisor);
			float value = 1f;
			CityUtils.ApplyModifier(ref value, cityModifiers, CityModifierType.PollutionHealthAffect);
			result.x = (int)((float)(-math.min(data.m_MaxAirAndGroundPollutionBonus, y)) * value);
		}
		return result;
	}
```

- `public GetHappinessFactor(Game.Simulation.CitizenHappinessSystem+HappinessFactor factor, Unity.Entities.DynamicBuffer<Game.Prefabs.HappinessFactorParameterData> parameters, Unity.Entities.ComponentLookup`1[[Game.Prefabs.Locked, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& locked) : Unity.Mathematics.float3`  

```csharp
private static float3 GetHappinessFactor(HappinessFactor factor, NativeArray<int4> happinessFactors, DynamicBuffer<HappinessFactorParameterData> parameters, ref ComponentLookup<Locked> locked)
	{
		int4 @int = 0;
		for (uint num = 0u; num < 16; num++)
		{
			@int += happinessFactors[GetFactorIndex(factor, num)];
		}
		Entity lockedEntity = parameters[(int)factor].m_LockedEntity;
		if (lockedEntity != Entity.Null && locked.HasEnabledComponent(lockedEntity))
		{
			return 0;
		}
		return ((@int.y > 0) ? new float3((float)@int.x / (2f * (float)@int.y), @int.z / @int.y, @int.w / @int.y) : default(float3)) - parameters[(int)factor].m_BaseLevel;
	}
```

- `private static GetHappinessFactor(Game.Simulation.CitizenHappinessSystem+HappinessFactor factor, Unity.Collections.NativeArray<Unity.Mathematics.int4> happinessFactors, Unity.Entities.DynamicBuffer<Game.Prefabs.HappinessFactorParameterData> parameters, Unity.Entities.ComponentLookup`1[[Game.Prefabs.Locked, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& locked) : Unity.Mathematics.float3`  

```csharp
private static float3 GetHappinessFactor(HappinessFactor factor, NativeArray<int4> happinessFactors, DynamicBuffer<HappinessFactorParameterData> parameters, ref ComponentLookup<Locked> locked)
	{
		int4 @int = 0;
		for (uint num = 0u; num < 16; num++)
		{
			@int += happinessFactors[GetFactorIndex(factor, num)];
		}
		Entity lockedEntity = parameters[(int)factor].m_LockedEntity;
		if (lockedEntity != Entity.Null && locked.HasEnabledComponent(lockedEntity))
		{
			return 0;
		}
		return ((@int.y > 0) ? new float3((float)@int.x / (2f * (float)@int.y), @int.z / @int.y, @int.w / @int.y) : default(float3)) - parameters[(int)factor].m_BaseLevel;
	}
```

- `public static GetHealthcareBonuses(System.Single curvePosition, Unity.Entities.DynamicBuffer<Game.Net.ServiceCoverage> serviceCoverage, Unity.Entities.ComponentLookup`1[[Game.Prefabs.Locked, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& locked, Unity.Entities.Entity healthcareService, Game.Prefabs.CitizenHappinessParameterData& data) : Unity.Mathematics.int2`  

```csharp
public static int2 GetHealthcareBonuses(float curvePosition, DynamicBuffer<Game.Net.ServiceCoverage> serviceCoverage, ref ComponentLookup<Locked> locked, Entity healthcareService, in CitizenHappinessParameterData data)
	{
		if (locked.HasEnabledComponent(healthcareService))
		{
			return new int2(0, 0);
		}
		int2 result = default(int2);
		float serviceCoverage2 = NetUtils.GetServiceCoverage(serviceCoverage, CoverageService.Healthcare, curvePosition);
		result.x = Mathf.RoundToInt(data.m_HealthCareHealthMultiplier * serviceCoverage2);
		result.y = Mathf.RoundToInt(data.m_HealthCareWellbeingMultiplier * serviceCoverage2);
		return result;
	}
```

- `public static GetHomelessBonuses(Game.Prefabs.CitizenHappinessParameterData& data) : Unity.Mathematics.int2`  

```csharp
public static int2 GetHomelessBonuses(in CitizenHappinessParameterData data)
	{
		return new int2(data.m_HomelessHealthEffect, data.m_HomelessWellbeingEffect);
	}
```

- `public static GetLeisureBonuses(System.Byte leisureValue) : Unity.Mathematics.int2`  

```csharp
public static int2 GetLeisureBonuses(byte leisureValue)
	{
		return new int2(0, (leisureValue - 128) / 16);
	}
```

- `public static GetMailBonuses(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Buildings.MailProducer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& mails, Unity.Entities.ComponentLookup`1[[Game.Prefabs.Locked, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& locked, Unity.Entities.Entity telecomService, Game.Prefabs.CitizenHappinessParameterData& data) : Unity.Mathematics.int2`  

```csharp
public static int2 GetMailBonuses(Entity building, ref ComponentLookup<MailProducer> mails, ref ComponentLookup<Locked> locked, Entity telecomService, in CitizenHappinessParameterData data)
	{
		if (locked.HasEnabledComponent(telecomService))
		{
			return new int2(0, 0);
		}
		int2 result = default(int2);
		if (mails.HasComponent(building))
		{
			MailProducer mailProducer = mails[building];
			int num = math.max(0, math.max(mailProducer.m_SendingMail, mailProducer.receivingMail) - data.m_NegligibleMail);
			result.x = 0;
			if (num < 25)
			{
				if (!mailProducer.mailDelivered)
				{
					return result;
				}
				int num2 = 125;
				int num3 = 25 - num;
				result.y = (num3 * num3 + (num2 >> 1)) / num2;
			}
			else
			{
				int num4 = 250;
				int num5 = math.min(50, num - 25);
				result.y = -((num5 * num5 + (num4 >> 1)) / num4);
			}
			result.y *= Mathf.RoundToInt(data.m_MailMultiplier);
		}
		return result;
	}
```

- `public static GetMaxHealth(System.Single ageInYears) : System.Int32`  

```csharp
public static int GetMaxHealth(float ageInYears)
	{
		if (ageInYears < 2f)
		{
			return 100;
		}
		if (ageInYears < 3f)
		{
			return 90;
		}
		if (ageInYears < 6f)
		{
			return 80;
		}
		return 80 - 10 * Mathf.FloorToInt(ageInYears - 5f);
	}
```

- `public static GetNoiseBonuses(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Objects.Transform, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& transforms, Unity.Collections.NativeArray<Game.Simulation.NoisePollution> noiseMap, Game.Prefabs.CitizenHappinessParameterData& data) : Unity.Mathematics.int2`  

```csharp
public static int2 GetNoiseBonuses(Entity building, ref ComponentLookup<Game.Objects.Transform> transforms, NativeArray<NoisePollution> noiseMap, in CitizenHappinessParameterData data)
	{
		int2 result = default(int2);
		if (transforms.HasComponent(building))
		{
			short y = (short)(NoisePollutionSystem.GetPollution(transforms[building].m_Position, noiseMap).m_Pollution / data.m_PollutionBonusDivisor);
			result.y = -math.min(data.m_MaxNoisePollutionBonus, y);
		}
		return result;
	}
```

- `public static GetSewageBonuses(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Buildings.WaterConsumer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& waterConsumers, Game.Prefabs.CitizenHappinessParameterData& data) : Unity.Mathematics.int2`  

```csharp
public static int2 GetSewageBonuses(Entity building, ref ComponentLookup<WaterConsumer> waterConsumers, in CitizenHappinessParameterData data)
	{
		if (waterConsumers.TryGetComponent(building, out var componentData))
		{
			float num = math.saturate((float)(int)componentData.m_SewageCooldownCounter / data.m_SewagePenaltyDelay);
			return new int2
			{
				x = (int)math.round((float)(-data.m_SewageHealthEffect) * num),
				y = (int)math.round((float)(-data.m_SewageWellbeingEffect) * num)
			};
		}
		return default(int2);
	}
```

- `public static GetSicknessBonuses(System.Boolean hasHealthProblem, Game.Prefabs.CitizenHappinessParameterData& data) : Unity.Mathematics.int2`  

```csharp
public static int2 GetSicknessBonuses(bool hasHealthProblem, in CitizenHappinessParameterData data)
	{
		if (hasHealthProblem)
		{
			return new int2(-data.m_HealthProblemHealthPenalty, 0);
		}
		return default(int2);
	}
```

- `public static GetTaxBonuses(System.Int32 educationLevel, Unity.Collections.NativeArray<System.Int32> taxRates, Game.Prefabs.CitizenHappinessParameterData& data) : Unity.Mathematics.int2`  

```csharp
public static int2 GetTaxBonuses(int educationLevel, NativeArray<int> taxRates, in CitizenHappinessParameterData data)
	{
		int residentialTaxRate = TaxSystem.GetResidentialTaxRate(educationLevel, taxRates);
		float num = 0f;
		switch (educationLevel)
		{
		case 0:
			num = data.m_TaxUneducatedMultiplier;
			break;
		case 1:
			num = data.m_TaxPoorlyEducatedMultiplier;
			break;
		case 2:
			num = data.m_TaxEducatedMultiplier;
			break;
		case 3:
			num = data.m_TaxWellEducatedMultiplier;
			break;
		case 4:
			num = data.m_TaxHighlyEducatedMultiplier;
			break;
		}
		return new int2(0, Mathf.RoundToInt((float)(residentialTaxRate - 10) * num));
	}
```

- `public static GetTelecomBonuses(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Objects.Transform, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& transforms, Game.Simulation.CellMapData<Game.Simulation.TelecomCoverage> telecomCoverage, Unity.Entities.ComponentLookup`1[[Game.Prefabs.Locked, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& locked, Unity.Entities.Entity telecomService, Game.Prefabs.CitizenHappinessParameterData& data) : Unity.Mathematics.int2`  

```csharp
public static int2 GetTelecomBonuses(Entity building, ref ComponentLookup<Game.Objects.Transform> transforms, CellMapData<TelecomCoverage> telecomCoverage, ref ComponentLookup<Locked> locked, Entity telecomService, in CitizenHappinessParameterData data)
	{
		if (locked.HasEnabledComponent(telecomService))
		{
			return default(int2);
		}
		int2 result = default(int2);
		if (transforms.HasComponent(building))
		{
			float3 position = transforms[building].m_Position;
			float num = TelecomCoverage.SampleNetworkQuality(telecomCoverage, position);
			float telecomBaseline = data.m_TelecomBaseline;
			if (num >= telecomBaseline)
			{
				float num2 = (num - telecomBaseline) / (1f - telecomBaseline);
				result.y = Mathf.RoundToInt(num2 * num2 * data.m_TelecomBonusMultiplier);
			}
			else
			{
				float num3 = 1f - num / telecomBaseline;
				result.y = Mathf.RoundToInt(num3 * num3 * (0f - data.m_TelecomPenaltyMultiplier));
			}
		}
		return result;
	}
```

- `private static GetTriggerTypeForHappinessFactor(Game.Simulation.CitizenHappinessSystem+HappinessFactor factor) : Game.Triggers.TriggerType`  

```csharp
private static TriggerType GetTriggerTypeForHappinessFactor(HappinessFactor factor)
	{
		switch (factor)
		{
		case HappinessFactor.Telecom:
			return TriggerType.TelecomHappinessFactor;
		case HappinessFactor.Crime:
			return TriggerType.CrimeHappinessFactor;
		case HappinessFactor.AirPollution:
			return TriggerType.AirPollutionHappinessFactor;
		case HappinessFactor.Apartment:
			return TriggerType.ApartmentHappinessFactor;
		case HappinessFactor.Electricity:
			return TriggerType.ElectricityHappinessFactor;
		case HappinessFactor.Healthcare:
			return TriggerType.HealthcareHappinessFactor;
		case HappinessFactor.GroundPollution:
			return TriggerType.GroundPollutionHappinessFactor;
		case HappinessFactor.NoisePollution:
			return TriggerType.NoisePollutionHappinessFactor;
		case HappinessFactor.Water:
			return TriggerType.WaterHappinessFactor;
		case HappinessFactor.WaterPollution:
			return TriggerType.WaterPollutionHappinessFactor;
		case HappinessFactor.Sewage:
			return TriggerType.SewageHappinessFactor;
		case HappinessFactor.Garbage:
			return TriggerType.GarbageHappinessFactor;
		case HappinessFactor.Entertainment:
			return TriggerType.EntertainmentHappinessFactor;
		case HappinessFactor.Education:
			return TriggerType.EducationHappinessFactor;
		case HappinessFactor.Mail:
			return TriggerType.MailHappinessFactor;
		case HappinessFactor.Welfare:
			return TriggerType.WelfareHappinessFactor;
		case HappinessFactor.Leisure:
			return TriggerType.LeisureHappinessFactor;
		case HappinessFactor.Tax:
			return TriggerType.TaxHappinessFactor;
		case HappinessFactor.Buildings:
			return TriggerType.BuildingsHappinessFactor;
		case HappinessFactor.Consumption:
			return TriggerType.WealthHappinessFactor;
		case HappinessFactor.TrafficPenalty:
			return TriggerType.TrafficPenaltyHappinessFactor;
		case HappinessFactor.DeathPenalty:
			return TriggerType.DeathPenaltyHappinessFactor;
		case HappinessFactor.Homelessness:
			return TriggerType.HomelessnessHappinessFactor;
		case HappinessFactor.ElectricityFee:
			return TriggerType.ElectricityFeeHappinessFactor;
		case HappinessFactor.WaterFee:
			return TriggerType.WaterFeeHappinessFactor;
		default:
			UnityEngine.Debug.LogError($"Unknown trigger type for happiness factor: {factor}");
			return TriggerType.NewNotification;
		}
	}
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 16;
	}
```

- `public static GetWaterFeeBonuses(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Buildings.WaterConsumer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& waterConsumers, System.Single relativeFee, Game.Prefabs.CitizenHappinessParameterData& data) : Unity.Mathematics.int2`  

```csharp
public static int2 GetWaterFeeBonuses(float relativeFee, in CitizenHappinessParameterData data)
	{
		return new int2
		{
			x = (int)math.round(data.m_WaterFeeHealthEffect.Evaluate(relativeFee)),
			y = (int)math.round(data.m_WaterFeeWellbeingEffect.Evaluate(relativeFee))
		};
	}
```

- `public static GetWaterFeeBonuses(System.Single relativeFee, Game.Prefabs.CitizenHappinessParameterData& data) : Unity.Mathematics.int2`  

```csharp
public static int2 GetWaterFeeBonuses(float relativeFee, in CitizenHappinessParameterData data)
	{
		return new int2
		{
			x = (int)math.round(data.m_WaterFeeHealthEffect.Evaluate(relativeFee)),
			y = (int)math.round(data.m_WaterFeeWellbeingEffect.Evaluate(relativeFee))
		};
	}
```

- `public static GetWaterFeeHappinessEffect(System.Single relativeFee, Game.Prefabs.CitizenHappinessParameterData& data) : System.Int32`  

```csharp
public static int GetWaterFeeHappinessEffect(float relativeFee, in CitizenHappinessParameterData data)
	{
		return (int)math.round((float)math.csum(GetWaterFeeBonuses(relativeFee, in data)) / 2f);
	}
```

- `public static GetWaterPollutionBonuses(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Buildings.WaterConsumer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& waterConsumers, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Game.Prefabs.CitizenHappinessParameterData& data) : Unity.Mathematics.int2`  

```csharp
public static int2 GetWaterPollutionBonuses(Entity building, ref ComponentLookup<WaterConsumer> waterConsumers, DynamicBuffer<CityModifier> cityModifiers, in CitizenHappinessParameterData data)
	{
		int2 result = default(int2);
		if (waterConsumers.HasComponent(building))
		{
			WaterConsumer waterConsumer = waterConsumers[building];
			if (waterConsumer.m_Pollution > 0f)
			{
				float value = 1f;
				CityUtils.ApplyModifier(ref value, cityModifiers, CityModifierType.PollutionHealthAffect);
				result.x = Mathf.RoundToInt(value * data.m_WaterPollutionBonusMultiplier * math.min(1f, 10f * waterConsumer.m_Pollution));
			}
		}
		return result;
	}
```

- `public static GetWaterSupplyBonuses(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Buildings.WaterConsumer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& waterConsumers, Game.Prefabs.CitizenHappinessParameterData& data) : Unity.Mathematics.int2`  

```csharp
public static int2 GetWaterSupplyBonuses(Entity building, ref ComponentLookup<WaterConsumer> waterConsumers, in CitizenHappinessParameterData data)
	{
		if (waterConsumers.TryGetComponent(building, out var componentData))
		{
			float num = math.saturate((float)(int)componentData.m_FreshCooldownCounter / data.m_WaterPenaltyDelay);
			return new int2
			{
				x = (int)math.round((float)(-data.m_WaterHealthPenalty) * num),
				y = (int)math.round((float)(-data.m_WaterWellbeingPenalty) * num)
			};
		}
		return default(int2);
	}
```

- `public static GetWelfareValue(System.Single curvePosition, Unity.Entities.DynamicBuffer<Game.Net.ServiceCoverage> serviceCoverage, Game.Prefabs.CitizenHappinessParameterData& data) : System.Single`  

```csharp
public static float GetWelfareValue(float curvePosition, DynamicBuffer<Game.Net.ServiceCoverage> serviceCoverage, in CitizenHappinessParameterData data)
	{
		return data.m_WelfareMultiplier * NetUtils.GetServiceCoverage(serviceCoverage, CoverageService.Welfare, curvePosition);
	}
```

- `public static GetWellfareBonuses(System.Single curvePosition, Unity.Entities.DynamicBuffer<Game.Net.ServiceCoverage> serviceCoverage, Game.Prefabs.CitizenHappinessParameterData& data, System.Int32 currentHappiness) : Unity.Mathematics.int2`  

```csharp
public static int2 GetWellfareBonuses(float curvePosition, DynamicBuffer<Game.Net.ServiceCoverage> serviceCoverage, in CitizenHappinessParameterData data, int currentHappiness)
	{
		int2 result = default(int2);
		float num = data.m_WelfareMultiplier * NetUtils.GetServiceCoverage(serviceCoverage, CoverageService.Welfare, curvePosition);
		result.y = Mathf.RoundToInt(num * (float)math.max(0, (50 - currentHappiness) / 50));
		return result;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_GroundPollutionSystem = base.World.GetOrCreateSystemManaged<GroundPollutionSystem>();
		m_AirPollutionSystem = base.World.GetOrCreateSystemManaged<AirPollutionSystem>();
		m_NoisePollutionSystem = base.World.GetOrCreateSystemManaged<NoisePollutionSystem>();
		m_TelecomCoverageSystem = base.World.GetOrCreateSystemManaged<TelecomCoverageSystem>();
		m_LocalEffectSystem = base.World.GetOrCreateSystemManaged<LocalEffectSystem>();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_TriggerSystem = base.World.GetOrCreateSystemManaged<TriggerSystem>();
		m_TaxSystem = base.World.GetOrCreateSystemManaged<TaxSystem>();
		m_CityStatisticsSystem = base.World.GetOrCreateSystemManaged<CityStatisticsSystem>();
		m_HappinessFactors = new NativeArray<int4>(400, Allocator.Persistent);
		m_FactorQueue = new NativeQueue<FactorItem>(Allocator.Persistent);
		m_HealthcareParameterQuery = GetEntityQuery(ComponentType.ReadOnly<HealthcareParameterData>());
		m_ParkParameterQuery = GetEntityQuery(ComponentType.ReadOnly<ParkParameterData>());
		m_EducationParameterQuery = GetEntityQuery(ComponentType.ReadOnly<EducationParameterData>());
		m_TelecomParameterQuery = GetEntityQuery(ComponentType.ReadOnly<TelecomParameterData>());
		m_GarbageParameterQuery = GetEntityQuery(ComponentType.ReadOnly<GarbageParameterData>());
		m_PoliceParameterQuery = GetEntityQuery(ComponentType.ReadOnly<PoliceConfigurationData>());
		m_CitizenHappinessParameterQuery = GetEntityQuery(ComponentType.ReadOnly<CitizenHappinessParameterData>());
		m_CitizenQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadWrite<Citizen>(),
				ComponentType.ReadOnly<HouseholdMember>(),
				ComponentType.ReadOnly<UpdateFrame>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_TimeSettingQuery = GetEntityQuery(ComponentType.ReadOnly<TimeSettingsData>());
		m_TimeDataQuery = GetEntityQuery(ComponentType.ReadOnly<TimeData>());
		m_HappinessFactorParameterQuery = GetEntityQuery(ComponentType.ReadOnly<HappinessFactorParameterData>());
		m_DebugData = new DebugWatchDistribution();
		RequireForUpdate(m_CitizenQuery);
		RequireForUpdate<ServiceFeeParameterData>();
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

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		m_DebugData.Dispose();
		m_HappinessFactors.Dispose();
		m_FactorQueue.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		uint updateFrameWithInterval = SimulationUtils.GetUpdateFrameWithInterval(m_SimulationSystem.frameIndex, (uint)GetUpdateInterval(SystemUpdatePhase.GameSimulation), 16);
		m_CitizenQuery.ResetFilter();
		m_CitizenQuery.AddSharedComponentFilter(new UpdateFrame(updateFrameWithInterval));
		NativeQueue<int>.ParallelWriter debugQueue = default(NativeQueue<int>.ParallelWriter);
		if (m_DebugData.IsEnabled)
		{
			debugQueue = m_DebugData.GetQueue(clear: false, out var _).AsParallelWriter();
		}
		JobHandle dependencies;
		JobHandle dependencies2;
		JobHandle dependencies3;
		JobHandle dependencies4;
		JobHandle dependencies5;
		JobHandle deps2;
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new CitizenHappinessJob
		{
			m_DebugQueue = debugQueue,
			m_DebugOn = m_DebugData.IsEnabled,
			m_CitizenType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_Citizen_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_HouseholdMemberType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_HouseholdMember_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CrimeVictimType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_CrimeVictim_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CriminalType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_Criminal_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_StudentType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_Student_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CurrentBuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_CurrentBuilding_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_HealthProblemType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_HealthProblem_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_Households = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Household_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HealthProblems = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HealthProblem_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Buildings = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ElectricityConsumers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_ElectricityConsumer_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Properties = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_PropertyRenter_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Resources = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Economy_Resources_RO_BufferLookup, ref base.CheckedStateRef),
			m_ServiceCoverages = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ServiceCoverage_RO_BufferLookup, ref base.CheckedStateRef),
			m_Transforms = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurrentDistrictData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_CurrentDistrict_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Prefabs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_WaterConsumers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_WaterConsumer_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Garbages = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_GarbageProducer_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HouseholdCitizens = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Citizens_HouseholdCitizen_RO_BufferLookup, ref base.CheckedStateRef),
			m_Locked = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_Locked_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CrimeProducers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_CrimeProducer_RO_ComponentLookup, ref base.CheckedStateRef),
			m_MailProducers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_MailProducer_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingPropertyDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingPropertyData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SpawnableBuildings = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnableBuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_DistrictModifiers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_DistrictModifier_RO_BufferLookup, ref base.CheckedStateRef),
			m_CityModifiers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_CityModifier_RO_BufferLookup, ref base.CheckedStateRef),
			m_ServiceFees = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_ServiceFee_RO_BufferLookup, ref base.CheckedStateRef),
			m_Prisons = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Prison_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Schools = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_School_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HomelessHouseholds = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HomelessHousehold_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PollutionMap = m_GroundPollutionSystem.GetMap(readOnly: true, out dependencies),
			m_AirPollutionMap = m_AirPollutionSystem.GetMap(readOnly: true, out dependencies2),
			m_NoisePollutionMap = m_NoisePollutionSystem.GetMap(readOnly: true, out dependencies3),
			m_TelecomCoverage = m_TelecomCoverageSystem.GetData(readOnly: true, out dependencies4),
			m_LocalEffectData = m_LocalEffectSystem.GetReadData(out dependencies5),
			m_HealthcareParameters = m_HealthcareParameterQuery.GetSingleton<HealthcareParameterData>(),
			m_ParkParameters = m_ParkParameterQuery.GetSingleton<ParkParameterData>(),
			m_EducationParameters = m_EducationParameterQuery.GetSingleton<EducationParameterData>(),
			m_TelecomParameters = m_TelecomParameterQuery.GetSingleton<TelecomParameterData>(),
			m_GarbageParameters = m_GarbageParameterQuery.GetSingleton<GarbageParameterData>(),
			m_PoliceParameters = m_PoliceParameterQuery.GetSingleton<PoliceConfigurationData>(),
			m_CitizenHappinessParameters = m_CitizenHappinessParameterQuery.GetSingleton<CitizenHappinessParameterData>(),
			m_SimulationFrame = m_SimulationSystem.frameIndex,
			m_TimeSettings = m_TimeSettingQuery.GetSingleton<TimeSettingsData>(),
			m_FeeParameters = __query_429327288_0.GetSingleton<ServiceFeeParameterData>(),
			m_TimeData = m_TimeDataQuery.GetSingleton<TimeData>(),
			m_TaxRates = m_TaxSystem.GetTaxRates(),
			m_RawUpdateFrame = updateFrameWithInterval,
			m_City = m_CitySystem.City,
			m_RandomSeed = RandomSeed.Next(),
			m_FactorQueue = m_FactorQueue.AsParallelWriter(),
			m_StatisticsEventQueue = m_CityStatisticsSystem.GetStatisticsEventQueue(out deps2).AsParallelWriter()
		}, m_CitizenQuery, JobHandle.CombineDependencies(dependencies5, dependencies4, JobHandle.CombineDependencies(dependencies2, dependencies3, JobHandle.CombineDependencies(base.Dependency, dependencies, deps2))));
		if (m_DebugData.IsEnabled)
		{
			m_DebugData.AddWriter(jobHandle);
		}
		m_GroundPollutionSystem.AddReader(jobHandle);
		m_AirPollutionSystem.AddReader(jobHandle);
		m_NoisePollutionSystem.AddReader(jobHandle);
		m_TelecomCoverageSystem.AddReader(jobHandle);
		m_LocalEffectSystem.AddLocalEffectReader(jobHandle);
		m_TaxSystem.AddReader(jobHandle);
		m_CityStatisticsSystem.AddWriter(jobHandle);
		HappinessFactorJob jobData = new HappinessFactorJob
		{
			m_FactorQueue = m_FactorQueue,
			m_HappinessFactors = m_HappinessFactors,
			m_RawUpdateFrame = updateFrameWithInterval,
			m_TriggerActionQueue = m_TriggerSystem.CreateActionBuffer(),
			m_ParameterEntity = m_HappinessFactorParameterQuery.GetSingletonEntity(),
			m_Parameters = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_HappinessFactorParameterData_RO_BufferLookup, ref base.CheckedStateRef),
			m_Locked = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_Locked_RO_ComponentLookup, ref base.CheckedStateRef)
		};
		base.Dependency = IJobExtensions.Schedule(jobData, jobHandle);
		m_LastDeps = base.Dependency;
		m_TriggerSystem.AddActionBufferWriter(base.Dependency);
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void SetDefaults(Context context)
	{
		for (int i = 0; i < 400; i++)
		{
			m_HappinessFactors[i] = default(int4);
		}
	}
```


## Nested types

- `Game.Simulation.CitizenHappinessSystem+HappinessFactor`  
- `Game.Simulation.CitizenHappinessSystem+FactorItem`  
- `Game.Simulation.CitizenHappinessSystem+CitizenHappinessJob`  
- `Game.Simulation.CitizenHappinessSystem+HappinessFactorJob`  
- `Game.Simulation.CitizenHappinessSystem+TypeHandle`  

