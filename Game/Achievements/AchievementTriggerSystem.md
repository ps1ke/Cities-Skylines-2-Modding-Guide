# Game.Achievements.AchievementTriggerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Achievements`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AchievementTriggerSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.ClimateSystem m_ClimateSystem;
    private Game.Simulation.TimeSystem m_TimeSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Unity.Entities.EntityQuery m_CreatedObjectQuery;
    private Unity.Entities.EntityQuery m_ObjectAchievementQuery;
    private Unity.Entities.EntityQuery m_UnlockQuery;
    private Unity.Entities.EntityQuery m_ParkQuery;
    private Unity.Entities.EntityQuery m_CreatedParkQuery;
    private Unity.Entities.EntityQuery m_LockedServiceQuery;
    private Unity.Entities.EntityQuery m_ServiceQuery;
    private Unity.Entities.EntityQuery m_LockedBuildingQuery;
    private Unity.Entities.EntityQuery m_BuildingQuery;
    private Unity.Entities.EntityQuery m_TransportLineQuery;
    private Unity.Entities.EntityQuery m_CreatedTransportLineQuery;
    private Unity.Entities.EntityQuery m_UniqueServiceBuildingPrefabQuery;
    private Unity.Entities.EntityQuery m_UniqueServiceBuildingQuery;
    private Unity.Entities.EntityQuery m_CreatedUniqueServiceBuildingQuery;
    private Unity.Entities.EntityQuery m_PolicyModificationQuery;
    private Unity.Entities.EntityQuery m_DistrictQuery;
    private Unity.Entities.EntityQuery m_ServiceDistrictBuildingQuery;
    private Unity.Entities.EntityQuery m_FossilEnergyProducersQuery;
    private Unity.Entities.EntityQuery m_RenewableEnergyProducersQuery;
    private Unity.Entities.EntityQuery m_EnergyProducersQuery;
    private Unity.Entities.EntityQuery m_WaterPumpingStationQuery;
    private Unity.Entities.EntityQuery m_ResidentialBuildingsQuery;
    private Unity.Entities.EntityQuery m_CommercialBuildingsQuery;
    private Unity.Entities.EntityQuery m_IndustrialBuildingsQuery;
    private Unity.Entities.EntityQuery m_FollowedCitizensQuery;
    private Unity.Entities.EntityQuery m_InfoviewQuery;
    private Unity.Entities.EntityQuery m_CreatedUniqueBuildingQuery;
    private Unity.Entities.EntityQuery m_UniqueBuildingQuery;
    private Unity.Entities.EntityQuery m_PlantQuery;
    private Unity.Entities.EntityQuery m_CreatedPlantQuery;
    private Unity.Entities.EntityQuery m_TimeDataQuery;
    private Unity.Entities.EntityQuery m_TimeSettingsQuery;
    private Unity.Entities.EntityQuery m_ProduceResourceCompaniesQuery;
    private Unity.Entities.EntityQuery m_CreatedAggregateElementQuery;
    private Unity.Entities.EntityQuery m_AggregateElementQuery;
    public Colossal.NativeCounter m_PatientsTreatedCounter;
    public Colossal.NativeCounter m_ProducedFishCounter;
    public Colossal.NativeCounter m_OffshoreOilProduceCounter;
    private Unity.Jobs.JobHandle m_TransportWriteDeps;
    private Unity.Collections.NativeQueue<Game.Achievements.TransportedResource> m_TransportedResourceQueue;
    private System.Int32 m_CachedPatientsTreatedCount;
    private System.Int32 m_CachedPopulationCount;
    private System.Int32 m_CachedHappiness;
    private System.Int32 m_CachedAttractiveness;
    private System.Int32 m_CachedTouristCount;
    private System.Boolean m_CheckUnlocks;
    private System.UInt32 m_LastCheckFrameIndex;
    private System.Collections.Generic.HashSet<Game.Prefabs.InfoviewPrefab> m_ViewedInfoviews;
    private System.Collections.Generic.Dictionary<Colossal.PSI.Common.AchievementId, System.Int32> m_IncrementalObjectAchievementProgress;
    private System.Collections.Generic.List<Colossal.PSI.Common.AchievementId> m_AbsoluteObjectAchievements;
    public Game.Achievements.AchievementTriggerSystem+ProgressBuffer m_LittleBitOfTLCBuffer;
    public Game.Achievements.AchievementTriggerSystem+ProgressBuffer m_HowMuchIsTheFishBuffer;
    public Game.Achievements.AchievementTriggerSystem+ProgressBuffer m_ADifferentPlatformerBuffer;
    public Game.Achievements.AchievementTriggerSystem+UserDataProgressBuffer m_SquasherDownerBuffer;
    public Game.Achievements.AchievementTriggerSystem+UserDataProgressBuffer m_ShipItBuffer;
    private Game.Achievements.AchievementTriggerSystem+TypeHandle __TypeHandle;
    private static Colossal.Logging.ILog sLog;
    private static readonly System.Int32 kMinCityEffectPopulation;
    private static readonly System.Int32 kAllSmilesHappiness;
    private static readonly System.Int32 kThisIsNotMyHappyPlaceHappiness;
    private static readonly System.Int32 kSimplyIrresistibleAttractiveness;
    private static readonly System.Int32 kZeroEmissionMinProduction;
    private static readonly System.Int32 kColossalGardenerLimit;
    private static readonly System.Int32 kTheDeepEndLoanAmount;

    public AchievementTriggerSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddWriter(Unity.Jobs.JobHandle writer);
    private System.Int32 CalculateEnergyProduction(Unity.Entities.EntityQuery entityQuery);
    private System.Boolean CheckFilter(Unity.Entities.DynamicBuffer<Game.Prefabs.AchievementFilterData> datas, Colossal.PSI.Common.AchievementId achievementID, System.Boolean defaultResult);
    private System.Boolean CheckFourSeasons();
    private System.Void CheckInGameAchievements();
    private System.Boolean CheckOneOfEverything();
    private System.Void CheckPolicyAchievements();
    private System.Void CheckTransportedResources();
    private System.Void CheckUnlockingAchievements();
    private System.Int32 CountAbsoluteObjectAchievementProgress(Colossal.PSI.Common.AchievementId achID);
    private System.Int32 CountLiftBridge();
    private System.Int32 CountParks();
    private System.Int32 CountSignatureBuildings();
    private System.Int32 CountUniqueServiceBuildingPrefabs();
    private System.Int32 CountUniqueServiceBuildings();
    public System.Void Deserialize<TReader>(TReader reader);
    public System.Boolean GetDebugData(Colossal.PSI.Common.AchievementId achievement, System.String& data);
    public Unity.Collections.NativeQueue<Game.Achievements.TransportedResource> GetTransportedResourceQueue();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    private System.Void OnInfoviewChanged(Game.Prefabs.InfoviewPrefab infoview);
    protected virtual System.Void OnUpdate();
    private System.Void Reset();
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
    private System.Boolean ShouldCheckOffshoreOilProduce();
    private System.Boolean ShouldCheckProducedFish();
}
```


## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.ClimateSystem m_ClimateSystem`  

```csharp
private Game.Simulation.ClimateSystem m_ClimateSystem;
```

- `private Game.Simulation.TimeSystem m_TimeSystem`  

```csharp
private Game.Simulation.TimeSystem m_TimeSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Unity.Entities.EntityQuery m_CreatedObjectQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedObjectQuery;
```

- `private Unity.Entities.EntityQuery m_ObjectAchievementQuery`  

```csharp
private Unity.Entities.EntityQuery m_ObjectAchievementQuery;
```

- `private Unity.Entities.EntityQuery m_UnlockQuery`  

```csharp
private Unity.Entities.EntityQuery m_UnlockQuery;
```

- `private Unity.Entities.EntityQuery m_ParkQuery`  

```csharp
private Unity.Entities.EntityQuery m_ParkQuery;
```

- `private Unity.Entities.EntityQuery m_CreatedParkQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedParkQuery;
```

- `private Unity.Entities.EntityQuery m_LockedServiceQuery`  

```csharp
private Unity.Entities.EntityQuery m_LockedServiceQuery;
```

- `private Unity.Entities.EntityQuery m_ServiceQuery`  

```csharp
private Unity.Entities.EntityQuery m_ServiceQuery;
```

- `private Unity.Entities.EntityQuery m_LockedBuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_LockedBuildingQuery;
```

- `private Unity.Entities.EntityQuery m_BuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingQuery;
```

- `private Unity.Entities.EntityQuery m_TransportLineQuery`  

```csharp
private Unity.Entities.EntityQuery m_TransportLineQuery;
```

- `private Unity.Entities.EntityQuery m_CreatedTransportLineQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedTransportLineQuery;
```

- `private Unity.Entities.EntityQuery m_UniqueServiceBuildingPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_UniqueServiceBuildingPrefabQuery;
```

- `private Unity.Entities.EntityQuery m_UniqueServiceBuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_UniqueServiceBuildingQuery;
```

- `private Unity.Entities.EntityQuery m_CreatedUniqueServiceBuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedUniqueServiceBuildingQuery;
```

- `private Unity.Entities.EntityQuery m_PolicyModificationQuery`  

```csharp
private Unity.Entities.EntityQuery m_PolicyModificationQuery;
```

- `private Unity.Entities.EntityQuery m_DistrictQuery`  

```csharp
private Unity.Entities.EntityQuery m_DistrictQuery;
```

- `private Unity.Entities.EntityQuery m_ServiceDistrictBuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_ServiceDistrictBuildingQuery;
```

- `private Unity.Entities.EntityQuery m_FossilEnergyProducersQuery`  

```csharp
private Unity.Entities.EntityQuery m_FossilEnergyProducersQuery;
```

- `private Unity.Entities.EntityQuery m_RenewableEnergyProducersQuery`  

```csharp
private Unity.Entities.EntityQuery m_RenewableEnergyProducersQuery;
```

- `private Unity.Entities.EntityQuery m_EnergyProducersQuery`  

```csharp
private Unity.Entities.EntityQuery m_EnergyProducersQuery;
```

- `private Unity.Entities.EntityQuery m_WaterPumpingStationQuery`  

```csharp
private Unity.Entities.EntityQuery m_WaterPumpingStationQuery;
```

- `private Unity.Entities.EntityQuery m_ResidentialBuildingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_ResidentialBuildingsQuery;
```

- `private Unity.Entities.EntityQuery m_CommercialBuildingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_CommercialBuildingsQuery;
```

- `private Unity.Entities.EntityQuery m_IndustrialBuildingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_IndustrialBuildingsQuery;
```

- `private Unity.Entities.EntityQuery m_FollowedCitizensQuery`  

```csharp
private Unity.Entities.EntityQuery m_FollowedCitizensQuery;
```

- `private Unity.Entities.EntityQuery m_InfoviewQuery`  

```csharp
private Unity.Entities.EntityQuery m_InfoviewQuery;
```

- `private Unity.Entities.EntityQuery m_CreatedUniqueBuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedUniqueBuildingQuery;
```

- `private Unity.Entities.EntityQuery m_UniqueBuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_UniqueBuildingQuery;
```

- `private Unity.Entities.EntityQuery m_PlantQuery`  

```csharp
private Unity.Entities.EntityQuery m_PlantQuery;
```

- `private Unity.Entities.EntityQuery m_CreatedPlantQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedPlantQuery;
```

- `private Unity.Entities.EntityQuery m_TimeDataQuery`  

```csharp
private Unity.Entities.EntityQuery m_TimeDataQuery;
```

- `private Unity.Entities.EntityQuery m_TimeSettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_TimeSettingsQuery;
```

- `private Unity.Entities.EntityQuery m_ProduceResourceCompaniesQuery`  

```csharp
private Unity.Entities.EntityQuery m_ProduceResourceCompaniesQuery;
```

- `private Unity.Entities.EntityQuery m_CreatedAggregateElementQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedAggregateElementQuery;
```

- `private Unity.Entities.EntityQuery m_AggregateElementQuery`  

```csharp
private Unity.Entities.EntityQuery m_AggregateElementQuery;
```

- `public Colossal.NativeCounter m_PatientsTreatedCounter`  

```csharp
public Colossal.NativeCounter m_PatientsTreatedCounter;
```

- `public Colossal.NativeCounter m_ProducedFishCounter`  

```csharp
public Colossal.NativeCounter m_ProducedFishCounter;
```

- `public Colossal.NativeCounter m_OffshoreOilProduceCounter`  

```csharp
public Colossal.NativeCounter m_OffshoreOilProduceCounter;
```

- `private Unity.Jobs.JobHandle m_TransportWriteDeps`  

```csharp
private Unity.Jobs.JobHandle m_TransportWriteDeps;
```

- `private Unity.Collections.NativeQueue<Game.Achievements.TransportedResource> m_TransportedResourceQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.Achievements.TransportedResource> m_TransportedResourceQueue;
```

- `private System.Int32 m_CachedPatientsTreatedCount`  

```csharp
private System.Int32 m_CachedPatientsTreatedCount;
```

- `private System.Int32 m_CachedPopulationCount`  

```csharp
private System.Int32 m_CachedPopulationCount;
```

- `private System.Int32 m_CachedHappiness`  

```csharp
private System.Int32 m_CachedHappiness;
```

- `private System.Int32 m_CachedAttractiveness`  

```csharp
private System.Int32 m_CachedAttractiveness;
```

- `private System.Int32 m_CachedTouristCount`  

```csharp
private System.Int32 m_CachedTouristCount;
```

- `private System.Boolean m_CheckUnlocks`  

```csharp
private System.Boolean m_CheckUnlocks;
```

- `private System.UInt32 m_LastCheckFrameIndex`  

```csharp
private System.UInt32 m_LastCheckFrameIndex;
```

- `private System.Collections.Generic.HashSet<Game.Prefabs.InfoviewPrefab> m_ViewedInfoviews`  

```csharp
private System.Collections.Generic.HashSet<Game.Prefabs.InfoviewPrefab> m_ViewedInfoviews;
```

- `private System.Collections.Generic.Dictionary<Colossal.PSI.Common.AchievementId, System.Int32> m_IncrementalObjectAchievementProgress`  

```csharp
private System.Collections.Generic.Dictionary<Colossal.PSI.Common.AchievementId, System.Int32> m_IncrementalObjectAchievementProgress;
```

- `private System.Collections.Generic.List<Colossal.PSI.Common.AchievementId> m_AbsoluteObjectAchievements`  

```csharp
private System.Collections.Generic.List<Colossal.PSI.Common.AchievementId> m_AbsoluteObjectAchievements;
```

- `public Game.Achievements.AchievementTriggerSystem+ProgressBuffer m_LittleBitOfTLCBuffer`  

```csharp
public Game.Achievements.AchievementTriggerSystem+ProgressBuffer m_LittleBitOfTLCBuffer;
```

- `public Game.Achievements.AchievementTriggerSystem+ProgressBuffer m_HowMuchIsTheFishBuffer`  

```csharp
public Game.Achievements.AchievementTriggerSystem+ProgressBuffer m_HowMuchIsTheFishBuffer;
```

- `public Game.Achievements.AchievementTriggerSystem+ProgressBuffer m_ADifferentPlatformerBuffer`  

```csharp
public Game.Achievements.AchievementTriggerSystem+ProgressBuffer m_ADifferentPlatformerBuffer;
```

- `public Game.Achievements.AchievementTriggerSystem+UserDataProgressBuffer m_SquasherDownerBuffer`  

```csharp
public Game.Achievements.AchievementTriggerSystem+UserDataProgressBuffer m_SquasherDownerBuffer;
```

- `public Game.Achievements.AchievementTriggerSystem+UserDataProgressBuffer m_ShipItBuffer`  

```csharp
public Game.Achievements.AchievementTriggerSystem+UserDataProgressBuffer m_ShipItBuffer;
```

- `private Game.Achievements.AchievementTriggerSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Achievements.AchievementTriggerSystem+TypeHandle __TypeHandle;
```

- `private static Colossal.Logging.ILog sLog`  

```csharp
private static Colossal.Logging.ILog sLog;
```

- `private static readonly System.Int32 kMinCityEffectPopulation`  

```csharp
private static readonly System.Int32 kMinCityEffectPopulation;
```

- `private static readonly System.Int32 kAllSmilesHappiness`  

```csharp
private static readonly System.Int32 kAllSmilesHappiness;
```

- `private static readonly System.Int32 kThisIsNotMyHappyPlaceHappiness`  

```csharp
private static readonly System.Int32 kThisIsNotMyHappyPlaceHappiness;
```

- `private static readonly System.Int32 kSimplyIrresistibleAttractiveness`  

```csharp
private static readonly System.Int32 kSimplyIrresistibleAttractiveness;
```

- `private static readonly System.Int32 kZeroEmissionMinProduction`  

```csharp
private static readonly System.Int32 kZeroEmissionMinProduction;
```

- `private static readonly System.Int32 kColossalGardenerLimit`  

```csharp
private static readonly System.Int32 kColossalGardenerLimit;
```

- `private static readonly System.Int32 kTheDeepEndLoanAmount`  

```csharp
private static readonly System.Int32 kTheDeepEndLoanAmount;
```


## Constructors

- `public AchievementTriggerSystem()`  

```csharp
[Preserve]
	public AchievementTriggerSystem()
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

- `public AddWriter(Unity.Jobs.JobHandle writer) : System.Void`  

```csharp
public void AddWriter(JobHandle writer)
	{
		m_TransportWriteDeps = JobHandle.CombineDependencies(m_TransportWriteDeps, writer);
	}
```

- `private CalculateEnergyProduction(Unity.Entities.EntityQuery entityQuery) : System.Int32`  

```csharp
private int CalculateEnergyProduction(EntityQuery entityQuery)
	{
		int num = 0;
		NativeArray<ElectricityProducer> nativeArray = entityQuery.ToComponentDataArray<ElectricityProducer>(Allocator.TempJob);
		for (int i = 0; i < nativeArray.Length; i++)
		{
			num += nativeArray[i].m_Capacity;
		}
		nativeArray.Dispose();
		return num;
	}
```

- `private CheckFilter(Unity.Entities.DynamicBuffer<Game.Prefabs.AchievementFilterData> datas, Colossal.PSI.Common.AchievementId achievementID, System.Boolean defaultResult = False) : System.Boolean`  

```csharp
private bool CheckFilter(DynamicBuffer<AchievementFilterData> datas, AchievementId achievementID, bool defaultResult = false)
	{
		for (int i = 0; i < datas.Length; i++)
		{
			if (datas[i].m_AchievementID == achievementID)
			{
				return datas[i].m_Allow;
			}
		}
		return defaultResult;
	}
```

- `private CheckFourSeasons() : System.Boolean`  

```csharp
private bool CheckFourSeasons()
	{
		if (!PlatformManager.instance.GetAchievement(Achievements.FourSeasons, out var achievement) || achievement.achieved)
		{
			return false;
		}
		Entity currentClimate = m_ClimateSystem.currentClimate;
		if (currentClimate == Entity.Null)
		{
			return false;
		}
		ClimatePrefab prefab = m_PrefabSystem.GetPrefab<ClimatePrefab>(currentClimate);
		if (prefab == null)
		{
			return false;
		}
		ClimateSystem.SeasonInfo[] seasons = prefab.m_Seasons;
		if ((seasons != null && seasons.Length < 4) || prefab.temperatureRange.min > 0f)
		{
			return false;
		}
		TimeData singleton = m_TimeDataQuery.GetSingleton<TimeData>();
		TimeSettingsData singleton2 = m_TimeSettingsQuery.GetSingleton<TimeSettingsData>();
		float startingDate = m_TimeSystem.GetStartingDate(singleton2, singleton);
		float elapsedYears = m_TimeSystem.GetElapsedYears(singleton2, singleton);
		return prefab.CountElapsedSeasons(startingDate, elapsedYears) >= prefab.m_Seasons?.Length;
	}
```

- `private CheckInGameAchievements() : System.Void`  

```csharp
private void CheckInGameAchievements()
	{
		if (!m_CreatedObjectQuery.IsEmptyIgnoreFilter)
		{
			NativeArray<Entity> nativeArray = m_CreatedObjectQuery.ToEntityArray(Allocator.TempJob);
			for (int i = 0; i < nativeArray.Length; i++)
			{
				if (!base.EntityManager.TryGetComponent<PrefabRef>(nativeArray[i], out var component) || !base.EntityManager.TryGetBuffer(component.m_Prefab, isReadOnly: true, out DynamicBuffer<ObjectAchievementData> buffer))
				{
					continue;
				}
				for (int j = 0; j < buffer.Length; j++)
				{
					if (buffer[j].m_BypassCounter)
					{
						PlatformManager.instance.UnlockAchievement(buffer[j].m_ID);
					}
					else if (buffer[j].m_AbsoluteCounter)
					{
						if (!m_AbsoluteObjectAchievements.Contains(buffer[j].m_ID))
						{
							m_AbsoluteObjectAchievements.Add(buffer[j].m_ID);
						}
					}
					else
					{
						int valueOrDefault = m_IncrementalObjectAchievementProgress.GetValueOrDefault(buffer[j].m_ID, 0);
						valueOrDefault++;
						m_IncrementalObjectAchievementProgress[buffer[j].m_ID] = valueOrDefault;
					}
				}
			}
			foreach (KeyValuePair<AchievementId, int> item in m_IncrementalObjectAchievementProgress)
			{
				if (PlatformManager.instance.GetAchievement(item.Key, out var achievement))
				{
					int b = achievement.maxProgress - achievement.progress;
					int value = Mathf.Min(item.Value, b);
					PlatformManager.instance.IndicateAchievementProgress(item.Key, value, IndicateType.Increment);
				}
			}
			foreach (AchievementId item2 in m_AbsoluteObjectAchievements)
			{
				if (PlatformManager.instance.GetAchievement(item2, out var achievement2) && !achievement2.achieved)
				{
					int a = CountAbsoluteObjectAchievementProgress(item2);
					a = Mathf.Min(a, achievement2.maxProgress);
					PlatformManager.instance.IndicateAchievementProgress(item2, a);
				}
			}
			m_IncrementalObjectAchievementProgress.Clear();
			m_AbsoluteObjectAchievements.Clear();
			nativeArray.Dispose();
		}
		int value2;
		if (!m_CreatedParkQuery.IsEmptyIgnoreFilter)
		{
			value2 = CountParks();
			PlatformManager.instance.IndicateAchievementProgress(Achievements.Groundskeeper, value2);
		}
		if (m_CheckUnlocks || !m_UnlockQuery.IsEmptyIgnoreFilter)
		{
			m_CheckUnlocks = false;
			CheckUnlockingAchievements();
		}
		if (base.EntityManager.TryGetComponent<Loan>(m_CitySystem.City, out var component2) && component2.m_LastModified >= m_LastCheckFrameIndex)
		{
			PlatformManager.instance.IndicateAchievementProgress(Achievements.TheDeepEnd, Mathf.Min(component2.m_Amount, kTheDeepEndLoanAmount));
		}
		if (base.EntityManager.TryGetComponent<Population>(m_CitySystem.City, out var component3))
		{
			int num = ((component3.m_Population >= 10000) ? 10000 : 1000);
			int num2 = component3.m_Population / num * num;
			if (num2 != m_CachedPopulationCount)
			{
				m_CachedPopulationCount = num2;
				PlatformManager.instance.IndicateAchievementProgress(Achievements.SixFigures, num2);
			}
		}
		if (!m_CreatedTransportLineQuery.IsEmptyIgnoreFilter || !m_PolicyModificationQuery.IsEmptyIgnoreFilter)
		{
			value2 = 0;
			NativeArray<Route> nativeArray2 = m_TransportLineQuery.ToComponentDataArray<Route>(Allocator.TempJob);
			try
			{
				for (int k = 0; k < nativeArray2.Length; k++)
				{
					if (!RouteUtils.CheckOption(nativeArray2[k], RouteOption.Inactive))
					{
						value2++;
					}
				}
			}
			finally
			{
				nativeArray2.Dispose();
			}
			PlatformManager.instance.IndicateAchievementProgress(Achievements.GoAnywhere, value2);
			PlatformManager.instance.IndicateAchievementProgress(Achievements.Spiderwebbing, value2);
		}
		if (component3.m_Population >= kMinCityEffectPopulation)
		{
			if (m_CachedHappiness < kAllSmilesHappiness && component3.m_AverageHappiness >= kAllSmilesHappiness)
			{
				PlatformManager.instance.UnlockAchievement(Achievements.AllSmiles);
			}
			if (m_CachedHappiness > kThisIsNotMyHappyPlaceHappiness && component3.m_AverageHappiness <= kThisIsNotMyHappyPlaceHappiness)
			{
				PlatformManager.instance.UnlockAchievement(Achievements.ThisIsNotMyHappyPlace);
			}
			m_CachedHappiness = component3.m_AverageHappiness;
			if (base.EntityManager.TryGetComponent<Tourism>(m_CitySystem.City, out var component4))
			{
				if (m_CachedAttractiveness < kSimplyIrresistibleAttractiveness && component4.m_Attractiveness >= kSimplyIrresistibleAttractiveness)
				{
					PlatformManager.instance.UnlockAchievement(Achievements.SimplyIrresistible);
				}
				m_CachedAttractiveness = component4.m_Attractiveness;
			}
		}
		if (!m_CreatedUniqueServiceBuildingQuery.IsEmptyIgnoreFilter && CheckOneOfEverything())
		{
			PlatformManager.instance.UnlockAchievement(Achievements.OneofEverything);
		}
		BufferLookup<CityStatistic> bufferLookup = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_CityStatistic_RO_BufferLookup, ref base.CheckedStateRef);
		value2 = m_CityStatisticsSystem.GetStatisticValue(bufferLookup, StatisticType.TouristCount) / 1000 * 1000;
		if (m_CachedTouristCount != value2)
		{
			PlatformManager.instance.IndicateAchievementProgress(Achievements.WelcomeOneandAll, value2);
		}
		m_CachedTouristCount = value2;
		int statisticValue = m_CityStatisticsSystem.GetStatisticValue(bufferLookup, StatisticType.EducationCount);
		int statisticValue2 = m_CityStatisticsSystem.GetStatisticValue(bufferLookup, StatisticType.EducationCount, 1);
		int statisticValue3 = m_CityStatisticsSystem.GetStatisticValue(bufferLookup, StatisticType.EducationCount, 2);
		int statisticValue4 = m_CityStatisticsSystem.GetStatisticValue(bufferLookup, StatisticType.EducationCount, 3);
		int statisticValue5 = m_CityStatisticsSystem.GetStatisticValue(bufferLookup, StatisticType.EducationCount, 4);
		int num3 = statisticValue + statisticValue2 + statisticValue3 + statisticValue4 + statisticValue5;
		if (num3 > 0 && (float)statisticValue5 / (float)num3 >= 0.15f)
		{
			PlatformManager.instance.UnlockAchievement(Achievements.TopoftheClass);
		}
		if (!m_ServiceDistrictBuildingQuery.IsEmptyIgnoreFilter)
		{
			NativeArray<Entity> nativeArray3 = m_ServiceDistrictBuildingQuery.ToEntityArray(Allocator.TempJob);
			try
			{
				for (int l = 0; l < nativeArray3.Length; l++)
				{
					if (base.EntityManager.TryGetBuffer(nativeArray3[l], isReadOnly: true, out DynamicBuffer<ServiceDistrict> buffer2) && buffer2.Length > 0)
					{
						PlatformManager.instance.UnlockAchievement(Achievements.HappytobeofService);
					}
				}
			}
			finally
			{
				nativeArray3.Dispose();
			}
		}
		int num4 = CalculateEnergyProduction(m_RenewableEnergyProducersQuery);
		int num5 = CalculateEnergyProduction(m_FossilEnergyProducersQuery);
		if (num4 >= kZeroEmissionMinProduction && num5 <= 0)
		{
			PlatformManager.instance.UnlockAchievement(Achievements.ZeroEmission);
		}
		int num6 = m_ResidentialBuildingsQuery.CalculateEntityCount();
		int num7 = m_CommercialBuildingsQuery.CalculateEntityCount();
		bool flag = false;
		bool flag2 = false;
		NativeArray<Entity> nativeArray4 = m_IndustrialBuildingsQuery.ToEntityArray(Allocator.TempJob);
		ComponentLookup<PrefabRef> componentLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef);
		ComponentLookup<OfficeBuilding> componentLookup2 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_OfficeBuilding_RO_ComponentLookup, ref base.CheckedStateRef);
		try
		{
			for (int m = 0; m < nativeArray4.Length; m++)
			{
				if (componentLookup2.HasComponent(componentLookup[nativeArray4[m]].m_Prefab))
				{
					flag2 = true;
				}
				else
				{
					flag = true;
				}
				if (flag && flag2)
				{
					break;
				}
			}
		}
		finally
		{
			nativeArray4.Dispose();
		}
		if (flag && flag2 && num6 > 0 && num7 > 0)
		{
			PlatformManager.instance.UnlockAchievement(Achievements.StrengthThroughDiversity);
		}
		if (!m_FollowedCitizensQuery.IsEmptyIgnoreFilter)
		{
			NativeArray<Entity> nativeArray5 = m_FollowedCitizensQuery.ToEntityArray(Allocator.TempJob);
			ComponentLookup<Citizen> componentLookup3 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Citizen_RO_ComponentLookup, ref base.CheckedStateRef);
			ComponentLookup<Followed> componentLookup4 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Followed_RO_ComponentLookup, ref base.CheckedStateRef);
			try
			{
				for (int n = 0; n < nativeArray5.Length; n++)
				{
					if (componentLookup3.HasComponent(nativeArray5[n]) && componentLookup3[nativeArray5[n]].GetAge() == CitizenAge.Elderly && componentLookup4.HasComponent(nativeArray5[n]) && componentLookup4[nativeArray5[n]].m_StartedFollowingAsChild)
					{
						PlatformManager.instance.UnlockAchievement(Achievements.YouLittleStalker);
					}
				}
			}
			finally
			{
				nativeArray5.Dispose();
			}
		}
		if (!m_PolicyModificationQuery.IsEmptyIgnoreFilter)
		{
			CheckPolicyAchievements();
		}
		if (m_PatientsTreatedCounter.Count > m_CachedPatientsTreatedCount)
		{
			int progress = m_PatientsTreatedCounter.Count - m_CachedPatientsTreatedCount;
			m_LittleBitOfTLCBuffer.AddProgress(progress);
			m_CachedPatientsTreatedCount = m_PatientsTreatedCounter.Count;
		}
		if (ShouldCheckOffshoreOilProduce() && m_OffshoreOilProduceCounter.Count > 0)
		{
			m_ADifferentPlatformerBuffer.AddProgress(m_OffshoreOilProduceCounter.Count);
			m_OffshoreOilProduceCounter.Count = 0;
		}
		if (ShouldCheckProducedFish() && m_ProducedFishCounter.Count > 0)
		{
			m_HowMuchIsTheFishBuffer.AddProgress(m_ProducedFishCounter.Count);
			m_ProducedFishCounter.Count = 0;
		}
		if (!m_CreatedUniqueBuildingQuery.IsEmptyIgnoreFilter)
		{
			int value3 = CountSignatureBuildings();
			PlatformManager.instance.IndicateAchievementProgress(Achievements.MakingAMark, value3);
			PlatformManager.instance.IndicateAchievementProgress(Achievements.TheArchitect, value3);
		}
		if (!m_ResidentialBuildingsQuery.IsEmptyIgnoreFilter && !m_CommercialBuildingsQuery.IsEmptyIgnoreFilter && !m_IndustrialBuildingsQuery.IsEmptyIgnoreFilter && !m_EnergyProducersQuery.IsEmptyIgnoreFilter && !m_WaterPumpingStationQuery.IsEmptyIgnoreFilter)
		{
			PlatformManager.instance.UnlockAchievement(Achievements.MyFirstCity);
		}
		if (!m_CreatedPlantQuery.IsEmptyIgnoreFilter && m_PlantQuery.CalculateEntityCount() >= kColossalGardenerLimit)
		{
			PlatformManager.instance.UnlockAchievement(Achievements.ColossalGardener);
		}
		if (CheckFourSeasons())
		{
			PlatformManager.instance.UnlockAchievement(Achievements.FourSeasons);
		}
		if (!m_CreatedAggregateElementQuery.IsEmptyIgnoreFilter && PlatformManager.instance.GetAchievement(Achievements.DrawMeLikeOneOfYourLiftBridges, out var achievement3) && !achievement3.achieved)
		{
			int value4 = CountLiftBridge();
			PlatformManager.instance.IndicateAchievementProgress(Achievements.DrawMeLikeOneOfYourLiftBridges, value4);
		}
		if (!m_TransportedResourceQueue.IsEmpty())
		{
			if (PlatformManager.instance.GetAchievement(Achievements.ShipIt, out var achievement4) && !achievement4.achieved && m_TransportWriteDeps.IsCompleted)
			{
				CheckTransportedResources();
			}
			else
			{
				m_TransportedResourceQueue.Clear();
			}
		}
		m_LastCheckFrameIndex = m_SimulationSystem.frameIndex;
	}
```

- `private CheckOneOfEverything() : System.Boolean`  

```csharp
private bool CheckOneOfEverything()
	{
		int num = CountUniqueServiceBuildingPrefabs();
		return CountUniqueServiceBuildings() == num;
	}
```

- `private CheckPolicyAchievements() : System.Void`  

```csharp
private void CheckPolicyAchievements()
	{
		if (m_DistrictQuery.IsEmptyIgnoreFilter)
		{
			return;
		}
		int num = 0;
		NativeArray<Entity> nativeArray = m_DistrictQuery.ToEntityArray(Allocator.TempJob);
		BufferLookup<Policy> bufferLookup = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Policies_Policy_RO_BufferLookup, ref base.CheckedStateRef);
		for (int i = 0; i < nativeArray.Length; i++)
		{
			DynamicBuffer<Policy> dynamicBuffer = bufferLookup[nativeArray[i]];
			for (int j = 0; j < dynamicBuffer.Length; j++)
			{
				if ((dynamicBuffer[j].m_Flags & PolicyFlags.Active) != 0)
				{
					num++;
					break;
				}
			}
		}
		nativeArray.Dispose();
		if (num > 0)
		{
			PlatformManager.instance.UnlockAchievement(Achievements.ExecutiveDecision);
		}
		PlatformManager.instance.IndicateAchievementProgress(Achievements.WideVariety, num);
	}
```

- `private CheckTransportedResources() : System.Void`  

```csharp
private void CheckTransportedResources()
	{
		int num = 0;
		TransportedResource item;
		while (m_TransportedResourceQueue.TryDequeue(out item))
		{
			BufferLookup<AchievementFilterData> bufferLookup = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_AchievementFilterData_RO_BufferLookup, ref base.CheckedStateRef);
			if (base.EntityManager.TryGetComponent<PrefabRef>(item.m_CargoTransport, out var component) && bufferLookup.TryGetBuffer(component.m_Prefab, out var bufferData) && CheckFilter(bufferData, Achievements.ShipIt))
			{
				num += item.m_Amount;
			}
		}
		if (num > 0)
		{
			m_ShipItBuffer.AddProgress(num);
		}
	}
```

- `private CheckUnlockingAchievements() : System.Void`  

```csharp
private void CheckUnlockingAchievements()
	{
		if (!m_ServiceQuery.IsEmptyIgnoreFilter && m_LockedServiceQuery.IsEmpty)
		{
			PlatformManager.instance.UnlockAchievement(Achievements.RoyalFlush);
		}
		if (!m_BuildingQuery.IsEmptyIgnoreFilter && m_LockedBuildingQuery.IsEmpty)
		{
			PlatformManager.instance.UnlockAchievement(Achievements.KeyToTheCity);
		}
	}
```

- `private CountAbsoluteObjectAchievementProgress(Colossal.PSI.Common.AchievementId achID) : System.Int32`  

```csharp
private int CountAbsoluteObjectAchievementProgress(AchievementId achID)
	{
		float num = 0f;
		NativeArray<Entity> nativeArray = m_ObjectAchievementQuery.ToEntityArray(Allocator.TempJob);
		for (int i = 0; i < nativeArray.Length; i++)
		{
			if (!base.EntityManager.TryGetComponent<PrefabRef>(nativeArray[i], out var component) || !base.EntityManager.TryGetBuffer(component.m_Prefab, isReadOnly: true, out DynamicBuffer<ObjectAchievementData> buffer))
			{
				continue;
			}
			bool flag = false;
			for (int j = 0; j < buffer.Length; j++)
			{
				if (buffer[j].m_ID == achID)
				{
					flag = true;
					break;
				}
			}
			if (!flag)
			{
				continue;
			}
			if (achID == Achievements.Pierfect || achID == Achievements.ItsPronouncedKey)
			{
				if (base.EntityManager.TryGetComponent<Curve>(nativeArray[i], out var component2))
				{
					num += component2.m_Length;
				}
			}
			else
			{
				num += 1f;
			}
		}
		nativeArray.Dispose();
		return (int)num;
	}
```

- `private CountLiftBridge() : System.Int32`  

```csharp
private int CountLiftBridge()
	{
		NativeArray<Entity> nativeArray = m_AggregateElementQuery.ToEntityArray(Allocator.TempJob);
		int num = 0;
		for (int i = 0; i < nativeArray.Length; i++)
		{
			if (base.EntityManager.TryGetBuffer(nativeArray[i], isReadOnly: true, out DynamicBuffer<AggregateElement> buffer) && buffer.Length > 0 && !base.EntityManager.HasComponent<Owner>(buffer[0].m_Edge) && base.EntityManager.HasComponent<Road>(buffer[0].m_Edge) && base.EntityManager.TryGetComponent<PrefabRef>(buffer[0].m_Edge, out var component) && base.EntityManager.TryGetComponent<NetGeometryData>(component.m_Prefab, out var component2) && (component2.m_Flags & Game.Net.GeometryFlags.StraightEdges) == 0 && (component2.m_IntersectLayers & Layer.Waterway) != Layer.None)
			{
				num++;
			}
		}
		nativeArray.Dispose();
		return num;
	}
```

- `private CountParks() : System.Int32`  

```csharp
private int CountParks()
	{
		int num = 0;
		NativeArray<PrefabRef> nativeArray = m_ParkQuery.ToComponentDataArray<PrefabRef>(Allocator.TempJob);
		BufferLookup<AchievementFilterData> bufferLookup = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_AchievementFilterData_RO_BufferLookup, ref base.CheckedStateRef);
		for (int i = 0; i < nativeArray.Length; i++)
		{
			Entity prefab = nativeArray[i].m_Prefab;
			if (!bufferLookup.TryGetBuffer(prefab, out var bufferData) || CheckFilter(bufferData, Achievements.Groundskeeper, defaultResult: true))
			{
				num++;
			}
		}
		nativeArray.Dispose();
		return num;
	}
```

- `private CountSignatureBuildings() : System.Int32`  

```csharp
private int CountSignatureBuildings()
	{
		NativeArray<PrefabRef> nativeArray = m_UniqueBuildingQuery.ToComponentDataArray<PrefabRef>(Allocator.TempJob);
		ComponentLookup<SignatureBuildingData> componentLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SignatureBuildingData_RO_ComponentLookup, ref base.CheckedStateRef);
		int num = 0;
		for (int i = 0; i < nativeArray.Length; i++)
		{
			if (componentLookup.HasComponent(nativeArray[i].m_Prefab))
			{
				num++;
			}
		}
		nativeArray.Dispose();
		return num;
	}
```

- `private CountUniqueServiceBuildingPrefabs() : System.Int32`  

```csharp
private int CountUniqueServiceBuildingPrefabs()
	{
		BufferLookup<AchievementFilterData> bufferLookup = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_AchievementFilterData_RO_BufferLookup, ref base.CheckedStateRef);
		int num = 0;
		NativeArray<Entity> nativeArray = m_UniqueServiceBuildingPrefabQuery.ToEntityArray(Allocator.TempJob);
		for (int i = 0; i < nativeArray.Length; i++)
		{
			if (!bufferLookup.TryGetBuffer(nativeArray[i], out var bufferData) || CheckFilter(bufferData, Achievements.OneofEverything, defaultResult: true))
			{
				num++;
			}
		}
		nativeArray.Dispose();
		return num;
	}
```

- `private CountUniqueServiceBuildings() : System.Int32`  

```csharp
private int CountUniqueServiceBuildings()
	{
		BufferLookup<AchievementFilterData> bufferLookup = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_AchievementFilterData_RO_BufferLookup, ref base.CheckedStateRef);
		int num = 0;
		NativeArray<PrefabRef> nativeArray = m_UniqueServiceBuildingQuery.ToComponentDataArray<PrefabRef>(Allocator.TempJob);
		for (int i = 0; i < nativeArray.Length; i++)
		{
			Entity prefab = nativeArray[i].m_Prefab;
			if (!bufferLookup.TryGetBuffer(prefab, out var bufferData) || CheckFilter(bufferData, Achievements.OneofEverything, defaultResult: true))
			{
				num++;
			}
		}
		nativeArray.Dispose();
		return num;
	}
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public GetDebugData(Colossal.PSI.Common.AchievementId achievement, System.String& data) : System.Boolean`  

```csharp
public bool GetDebugData(AchievementId achievement, out string data)
	{
		if (achievement == Achievements.ALittleBitofTLC)
		{
			data = $"{m_LittleBitOfTLCBuffer?.m_Progress ?? 0}";
			return true;
		}
		if (achievement == Achievements.HowMuchIsTheFish)
		{
			data = $"{m_HowMuchIsTheFishBuffer?.m_Progress ?? 0}";
			return true;
		}
		if (achievement == Achievements.ADifferentPlatformer)
		{
			data = $"{m_ADifferentPlatformerBuffer?.m_Progress ?? 0}";
			return true;
		}
		if (achievement == Achievements.OneofEverything)
		{
			data = $"{CountUniqueServiceBuildings()}/{CountUniqueServiceBuildingPrefabs()}";
			return true;
		}
		data = string.Empty;
		return false;
	}
```

- `public GetTransportedResourceQueue() : Unity.Collections.NativeQueue<Game.Achievements.TransportedResource>`  

```csharp
public NativeQueue<TransportedResource> GetTransportedResourceQueue()
	{
		return m_TransportedResourceQueue;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_LittleBitOfTLCBuffer = new ProgressBuffer(Achievements.ALittleBitofTLC, 1000, IndicateType.Absolute);
		m_SquasherDownerBuffer = new UserDataProgressBuffer(Achievements.SquasherDowner, 10, IndicateType.Increment, "SquasherDowner");
		m_PatientsTreatedCounter = new NativeCounter(Allocator.Persistent);
		m_ProducedFishCounter = new NativeCounter(Allocator.Persistent);
		m_OffshoreOilProduceCounter = new NativeCounter(Allocator.Persistent);
		m_TransportedResourceQueue = new NativeQueue<TransportedResource>(Allocator.Persistent);
		m_HowMuchIsTheFishBuffer = new ProgressBuffer(Achievements.HowMuchIsTheFish, 100000, IndicateType.Absolute);
		m_ADifferentPlatformerBuffer = new ProgressBuffer(Achievements.ADifferentPlatformer, 10000, IndicateType.Absolute);
		m_ShipItBuffer = new UserDataProgressBuffer(Achievements.ShipIt, 1000000, IndicateType.Increment, "ShipIt");
		m_CachedPatientsTreatedCount = 0;
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_CityStatisticsSystem = base.World.GetOrCreateSystemManaged<CityStatisticsSystem>();
		m_CityConfigurationSystem = base.World.GetOrCreateSystemManaged<CityConfigurationSystem>();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_ClimateSystem = base.World.GetOrCreateSystemManaged<ClimateSystem>();
		m_TimeSystem = base.World.GetOrCreateSystemManaged<TimeSystem>();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_CreatedObjectQuery = GetEntityQuery(ComponentType.ReadOnly<ObjectAchievement>(), ComponentType.ReadOnly<Created>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_ObjectAchievementQuery = GetEntityQuery(ComponentType.ReadOnly<ObjectAchievement>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_UnlockQuery = GetEntityQuery(ComponentType.ReadOnly<Unlock>());
		m_ParkQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Buildings.Park>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<Extension>(), ComponentType.Exclude<Game.Buildings.ServiceUpgrade>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_CreatedParkQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Buildings.Park>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.ReadOnly<Created>(), ComponentType.Exclude<Extension>(), ComponentType.Exclude<Game.Buildings.ServiceUpgrade>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_LockedServiceQuery = GetEntityQuery(ComponentType.ReadOnly<ServiceData>(), ComponentType.ReadOnly<Locked>());
		m_ServiceQuery = GetEntityQuery(ComponentType.ReadOnly<ServiceData>());
		m_BuildingQuery = GetEntityQuery(ComponentType.ReadOnly<BuildingData>());
		m_LockedBuildingQuery = GetEntityQuery(ComponentType.ReadOnly<BuildingData>(), ComponentType.ReadOnly<Locked>());
		m_TransportLineQuery = GetEntityQuery(ComponentType.ReadOnly<TransportLine>(), ComponentType.ReadOnly<Route>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_CreatedTransportLineQuery = GetEntityQuery(ComponentType.ReadOnly<TransportLine>(), ComponentType.ReadOnly<Created>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_UniqueServiceBuildingPrefabQuery = GetEntityQuery(ComponentType.ReadOnly<UniqueObjectData>(), ComponentType.ReadOnly<CollectedServiceBuildingBudgetData>(), ComponentType.ReadOnly<PrefabData>());
		m_UniqueServiceBuildingQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Objects.UniqueObject>(), ComponentType.ReadOnly<CityServiceUpkeep>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_CreatedUniqueServiceBuildingQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Objects.UniqueObject>(), ComponentType.ReadOnly<CityServiceUpkeep>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.ReadOnly<Created>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_PolicyModificationQuery = GetEntityQuery(ComponentType.ReadOnly<Modify>());
		m_DistrictQuery = GetEntityQuery(ComponentType.ReadOnly<District>(), ComponentType.ReadOnly<Policy>());
		m_ServiceDistrictBuildingQuery = GetEntityQuery(ComponentType.ReadOnly<Building>(), ComponentType.ReadOnly<ServiceDistrict>(), ComponentType.Exclude<Deleted>());
		m_FossilEnergyProducersQuery = GetEntityQuery(ComponentType.ReadOnly<ElectricityProducer>(), ComponentType.Exclude<RenewableElectricityProduction>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_RenewableEnergyProducersQuery = GetEntityQuery(ComponentType.ReadOnly<ElectricityProducer>(), ComponentType.ReadOnly<RenewableElectricityProduction>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_EnergyProducersQuery = GetEntityQuery(ComponentType.ReadOnly<ElectricityProducer>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_WaterPumpingStationQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Buildings.WaterPumpingStation>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_ResidentialBuildingsQuery = GetEntityQuery(ComponentType.ReadOnly<Building>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.ReadOnly<ResidentialProperty>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_CommercialBuildingsQuery = GetEntityQuery(ComponentType.ReadOnly<Building>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.ReadOnly<CommercialProperty>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_IndustrialBuildingsQuery = GetEntityQuery(ComponentType.ReadOnly<Building>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.ReadOnly<IndustrialProperty>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_FollowedCitizensQuery = GetEntityQuery(ComponentType.ReadOnly<Followed>(), ComponentType.ReadOnly<Citizen>());
		m_InfoviewQuery = GetEntityQuery(ComponentType.ReadOnly<InfoviewData>());
		m_UniqueBuildingQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Objects.UniqueObject>(), ComponentType.ReadOnly<Building>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_CreatedUniqueBuildingQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Objects.UniqueObject>(), ComponentType.ReadOnly<Building>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.ReadOnly<Created>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_PlantQuery = GetEntityQuery(ComponentType.ReadOnly<Plant>(), ComponentType.Exclude<Owner>(), ComponentType.Exclude<Native>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_CreatedPlantQuery = GetEntityQuery(ComponentType.ReadOnly<Plant>(), ComponentType.ReadOnly<Created>(), ComponentType.Exclude<Owner>(), ComponentType.Exclude<Native>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_ProduceResourceCompaniesQuery = GetEntityQuery(ComponentType.ReadOnly<PropertyRenter>(), ComponentType.ReadOnly<Game.Companies.ProcessingCompany>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_CreatedAggregateElementQuery = GetEntityQuery(ComponentType.ReadOnly<AggregateElement>(), ComponentType.ReadOnly<Created>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_AggregateElementQuery = GetEntityQuery(ComponentType.ReadOnly<AggregateElement>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_TimeDataQuery = GetEntityQuery(ComponentType.ReadOnly<TimeData>());
		m_TimeSettingsQuery = GetEntityQuery(ComponentType.ReadOnly<TimeSettingsData>());
		ToolSystem toolSystem = m_ToolSystem;
		toolSystem.EventInfoviewChanged = (Action<InfoviewPrefab>)Delegate.Combine(toolSystem.EventInfoviewChanged, new Action<InfoviewPrefab>(OnInfoviewChanged));
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
		base.OnDestroy();
		m_PatientsTreatedCounter.Dispose();
		m_ProducedFishCounter.Dispose();
		m_OffshoreOilProduceCounter.Dispose();
		m_SquasherDownerBuffer.Dispose();
		m_ShipItBuffer.Dispose();
		m_TransportedResourceQueue.Dispose();
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		Reset();
		PlatformManager.instance.achievementsEnabled &= m_CityConfigurationSystem.usedMods.Count == 0 && !m_CityConfigurationSystem.unlimitedMoney && !m_CityConfigurationSystem.unlockAll && !m_CityConfigurationSystem.unlockMapTiles;
	}
```

- `private OnInfoviewChanged(Game.Prefabs.InfoviewPrefab infoview) : System.Void`  

```csharp
private void OnInfoviewChanged(InfoviewPrefab infoview)
	{
		m_ViewedInfoviews.Add(infoview);
		if (m_ViewedInfoviews.Count == m_InfoviewQuery.CalculateEntityCount())
		{
			PlatformManager.instance.UnlockAchievement(Achievements.TheInspector);
		}
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (!m_ToolSystem.actionMode.IsEditor() && PlatformManager.instance.achievementsEnabled && GameManager.instance.state != GameManager.State.Loading && GameManager.instance.gameMode.IsGameOrEditor())
		{
			CheckInGameAchievements();
		}
	}
```

- `private Reset() : System.Void`  

```csharp
private void Reset()
	{
		m_CachedHappiness = 50;
		m_CachedAttractiveness = 0;
		m_CheckUnlocks = true;
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
		Reset();
		m_LittleBitOfTLCBuffer.m_Progress = 0;
		m_HowMuchIsTheFishBuffer.m_Progress = 0;
		m_ADifferentPlatformerBuffer.m_Progress = 0;
	}
```

- `private ShouldCheckOffshoreOilProduce() : System.Boolean`  

```csharp
private bool ShouldCheckOffshoreOilProduce()
	{
		if (m_ProduceResourceCompaniesQuery.IsEmptyIgnoreFilter)
		{
			return false;
		}
		if (PlatformManager.instance.GetAchievement(Achievements.ADifferentPlatformer, out var achievement) && !achievement.achieved)
		{
			return true;
		}
		return false;
	}
```

- `private ShouldCheckProducedFish() : System.Boolean`  

```csharp
private bool ShouldCheckProducedFish()
	{
		if (m_ProduceResourceCompaniesQuery.IsEmptyIgnoreFilter)
		{
			return false;
		}
		if (PlatformManager.instance.GetAchievement(Achievements.HowMuchIsTheFish, out var achievement) && !achievement.achieved)
		{
			return true;
		}
		return false;
	}
```


## Nested types

- `Game.Achievements.AchievementTriggerSystem+ProgressBuffer`  
- `Game.Achievements.AchievementTriggerSystem+UserDataProgressBuffer`  
- `Game.Achievements.AchievementTriggerSystem+ProcessDependencyDataJob`  
- `Game.Achievements.AchievementTriggerSystem+TypeHandle`  

