# Game.Achievements.AchievementTriggerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Achievements`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  
- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Simulation.ClimateSystem m_ClimateSystem`  
- `private Game.Simulation.TimeSystem m_TimeSystem`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Unity.Entities.EntityQuery m_CreatedObjectQuery`  
- `private Unity.Entities.EntityQuery m_ObjectAchievementQuery`  
- `private Unity.Entities.EntityQuery m_UnlockQuery`  
- `private Unity.Entities.EntityQuery m_ParkQuery`  
- `private Unity.Entities.EntityQuery m_CreatedParkQuery`  
- `private Unity.Entities.EntityQuery m_LockedServiceQuery`  
- `private Unity.Entities.EntityQuery m_ServiceQuery`  
- `private Unity.Entities.EntityQuery m_LockedBuildingQuery`  
- `private Unity.Entities.EntityQuery m_BuildingQuery`  
- `private Unity.Entities.EntityQuery m_TransportLineQuery`  
- `private Unity.Entities.EntityQuery m_CreatedTransportLineQuery`  
- `private Unity.Entities.EntityQuery m_UniqueServiceBuildingPrefabQuery`  
- `private Unity.Entities.EntityQuery m_UniqueServiceBuildingQuery`  
- `private Unity.Entities.EntityQuery m_CreatedUniqueServiceBuildingQuery`  
- `private Unity.Entities.EntityQuery m_PolicyModificationQuery`  
- `private Unity.Entities.EntityQuery m_DistrictQuery`  
- `private Unity.Entities.EntityQuery m_ServiceDistrictBuildingQuery`  
- `private Unity.Entities.EntityQuery m_FossilEnergyProducersQuery`  
- `private Unity.Entities.EntityQuery m_RenewableEnergyProducersQuery`  
- `private Unity.Entities.EntityQuery m_EnergyProducersQuery`  
- `private Unity.Entities.EntityQuery m_WaterPumpingStationQuery`  
- `private Unity.Entities.EntityQuery m_ResidentialBuildingsQuery`  
- `private Unity.Entities.EntityQuery m_CommercialBuildingsQuery`  
- `private Unity.Entities.EntityQuery m_IndustrialBuildingsQuery`  
- `private Unity.Entities.EntityQuery m_FollowedCitizensQuery`  
- `private Unity.Entities.EntityQuery m_InfoviewQuery`  
- `private Unity.Entities.EntityQuery m_CreatedUniqueBuildingQuery`  
- `private Unity.Entities.EntityQuery m_UniqueBuildingQuery`  
- `private Unity.Entities.EntityQuery m_PlantQuery`  
- `private Unity.Entities.EntityQuery m_CreatedPlantQuery`  
- `private Unity.Entities.EntityQuery m_TimeDataQuery`  
- `private Unity.Entities.EntityQuery m_TimeSettingsQuery`  
- `private Unity.Entities.EntityQuery m_ProduceResourceCompaniesQuery`  
- `private Unity.Entities.EntityQuery m_CreatedAggregateElementQuery`  
- `private Unity.Entities.EntityQuery m_AggregateElementQuery`  
- `public Colossal.NativeCounter m_PatientsTreatedCounter`  
- `public Colossal.NativeCounter m_ProducedFishCounter`  
- `public Colossal.NativeCounter m_OffshoreOilProduceCounter`  
- `private Unity.Jobs.JobHandle m_TransportWriteDeps`  
- `private Unity.Collections.NativeQueue<Game.Achievements.TransportedResource> m_TransportedResourceQueue`  
- `private System.Int32 m_CachedPatientsTreatedCount`  
- `private System.Int32 m_CachedPopulationCount`  
- `private System.Int32 m_CachedHappiness`  
- `private System.Int32 m_CachedAttractiveness`  
- `private System.Int32 m_CachedTouristCount`  
- `private System.Boolean m_CheckUnlocks`  
- `private System.UInt32 m_LastCheckFrameIndex`  
- `private System.Collections.Generic.HashSet<Game.Prefabs.InfoviewPrefab> m_ViewedInfoviews`  
- `private System.Collections.Generic.Dictionary<Colossal.PSI.Common.AchievementId, System.Int32> m_IncrementalObjectAchievementProgress`  
- `private System.Collections.Generic.List<Colossal.PSI.Common.AchievementId> m_AbsoluteObjectAchievements`  
- `public Game.Achievements.AchievementTriggerSystem+ProgressBuffer m_LittleBitOfTLCBuffer`  
- `public Game.Achievements.AchievementTriggerSystem+ProgressBuffer m_HowMuchIsTheFishBuffer`  
- `public Game.Achievements.AchievementTriggerSystem+ProgressBuffer m_ADifferentPlatformerBuffer`  
- `public Game.Achievements.AchievementTriggerSystem+UserDataProgressBuffer m_SquasherDownerBuffer`  
- `public Game.Achievements.AchievementTriggerSystem+UserDataProgressBuffer m_ShipItBuffer`  
- `private Game.Achievements.AchievementTriggerSystem+TypeHandle __TypeHandle`  
- `private static Colossal.Logging.ILog sLog`  
- `private static readonly System.Int32 kMinCityEffectPopulation`  
- `private static readonly System.Int32 kAllSmilesHappiness`  
- `private static readonly System.Int32 kThisIsNotMyHappyPlaceHappiness`  
- `private static readonly System.Int32 kSimplyIrresistibleAttractiveness`  
- `private static readonly System.Int32 kZeroEmissionMinProduction`  
- `private static readonly System.Int32 kColossalGardenerLimit`  
- `private static readonly System.Int32 kTheDeepEndLoanAmount`  

## Constructors

- `public AchievementTriggerSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public AddWriter(Unity.Jobs.JobHandle writer) : System.Void`  
- `private CalculateEnergyProduction(Unity.Entities.EntityQuery entityQuery) : System.Int32`  
- `private CheckFilter(Unity.Entities.DynamicBuffer<Game.Prefabs.AchievementFilterData> datas, Colossal.PSI.Common.AchievementId achievementID, System.Boolean defaultResult = False) : System.Boolean`  
- `private CheckFourSeasons() : System.Boolean`  
- `private CheckInGameAchievements() : System.Void`  
- `private CheckOneOfEverything() : System.Boolean`  
- `private CheckPolicyAchievements() : System.Void`  
- `private CheckTransportedResources() : System.Void`  
- `private CheckUnlockingAchievements() : System.Void`  
- `private CountAbsoluteObjectAchievementProgress(Colossal.PSI.Common.AchievementId achID) : System.Int32`  
- `private CountLiftBridge() : System.Int32`  
- `private CountParks() : System.Int32`  
- `private CountSignatureBuildings() : System.Int32`  
- `private CountUniqueServiceBuildingPrefabs() : System.Int32`  
- `private CountUniqueServiceBuildings() : System.Int32`  
- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public GetDebugData(Colossal.PSI.Common.AchievementId achievement, System.String& data) : System.Boolean`  
- `public GetTransportedResourceQueue() : Unity.Collections.NativeQueue<Game.Achievements.TransportedResource>`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `private OnInfoviewChanged(Game.Prefabs.InfoviewPrefab infoview) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private Reset() : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  
- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  
- `private ShouldCheckOffshoreOilProduce() : System.Boolean`  
- `private ShouldCheckProducedFish() : System.Boolean`  

## Nested types

- `Game.Achievements.AchievementTriggerSystem+ProgressBuffer`  
- `Game.Achievements.AchievementTriggerSystem+UserDataProgressBuffer`  
- `Game.Achievements.AchievementTriggerSystem+ProcessDependencyDataJob`  
- `Game.Achievements.AchievementTriggerSystem+TypeHandle`  

