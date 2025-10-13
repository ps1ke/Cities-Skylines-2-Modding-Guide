# Game.UI.InGame.DeveloperInfoUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class DeveloperInfoUISystem : Game.UI.UISystemBase
{
    protected Game.Simulation.CitySystem m_CitySystem;
    protected Game.UI.NameSystem m_NameSystem;
    protected Game.Prefabs.PrefabSystem m_PrefabSystem;
    protected Game.Prefabs.ResourceSystem m_ResourceSystem;
    protected Game.Simulation.SimulationSystem m_SimulationSystem;
    protected Game.UI.InGame.SelectedInfoUISystem m_InfoUISystem;
    protected Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
    protected Game.Simulation.AirPollutionSystem m_AirPollutionSystem;
    protected Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem;
    protected Game.Simulation.TelecomCoverageSystem m_TelecomCoverageSystem;
    protected Game.Simulation.TaxSystem m_TaxSystem;
    protected Game.Rendering.BatchManagerSystem m_BatchManagerSystem;
    protected Unity.Entities.EntityQuery m_CitizenHappinessParameterQuery;
    protected Unity.Entities.EntityQuery m_HealthcareParameterQuery;
    protected Unity.Entities.EntityQuery m_ParkParameterQuery;
    protected Unity.Entities.EntityQuery m_EducationParameterQuery;
    protected Unity.Entities.EntityQuery m_TelecomParameterQuery;
    protected Unity.Entities.EntityQuery m_HappinessFactorParameterQuery;
    protected Unity.Entities.EntityQuery m_EconomyParameterQuery;
    protected Unity.Entities.EntityQuery m_ProcessQuery;
    protected Unity.Entities.EntityQuery m_TimeDataQuery;
    protected Unity.Entities.EntityQuery m_GarbageParameterQuery;
    private Game.UI.InGame.DeveloperInfoUISystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_746694604_0;
    private Unity.Entities.EntityQuery __query_746694604_1;
    private Unity.Entities.EntityQuery __query_746694604_2;
    private Unity.Entities.EntityQuery __query_746694604_3;
    private Unity.Entities.EntityQuery __query_746694604_4;
    private Unity.Entities.EntityQuery __query_746694604_5;
    private Unity.Entities.EntityQuery __query_746694604_6;

    public DeveloperInfoUISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void AddResources(Unity.Entities.DynamicBuffer<Game.Economy.Resources> source, Unity.Collections.NativeList<Game.Economy.Resources> target);
    protected System.Void AddUpgradeData<T>(Unity.Entities.Entity entity, T& data);
    private System.Void CheckParkingLanes(Unity.Entities.DynamicBuffer<Game.Objects.SubObject> subObjects, System.Int32& slotCapacity, System.Int32& parkedCars, System.Int32& parkingFee, System.Int32& laneCount, Unity.Collections.NativeList`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parkedCarList);
    private System.Void CheckParkingLanes(Unity.Entities.DynamicBuffer<Game.Net.SubNet> subNets, System.Int32& slotCapacity, System.Int32& parkedCars, System.Int32& parkingFee, System.Int32& laneCount, Unity.Collections.NativeList`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parkedCarList);
    private System.Void CheckParkingLanes(Unity.Entities.DynamicBuffer<Game.Net.SubLane> subLanes, System.Int32& slotCapacity, System.Int32& parkedCars, System.Int32& parkingFee, System.Int32& laneCount, Unity.Collections.NativeList`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parkedCarList);
    private static System.String ConsumptionToString(System.Int32 dailyConsumption, System.Int32 citizens, Game.Prefabs.CitizenHappinessParameterData happinessParameters);
    private System.String GetAgeString(Unity.Entities.Entity entity);
    private System.String GetEducationString(System.Int32 education);
    private System.String GetGarbageStatus(System.Int32 accumulation, System.Int32 garbage, System.Int32 homeless, System.Int32 homelessProduce);
    private static System.String GetLevelupTime(System.Int32 condition, System.Int32 levelup, System.Int32 changePerDay);
    private Unity.Entities.Entity GetPassengerWaiting(Unity.Entities.Entity vehicleEntity);
    private Unity.Entities.Entity GetPassengerWaiting2(Unity.Entities.Entity vehicleEntity);
    private System.String GetPurposeText(Game.Citizens.TravelPurpose purpose, System.Boolean tourist, Game.Citizens.Criminal criminal, Unity.Entities.Entity& entity);
    private System.Boolean GetRoutePosition(Unity.Entities.Entity transportVehicle, System.Int32& nextWaypointIndex, System.Single& segmentPosition);
    private System.String GetTimeString(System.Single time);
    private System.Boolean HasAccidentSiteInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasAddressInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasAmbulanceInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasAnimalInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasAreaInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasBatchInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasBatteriesInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasBoardingVehicleInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasCargoTransportInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasCitizenInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasCompany(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Unity.Entities.Entity& company);
    private System.Boolean HasCompanyEconomyInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasCompanyInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasCompanyProfitInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasContentPrerequisite(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasControllerInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasCreatureInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasCrimeInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasDamagedInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasDeathcareInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasDeliveryTruckInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasDestroyedBuildingInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasDestroyedInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasEfficiencyInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasElectricityConsumeInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasElectricityProductionInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasEmployeesInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasEntityInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasEventInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasExtractorCompanyInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasFacingWeatherInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasFireEngineInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasFloodedInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasGarbageInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasGarbageProcessingInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasGarbageTruckInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasGroupLeaderInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasGroupMemberInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasHearseInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasHomelessInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasHouseholdInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasHouseholdPetsInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasHouseholdsInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasInDangerInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasInvolvedInAccidentInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasKeeperInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasLandValueInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasMailBoxInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasMailInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasMailProcessingSpeedInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasMailSenderInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasMaintenanceVehicleInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasMeshGroupInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasMeshPrefabInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasMovingInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasNetworkCapacityInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasNotificationInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasOnFireInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasOwnerInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasParkInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasParkingInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasPassengerInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasPatientsInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasPersonalCarInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasPoliceCarInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasPoliceInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasPollutionInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasPostVanInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasPrisonInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasProcessingCompanyInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasPublicTransportInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasRentInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasResidentsInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasResourceProductionInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasSendReceiveMailInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasServiceCompanyInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasShelterInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasSpectatorSiteInfo(Unity.Entities.Entity entity, Unity.Entities.Entity _);
    private System.Boolean HasStorageInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasStoredGarbageInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasStoredMailInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasStoredResourcesInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasStudentsInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasTelecomRangeInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasTradeCostInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasTradePartnerInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasTransferRequestInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasTreeInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasVehicleInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasVehicleModelInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasWaitingPassengerInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasWarehouseInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasWaterConsumeInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasZoneHappinessInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasZoneInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private System.Boolean HasZoneLevelInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private static System.String HealthToString(System.Int32 wellbeing);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    private System.String ServicesToString(System.Int32 services, System.Int32 maxServices);
    private System.Void UpdateAccidentSiteInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
    private System.Void UpdateAddressInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
    private System.Void UpdateAmbulanceInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
    private System.Void UpdateAnimalInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
    private System.Void UpdateAreaInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
    private System.Void UpdateBatchInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
    private System.Void UpdateBatteriesInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
    private System.Void UpdateBoardingVehicleInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
    private System.Void UpdateCargoTransportInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
    private System.Void UpdateCitizenInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
    private System.Void UpdateCompanyEconomyInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
    private System.Void UpdateCompanyInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
    private System.Void UpdateCompanyProfitInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
    private System.Void UpdateContentPrerequisite(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
    private System.Void UpdateControllerInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
    private System.Void UpdateCreatureInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
    private System.Void UpdateCrimeInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
    private System.Void UpdateDamagedInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
    private System.Void UpdateDeathcareInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.CapacityInfo info);
    private System.Void UpdateDeliveryTruckInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
    private System.Void UpdateDestroyedBuildingInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.CapacityInfo info);
    private System.Void UpdateDestroyedInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
    private System.Void UpdateEfficiencyInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
    private System.Void UpdateElectricityConsumeInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
    private System.Void UpdateElectricityProductionInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
    private System.Void UpdateEmployeesInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
    private System.Void UpdateEntityInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
    private System.Void UpdateEventInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
    private System.Void UpdateExtractorCompanyInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
    private System.Void UpdateFacingWeatherInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
    private System.Void UpdateFireEngineInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
    private System.Void UpdateFloodedInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
    private System.Void UpdateGarbageInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
    private System.Void UpdateGarbageProcessingInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
    private System.Void UpdateGarbageTruckInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
    private System.Void UpdateGroupLeaderInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
    private System.Void UpdateGroupMemberInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
    private System.Void UpdateHearseInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
    private System.Void UpdateHomelessInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
    private System.Void UpdateHouseholdInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
    private System.Void UpdateHouseholdPetsInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
    private System.Void UpdateHouseholdsInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
    private System.Void UpdateInDangerInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
    private System.Void UpdateInvolvedInAccidentInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
    private System.Void UpdateKeeperInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
    private System.Void UpdateLandValueInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
    private System.Void UpdateMailBoxInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.CapacityInfo info);
    private System.Void UpdateMailInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
    private System.Void UpdateMailProcessingSpeedInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
    private System.Void UpdateMailSenderInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.CapacityInfo info);
    private System.Void UpdateMaintenanceVehicleInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
    private System.Void UpdateMeshGroupInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
    private System.Void UpdateMeshPrefabInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
    private System.Void UpdateMovingInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.CapacityInfo info);
    private System.Void UpdateNetworkCapacityInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.CapacityInfo info);
    private System.Void UpdateNotificationInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
    private System.Void UpdateOnFireInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
    private System.Void UpdateOwnerInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
    private System.Void UpdateParkInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
    private System.Void UpdateParkingInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
    private System.Void UpdatePassengerInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.CapacityInfo info);
    private System.Void UpdatePatientsInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
    private System.Void UpdatePersonalCarInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
    private System.Void UpdatePoliceCarInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
    private System.Void UpdatePoliceInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.CapacityInfo info);
    private System.Void UpdatePollutionInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
    private System.Void UpdatePostVanInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
    private System.Void UpdatePrisonInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
    private System.Void UpdateProcessingCompanyInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
    private System.Void UpdatePublicTransportInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
    private System.Void UpdateRentInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
    private System.Void UpdateResidentInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
    private System.Void UpdateResourceProductionInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
    private System.Void UpdateSendReceiveMailInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
    private System.Void UpdateServiceCompanyInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
    private System.Void UpdateShelterInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.CapacityInfo info);
    private System.Void UpdateSpectatorSiteInfo(Unity.Entities.Entity entity, Unity.Entities.Entity _, Game.UI.InGame.GenericInfo info);
    private System.Void UpdateStorageInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
    private System.Void UpdateStoredGarbageInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.CapacityInfo info);
    private System.Void UpdateStoredMailInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.CapacityInfo info);
    private System.Void UpdateStoredResourcesInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
    private System.Void UpdateStudentsInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
    private System.Void UpdateTelecomRangeInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
    private System.Void UpdateTradeCostInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList infos);
    private System.Void UpdateTradePartnerInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
    private System.Void UpdateTransferRequestInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
    private System.Void UpdateTreeInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.CapacityInfo info);
    private System.Void UpdateVehicleInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
    private System.Void UpdateVehicleModelInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
    private System.Void UpdateWaitingPassengerInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
    private System.Void UpdateWarehouseInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
    private System.Void UpdateWaterConsumeInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
    private System.Void UpdateZoneHappinessInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
    private System.Void UpdateZoneInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
    private System.Void UpdateZoneLevelInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.CapacityInfo info);
    private static System.String WellbeingToString(System.Int32 wellbeing);
    private System.String WorthToString(System.Int32 worth);
}
```


## Fields

- `protected Game.Simulation.CitySystem m_CitySystem`  

```csharp
protected Game.Simulation.CitySystem m_CitySystem;
```

- `protected Game.UI.NameSystem m_NameSystem`  

```csharp
protected Game.UI.NameSystem m_NameSystem;
```

- `protected Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
protected Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `protected Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
protected Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `protected Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
protected Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `protected Game.UI.InGame.SelectedInfoUISystem m_InfoUISystem`  

```csharp
protected Game.UI.InGame.SelectedInfoUISystem m_InfoUISystem;
```

- `protected Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem`  

```csharp
protected Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
```

- `protected Game.Simulation.AirPollutionSystem m_AirPollutionSystem`  

```csharp
protected Game.Simulation.AirPollutionSystem m_AirPollutionSystem;
```

- `protected Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem`  

```csharp
protected Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem;
```

- `protected Game.Simulation.TelecomCoverageSystem m_TelecomCoverageSystem`  

```csharp
protected Game.Simulation.TelecomCoverageSystem m_TelecomCoverageSystem;
```

- `protected Game.Simulation.TaxSystem m_TaxSystem`  

```csharp
protected Game.Simulation.TaxSystem m_TaxSystem;
```

- `protected Game.Rendering.BatchManagerSystem m_BatchManagerSystem`  

```csharp
protected Game.Rendering.BatchManagerSystem m_BatchManagerSystem;
```

- `protected Unity.Entities.EntityQuery m_CitizenHappinessParameterQuery`  

```csharp
protected Unity.Entities.EntityQuery m_CitizenHappinessParameterQuery;
```

- `protected Unity.Entities.EntityQuery m_HealthcareParameterQuery`  

```csharp
protected Unity.Entities.EntityQuery m_HealthcareParameterQuery;
```

- `protected Unity.Entities.EntityQuery m_ParkParameterQuery`  

```csharp
protected Unity.Entities.EntityQuery m_ParkParameterQuery;
```

- `protected Unity.Entities.EntityQuery m_EducationParameterQuery`  

```csharp
protected Unity.Entities.EntityQuery m_EducationParameterQuery;
```

- `protected Unity.Entities.EntityQuery m_TelecomParameterQuery`  

```csharp
protected Unity.Entities.EntityQuery m_TelecomParameterQuery;
```

- `protected Unity.Entities.EntityQuery m_HappinessFactorParameterQuery`  

```csharp
protected Unity.Entities.EntityQuery m_HappinessFactorParameterQuery;
```

- `protected Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
protected Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `protected Unity.Entities.EntityQuery m_ProcessQuery`  

```csharp
protected Unity.Entities.EntityQuery m_ProcessQuery;
```

- `protected Unity.Entities.EntityQuery m_TimeDataQuery`  

```csharp
protected Unity.Entities.EntityQuery m_TimeDataQuery;
```

- `protected Unity.Entities.EntityQuery m_GarbageParameterQuery`  

```csharp
protected Unity.Entities.EntityQuery m_GarbageParameterQuery;
```

- `private Game.UI.InGame.DeveloperInfoUISystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.DeveloperInfoUISystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_746694604_0`  

```csharp
private Unity.Entities.EntityQuery __query_746694604_0;
```

- `private Unity.Entities.EntityQuery __query_746694604_1`  

```csharp
private Unity.Entities.EntityQuery __query_746694604_1;
```

- `private Unity.Entities.EntityQuery __query_746694604_2`  

```csharp
private Unity.Entities.EntityQuery __query_746694604_2;
```

- `private Unity.Entities.EntityQuery __query_746694604_3`  

```csharp
private Unity.Entities.EntityQuery __query_746694604_3;
```

- `private Unity.Entities.EntityQuery __query_746694604_4`  

```csharp
private Unity.Entities.EntityQuery __query_746694604_4;
```

- `private Unity.Entities.EntityQuery __query_746694604_5`  

```csharp
private Unity.Entities.EntityQuery __query_746694604_5;
```

- `private Unity.Entities.EntityQuery __query_746694604_6`  

```csharp
private Unity.Entities.EntityQuery __query_746694604_6;
```


## Constructors

- `public DeveloperInfoUISystem()`  

```csharp
public DeveloperInfoUISystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private AddResources(Unity.Entities.DynamicBuffer<Game.Economy.Resources> source, Unity.Collections.NativeList<Game.Economy.Resources> target) : System.Void`  

```csharp
private System.Void AddResources(Unity.Entities.DynamicBuffer<Game.Economy.Resources> source, Unity.Collections.NativeList<Game.Economy.Resources> target);
```

- `protected AddUpgradeData<T>(Unity.Entities.Entity entity, T& data) : System.Void`  

```csharp
protected System.Void AddUpgradeData<T>(Unity.Entities.Entity entity, T& data);
```

- `private CheckParkingLanes(Unity.Entities.DynamicBuffer<Game.Objects.SubObject> subObjects, System.Int32& slotCapacity, System.Int32& parkedCars, System.Int32& parkingFee, System.Int32& laneCount, Unity.Collections.NativeList`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parkedCarList) : System.Void`  

```csharp
private System.Void CheckParkingLanes(Unity.Entities.DynamicBuffer<Game.Objects.SubObject> subObjects, System.Int32& slotCapacity, System.Int32& parkedCars, System.Int32& parkingFee, System.Int32& laneCount, Unity.Collections.NativeList`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parkedCarList);
```

- `private CheckParkingLanes(Unity.Entities.DynamicBuffer<Game.Net.SubNet> subNets, System.Int32& slotCapacity, System.Int32& parkedCars, System.Int32& parkingFee, System.Int32& laneCount, Unity.Collections.NativeList`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parkedCarList) : System.Void`  

```csharp
private System.Void CheckParkingLanes(Unity.Entities.DynamicBuffer<Game.Net.SubNet> subNets, System.Int32& slotCapacity, System.Int32& parkedCars, System.Int32& parkingFee, System.Int32& laneCount, Unity.Collections.NativeList`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parkedCarList);
```

- `private CheckParkingLanes(Unity.Entities.DynamicBuffer<Game.Net.SubLane> subLanes, System.Int32& slotCapacity, System.Int32& parkedCars, System.Int32& parkingFee, System.Int32& laneCount, Unity.Collections.NativeList`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parkedCarList) : System.Void`  

```csharp
private System.Void CheckParkingLanes(Unity.Entities.DynamicBuffer<Game.Net.SubLane> subLanes, System.Int32& slotCapacity, System.Int32& parkedCars, System.Int32& parkingFee, System.Int32& laneCount, Unity.Collections.NativeList`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parkedCarList);
```

- `private static ConsumptionToString(System.Int32 dailyConsumption, System.Int32 citizens, Game.Prefabs.CitizenHappinessParameterData happinessParameters) : System.String`  

```csharp
private static System.String ConsumptionToString(System.Int32 dailyConsumption, System.Int32 citizens, Game.Prefabs.CitizenHappinessParameterData happinessParameters);
```

- `private GetAgeString(Unity.Entities.Entity entity) : System.String`  

```csharp
private System.String GetAgeString(Unity.Entities.Entity entity);
```

- `private GetEducationString(System.Int32 education) : System.String`  

```csharp
private System.String GetEducationString(System.Int32 education);
```

- `private GetGarbageStatus(System.Int32 accumulation, System.Int32 garbage, System.Int32 homeless, System.Int32 homelessProduce) : System.String`  

```csharp
private System.String GetGarbageStatus(System.Int32 accumulation, System.Int32 garbage, System.Int32 homeless, System.Int32 homelessProduce);
```

- `private static GetLevelupTime(System.Int32 condition, System.Int32 levelup, System.Int32 changePerDay) : System.String`  

```csharp
private static System.String GetLevelupTime(System.Int32 condition, System.Int32 levelup, System.Int32 changePerDay);
```

- `private GetPassengerWaiting(Unity.Entities.Entity vehicleEntity) : Unity.Entities.Entity`  

```csharp
private Unity.Entities.Entity GetPassengerWaiting(Unity.Entities.Entity vehicleEntity);
```

- `private GetPassengerWaiting2(Unity.Entities.Entity vehicleEntity) : Unity.Entities.Entity`  

```csharp
private Unity.Entities.Entity GetPassengerWaiting2(Unity.Entities.Entity vehicleEntity);
```

- `private GetPurposeText(Game.Citizens.TravelPurpose purpose, System.Boolean tourist, Game.Citizens.Criminal criminal, Unity.Entities.Entity& entity) : System.String`  

```csharp
private System.String GetPurposeText(Game.Citizens.TravelPurpose purpose, System.Boolean tourist, Game.Citizens.Criminal criminal, Unity.Entities.Entity& entity);
```

- `private GetRoutePosition(Unity.Entities.Entity transportVehicle, System.Int32& nextWaypointIndex, System.Single& segmentPosition) : System.Boolean`  

```csharp
private System.Boolean GetRoutePosition(Unity.Entities.Entity transportVehicle, System.Int32& nextWaypointIndex, System.Single& segmentPosition);
```

- `private GetTimeString(System.Single time) : System.String`  

```csharp
private System.String GetTimeString(System.Single time);
```

- `private HasAccidentSiteInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasAccidentSiteInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasAddressInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasAddressInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasAmbulanceInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasAmbulanceInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasAnimalInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasAnimalInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasAreaInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasAreaInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasBatchInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasBatchInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasBatteriesInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasBatteriesInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasBoardingVehicleInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasBoardingVehicleInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasCargoTransportInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasCargoTransportInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasCitizenInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasCitizenInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasCompany(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Unity.Entities.Entity& company) : System.Boolean`  

```csharp
private System.Boolean HasCompany(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Unity.Entities.Entity& company);
```

- `private HasCompanyEconomyInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasCompanyEconomyInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasCompanyInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasCompanyInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasCompanyProfitInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasCompanyProfitInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasContentPrerequisite(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasContentPrerequisite(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasControllerInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasControllerInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasCreatureInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasCreatureInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasCrimeInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasCrimeInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasDamagedInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasDamagedInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasDeathcareInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasDeathcareInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasDeliveryTruckInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasDeliveryTruckInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasDestroyedBuildingInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasDestroyedBuildingInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasDestroyedInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasDestroyedInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasEfficiencyInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasEfficiencyInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasElectricityConsumeInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasElectricityConsumeInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasElectricityProductionInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasElectricityProductionInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasEmployeesInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasEmployeesInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasEntityInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasEntityInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasEventInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasEventInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasExtractorCompanyInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasExtractorCompanyInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasFacingWeatherInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasFacingWeatherInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasFireEngineInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasFireEngineInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasFloodedInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasFloodedInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasGarbageInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasGarbageInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasGarbageProcessingInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasGarbageProcessingInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasGarbageTruckInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasGarbageTruckInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasGroupLeaderInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasGroupLeaderInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasGroupMemberInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasGroupMemberInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasHearseInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasHearseInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasHomelessInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasHomelessInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasHouseholdInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasHouseholdInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasHouseholdPetsInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasHouseholdPetsInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasHouseholdsInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasHouseholdsInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasInDangerInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasInDangerInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasInvolvedInAccidentInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasInvolvedInAccidentInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasKeeperInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasKeeperInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasLandValueInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasLandValueInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasMailBoxInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasMailBoxInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasMailInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasMailInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasMailProcessingSpeedInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasMailProcessingSpeedInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasMailSenderInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasMailSenderInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasMaintenanceVehicleInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasMaintenanceVehicleInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasMeshGroupInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasMeshGroupInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasMeshPrefabInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasMeshPrefabInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasMovingInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasMovingInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasNetworkCapacityInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasNetworkCapacityInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasNotificationInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasNotificationInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasOnFireInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasOnFireInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasOwnerInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasOwnerInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasParkInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasParkInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasParkingInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasParkingInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasPassengerInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasPassengerInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasPatientsInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasPatientsInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasPersonalCarInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasPersonalCarInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasPoliceCarInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasPoliceCarInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasPoliceInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasPoliceInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasPollutionInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasPollutionInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasPostVanInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasPostVanInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasPrisonInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasPrisonInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasProcessingCompanyInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasProcessingCompanyInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasPublicTransportInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasPublicTransportInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasRentInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasRentInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasResidentsInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasResidentsInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasResourceProductionInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasResourceProductionInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasSendReceiveMailInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasSendReceiveMailInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasServiceCompanyInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasServiceCompanyInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasShelterInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasShelterInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasSpectatorSiteInfo(Unity.Entities.Entity entity, Unity.Entities.Entity _) : System.Boolean`  

```csharp
private System.Boolean HasSpectatorSiteInfo(Unity.Entities.Entity entity, Unity.Entities.Entity _);
```

- `private HasStorageInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasStorageInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasStoredGarbageInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasStoredGarbageInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasStoredMailInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasStoredMailInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasStoredResourcesInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasStoredResourcesInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasStudentsInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasStudentsInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasTelecomRangeInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasTelecomRangeInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasTradeCostInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasTradeCostInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasTradePartnerInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasTradePartnerInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasTransferRequestInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasTransferRequestInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasTreeInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasTreeInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasVehicleInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasVehicleInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasVehicleModelInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasVehicleModelInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasWaitingPassengerInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasWaitingPassengerInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasWarehouseInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasWarehouseInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasWaterConsumeInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasWaterConsumeInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasZoneHappinessInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasZoneHappinessInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasZoneInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasZoneInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private HasZoneLevelInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
private System.Boolean HasZoneLevelInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private static HealthToString(System.Int32 wellbeing) : System.String`  

```csharp
private static System.String HealthToString(System.Int32 wellbeing);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private ServicesToString(System.Int32 services, System.Int32 maxServices) : System.String`  

```csharp
private System.String ServicesToString(System.Int32 services, System.Int32 maxServices);
```

- `private UpdateAccidentSiteInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info) : System.Void`  

```csharp
private System.Void UpdateAccidentSiteInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
```

- `private UpdateAddressInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info) : System.Void`  

```csharp
private System.Void UpdateAddressInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
```

- `private UpdateAmbulanceInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info) : System.Void`  

```csharp
private System.Void UpdateAmbulanceInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
```

- `private UpdateAnimalInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info) : System.Void`  

```csharp
private System.Void UpdateAnimalInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
```

- `private UpdateAreaInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info) : System.Void`  

```csharp
private System.Void UpdateAreaInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
```

- `private UpdateBatchInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info) : System.Void`  

```csharp
private System.Void UpdateBatchInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
```

- `private UpdateBatteriesInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info) : System.Void`  

```csharp
private System.Void UpdateBatteriesInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
```

- `private UpdateBoardingVehicleInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info) : System.Void`  

```csharp
private System.Void UpdateBoardingVehicleInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
```

- `private UpdateCargoTransportInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info) : System.Void`  

```csharp
private System.Void UpdateCargoTransportInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
```

- `private UpdateCitizenInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info) : System.Void`  

```csharp
private System.Void UpdateCitizenInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
```

- `private UpdateCompanyEconomyInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info) : System.Void`  

```csharp
private System.Void UpdateCompanyEconomyInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
```

- `private UpdateCompanyInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info) : System.Void`  

```csharp
private System.Void UpdateCompanyInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
```

- `private UpdateCompanyProfitInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info) : System.Void`  

```csharp
private System.Void UpdateCompanyProfitInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
```

- `private UpdateContentPrerequisite(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info) : System.Void`  

```csharp
private System.Void UpdateContentPrerequisite(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
```

- `private UpdateControllerInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info) : System.Void`  

```csharp
private System.Void UpdateControllerInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
```

- `private UpdateCreatureInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info) : System.Void`  

```csharp
private System.Void UpdateCreatureInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
```

- `private UpdateCrimeInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info) : System.Void`  

```csharp
private System.Void UpdateCrimeInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
```

- `private UpdateDamagedInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info) : System.Void`  

```csharp
private System.Void UpdateDamagedInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
```

- `private UpdateDeathcareInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.CapacityInfo info) : System.Void`  

```csharp
private System.Void UpdateDeathcareInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.CapacityInfo info);
```

- `private UpdateDeliveryTruckInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info) : System.Void`  

```csharp
private System.Void UpdateDeliveryTruckInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
```

- `private UpdateDestroyedBuildingInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.CapacityInfo info) : System.Void`  

```csharp
private System.Void UpdateDestroyedBuildingInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.CapacityInfo info);
```

- `private UpdateDestroyedInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info) : System.Void`  

```csharp
private System.Void UpdateDestroyedInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
```

- `private UpdateEfficiencyInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info) : System.Void`  

```csharp
private System.Void UpdateEfficiencyInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
```

- `private UpdateElectricityConsumeInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info) : System.Void`  

```csharp
private System.Void UpdateElectricityConsumeInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
```

- `private UpdateElectricityProductionInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info) : System.Void`  

```csharp
private System.Void UpdateElectricityProductionInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
```

- `private UpdateEmployeesInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info) : System.Void`  

```csharp
private System.Void UpdateEmployeesInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
```

- `private UpdateEntityInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info) : System.Void`  

```csharp
private System.Void UpdateEntityInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
```

- `private UpdateEventInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info) : System.Void`  

```csharp
private System.Void UpdateEventInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
```

- `private UpdateExtractorCompanyInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info) : System.Void`  

```csharp
private System.Void UpdateExtractorCompanyInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
```

- `private UpdateFacingWeatherInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info) : System.Void`  

```csharp
private System.Void UpdateFacingWeatherInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
```

- `private UpdateFireEngineInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info) : System.Void`  

```csharp
private System.Void UpdateFireEngineInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
```

- `private UpdateFloodedInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info) : System.Void`  

```csharp
private System.Void UpdateFloodedInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
```

- `private UpdateGarbageInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info) : System.Void`  

```csharp
private System.Void UpdateGarbageInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
```

- `private UpdateGarbageProcessingInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info) : System.Void`  

```csharp
private System.Void UpdateGarbageProcessingInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
```

- `private UpdateGarbageTruckInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info) : System.Void`  

```csharp
private System.Void UpdateGarbageTruckInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
```

- `private UpdateGroupLeaderInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info) : System.Void`  

```csharp
private System.Void UpdateGroupLeaderInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
```

- `private UpdateGroupMemberInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info) : System.Void`  

```csharp
private System.Void UpdateGroupMemberInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
```

- `private UpdateHearseInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info) : System.Void`  

```csharp
private System.Void UpdateHearseInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
```

- `private UpdateHomelessInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info) : System.Void`  

```csharp
private System.Void UpdateHomelessInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
```

- `private UpdateHouseholdInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info) : System.Void`  

```csharp
private System.Void UpdateHouseholdInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
```

- `private UpdateHouseholdPetsInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info) : System.Void`  

```csharp
private System.Void UpdateHouseholdPetsInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
```

- `private UpdateHouseholdsInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info) : System.Void`  

```csharp
private System.Void UpdateHouseholdsInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
```

- `private UpdateInDangerInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info) : System.Void`  

```csharp
private System.Void UpdateInDangerInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
```

- `private UpdateInvolvedInAccidentInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info) : System.Void`  

```csharp
private System.Void UpdateInvolvedInAccidentInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
```

- `private UpdateKeeperInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info) : System.Void`  

```csharp
private System.Void UpdateKeeperInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
```

- `private UpdateLandValueInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info) : System.Void`  

```csharp
private System.Void UpdateLandValueInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
```

- `private UpdateMailBoxInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.CapacityInfo info) : System.Void`  

```csharp
private System.Void UpdateMailBoxInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.CapacityInfo info);
```

- `private UpdateMailInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info) : System.Void`  

```csharp
private System.Void UpdateMailInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
```

- `private UpdateMailProcessingSpeedInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info) : System.Void`  

```csharp
private System.Void UpdateMailProcessingSpeedInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
```

- `private UpdateMailSenderInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.CapacityInfo info) : System.Void`  

```csharp
private System.Void UpdateMailSenderInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.CapacityInfo info);
```

- `private UpdateMaintenanceVehicleInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info) : System.Void`  

```csharp
private System.Void UpdateMaintenanceVehicleInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
```

- `private UpdateMeshGroupInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info) : System.Void`  

```csharp
private System.Void UpdateMeshGroupInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
```

- `private UpdateMeshPrefabInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info) : System.Void`  

```csharp
private System.Void UpdateMeshPrefabInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
```

- `private UpdateMovingInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.CapacityInfo info) : System.Void`  

```csharp
private System.Void UpdateMovingInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.CapacityInfo info);
```

- `private UpdateNetworkCapacityInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.CapacityInfo info) : System.Void`  

```csharp
private System.Void UpdateNetworkCapacityInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.CapacityInfo info);
```

- `private UpdateNotificationInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info) : System.Void`  

```csharp
private System.Void UpdateNotificationInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
```

- `private UpdateOnFireInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info) : System.Void`  

```csharp
private System.Void UpdateOnFireInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
```

- `private UpdateOwnerInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info) : System.Void`  

```csharp
private System.Void UpdateOwnerInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
```

- `private UpdateParkInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info) : System.Void`  

```csharp
private System.Void UpdateParkInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
```

- `private UpdateParkingInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info) : System.Void`  

```csharp
private System.Void UpdateParkingInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
```

- `private UpdatePassengerInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.CapacityInfo info) : System.Void`  

```csharp
private System.Void UpdatePassengerInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.CapacityInfo info);
```

- `private UpdatePatientsInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info) : System.Void`  

```csharp
private System.Void UpdatePatientsInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
```

- `private UpdatePersonalCarInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info) : System.Void`  

```csharp
private System.Void UpdatePersonalCarInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
```

- `private UpdatePoliceCarInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info) : System.Void`  

```csharp
private System.Void UpdatePoliceCarInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
```

- `private UpdatePoliceInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.CapacityInfo info) : System.Void`  

```csharp
private System.Void UpdatePoliceInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.CapacityInfo info);
```

- `private UpdatePollutionInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info) : System.Void`  

```csharp
private System.Void UpdatePollutionInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
```

- `private UpdatePostVanInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info) : System.Void`  

```csharp
private System.Void UpdatePostVanInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
```

- `private UpdatePrisonInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info) : System.Void`  

```csharp
private System.Void UpdatePrisonInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
```

- `private UpdateProcessingCompanyInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info) : System.Void`  

```csharp
private System.Void UpdateProcessingCompanyInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
```

- `private UpdatePublicTransportInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info) : System.Void`  

```csharp
private System.Void UpdatePublicTransportInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
```

- `private UpdateRentInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info) : System.Void`  

```csharp
private System.Void UpdateRentInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
```

- `private UpdateResidentInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info) : System.Void`  

```csharp
private System.Void UpdateResidentInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
```

- `private UpdateResourceProductionInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info) : System.Void`  

```csharp
private System.Void UpdateResourceProductionInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
```

- `private UpdateSendReceiveMailInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info) : System.Void`  

```csharp
private System.Void UpdateSendReceiveMailInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
```

- `private UpdateServiceCompanyInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info) : System.Void`  

```csharp
private System.Void UpdateServiceCompanyInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
```

- `private UpdateShelterInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.CapacityInfo info) : System.Void`  

```csharp
private System.Void UpdateShelterInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.CapacityInfo info);
```

- `private UpdateSpectatorSiteInfo(Unity.Entities.Entity entity, Unity.Entities.Entity _, Game.UI.InGame.GenericInfo info) : System.Void`  

```csharp
private System.Void UpdateSpectatorSiteInfo(Unity.Entities.Entity entity, Unity.Entities.Entity _, Game.UI.InGame.GenericInfo info);
```

- `private UpdateStorageInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info) : System.Void`  

```csharp
private System.Void UpdateStorageInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
```

- `private UpdateStoredGarbageInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.CapacityInfo info) : System.Void`  

```csharp
private System.Void UpdateStoredGarbageInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.CapacityInfo info);
```

- `private UpdateStoredMailInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.CapacityInfo info) : System.Void`  

```csharp
private System.Void UpdateStoredMailInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.CapacityInfo info);
```

- `private UpdateStoredResourcesInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info) : System.Void`  

```csharp
private System.Void UpdateStoredResourcesInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
```

- `private UpdateStudentsInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info) : System.Void`  

```csharp
private System.Void UpdateStudentsInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
```

- `private UpdateTelecomRangeInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info) : System.Void`  

```csharp
private System.Void UpdateTelecomRangeInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
```

- `private UpdateTradeCostInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList infos) : System.Void`  

```csharp
private System.Void UpdateTradeCostInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList infos);
```

- `private UpdateTradePartnerInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info) : System.Void`  

```csharp
private System.Void UpdateTradePartnerInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
```

- `private UpdateTransferRequestInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info) : System.Void`  

```csharp
private System.Void UpdateTransferRequestInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
```

- `private UpdateTreeInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.CapacityInfo info) : System.Void`  

```csharp
private System.Void UpdateTreeInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.CapacityInfo info);
```

- `private UpdateVehicleInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info) : System.Void`  

```csharp
private System.Void UpdateVehicleInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
```

- `private UpdateVehicleModelInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info) : System.Void`  

```csharp
private System.Void UpdateVehicleModelInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
```

- `private UpdateWaitingPassengerInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info) : System.Void`  

```csharp
private System.Void UpdateWaitingPassengerInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.InfoList info);
```

- `private UpdateWarehouseInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info) : System.Void`  

```csharp
private System.Void UpdateWarehouseInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
```

- `private UpdateWaterConsumeInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info) : System.Void`  

```csharp
private System.Void UpdateWaterConsumeInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
```

- `private UpdateZoneHappinessInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info) : System.Void`  

```csharp
private System.Void UpdateZoneHappinessInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
```

- `private UpdateZoneInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info) : System.Void`  

```csharp
private System.Void UpdateZoneInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.GenericInfo info);
```

- `private UpdateZoneLevelInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.CapacityInfo info) : System.Void`  

```csharp
private System.Void UpdateZoneLevelInfo(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Game.UI.InGame.CapacityInfo info);
```

- `private static WellbeingToString(System.Int32 wellbeing) : System.String`  

```csharp
private static System.String WellbeingToString(System.Int32 wellbeing);
```

- `private WorthToString(System.Int32 worth) : System.String`  

```csharp
private System.String WorthToString(System.Int32 worth);
```


## Nested types

- `Game.UI.InGame.DeveloperInfoUISystem+BuildingHappinessFactorValue`  
- `Game.UI.InGame.DeveloperInfoUISystem+TypeHandle`  

