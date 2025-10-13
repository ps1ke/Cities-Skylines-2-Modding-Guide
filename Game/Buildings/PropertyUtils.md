# Game.Buildings.PropertyUtils

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class PropertyUtils
{
    public static readonly System.Single kHomelessApartmentSize;

    public static System.Single GetApartmentQuality(System.Int32 familySize, System.Int32 children, Unity.Entities.Entity building, Game.Buildings.Building& buildingData, Unity.Entities.Entity buildingPrefab, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingPropertyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildingProperties, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildingDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.SpawnableBuildingData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& spawnableDatas, Unity.Entities.ComponentLookup`1[[Game.Buildings.CrimeProducer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& crimes, Unity.Entities.BufferLookup`1[[Game.Net.ServiceCoverage, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& serviceCoverages, Unity.Entities.ComponentLookup`1[[Game.Prefabs.Locked, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& locked, Unity.Entities.ComponentLookup`1[[Game.Buildings.ElectricityConsumer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& electricityConsumers, Unity.Entities.ComponentLookup`1[[Game.Buildings.WaterConsumer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& waterConsumers, Unity.Entities.ComponentLookup`1[[Game.Buildings.GarbageProducer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& garbageProducers, Unity.Entities.ComponentLookup`1[[Game.Buildings.MailProducer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& mailProducers, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabs, Unity.Entities.ComponentLookup`1[[Game.Objects.Transform, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& transforms, Unity.Entities.ComponentLookup`1[[Game.Buildings.Abandoned, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& abandoneds, Unity.Collections.NativeArray<Game.Simulation.GroundPollution> pollutionMap, Unity.Collections.NativeArray<Game.Simulation.AirPollution> airPollutionMap, Unity.Collections.NativeArray<Game.Simulation.NoisePollution> noiseMap, Game.Simulation.CellMapData<Game.Simulation.TelecomCoverage> telecomCoverages, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Unity.Entities.Entity healthcareService, Unity.Entities.Entity entertainmentService, Unity.Entities.Entity educationService, Unity.Entities.Entity telecomService, Unity.Entities.Entity garbageService, Unity.Entities.Entity policeService, Game.Prefabs.CitizenHappinessParameterData happinessParameterData, Game.Prefabs.GarbageParameterData garbageParameterData, System.Int32 averageHappiness);
    public static System.Int32 GetBuildingLevel(Unity.Entities.Entity prefabEntity, Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> spawnableBuildingDatas);
    public static System.Single GetCachedApartmentQuality(System.Int32 familySize, System.Int32 children, System.Int32 averageHappiness, Game.Simulation.HouseholdFindPropertySystem+GenericApartmentQuality quality);
    public static Unity.Mathematics.int2 GetElectricityBonusForApartmentQuality(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Buildings.ElectricityConsumer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& electricityConsumers, Game.Prefabs.CitizenHappinessParameterData& data);
    public static Game.Simulation.HouseholdFindPropertySystem+GenericApartmentQuality GetGenericApartmentQuality(Unity.Entities.Entity building, Unity.Entities.Entity buildingPrefab, Game.Buildings.Building& buildingData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingPropertyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildingProperties, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildingDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.SpawnableBuildingData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& spawnableDatas, Unity.Entities.ComponentLookup`1[[Game.Buildings.CrimeProducer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& crimes, Unity.Entities.BufferLookup`1[[Game.Net.ServiceCoverage, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& serviceCoverages, Unity.Entities.ComponentLookup`1[[Game.Prefabs.Locked, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& locked, Unity.Entities.ComponentLookup`1[[Game.Buildings.ElectricityConsumer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& electricityConsumers, Unity.Entities.ComponentLookup`1[[Game.Buildings.WaterConsumer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& waterConsumers, Unity.Entities.ComponentLookup`1[[Game.Buildings.GarbageProducer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& garbageProducers, Unity.Entities.ComponentLookup`1[[Game.Buildings.MailProducer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& mailProducers, Unity.Entities.ComponentLookup`1[[Game.Objects.Transform, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& transforms, Unity.Entities.ComponentLookup`1[[Game.Buildings.Abandoned, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& abandoneds, Unity.Collections.NativeArray<Game.Simulation.GroundPollution> pollutionMap, Unity.Collections.NativeArray<Game.Simulation.AirPollution> airPollutionMap, Unity.Collections.NativeArray<Game.Simulation.NoisePollution> noiseMap, Game.Simulation.CellMapData<Game.Simulation.TelecomCoverage> telecomCoverages, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Unity.Entities.Entity healthcareService, Unity.Entities.Entity entertainmentService, Unity.Entities.Entity educationService, Unity.Entities.Entity telecomService, Unity.Entities.Entity garbageService, Unity.Entities.Entity policeService, Game.Prefabs.CitizenHappinessParameterData happinessParameterData, Game.Prefabs.GarbageParameterData garbageParameterData);
    public static System.Single GetPropertyScore(Unity.Entities.Entity property, Unity.Entities.Entity household, Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> citizenBuffer, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingPropertyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildingProperties, Unity.Entities.ComponentLookup`1[[Game.Buildings.Building, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildings, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildingDatas, Unity.Entities.ComponentLookup`1[[Game.Citizens.Household, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& households, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.Student, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& students, Unity.Entities.ComponentLookup`1[[Game.Citizens.Worker, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& workers, Unity.Entities.ComponentLookup`1[[Game.Prefabs.SpawnableBuildingData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& spawnableDatas, Unity.Entities.ComponentLookup`1[[Game.Buildings.CrimeProducer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& crimes, Unity.Entities.BufferLookup`1[[Game.Net.ServiceCoverage, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& serviceCoverages, Unity.Entities.ComponentLookup`1[[Game.Prefabs.Locked, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& locked, Unity.Entities.ComponentLookup`1[[Game.Buildings.ElectricityConsumer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& electricityConsumers, Unity.Entities.ComponentLookup`1[[Game.Buildings.WaterConsumer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& waterConsumers, Unity.Entities.ComponentLookup`1[[Game.Buildings.GarbageProducer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& garbageProducers, Unity.Entities.ComponentLookup`1[[Game.Buildings.MailProducer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& mailProducers, Unity.Entities.ComponentLookup`1[[Game.Objects.Transform, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& transforms, Unity.Entities.ComponentLookup`1[[Game.Buildings.Abandoned, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& abandoneds, Unity.Entities.ComponentLookup`1[[Game.Buildings.Park, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parks, Unity.Entities.BufferLookup`1[[Game.Net.ResourceAvailability, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& availabilities, Unity.Collections.NativeArray<System.Int32> taxRates, Unity.Collections.NativeArray<Game.Simulation.GroundPollution> pollutionMap, Unity.Collections.NativeArray<Game.Simulation.AirPollution> airPollutionMap, Unity.Collections.NativeArray<Game.Simulation.NoisePollution> noiseMap, Game.Simulation.CellMapData<Game.Simulation.TelecomCoverage> telecomCoverages, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Unity.Entities.Entity healthcareService, Unity.Entities.Entity entertainmentService, Unity.Entities.Entity educationService, Unity.Entities.Entity telecomService, Unity.Entities.Entity garbageService, Unity.Entities.Entity policeService, Game.Prefabs.CitizenHappinessParameterData citizenHappinessParameterData, Game.Prefabs.GarbageParameterData garbageParameterData);
    public static System.Int32 GetRentPricePerRenter(Game.Prefabs.BuildingPropertyData buildingPropertyData, System.Int32 buildingLevel, System.Int32 lotSize, System.Single landValueBase, Game.Zones.AreaType areaType, Game.Prefabs.EconomyParameterData& economyParameterData, System.Boolean ignoreLandValue);
    public static System.Int32 GetResidentialProperties(Game.Prefabs.BuildingPropertyData propertyData);
    public static System.Single GetServiceAvailability(Unity.Entities.Entity roadEdge, System.Single curvePos, Unity.Entities.BufferLookup<Game.Net.ResourceAvailability> availabilities);
    public static Unity.Mathematics.int2 GetSewageBonusForApartmentQuality(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Buildings.WaterConsumer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& waterConsumers, Game.Prefabs.CitizenHappinessParameterData& data);
    public static Unity.Mathematics.int2 GetWaterBonusForApartmentQuality(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Buildings.WaterConsumer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& waterConsumers, Game.Prefabs.CitizenHappinessParameterData& data);
    public static Game.Prefabs.ZoneDensity GetZoneDensity(Game.Prefabs.ZoneData zoneData, Game.Prefabs.ZonePropertiesData zonePropertiesData);
    public static System.Boolean IsMixedBuilding(Unity.Entities.Entity buildingPrefab, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingPropertyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildingPropertyDatas);
    public static System.Boolean IsMixedBuilding(Game.Prefabs.BuildingPropertyData buildingPropertyData);
}
```


## Fields

- `public static readonly System.Single kHomelessApartmentSize`  

```csharp
public static readonly System.Single kHomelessApartmentSize;
```


## Methods

- `public static GetApartmentQuality(System.Int32 familySize, System.Int32 children, Unity.Entities.Entity building, Game.Buildings.Building& buildingData, Unity.Entities.Entity buildingPrefab, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingPropertyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildingProperties, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildingDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.SpawnableBuildingData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& spawnableDatas, Unity.Entities.ComponentLookup`1[[Game.Buildings.CrimeProducer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& crimes, Unity.Entities.BufferLookup`1[[Game.Net.ServiceCoverage, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& serviceCoverages, Unity.Entities.ComponentLookup`1[[Game.Prefabs.Locked, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& locked, Unity.Entities.ComponentLookup`1[[Game.Buildings.ElectricityConsumer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& electricityConsumers, Unity.Entities.ComponentLookup`1[[Game.Buildings.WaterConsumer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& waterConsumers, Unity.Entities.ComponentLookup`1[[Game.Buildings.GarbageProducer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& garbageProducers, Unity.Entities.ComponentLookup`1[[Game.Buildings.MailProducer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& mailProducers, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabs, Unity.Entities.ComponentLookup`1[[Game.Objects.Transform, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& transforms, Unity.Entities.ComponentLookup`1[[Game.Buildings.Abandoned, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& abandoneds, Unity.Collections.NativeArray<Game.Simulation.GroundPollution> pollutionMap, Unity.Collections.NativeArray<Game.Simulation.AirPollution> airPollutionMap, Unity.Collections.NativeArray<Game.Simulation.NoisePollution> noiseMap, Game.Simulation.CellMapData<Game.Simulation.TelecomCoverage> telecomCoverages, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Unity.Entities.Entity healthcareService, Unity.Entities.Entity entertainmentService, Unity.Entities.Entity educationService, Unity.Entities.Entity telecomService, Unity.Entities.Entity garbageService, Unity.Entities.Entity policeService, Game.Prefabs.CitizenHappinessParameterData happinessParameterData, Game.Prefabs.GarbageParameterData garbageParameterData, System.Int32 averageHappiness) : System.Single`  

```csharp
public static float GetApartmentQuality(int familySize, int children, Entity building, ref Building buildingData, Entity buildingPrefab, ref ComponentLookup<BuildingPropertyData> buildingProperties, ref ComponentLookup<BuildingData> buildingDatas, ref ComponentLookup<SpawnableBuildingData> spawnableDatas, ref ComponentLookup<CrimeProducer> crimes, ref BufferLookup<Game.Net.ServiceCoverage> serviceCoverages, ref ComponentLookup<Locked> locked, ref ComponentLookup<ElectricityConsumer> electricityConsumers, ref ComponentLookup<WaterConsumer> waterConsumers, ref ComponentLookup<GarbageProducer> garbageProducers, ref ComponentLookup<MailProducer> mailProducers, ref ComponentLookup<PrefabRef> prefabs, ref ComponentLookup<Game.Objects.Transform> transforms, ref ComponentLookup<Abandoned> abandoneds, NativeArray<GroundPollution> pollutionMap, NativeArray<AirPollution> airPollutionMap, NativeArray<NoisePollution> noiseMap, CellMapData<TelecomCoverage> telecomCoverages, DynamicBuffer<CityModifier> cityModifiers, Entity healthcareService, Entity entertainmentService, Entity educationService, Entity telecomService, Entity garbageService, Entity policeService, CitizenHappinessParameterData happinessParameterData, GarbageParameterData garbageParameterData, int averageHappiness)
	{
		HouseholdFindPropertySystem.GenericApartmentQuality genericApartmentQuality = GetGenericApartmentQuality(building, buildingPrefab, ref buildingData, ref buildingProperties, ref buildingDatas, ref spawnableDatas, ref crimes, ref serviceCoverages, ref locked, ref electricityConsumers, ref waterConsumers, ref garbageProducers, ref mailProducers, ref transforms, ref abandoneds, pollutionMap, airPollutionMap, noiseMap, telecomCoverages, cityModifiers, healthcareService, entertainmentService, educationService, telecomService, garbageService, policeService, happinessParameterData, garbageParameterData);
		int2 cachedWelfareBonuses = CitizenHappinessSystem.GetCachedWelfareBonuses(genericApartmentQuality.welfareBonus, averageHappiness);
		return CitizenHappinessSystem.GetApartmentWellbeing(genericApartmentQuality.apartmentSize / (float)familySize, spawnableDatas[buildingPrefab].m_Level) + math.sqrt(children) * (genericApartmentQuality.educationBonus.x + genericApartmentQuality.educationBonus.y) + (float)cachedWelfareBonuses.x + (float)cachedWelfareBonuses.y + genericApartmentQuality.score;
	}
```

- `public static GetBuildingLevel(Unity.Entities.Entity prefabEntity, Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> spawnableBuildingDatas) : System.Int32`  

```csharp
public static int GetBuildingLevel(Entity prefabEntity, ComponentLookup<SpawnableBuildingData> spawnableBuildingDatas)
	{
		if (spawnableBuildingDatas.TryGetComponent(prefabEntity, out var componentData))
		{
			return componentData.m_Level;
		}
		return 1;
	}
```

- `public static GetCachedApartmentQuality(System.Int32 familySize, System.Int32 children, System.Int32 averageHappiness, Game.Simulation.HouseholdFindPropertySystem+GenericApartmentQuality quality) : System.Single`  

```csharp
public static float GetCachedApartmentQuality(int familySize, int children, int averageHappiness, HouseholdFindPropertySystem.GenericApartmentQuality quality)
	{
		int2 cachedWelfareBonuses = CitizenHappinessSystem.GetCachedWelfareBonuses(quality.welfareBonus, averageHappiness);
		return CitizenHappinessSystem.GetApartmentWellbeing(quality.apartmentSize / (float)familySize, quality.level) + math.sqrt(children) * (quality.educationBonus.x + quality.educationBonus.y) + (float)cachedWelfareBonuses.x + (float)cachedWelfareBonuses.y + quality.score;
	}
```

- `public static GetElectricityBonusForApartmentQuality(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Buildings.ElectricityConsumer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& electricityConsumers, Game.Prefabs.CitizenHappinessParameterData& data) : Unity.Mathematics.int2`  

```csharp
public static int2 GetElectricityBonusForApartmentQuality(Entity building, ref ComponentLookup<ElectricityConsumer> electricityConsumers, in CitizenHappinessParameterData data)
	{
		if (electricityConsumers.TryGetComponent(building, out var componentData) && !componentData.electricityConnected)
		{
			return new int2
			{
				y = (int)math.round(0f - data.m_ElectricityWellbeingPenalty)
			};
		}
		return default(int2);
	}
```

- `public static GetGenericApartmentQuality(Unity.Entities.Entity building, Unity.Entities.Entity buildingPrefab, Game.Buildings.Building& buildingData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingPropertyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildingProperties, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildingDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.SpawnableBuildingData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& spawnableDatas, Unity.Entities.ComponentLookup`1[[Game.Buildings.CrimeProducer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& crimes, Unity.Entities.BufferLookup`1[[Game.Net.ServiceCoverage, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& serviceCoverages, Unity.Entities.ComponentLookup`1[[Game.Prefabs.Locked, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& locked, Unity.Entities.ComponentLookup`1[[Game.Buildings.ElectricityConsumer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& electricityConsumers, Unity.Entities.ComponentLookup`1[[Game.Buildings.WaterConsumer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& waterConsumers, Unity.Entities.ComponentLookup`1[[Game.Buildings.GarbageProducer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& garbageProducers, Unity.Entities.ComponentLookup`1[[Game.Buildings.MailProducer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& mailProducers, Unity.Entities.ComponentLookup`1[[Game.Objects.Transform, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& transforms, Unity.Entities.ComponentLookup`1[[Game.Buildings.Abandoned, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& abandoneds, Unity.Collections.NativeArray<Game.Simulation.GroundPollution> pollutionMap, Unity.Collections.NativeArray<Game.Simulation.AirPollution> airPollutionMap, Unity.Collections.NativeArray<Game.Simulation.NoisePollution> noiseMap, Game.Simulation.CellMapData<Game.Simulation.TelecomCoverage> telecomCoverages, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Unity.Entities.Entity healthcareService, Unity.Entities.Entity entertainmentService, Unity.Entities.Entity educationService, Unity.Entities.Entity telecomService, Unity.Entities.Entity garbageService, Unity.Entities.Entity policeService, Game.Prefabs.CitizenHappinessParameterData happinessParameterData, Game.Prefabs.GarbageParameterData garbageParameterData) : Game.Simulation.HouseholdFindPropertySystem+GenericApartmentQuality`  

```csharp
public static HouseholdFindPropertySystem.GenericApartmentQuality GetGenericApartmentQuality(Entity building, Entity buildingPrefab, ref Building buildingData, ref ComponentLookup<BuildingPropertyData> buildingProperties, ref ComponentLookup<BuildingData> buildingDatas, ref ComponentLookup<SpawnableBuildingData> spawnableDatas, ref ComponentLookup<CrimeProducer> crimes, ref BufferLookup<Game.Net.ServiceCoverage> serviceCoverages, ref ComponentLookup<Locked> locked, ref ComponentLookup<ElectricityConsumer> electricityConsumers, ref ComponentLookup<WaterConsumer> waterConsumers, ref ComponentLookup<GarbageProducer> garbageProducers, ref ComponentLookup<MailProducer> mailProducers, ref ComponentLookup<Game.Objects.Transform> transforms, ref ComponentLookup<Abandoned> abandoneds, NativeArray<GroundPollution> pollutionMap, NativeArray<AirPollution> airPollutionMap, NativeArray<NoisePollution> noiseMap, CellMapData<TelecomCoverage> telecomCoverages, DynamicBuffer<CityModifier> cityModifiers, Entity healthcareService, Entity entertainmentService, Entity educationService, Entity telecomService, Entity garbageService, Entity policeService, CitizenHappinessParameterData happinessParameterData, GarbageParameterData garbageParameterData)
	{
		HouseholdFindPropertySystem.GenericApartmentQuality result = default(HouseholdFindPropertySystem.GenericApartmentQuality);
		bool flag = true;
		BuildingPropertyData buildingPropertyData = default(BuildingPropertyData);
		SpawnableBuildingData spawnableBuildingData = default(SpawnableBuildingData);
		if (buildingProperties.HasComponent(buildingPrefab))
		{
			buildingPropertyData = buildingProperties[buildingPrefab];
			flag = false;
		}
		BuildingData buildingData2 = buildingDatas[buildingPrefab];
		if (spawnableDatas.HasComponent(buildingPrefab) && !abandoneds.HasComponent(building))
		{
			spawnableBuildingData = spawnableDatas[buildingPrefab];
		}
		else
		{
			flag = true;
		}
		result.apartmentSize = (flag ? kHomelessApartmentSize : (buildingPropertyData.m_SpaceMultiplier * (float)buildingData2.m_LotSize.x * (float)buildingData2.m_LotSize.y / math.max(1f, buildingPropertyData.m_ResidentialProperties)));
		result.level = spawnableBuildingData.m_Level;
		int2 @int = default(int2);
		int2 healthcareBonuses;
		if (serviceCoverages.HasBuffer(buildingData.m_RoadEdge))
		{
			DynamicBuffer<Game.Net.ServiceCoverage> serviceCoverage = serviceCoverages[buildingData.m_RoadEdge];
			healthcareBonuses = CitizenHappinessSystem.GetHealthcareBonuses(buildingData.m_CurvePosition, serviceCoverage, ref locked, healthcareService, in happinessParameterData);
			@int += healthcareBonuses;
			healthcareBonuses = CitizenHappinessSystem.GetEntertainmentBonuses(buildingData.m_CurvePosition, serviceCoverage, cityModifiers, ref locked, entertainmentService, in happinessParameterData);
			@int += healthcareBonuses;
			result.welfareBonus = CitizenHappinessSystem.GetWelfareValue(buildingData.m_CurvePosition, serviceCoverage, in happinessParameterData);
			result.educationBonus = CitizenHappinessSystem.GetEducationBonuses(buildingData.m_CurvePosition, serviceCoverage, ref locked, educationService, in happinessParameterData, 1);
		}
		int2 crimeBonuses = CitizenHappinessSystem.GetCrimeBonuses(default(CrimeVictim), building, ref crimes, ref locked, policeService, in happinessParameterData);
		healthcareBonuses = (flag ? new int2(0, -happinessParameterData.m_MaxCrimePenalty - crimeBonuses.y) : crimeBonuses);
		@int += healthcareBonuses;
		healthcareBonuses = CitizenHappinessSystem.GetGroundPollutionBonuses(building, ref transforms, pollutionMap, cityModifiers, in happinessParameterData);
		@int += healthcareBonuses;
		healthcareBonuses = CitizenHappinessSystem.GetAirPollutionBonuses(building, ref transforms, airPollutionMap, cityModifiers, in happinessParameterData);
		@int += healthcareBonuses;
		healthcareBonuses = CitizenHappinessSystem.GetNoiseBonuses(building, ref transforms, noiseMap, in happinessParameterData);
		@int += healthcareBonuses;
		healthcareBonuses = CitizenHappinessSystem.GetTelecomBonuses(building, ref transforms, telecomCoverages, ref locked, telecomService, in happinessParameterData);
		@int += healthcareBonuses;
		healthcareBonuses = GetElectricityBonusForApartmentQuality(building, ref electricityConsumers, in happinessParameterData);
		@int += healthcareBonuses;
		healthcareBonuses = GetWaterBonusForApartmentQuality(building, ref waterConsumers, in happinessParameterData);
		@int += healthcareBonuses;
		healthcareBonuses = GetSewageBonusForApartmentQuality(building, ref waterConsumers, in happinessParameterData);
		@int += healthcareBonuses;
		healthcareBonuses = CitizenHappinessSystem.GetWaterPollutionBonuses(building, ref waterConsumers, cityModifiers, in happinessParameterData);
		@int += healthcareBonuses;
		healthcareBonuses = CitizenHappinessSystem.GetGarbageBonuses(building, ref garbageProducers, ref locked, garbageService, in garbageParameterData);
		@int += healthcareBonuses;
		healthcareBonuses = CitizenHappinessSystem.GetMailBonuses(building, ref mailProducers, ref locked, telecomService, in happinessParameterData);
		@int += healthcareBonuses;
		if (flag)
		{
			healthcareBonuses = CitizenHappinessSystem.GetHomelessBonuses(in happinessParameterData);
			@int += healthcareBonuses;
		}
		result.score = @int.x + @int.y;
		return result;
	}
```

- `public static GetPropertyScore(Unity.Entities.Entity property, Unity.Entities.Entity household, Unity.Entities.DynamicBuffer<Game.Citizens.HouseholdCitizen> citizenBuffer, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingPropertyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildingProperties, Unity.Entities.ComponentLookup`1[[Game.Buildings.Building, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildings, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildingDatas, Unity.Entities.ComponentLookup`1[[Game.Citizens.Household, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& households, Unity.Entities.ComponentLookup`1[[Game.Citizens.Citizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& citizens, Unity.Entities.ComponentLookup`1[[Game.Citizens.Student, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& students, Unity.Entities.ComponentLookup`1[[Game.Citizens.Worker, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& workers, Unity.Entities.ComponentLookup`1[[Game.Prefabs.SpawnableBuildingData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& spawnableDatas, Unity.Entities.ComponentLookup`1[[Game.Buildings.CrimeProducer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& crimes, Unity.Entities.BufferLookup`1[[Game.Net.ServiceCoverage, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& serviceCoverages, Unity.Entities.ComponentLookup`1[[Game.Prefabs.Locked, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& locked, Unity.Entities.ComponentLookup`1[[Game.Buildings.ElectricityConsumer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& electricityConsumers, Unity.Entities.ComponentLookup`1[[Game.Buildings.WaterConsumer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& waterConsumers, Unity.Entities.ComponentLookup`1[[Game.Buildings.GarbageProducer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& garbageProducers, Unity.Entities.ComponentLookup`1[[Game.Buildings.MailProducer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& mailProducers, Unity.Entities.ComponentLookup`1[[Game.Objects.Transform, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& transforms, Unity.Entities.ComponentLookup`1[[Game.Buildings.Abandoned, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& abandoneds, Unity.Entities.ComponentLookup`1[[Game.Buildings.Park, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parks, Unity.Entities.BufferLookup`1[[Game.Net.ResourceAvailability, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& availabilities, Unity.Collections.NativeArray<System.Int32> taxRates, Unity.Collections.NativeArray<Game.Simulation.GroundPollution> pollutionMap, Unity.Collections.NativeArray<Game.Simulation.AirPollution> airPollutionMap, Unity.Collections.NativeArray<Game.Simulation.NoisePollution> noiseMap, Game.Simulation.CellMapData<Game.Simulation.TelecomCoverage> telecomCoverages, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Unity.Entities.Entity healthcareService, Unity.Entities.Entity entertainmentService, Unity.Entities.Entity educationService, Unity.Entities.Entity telecomService, Unity.Entities.Entity garbageService, Unity.Entities.Entity policeService, Game.Prefabs.CitizenHappinessParameterData citizenHappinessParameterData, Game.Prefabs.GarbageParameterData garbageParameterData) : System.Single`  

```csharp
public static float GetPropertyScore(Entity property, Entity household, DynamicBuffer<HouseholdCitizen> citizenBuffer, ref ComponentLookup<PrefabRef> prefabRefs, ref ComponentLookup<BuildingPropertyData> buildingProperties, ref ComponentLookup<Building> buildings, ref ComponentLookup<BuildingData> buildingDatas, ref ComponentLookup<Household> households, ref ComponentLookup<Citizen> citizens, ref ComponentLookup<Game.Citizens.Student> students, ref ComponentLookup<Worker> workers, ref ComponentLookup<SpawnableBuildingData> spawnableDatas, ref ComponentLookup<CrimeProducer> crimes, ref BufferLookup<Game.Net.ServiceCoverage> serviceCoverages, ref ComponentLookup<Locked> locked, ref ComponentLookup<ElectricityConsumer> electricityConsumers, ref ComponentLookup<WaterConsumer> waterConsumers, ref ComponentLookup<GarbageProducer> garbageProducers, ref ComponentLookup<MailProducer> mailProducers, ref ComponentLookup<Game.Objects.Transform> transforms, ref ComponentLookup<Abandoned> abandoneds, ref ComponentLookup<Park> parks, ref BufferLookup<ResourceAvailability> availabilities, NativeArray<int> taxRates, NativeArray<GroundPollution> pollutionMap, NativeArray<AirPollution> airPollutionMap, NativeArray<NoisePollution> noiseMap, CellMapData<TelecomCoverage> telecomCoverages, DynamicBuffer<CityModifier> cityModifiers, Entity healthcareService, Entity entertainmentService, Entity educationService, Entity telecomService, Entity garbageService, Entity policeService, CitizenHappinessParameterData citizenHappinessParameterData, GarbageParameterData garbageParameterData)
	{
		if (!buildings.HasComponent(property))
		{
			return float.NegativeInfinity;
		}
		bool flag = (households[household].m_Flags & HouseholdFlags.MovedIn) != 0;
		bool flag2 = BuildingUtils.IsHomelessShelterBuilding(property, ref parks, ref abandoneds);
		if (flag2 && !flag)
		{
			return float.NegativeInfinity;
		}
		Building buildingData = buildings[property];
		Entity prefab = prefabRefs[property].m_Prefab;
		HouseholdFindPropertySystem.GenericApartmentQuality genericApartmentQuality = GetGenericApartmentQuality(property, prefab, ref buildingData, ref buildingProperties, ref buildingDatas, ref spawnableDatas, ref crimes, ref serviceCoverages, ref locked, ref electricityConsumers, ref waterConsumers, ref garbageProducers, ref mailProducers, ref transforms, ref abandoneds, pollutionMap, airPollutionMap, noiseMap, telecomCoverages, cityModifiers, healthcareService, entertainmentService, educationService, telecomService, garbageService, policeService, citizenHappinessParameterData, garbageParameterData);
		int length = citizenBuffer.Length;
		float num = 0f;
		int num2 = 0;
		int num3 = 0;
		int num4 = 0;
		int num5 = 0;
		int num6 = 0;
		for (int i = 0; i < citizenBuffer.Length; i++)
		{
			Entity citizen = citizenBuffer[i].m_Citizen;
			Citizen citizen2 = citizens[citizen];
			num4 += citizen2.Happiness;
			if (citizen2.GetAge() == CitizenAge.Child)
			{
				num5++;
			}
			else
			{
				num3++;
				num6 += CitizenHappinessSystem.GetTaxBonuses(citizen2.GetEducationLevel(), taxRates, in citizenHappinessParameterData).y;
			}
			if (students.HasComponent(citizen))
			{
				num2++;
				Game.Citizens.Student student = students[citizen];
				if (student.m_School != property)
				{
					num += student.m_LastCommuteTime;
				}
			}
			else if (workers.HasComponent(citizen))
			{
				num2++;
				Worker worker = workers[citizen];
				if (worker.m_Workplace != property)
				{
					num += worker.m_LastCommuteTime;
				}
			}
		}
		if (num2 > 0)
		{
			num /= (float)num2;
		}
		if (citizenBuffer.Length > 0)
		{
			num4 /= citizenBuffer.Length;
			if (num3 > 0)
			{
				num6 /= num3;
			}
		}
		float serviceAvailability = GetServiceAvailability(buildingData.m_RoadEdge, buildingData.m_CurvePosition, availabilities);
		float cachedApartmentQuality = GetCachedApartmentQuality(length, num5, num4, genericApartmentQuality);
		float num7 = (flag2 ? (-1000) : 0);
		return serviceAvailability + cachedApartmentQuality + (float)(2 * num6) - num + num7;
	}
```

- `public static GetRentPricePerRenter(Game.Prefabs.BuildingPropertyData buildingPropertyData, System.Int32 buildingLevel, System.Int32 lotSize, System.Single landValueBase, Game.Zones.AreaType areaType, Game.Prefabs.EconomyParameterData& economyParameterData, System.Boolean ignoreLandValue = False) : System.Int32`  

```csharp
public static int GetRentPricePerRenter(BuildingPropertyData buildingPropertyData, int buildingLevel, int lotSize, float landValueBase, Game.Zones.AreaType areaType, ref EconomyParameterData economyParameterData, bool ignoreLandValue = false)
	{
		float num = economyParameterData.m_RentPriceBuildingZoneTypeBase.x;
		float num2 = economyParameterData.m_LandValueModifier.x;
		switch (areaType)
		{
		case Game.Zones.AreaType.Commercial:
			num = economyParameterData.m_RentPriceBuildingZoneTypeBase.y;
			num2 = economyParameterData.m_LandValueModifier.y;
			break;
		case Game.Zones.AreaType.Industrial:
			num = economyParameterData.m_RentPriceBuildingZoneTypeBase.z;
			num2 = economyParameterData.m_LandValueModifier.z;
			break;
		}
		float num3 = ((!ignoreLandValue) ? ((landValueBase * num2 + num * (float)buildingLevel) * (float)lotSize * buildingPropertyData.m_SpaceMultiplier) : (num * (float)buildingLevel * (float)lotSize * buildingPropertyData.m_SpaceMultiplier));
		float num4 = ((!IsMixedBuilding(buildingPropertyData)) ? ((float)buildingPropertyData.CountProperties()) : ((float)Mathf.RoundToInt((float)buildingPropertyData.m_ResidentialProperties / (1f - economyParameterData.m_MixedBuildingCompanyRentPercentage))));
		return Mathf.RoundToInt(num3 / num4);
	}
```

- `public static GetResidentialProperties(Game.Prefabs.BuildingPropertyData propertyData) : System.Int32`  

```csharp
public static int GetResidentialProperties(BuildingPropertyData propertyData)
	{
		return propertyData.CountProperties(Game.Zones.AreaType.Residential);
	}
```

- `public static GetServiceAvailability(Unity.Entities.Entity roadEdge, System.Single curvePos, Unity.Entities.BufferLookup<Game.Net.ResourceAvailability> availabilities) : System.Single`  

```csharp
public static float GetServiceAvailability(Entity roadEdge, float curvePos, BufferLookup<ResourceAvailability> availabilities)
	{
		if (availabilities.HasBuffer(roadEdge))
		{
			return NetUtils.GetAvailability(availabilities[roadEdge], AvailableResource.Services, curvePos);
		}
		return 0f;
	}
```

- `public static GetSewageBonusForApartmentQuality(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Buildings.WaterConsumer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& waterConsumers, Game.Prefabs.CitizenHappinessParameterData& data) : Unity.Mathematics.int2`  

```csharp
public static int2 GetSewageBonusForApartmentQuality(Entity building, ref ComponentLookup<WaterConsumer> waterConsumers, in CitizenHappinessParameterData data)
	{
		if (waterConsumers.TryGetComponent(building, out var componentData) && !componentData.sewageConnected)
		{
			return new int2
			{
				x = (int)math.round(-data.m_SewageHealthEffect),
				y = (int)math.round(-data.m_SewageWellbeingEffect)
			};
		}
		return default(int2);
	}
```

- `public static GetWaterBonusForApartmentQuality(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Buildings.WaterConsumer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& waterConsumers, Game.Prefabs.CitizenHappinessParameterData& data) : Unity.Mathematics.int2`  

```csharp
public static int2 GetWaterBonusForApartmentQuality(Entity building, ref ComponentLookup<WaterConsumer> waterConsumers, in CitizenHappinessParameterData data)
	{
		if (waterConsumers.TryGetComponent(building, out var componentData) && !componentData.waterConnected)
		{
			return new int2
			{
				x = (int)math.round(-data.m_WaterHealthPenalty),
				y = (int)math.round(-data.m_WaterWellbeingPenalty)
			};
		}
		return default(int2);
	}
```

- `public static GetZoneDensity(Game.Prefabs.ZoneData zoneData, Game.Prefabs.ZonePropertiesData zonePropertiesData) : Game.Prefabs.ZoneDensity`  

```csharp
public static ZoneDensity GetZoneDensity(ZoneData zoneData, ZonePropertiesData zonePropertiesData)
	{
		if (zoneData.m_AreaType == Game.Zones.AreaType.Residential)
		{
			if (zonePropertiesData.m_ScaleResidentials)
			{
				if (zonePropertiesData.m_ResidentialProperties < zonePropertiesData.m_SpaceMultiplier)
				{
					return ZoneDensity.Medium;
				}
				return ZoneDensity.High;
			}
			return ZoneDensity.Low;
		}
		if (zoneData.m_AreaType == Game.Zones.AreaType.Commercial)
		{
			if (zonePropertiesData.m_SpaceMultiplier > 1f)
			{
				return ZoneDensity.High;
			}
			return ZoneDensity.Low;
		}
		if (zoneData.m_AreaType == Game.Zones.AreaType.Industrial)
		{
			if (zoneData.IsOffice())
			{
				if (zonePropertiesData.m_SpaceMultiplier < 10f)
				{
					return ZoneDensity.Low;
				}
				return ZoneDensity.High;
			}
			return ZoneDensity.Low;
		}
		Assert.IsTrue(condition: false, $"Unknown Zone area type:{zoneData.m_AreaType}");
		return ZoneDensity.Low;
	}
```

- `public static IsMixedBuilding(Unity.Entities.Entity buildingPrefab, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingPropertyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildingPropertyDatas) : System.Boolean`  

```csharp
public static bool IsMixedBuilding(BuildingPropertyData buildingPropertyData)
	{
		if (buildingPropertyData.m_ResidentialProperties > 0)
		{
			if (buildingPropertyData.m_AllowedSold == Resource.NoResource)
			{
				return buildingPropertyData.m_AllowedManufactured != Resource.NoResource;
			}
			return true;
		}
		return false;
	}
```

- `public static IsMixedBuilding(Game.Prefabs.BuildingPropertyData buildingPropertyData) : System.Boolean`  

```csharp
public static bool IsMixedBuilding(BuildingPropertyData buildingPropertyData)
	{
		if (buildingPropertyData.m_ResidentialProperties > 0)
		{
			if (buildingPropertyData.m_AllowedSold == Resource.NoResource)
			{
				return buildingPropertyData.m_AllowedManufactured != Resource.NoResource;
			}
			return true;
		}
		return false;
	}
```


## Nested types

- `Game.Buildings.PropertyUtils+ExtractorFindCompanyJob`  
- `Game.Buildings.PropertyUtils+CompanyFindPropertyJob`  

