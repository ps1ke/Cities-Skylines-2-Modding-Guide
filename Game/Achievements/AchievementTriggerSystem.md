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
public AchievementTriggerSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public AddWriter(Unity.Jobs.JobHandle writer) : System.Void`  

```csharp
public System.Void AddWriter(Unity.Jobs.JobHandle writer);
```

- `private CalculateEnergyProduction(Unity.Entities.EntityQuery entityQuery) : System.Int32`  

```csharp
private System.Int32 CalculateEnergyProduction(Unity.Entities.EntityQuery entityQuery);
```

- `private CheckFilter(Unity.Entities.DynamicBuffer<Game.Prefabs.AchievementFilterData> datas, Colossal.PSI.Common.AchievementId achievementID, System.Boolean defaultResult = False) : System.Boolean`  

```csharp
private System.Boolean CheckFilter(Unity.Entities.DynamicBuffer<Game.Prefabs.AchievementFilterData> datas, Colossal.PSI.Common.AchievementId achievementID, System.Boolean defaultResult);
```

- `private CheckFourSeasons() : System.Boolean`  

```csharp
private System.Boolean CheckFourSeasons();
```

- `private CheckInGameAchievements() : System.Void`  

```csharp
private System.Void CheckInGameAchievements();
```

- `private CheckOneOfEverything() : System.Boolean`  

```csharp
private System.Boolean CheckOneOfEverything();
```

- `private CheckPolicyAchievements() : System.Void`  

```csharp
private System.Void CheckPolicyAchievements();
```

- `private CheckTransportedResources() : System.Void`  

```csharp
private System.Void CheckTransportedResources();
```

- `private CheckUnlockingAchievements() : System.Void`  

```csharp
private System.Void CheckUnlockingAchievements();
```

- `private CountAbsoluteObjectAchievementProgress(Colossal.PSI.Common.AchievementId achID) : System.Int32`  

```csharp
private System.Int32 CountAbsoluteObjectAchievementProgress(Colossal.PSI.Common.AchievementId achID);
```

- `private CountLiftBridge() : System.Int32`  

```csharp
private System.Int32 CountLiftBridge();
```

- `private CountParks() : System.Int32`  

```csharp
private System.Int32 CountParks();
```

- `private CountSignatureBuildings() : System.Int32`  

```csharp
private System.Int32 CountSignatureBuildings();
```

- `private CountUniqueServiceBuildingPrefabs() : System.Int32`  

```csharp
private System.Int32 CountUniqueServiceBuildingPrefabs();
```

- `private CountUniqueServiceBuildings() : System.Int32`  

```csharp
private System.Int32 CountUniqueServiceBuildings();
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public GetDebugData(Colossal.PSI.Common.AchievementId achievement, System.String& data) : System.Boolean`  

```csharp
public System.Boolean GetDebugData(Colossal.PSI.Common.AchievementId achievement, System.String& data);
```

- `public GetTransportedResourceQueue() : Unity.Collections.NativeQueue<Game.Achievements.TransportedResource>`  

```csharp
public Unity.Collections.NativeQueue<Game.Achievements.TransportedResource> GetTransportedResourceQueue();
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

- `private OnInfoviewChanged(Game.Prefabs.InfoviewPrefab infoview) : System.Void`  

```csharp
private System.Void OnInfoviewChanged(Game.Prefabs.InfoviewPrefab infoview);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private Reset() : System.Void`  

```csharp
private System.Void Reset();
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
```

- `private ShouldCheckOffshoreOilProduce() : System.Boolean`  

```csharp
private System.Boolean ShouldCheckOffshoreOilProduce();
```

- `private ShouldCheckProducedFish() : System.Boolean`  

```csharp
private System.Boolean ShouldCheckProducedFish();
```


## Nested types

- `Game.Achievements.AchievementTriggerSystem+ProgressBuffer`  
- `Game.Achievements.AchievementTriggerSystem+UserDataProgressBuffer`  
- `Game.Achievements.AchievementTriggerSystem+ProcessDependencyDataJob`  
- `Game.Achievements.AchievementTriggerSystem+TypeHandle`  

