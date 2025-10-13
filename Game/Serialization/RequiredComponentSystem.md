# Game.Serialization.RequiredComponentSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class RequiredComponentSystem : Game.GameSystemBase
{
    private Game.Serialization.LoadGameSystem m_LoadGameSystem;
    private Unity.Entities.EntityQuery m_BlockedLaneQuery;
    private Unity.Entities.EntityQuery m_CarLaneQuery;
    private Unity.Entities.EntityQuery m_BuildingEfficiencyQuery;
    private Unity.Entities.EntityQuery m_PolicyQuery;
    private Unity.Entities.EntityQuery m_CityModifierQuery;
    private Unity.Entities.EntityQuery m_ServiceDispatchQuery;
    private Unity.Entities.EntityQuery m_PathInformationQuery;
    private Unity.Entities.EntityQuery m_NodeGeometryQuery;
    private Unity.Entities.EntityQuery m_MeshColorQuery;
    private Unity.Entities.EntityQuery m_MeshBatchQuery;
    private Unity.Entities.EntityQuery m_RoutePolicyQuery;
    private Unity.Entities.EntityQuery m_RouteModifierQuery;
    private Unity.Entities.EntityQuery m_EdgeQuery;
    private Unity.Entities.EntityQuery m_StorageTaxQuery;
    private Unity.Entities.EntityQuery m_CityFeeQuery;
    private Unity.Entities.EntityQuery m_CityFeeQuery2;
    private Unity.Entities.EntityQuery m_ServiceFeeParameterQuery;
    private Unity.Entities.EntityQuery m_OutsideGarbageQuery;
    private Unity.Entities.EntityQuery m_OutsideFireStationQuery;
    private Unity.Entities.EntityQuery m_OutsidePoliceStationQuery;
    private Unity.Entities.EntityQuery m_OutsideEfficiencyQuery;
    private Unity.Entities.EntityQuery m_RouteInfoQuery;
    private Unity.Entities.EntityQuery m_CompanyProfitabilityQuery;
    private Unity.Entities.EntityQuery m_StorageQuery;
    private Unity.Entities.EntityQuery m_RouteBufferIndexQuery;
    private Unity.Entities.EntityQuery m_CurveElementQuery;
    private Unity.Entities.EntityQuery m_CitizenPrefabQuery;
    private Unity.Entities.EntityQuery m_CitizenNameQuery;
    private Unity.Entities.EntityQuery m_HouseholdNameQuery;
    private Unity.Entities.EntityQuery m_LabelVertexQuery;
    private Unity.Entities.EntityQuery m_DistrictNameQuery;
    private Unity.Entities.EntityQuery m_AnimalNameQuery;
    private Unity.Entities.EntityQuery m_HouseholdPetQuery;
    private Unity.Entities.EntityQuery m_RoadNameQuery;
    private Unity.Entities.EntityQuery m_RouteNumberQuery;
    private Unity.Entities.EntityQuery m_ChirpRandomLocQuery;
    private Unity.Entities.EntityQuery m_BlockerQuery;
    private Unity.Entities.EntityQuery m_CitizenPresenceQuery;
    private Unity.Entities.EntityQuery m_SubLaneQuery;
    private Unity.Entities.EntityQuery m_SubObjectQuery;
    private Unity.Entities.EntityQuery m_NativeQuery;
    private Unity.Entities.EntityQuery m_GuestVehicleQuery;
    private Unity.Entities.EntityQuery m_TravelPurposeQuery;
    private Unity.Entities.EntityQuery m_TreeEffectQuery;
    private Unity.Entities.EntityQuery m_TakeoffLocationQuery;
    private Unity.Entities.EntityQuery m_LeisureQuery;
    private Unity.Entities.EntityQuery m_PlayerMoneyQuery;
    private Unity.Entities.EntityQuery m_PseudoRandomSeedQuery;
    private Unity.Entities.EntityQuery m_TransportDepotQuery;
    private Unity.Entities.EntityQuery m_ServiceUsageQuery;
    private Unity.Entities.EntityQuery m_OutsideSellerQuery;
    private Unity.Entities.EntityQuery m_LoadingResourcesQuery;
    private Unity.Entities.EntityQuery m_CompanyVehicleQuery;
    private Unity.Entities.EntityQuery m_LaneRestrictionQuery;
    private Unity.Entities.EntityQuery m_LaneOverlapQuery;
    private Unity.Entities.EntityQuery m_DispatchedRequestQuery;
    private Unity.Entities.EntityQuery m_HomelessShelterQuery;
    private Unity.Entities.EntityQuery m_QueueQuery;
    private Unity.Entities.EntityQuery m_BoneHistoryQuery;
    private Unity.Entities.EntityQuery m_UnspawnedQuery;
    private Unity.Entities.EntityQuery m_ConnectionLaneQuery;
    private Unity.Entities.EntityQuery m_AreaLaneQuery;
    private Unity.Entities.EntityQuery m_OfficeQuery;
    private Unity.Entities.EntityQuery m_VehicleModelQuery;
    private Unity.Entities.EntityQuery m_PassengerTransportQuery;
    private Unity.Entities.EntityQuery m_ObjectColorQuery;
    private Unity.Entities.EntityQuery m_OutsideConnectionQuery;
    private Unity.Entities.EntityQuery m_NetConditionQuery;
    private Unity.Entities.EntityQuery m_NetPollutionQuery;
    private Unity.Entities.EntityQuery m_TrafficSpawnerQuery;
    private Unity.Entities.EntityQuery m_AreaExpandQuery;
    private Unity.Entities.EntityQuery m_EmissiveQuery;
    private Unity.Entities.EntityQuery m_TrainBogieFrameQuery;
    private Unity.Entities.EntityQuery m_EditorContainerQuery;
    private Unity.Entities.EntityQuery m_ProcessingTradeCostQuery;
    private Unity.Entities.EntityQuery m_StorageConditionQuery;
    private Unity.Entities.EntityQuery m_LaneColorQuery;
    private Unity.Entities.EntityQuery m_CompanyNotificationQuery;
    private Unity.Entities.EntityQuery m_PlantQuery;
    private Unity.Entities.EntityQuery m_CityPopulationQuery;
    private Unity.Entities.EntityQuery m_CityTourismQuery;
    private Unity.Entities.EntityQuery m_LaneElevationQuery;
    private Unity.Entities.EntityQuery m_BuildingNotificationQuery;
    private Unity.Entities.EntityQuery m_AreaElevationQuery;
    private Unity.Entities.EntityQuery m_BuildingLotQuery;
    private Unity.Entities.EntityQuery m_AreaTerrainQuery;
    private Unity.Entities.EntityQuery m_OwnedVehicleQuery;
    private Unity.Entities.EntityQuery m_EdgeMappingQuery;
    private Unity.Entities.EntityQuery m_SubFlowQuery;
    private Unity.Entities.EntityQuery m_PointOfInterestQuery;
    private Unity.Entities.EntityQuery m_BuildableAreaQuery;
    private Unity.Entities.EntityQuery m_SubAreaQuery;
    private Unity.Entities.EntityQuery m_CrimeVictimQuery;
    private Unity.Entities.EntityQuery m_ArrivedQuery;
    private Unity.Entities.EntityQuery m_MailSenderQuery;
    private Unity.Entities.EntityQuery m_CarKeeperQuery;
    private Unity.Entities.EntityQuery m_NeedAddHasJobSeekerQuery;
    private Unity.Entities.EntityQuery m_NeedAddPropertySeekerQuery;
    private Unity.Entities.EntityQuery m_AgeGroupQuery;
    private Unity.Entities.EntityQuery m_PrefabRefQuery;
    private Unity.Entities.EntityQuery m_LabelMaterialQuery;
    private Unity.Entities.EntityQuery m_ArrowMaterialQuery;
    private Unity.Entities.EntityQuery m_LockedQuery;
    private Unity.Entities.EntityQuery m_OutsideUpdateQuery;
    private Unity.Entities.EntityQuery m_WaitingPassengersQuery;
    private Unity.Entities.EntityQuery m_ObjectSurfaceQuery;
    private Unity.Entities.EntityQuery m_WaitingPassengersQuery2;
    private Unity.Entities.EntityQuery m_PillarQuery;
    private Unity.Entities.EntityQuery m_LegacyEfficiencyQuery;
    private Unity.Entities.EntityQuery m_SignatureQuery;
    private Unity.Entities.EntityQuery m_SubObjectOwnerQuery;
    private Unity.Entities.EntityQuery m_DangerLevelMissingQuery;
    private Unity.Entities.EntityQuery m_MeshGroupQuery;
    private Unity.Entities.EntityQuery m_UpdateFrameQuery;
    private Unity.Entities.EntityQuery m_FenceQuery;
    private Unity.Entities.EntityQuery m_NetGeometrySectionQuery;
    private Unity.Entities.EntityQuery m_NetLaneArchetypeDataQuery;
    private Unity.Entities.EntityQuery m_PathfindUpdatedQuery;
    private Unity.Entities.EntityQuery m_RouteColorQuery;
    private Unity.Entities.EntityQuery m_CitizenQuery;
    private Unity.Entities.EntityQuery m_ServiceUpkeepQuery;
    private Unity.Entities.EntityQuery m_MoveableBridgeQuery;
    private Game.Serialization.RequiredComponentSystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_1938549531_0;

    public RequiredComponentSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Serialization.LoadGameSystem m_LoadGameSystem`  

```csharp
private Game.Serialization.LoadGameSystem m_LoadGameSystem;
```

- `private Unity.Entities.EntityQuery m_BlockedLaneQuery`  

```csharp
private Unity.Entities.EntityQuery m_BlockedLaneQuery;
```

- `private Unity.Entities.EntityQuery m_CarLaneQuery`  

```csharp
private Unity.Entities.EntityQuery m_CarLaneQuery;
```

- `private Unity.Entities.EntityQuery m_BuildingEfficiencyQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingEfficiencyQuery;
```

- `private Unity.Entities.EntityQuery m_PolicyQuery`  

```csharp
private Unity.Entities.EntityQuery m_PolicyQuery;
```

- `private Unity.Entities.EntityQuery m_CityModifierQuery`  

```csharp
private Unity.Entities.EntityQuery m_CityModifierQuery;
```

- `private Unity.Entities.EntityQuery m_ServiceDispatchQuery`  

```csharp
private Unity.Entities.EntityQuery m_ServiceDispatchQuery;
```

- `private Unity.Entities.EntityQuery m_PathInformationQuery`  

```csharp
private Unity.Entities.EntityQuery m_PathInformationQuery;
```

- `private Unity.Entities.EntityQuery m_NodeGeometryQuery`  

```csharp
private Unity.Entities.EntityQuery m_NodeGeometryQuery;
```

- `private Unity.Entities.EntityQuery m_MeshColorQuery`  

```csharp
private Unity.Entities.EntityQuery m_MeshColorQuery;
```

- `private Unity.Entities.EntityQuery m_MeshBatchQuery`  

```csharp
private Unity.Entities.EntityQuery m_MeshBatchQuery;
```

- `private Unity.Entities.EntityQuery m_RoutePolicyQuery`  

```csharp
private Unity.Entities.EntityQuery m_RoutePolicyQuery;
```

- `private Unity.Entities.EntityQuery m_RouteModifierQuery`  

```csharp
private Unity.Entities.EntityQuery m_RouteModifierQuery;
```

- `private Unity.Entities.EntityQuery m_EdgeQuery`  

```csharp
private Unity.Entities.EntityQuery m_EdgeQuery;
```

- `private Unity.Entities.EntityQuery m_StorageTaxQuery`  

```csharp
private Unity.Entities.EntityQuery m_StorageTaxQuery;
```

- `private Unity.Entities.EntityQuery m_CityFeeQuery`  

```csharp
private Unity.Entities.EntityQuery m_CityFeeQuery;
```

- `private Unity.Entities.EntityQuery m_CityFeeQuery2`  

```csharp
private Unity.Entities.EntityQuery m_CityFeeQuery2;
```

- `private Unity.Entities.EntityQuery m_ServiceFeeParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_ServiceFeeParameterQuery;
```

- `private Unity.Entities.EntityQuery m_OutsideGarbageQuery`  

```csharp
private Unity.Entities.EntityQuery m_OutsideGarbageQuery;
```

- `private Unity.Entities.EntityQuery m_OutsideFireStationQuery`  

```csharp
private Unity.Entities.EntityQuery m_OutsideFireStationQuery;
```

- `private Unity.Entities.EntityQuery m_OutsidePoliceStationQuery`  

```csharp
private Unity.Entities.EntityQuery m_OutsidePoliceStationQuery;
```

- `private Unity.Entities.EntityQuery m_OutsideEfficiencyQuery`  

```csharp
private Unity.Entities.EntityQuery m_OutsideEfficiencyQuery;
```

- `private Unity.Entities.EntityQuery m_RouteInfoQuery`  

```csharp
private Unity.Entities.EntityQuery m_RouteInfoQuery;
```

- `private Unity.Entities.EntityQuery m_CompanyProfitabilityQuery`  

```csharp
private Unity.Entities.EntityQuery m_CompanyProfitabilityQuery;
```

- `private Unity.Entities.EntityQuery m_StorageQuery`  

```csharp
private Unity.Entities.EntityQuery m_StorageQuery;
```

- `private Unity.Entities.EntityQuery m_RouteBufferIndexQuery`  

```csharp
private Unity.Entities.EntityQuery m_RouteBufferIndexQuery;
```

- `private Unity.Entities.EntityQuery m_CurveElementQuery`  

```csharp
private Unity.Entities.EntityQuery m_CurveElementQuery;
```

- `private Unity.Entities.EntityQuery m_CitizenPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_CitizenPrefabQuery;
```

- `private Unity.Entities.EntityQuery m_CitizenNameQuery`  

```csharp
private Unity.Entities.EntityQuery m_CitizenNameQuery;
```

- `private Unity.Entities.EntityQuery m_HouseholdNameQuery`  

```csharp
private Unity.Entities.EntityQuery m_HouseholdNameQuery;
```

- `private Unity.Entities.EntityQuery m_LabelVertexQuery`  

```csharp
private Unity.Entities.EntityQuery m_LabelVertexQuery;
```

- `private Unity.Entities.EntityQuery m_DistrictNameQuery`  

```csharp
private Unity.Entities.EntityQuery m_DistrictNameQuery;
```

- `private Unity.Entities.EntityQuery m_AnimalNameQuery`  

```csharp
private Unity.Entities.EntityQuery m_AnimalNameQuery;
```

- `private Unity.Entities.EntityQuery m_HouseholdPetQuery`  

```csharp
private Unity.Entities.EntityQuery m_HouseholdPetQuery;
```

- `private Unity.Entities.EntityQuery m_RoadNameQuery`  

```csharp
private Unity.Entities.EntityQuery m_RoadNameQuery;
```

- `private Unity.Entities.EntityQuery m_RouteNumberQuery`  

```csharp
private Unity.Entities.EntityQuery m_RouteNumberQuery;
```

- `private Unity.Entities.EntityQuery m_ChirpRandomLocQuery`  

```csharp
private Unity.Entities.EntityQuery m_ChirpRandomLocQuery;
```

- `private Unity.Entities.EntityQuery m_BlockerQuery`  

```csharp
private Unity.Entities.EntityQuery m_BlockerQuery;
```

- `private Unity.Entities.EntityQuery m_CitizenPresenceQuery`  

```csharp
private Unity.Entities.EntityQuery m_CitizenPresenceQuery;
```

- `private Unity.Entities.EntityQuery m_SubLaneQuery`  

```csharp
private Unity.Entities.EntityQuery m_SubLaneQuery;
```

- `private Unity.Entities.EntityQuery m_SubObjectQuery`  

```csharp
private Unity.Entities.EntityQuery m_SubObjectQuery;
```

- `private Unity.Entities.EntityQuery m_NativeQuery`  

```csharp
private Unity.Entities.EntityQuery m_NativeQuery;
```

- `private Unity.Entities.EntityQuery m_GuestVehicleQuery`  

```csharp
private Unity.Entities.EntityQuery m_GuestVehicleQuery;
```

- `private Unity.Entities.EntityQuery m_TravelPurposeQuery`  

```csharp
private Unity.Entities.EntityQuery m_TravelPurposeQuery;
```

- `private Unity.Entities.EntityQuery m_TreeEffectQuery`  

```csharp
private Unity.Entities.EntityQuery m_TreeEffectQuery;
```

- `private Unity.Entities.EntityQuery m_TakeoffLocationQuery`  

```csharp
private Unity.Entities.EntityQuery m_TakeoffLocationQuery;
```

- `private Unity.Entities.EntityQuery m_LeisureQuery`  

```csharp
private Unity.Entities.EntityQuery m_LeisureQuery;
```

- `private Unity.Entities.EntityQuery m_PlayerMoneyQuery`  

```csharp
private Unity.Entities.EntityQuery m_PlayerMoneyQuery;
```

- `private Unity.Entities.EntityQuery m_PseudoRandomSeedQuery`  

```csharp
private Unity.Entities.EntityQuery m_PseudoRandomSeedQuery;
```

- `private Unity.Entities.EntityQuery m_TransportDepotQuery`  

```csharp
private Unity.Entities.EntityQuery m_TransportDepotQuery;
```

- `private Unity.Entities.EntityQuery m_ServiceUsageQuery`  

```csharp
private Unity.Entities.EntityQuery m_ServiceUsageQuery;
```

- `private Unity.Entities.EntityQuery m_OutsideSellerQuery`  

```csharp
private Unity.Entities.EntityQuery m_OutsideSellerQuery;
```

- `private Unity.Entities.EntityQuery m_LoadingResourcesQuery`  

```csharp
private Unity.Entities.EntityQuery m_LoadingResourcesQuery;
```

- `private Unity.Entities.EntityQuery m_CompanyVehicleQuery`  

```csharp
private Unity.Entities.EntityQuery m_CompanyVehicleQuery;
```

- `private Unity.Entities.EntityQuery m_LaneRestrictionQuery`  

```csharp
private Unity.Entities.EntityQuery m_LaneRestrictionQuery;
```

- `private Unity.Entities.EntityQuery m_LaneOverlapQuery`  

```csharp
private Unity.Entities.EntityQuery m_LaneOverlapQuery;
```

- `private Unity.Entities.EntityQuery m_DispatchedRequestQuery`  

```csharp
private Unity.Entities.EntityQuery m_DispatchedRequestQuery;
```

- `private Unity.Entities.EntityQuery m_HomelessShelterQuery`  

```csharp
private Unity.Entities.EntityQuery m_HomelessShelterQuery;
```

- `private Unity.Entities.EntityQuery m_QueueQuery`  

```csharp
private Unity.Entities.EntityQuery m_QueueQuery;
```

- `private Unity.Entities.EntityQuery m_BoneHistoryQuery`  

```csharp
private Unity.Entities.EntityQuery m_BoneHistoryQuery;
```

- `private Unity.Entities.EntityQuery m_UnspawnedQuery`  

```csharp
private Unity.Entities.EntityQuery m_UnspawnedQuery;
```

- `private Unity.Entities.EntityQuery m_ConnectionLaneQuery`  

```csharp
private Unity.Entities.EntityQuery m_ConnectionLaneQuery;
```

- `private Unity.Entities.EntityQuery m_AreaLaneQuery`  

```csharp
private Unity.Entities.EntityQuery m_AreaLaneQuery;
```

- `private Unity.Entities.EntityQuery m_OfficeQuery`  

```csharp
private Unity.Entities.EntityQuery m_OfficeQuery;
```

- `private Unity.Entities.EntityQuery m_VehicleModelQuery`  

```csharp
private Unity.Entities.EntityQuery m_VehicleModelQuery;
```

- `private Unity.Entities.EntityQuery m_PassengerTransportQuery`  

```csharp
private Unity.Entities.EntityQuery m_PassengerTransportQuery;
```

- `private Unity.Entities.EntityQuery m_ObjectColorQuery`  

```csharp
private Unity.Entities.EntityQuery m_ObjectColorQuery;
```

- `private Unity.Entities.EntityQuery m_OutsideConnectionQuery`  

```csharp
private Unity.Entities.EntityQuery m_OutsideConnectionQuery;
```

- `private Unity.Entities.EntityQuery m_NetConditionQuery`  

```csharp
private Unity.Entities.EntityQuery m_NetConditionQuery;
```

- `private Unity.Entities.EntityQuery m_NetPollutionQuery`  

```csharp
private Unity.Entities.EntityQuery m_NetPollutionQuery;
```

- `private Unity.Entities.EntityQuery m_TrafficSpawnerQuery`  

```csharp
private Unity.Entities.EntityQuery m_TrafficSpawnerQuery;
```

- `private Unity.Entities.EntityQuery m_AreaExpandQuery`  

```csharp
private Unity.Entities.EntityQuery m_AreaExpandQuery;
```

- `private Unity.Entities.EntityQuery m_EmissiveQuery`  

```csharp
private Unity.Entities.EntityQuery m_EmissiveQuery;
```

- `private Unity.Entities.EntityQuery m_TrainBogieFrameQuery`  

```csharp
private Unity.Entities.EntityQuery m_TrainBogieFrameQuery;
```

- `private Unity.Entities.EntityQuery m_EditorContainerQuery`  

```csharp
private Unity.Entities.EntityQuery m_EditorContainerQuery;
```

- `private Unity.Entities.EntityQuery m_ProcessingTradeCostQuery`  

```csharp
private Unity.Entities.EntityQuery m_ProcessingTradeCostQuery;
```

- `private Unity.Entities.EntityQuery m_StorageConditionQuery`  

```csharp
private Unity.Entities.EntityQuery m_StorageConditionQuery;
```

- `private Unity.Entities.EntityQuery m_LaneColorQuery`  

```csharp
private Unity.Entities.EntityQuery m_LaneColorQuery;
```

- `private Unity.Entities.EntityQuery m_CompanyNotificationQuery`  

```csharp
private Unity.Entities.EntityQuery m_CompanyNotificationQuery;
```

- `private Unity.Entities.EntityQuery m_PlantQuery`  

```csharp
private Unity.Entities.EntityQuery m_PlantQuery;
```

- `private Unity.Entities.EntityQuery m_CityPopulationQuery`  

```csharp
private Unity.Entities.EntityQuery m_CityPopulationQuery;
```

- `private Unity.Entities.EntityQuery m_CityTourismQuery`  

```csharp
private Unity.Entities.EntityQuery m_CityTourismQuery;
```

- `private Unity.Entities.EntityQuery m_LaneElevationQuery`  

```csharp
private Unity.Entities.EntityQuery m_LaneElevationQuery;
```

- `private Unity.Entities.EntityQuery m_BuildingNotificationQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingNotificationQuery;
```

- `private Unity.Entities.EntityQuery m_AreaElevationQuery`  

```csharp
private Unity.Entities.EntityQuery m_AreaElevationQuery;
```

- `private Unity.Entities.EntityQuery m_BuildingLotQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingLotQuery;
```

- `private Unity.Entities.EntityQuery m_AreaTerrainQuery`  

```csharp
private Unity.Entities.EntityQuery m_AreaTerrainQuery;
```

- `private Unity.Entities.EntityQuery m_OwnedVehicleQuery`  

```csharp
private Unity.Entities.EntityQuery m_OwnedVehicleQuery;
```

- `private Unity.Entities.EntityQuery m_EdgeMappingQuery`  

```csharp
private Unity.Entities.EntityQuery m_EdgeMappingQuery;
```

- `private Unity.Entities.EntityQuery m_SubFlowQuery`  

```csharp
private Unity.Entities.EntityQuery m_SubFlowQuery;
```

- `private Unity.Entities.EntityQuery m_PointOfInterestQuery`  

```csharp
private Unity.Entities.EntityQuery m_PointOfInterestQuery;
```

- `private Unity.Entities.EntityQuery m_BuildableAreaQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildableAreaQuery;
```

- `private Unity.Entities.EntityQuery m_SubAreaQuery`  

```csharp
private Unity.Entities.EntityQuery m_SubAreaQuery;
```

- `private Unity.Entities.EntityQuery m_CrimeVictimQuery`  

```csharp
private Unity.Entities.EntityQuery m_CrimeVictimQuery;
```

- `private Unity.Entities.EntityQuery m_ArrivedQuery`  

```csharp
private Unity.Entities.EntityQuery m_ArrivedQuery;
```

- `private Unity.Entities.EntityQuery m_MailSenderQuery`  

```csharp
private Unity.Entities.EntityQuery m_MailSenderQuery;
```

- `private Unity.Entities.EntityQuery m_CarKeeperQuery`  

```csharp
private Unity.Entities.EntityQuery m_CarKeeperQuery;
```

- `private Unity.Entities.EntityQuery m_NeedAddHasJobSeekerQuery`  

```csharp
private Unity.Entities.EntityQuery m_NeedAddHasJobSeekerQuery;
```

- `private Unity.Entities.EntityQuery m_NeedAddPropertySeekerQuery`  

```csharp
private Unity.Entities.EntityQuery m_NeedAddPropertySeekerQuery;
```

- `private Unity.Entities.EntityQuery m_AgeGroupQuery`  

```csharp
private Unity.Entities.EntityQuery m_AgeGroupQuery;
```

- `private Unity.Entities.EntityQuery m_PrefabRefQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrefabRefQuery;
```

- `private Unity.Entities.EntityQuery m_LabelMaterialQuery`  

```csharp
private Unity.Entities.EntityQuery m_LabelMaterialQuery;
```

- `private Unity.Entities.EntityQuery m_ArrowMaterialQuery`  

```csharp
private Unity.Entities.EntityQuery m_ArrowMaterialQuery;
```

- `private Unity.Entities.EntityQuery m_LockedQuery`  

```csharp
private Unity.Entities.EntityQuery m_LockedQuery;
```

- `private Unity.Entities.EntityQuery m_OutsideUpdateQuery`  

```csharp
private Unity.Entities.EntityQuery m_OutsideUpdateQuery;
```

- `private Unity.Entities.EntityQuery m_WaitingPassengersQuery`  

```csharp
private Unity.Entities.EntityQuery m_WaitingPassengersQuery;
```

- `private Unity.Entities.EntityQuery m_ObjectSurfaceQuery`  

```csharp
private Unity.Entities.EntityQuery m_ObjectSurfaceQuery;
```

- `private Unity.Entities.EntityQuery m_WaitingPassengersQuery2`  

```csharp
private Unity.Entities.EntityQuery m_WaitingPassengersQuery2;
```

- `private Unity.Entities.EntityQuery m_PillarQuery`  

```csharp
private Unity.Entities.EntityQuery m_PillarQuery;
```

- `private Unity.Entities.EntityQuery m_LegacyEfficiencyQuery`  

```csharp
private Unity.Entities.EntityQuery m_LegacyEfficiencyQuery;
```

- `private Unity.Entities.EntityQuery m_SignatureQuery`  

```csharp
private Unity.Entities.EntityQuery m_SignatureQuery;
```

- `private Unity.Entities.EntityQuery m_SubObjectOwnerQuery`  

```csharp
private Unity.Entities.EntityQuery m_SubObjectOwnerQuery;
```

- `private Unity.Entities.EntityQuery m_DangerLevelMissingQuery`  

```csharp
private Unity.Entities.EntityQuery m_DangerLevelMissingQuery;
```

- `private Unity.Entities.EntityQuery m_MeshGroupQuery`  

```csharp
private Unity.Entities.EntityQuery m_MeshGroupQuery;
```

- `private Unity.Entities.EntityQuery m_UpdateFrameQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdateFrameQuery;
```

- `private Unity.Entities.EntityQuery m_FenceQuery`  

```csharp
private Unity.Entities.EntityQuery m_FenceQuery;
```

- `private Unity.Entities.EntityQuery m_NetGeometrySectionQuery`  

```csharp
private Unity.Entities.EntityQuery m_NetGeometrySectionQuery;
```

- `private Unity.Entities.EntityQuery m_NetLaneArchetypeDataQuery`  

```csharp
private Unity.Entities.EntityQuery m_NetLaneArchetypeDataQuery;
```

- `private Unity.Entities.EntityQuery m_PathfindUpdatedQuery`  

```csharp
private Unity.Entities.EntityQuery m_PathfindUpdatedQuery;
```

- `private Unity.Entities.EntityQuery m_RouteColorQuery`  

```csharp
private Unity.Entities.EntityQuery m_RouteColorQuery;
```

- `private Unity.Entities.EntityQuery m_CitizenQuery`  

```csharp
private Unity.Entities.EntityQuery m_CitizenQuery;
```

- `private Unity.Entities.EntityQuery m_ServiceUpkeepQuery`  

```csharp
private Unity.Entities.EntityQuery m_ServiceUpkeepQuery;
```

- `private Unity.Entities.EntityQuery m_MoveableBridgeQuery`  

```csharp
private Unity.Entities.EntityQuery m_MoveableBridgeQuery;
```

- `private Game.Serialization.RequiredComponentSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Serialization.RequiredComponentSystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_1938549531_0`  

```csharp
private Unity.Entities.EntityQuery __query_1938549531_0;
```


## Constructors

- `public RequiredComponentSystem()`  

```csharp
[Preserve]
	public RequiredComponentSystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		EntityQueryBuilder entityQueryBuilder = new EntityQueryBuilder(Allocator.Temp);
		EntityQueryBuilder entityQueryBuilder2 = entityQueryBuilder.WithAll<TimeData>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_1938549531_0 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder.Dispose();
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_LoadGameSystem = base.World.GetOrCreateSystemManaged<LoadGameSystem>();
		m_BlockedLaneQuery = GetEntityQuery(ComponentType.ReadOnly<Car>(), ComponentType.Exclude<BlockedLane>());
		m_CarLaneQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Net.CarLane>(), ComponentType.Exclude<MasterLane>(), ComponentType.Exclude<LaneFlow>());
		m_BuildingEfficiencyQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Buildings.TransportDepot>(), ComponentType.ReadOnly<Building>(), ComponentType.Exclude<Efficiency>());
		m_PolicyQuery = GetEntityQuery(ComponentType.ReadOnly<Game.City.City>(), ComponentType.Exclude<Policy>());
		m_CityModifierQuery = GetEntityQuery(ComponentType.ReadOnly<Game.City.City>(), ComponentType.Exclude<CityModifier>());
		m_ServiceDispatchQuery = GetEntityQuery(new EntityQueryDesc
		{
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Game.Vehicles.PublicTransport>(),
				ComponentType.ReadOnly<Game.Vehicles.CargoTransport>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<ServiceDispatch>() }
		});
		m_PathInformationQuery = GetEntityQuery(new EntityQueryDesc
		{
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Game.Vehicles.PublicTransport>(),
				ComponentType.ReadOnly<Game.Vehicles.CargoTransport>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<PathInformation>() }
		});
		m_NodeGeometryQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Net.Node>(), ComponentType.ReadOnly<Game.Net.SubLane>(), ComponentType.Exclude<NodeGeometry>());
		m_MeshColorQuery = GetEntityQuery(new EntityQueryDesc
		{
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Tree>(),
				ComponentType.ReadOnly<Plant>(),
				ComponentType.ReadOnly<Human>()
			},
			None = new ComponentType[1] { ComponentType.Exclude<MeshColor>() }
		});
		m_MeshBatchQuery = GetEntityQuery(new EntityQueryDesc
		{
			Any = new ComponentType[6]
			{
				ComponentType.ReadOnly<NodeGeometry>(),
				ComponentType.ReadOnly<EdgeGeometry>(),
				ComponentType.ReadOnly<LaneGeometry>(),
				ComponentType.ReadOnly<ObjectGeometry>(),
				ComponentType.ReadOnly<Game.Objects.Marker>(),
				ComponentType.ReadOnly<Block>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<MeshBatch>() }
		});
		m_RoutePolicyQuery = GetEntityQuery(ComponentType.ReadOnly<Route>(), ComponentType.Exclude<Policy>(), ComponentType.Exclude<RouteModifier>());
		m_RouteModifierQuery = GetEntityQuery(ComponentType.ReadOnly<Route>(), ComponentType.Exclude<RouteModifier>());
		m_EdgeQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Net.Edge>(), ComponentType.ReadOnly<ConnectedBuilding>(), ComponentType.Exclude<Density>());
		m_StorageTaxQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Companies.StorageCompany>(), ComponentType.ReadOnly<TaxPayer>());
		m_CityFeeQuery = GetEntityQuery(ComponentType.ReadOnly<Game.City.City>(), ComponentType.Exclude<ServiceFee>());
		m_CityFeeQuery2 = GetEntityQuery(ComponentType.ReadOnly<Game.City.City>(), ComponentType.ReadWrite<ServiceFee>());
		m_ServiceFeeParameterQuery = GetEntityQuery(ComponentType.ReadOnly<ServiceFeeParameterData>());
		m_OutsideGarbageQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Objects.OutsideConnection>(), ComponentType.Exclude<Game.Buildings.GarbageFacility>());
		m_OutsideFireStationQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Objects.OutsideConnection>(), ComponentType.Exclude<Game.Buildings.FireStation>());
		m_OutsidePoliceStationQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Objects.OutsideConnection>(), ComponentType.Exclude<Game.Buildings.PoliceStation>());
		m_OutsideEfficiencyQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Objects.OutsideConnection>(), ComponentType.Exclude<Efficiency>());
		m_RouteInfoQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Routes.Segment>(), ComponentType.ReadOnly<PathTargets>(), ComponentType.Exclude<RouteInfo>());
		m_CompanyProfitabilityQuery = GetEntityQuery(ComponentType.ReadOnly<CompanyData>(), ComponentType.Exclude<Profitability>(), ComponentType.Exclude<Game.Companies.StorageCompany>());
		m_StorageQuery = GetEntityQuery(ComponentType.ReadOnly<IndustrialProperty>(), ComponentType.Exclude<StorageProperty>());
		m_RouteBufferIndexQuery = GetEntityQuery(ComponentType.ReadOnly<Route>(), ComponentType.Exclude<RouteBufferIndex>());
		m_CurveElementQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Routes.Segment>(), ComponentType.Exclude<CurveElement>());
		m_CitizenPrefabQuery = GetEntityQuery(ComponentType.ReadOnly<Citizen>(), ComponentType.Exclude<PrefabRef>());
		m_CitizenNameQuery = GetEntityQuery(ComponentType.ReadOnly<Citizen>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<RandomLocalizationIndex>());
		m_HouseholdNameQuery = GetEntityQuery(ComponentType.ReadOnly<Household>(), ComponentType.Exclude<RandomLocalizationIndex>());
		m_DistrictNameQuery = GetEntityQuery(ComponentType.ReadOnly<District>(), ComponentType.ReadOnly<Area>(), ComponentType.Exclude<RandomLocalizationIndex>());
		m_AnimalNameQuery = GetEntityQuery(ComponentType.ReadOnly<Animal>(), ComponentType.Exclude<RandomLocalizationIndex>());
		m_HouseholdPetQuery = GetEntityQuery(ComponentType.ReadOnly<HouseholdPet>(), ComponentType.Exclude<RandomLocalizationIndex>());
		m_RoadNameQuery = GetEntityQuery(ComponentType.ReadOnly<Aggregate>(), ComponentType.ReadOnly<LabelMaterial>(), ComponentType.Exclude<RandomLocalizationIndex>());
		m_LabelVertexQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Areas.LabelExtents>(), ComponentType.Exclude<Game.Areas.LabelVertex>());
		m_RouteNumberQuery = GetEntityQuery(ComponentType.ReadOnly<TransportLine>(), ComponentType.Exclude<RouteNumber>());
		m_ChirpRandomLocQuery = GetEntityQuery(new EntityQueryDesc
		{
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<LifePathEntry>(),
				ComponentType.ReadOnly<ChirpEntity>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<RandomLocalizationIndex>() }
		});
		m_BlockerQuery = GetEntityQuery(new EntityQueryDesc
		{
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<HumanCurrentLane>(),
				ComponentType.ReadOnly<AnimalCurrentLane>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Blocker>() }
		});
		m_CitizenPresenceQuery = GetEntityQuery(ComponentType.ReadOnly<Building>(), ComponentType.Exclude<CitizenPresence>());
		m_SubLaneQuery = GetEntityQuery(ComponentType.ReadOnly<Building>(), ComponentType.Exclude<Game.Net.SubLane>());
		m_SubObjectQuery = GetEntityQuery(ComponentType.ReadOnly<Building>(), ComponentType.Exclude<Game.Objects.SubObject>());
		m_NativeQuery = GetEntityQuery(ComponentType.ReadOnly<MapTile>(), ComponentType.Exclude<Native>(), ComponentType.Exclude<Owner>());
		m_GuestVehicleQuery = GetEntityQuery(new EntityQueryDesc
		{
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Game.Buildings.PostFacility>(),
				ComponentType.ReadOnly<Game.Buildings.GarbageFacility>()
			},
			None = new ComponentType[3]
			{
				ComponentType.ReadOnly<Game.Buildings.ServiceUpgrade>(),
				ComponentType.ReadOnly<Game.Objects.OutsideConnection>(),
				ComponentType.ReadOnly<GuestVehicle>()
			}
		});
		m_TravelPurposeQuery = GetEntityQuery(ComponentType.ReadOnly<TravelPurpose>());
		m_TreeEffectQuery = GetEntityQuery(ComponentType.ReadOnly<Tree>(), ComponentType.Exclude<EnabledEffect>());
		m_TakeoffLocationQuery = GetEntityQuery(ComponentType.ReadOnly<AirplaneStop>(), ComponentType.ReadOnly<Game.Net.SubLane>(), ComponentType.Exclude<Game.Routes.TakeoffLocation>());
		m_LeisureQuery = GetEntityQuery(ComponentType.ReadOnly<CompanyData>(), ComponentType.Exclude<Game.Buildings.LeisureProvider>(), ComponentType.ReadOnly<PrefabRef>());
		m_PlayerMoneyQuery = GetEntityQuery(ComponentType.ReadOnly<Game.City.City>(), ComponentType.ReadWrite<Game.Economy.Resources>(), ComponentType.Exclude<PlayerMoney>());
		m_PseudoRandomSeedQuery = GetEntityQuery(new EntityQueryDesc
		{
			Any = new ComponentType[6]
			{
				ComponentType.ReadOnly<NodeGeometry>(),
				ComponentType.ReadOnly<EdgeGeometry>(),
				ComponentType.ReadOnly<ObjectGeometry>(),
				ComponentType.ReadOnly<AssetStamp>(),
				ComponentType.ReadOnly<Game.Objects.Marker>(),
				ComponentType.ReadOnly<Game.Areas.Lot>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<PseudoRandomSeed>() }
		});
		m_TransportDepotQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Objects.OutsideConnection>(), ComponentType.ReadOnly<Game.Buildings.GarbageFacility>(), ComponentType.Exclude<Game.Buildings.TransportDepot>());
		m_ServiceUsageQuery = GetEntityQuery(ComponentType.ReadOnly<CityServiceUpkeep>(), ComponentType.Exclude<ServiceUsage>());
		m_OutsideSellerQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Objects.OutsideConnection>(), ComponentType.Exclude<ResourceSeller>());
		m_LoadingResourcesQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Vehicles.CargoTransport>(), ComponentType.Exclude<LoadingResources>());
		m_CompanyVehicleQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Companies.ProcessingCompany>(), ComponentType.Exclude<OwnedVehicle>());
		m_LaneRestrictionQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Owner>() },
			Any = new ComponentType[7]
			{
				ComponentType.ReadOnly<Game.Net.CarLane>(),
				ComponentType.ReadOnly<Game.Net.ParkingLane>(),
				ComponentType.ReadOnly<Game.Net.PedestrianLane>(),
				ComponentType.ReadOnly<Game.Net.ConnectionLane>(),
				ComponentType.ReadOnly<Game.Routes.TransportStop>(),
				ComponentType.ReadOnly<Game.Routes.TakeoffLocation>(),
				ComponentType.ReadOnly<Game.Objects.SpawnLocation>()
			}
		});
		m_LaneOverlapQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Net.ParkingLane>(), ComponentType.Exclude<LaneOverlap>());
		m_DispatchedRequestQuery = GetEntityQuery(new EntityQueryDesc
		{
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<TransportLine>(),
				ComponentType.ReadOnly<TaxiStand>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<DispatchedRequest>() }
		});
		m_HomelessShelterQuery = GetEntityQuery(new EntityQueryDesc
		{
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Game.Buildings.Park>(),
				ComponentType.ReadOnly<Abandoned>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Renter>() }
		});
		m_QueueQuery = GetEntityQuery(ComponentType.ReadOnly<Human>(), ComponentType.Exclude<Queue>());
		m_BoneHistoryQuery = GetEntityQuery(ComponentType.ReadOnly<Bone>(), ComponentType.Exclude<BoneHistory>());
		m_UnspawnedQuery = GetEntityQuery(ComponentType.ReadOnly<CurrentVehicle>(), ComponentType.Exclude<Unspawned>());
		m_ConnectionLaneQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Net.ConnectionLane>(), ComponentType.ReadOnly<NodeLane>());
		m_AreaLaneQuery = GetEntityQuery(ComponentType.ReadOnly<Area>(), ComponentType.ReadOnly<Game.Net.SubLane>());
		m_OfficeQuery = GetEntityQuery(ComponentType.ReadOnly<IndustrialProperty>(), ComponentType.Exclude<OfficeProperty>());
		m_VehicleModelQuery = GetEntityQuery(ComponentType.ReadOnly<TransportLine>());
		m_PassengerTransportQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Vehicles.PublicTransport>(), ComponentType.Exclude<PassengerTransport>(), ComponentType.Exclude<EvacuatingTransport>(), ComponentType.Exclude<PrisonerTransport>());
		m_ObjectColorQuery = GetEntityQuery(new EntityQueryDesc
		{
			Any = new ComponentType[5]
			{
				ComponentType.ReadOnly<Tree>(),
				ComponentType.ReadOnly<Vehicle>(),
				ComponentType.ReadOnly<Creature>(),
				ComponentType.ReadOnly<Extension>(),
				ComponentType.ReadOnly<Game.Objects.UtilityObject>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Game.Objects.Color>() }
		});
		m_OutsideConnectionQuery = GetEntityQuery(new EntityQueryDesc
		{
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Game.Objects.ElectricityOutsideConnection>(),
				ComponentType.ReadOnly<Game.Objects.WaterPipeOutsideConnection>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Game.Objects.OutsideConnection>() }
		});
		m_NetConditionQuery = GetEntityQuery(ComponentType.ReadOnly<Road>(), ComponentType.Exclude<NetCondition>());
		m_NetPollutionQuery = GetEntityQuery(ComponentType.ReadOnly<Road>(), ComponentType.Exclude<Game.Net.Pollution>());
		m_TrafficSpawnerQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Objects.OutsideConnection>(), ComponentType.ReadOnly<OwnedVehicle>(), ComponentType.Exclude<Game.Buildings.TrafficSpawner>());
		m_AreaExpandQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Areas.Surface>(), ComponentType.Exclude<Expand>());
		m_EmissiveQuery = GetEntityQuery(new EntityQueryDesc
		{
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<TrafficLight>(),
				ComponentType.ReadOnly<Car>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Emissive>() }
		});
		m_TrainBogieFrameQuery = GetEntityQuery(ComponentType.ReadOnly<TrainCurrentLane>(), ComponentType.Exclude<TrainBogieFrame>());
		m_ProcessingTradeCostQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Companies.ProcessingCompany>(), ComponentType.Exclude<TradeCost>());
		m_EditorContainerQuery = GetEntityQuery(new EntityQueryDesc
		{
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Game.Net.Node>(),
				ComponentType.ReadOnly<Game.Net.Edge>(),
				ComponentType.ReadOnly<Game.Objects.Object>()
			},
			None = new ComponentType[6]
			{
				ComponentType.ReadOnly<NodeGeometry>(),
				ComponentType.ReadOnly<EdgeGeometry>(),
				ComponentType.ReadOnly<ObjectGeometry>(),
				ComponentType.ReadOnly<AssetStamp>(),
				ComponentType.ReadOnly<Game.Objects.Marker>(),
				ComponentType.ReadOnly<Game.Tools.EditorContainer>()
			}
		});
		m_StorageConditionQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Companies.StorageCompany>(), ComponentType.ReadOnly<PropertyRenter>());
		m_LaneColorQuery = GetEntityQuery(new EntityQueryDesc
		{
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Game.Net.TrackLane>(),
				ComponentType.ReadOnly<Game.Net.UtilityLane>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<LaneColor>() }
		});
		m_CompanyNotificationQuery = GetEntityQuery(ComponentType.ReadOnly<CompanyData>(), ComponentType.Exclude<CompanyNotifications>());
		m_PlantQuery = GetEntityQuery(ComponentType.ReadOnly<Tree>(), ComponentType.Exclude<Plant>());
		m_CityPopulationQuery = GetEntityQuery(ComponentType.ReadOnly<Game.City.City>(), ComponentType.Exclude<Population>());
		m_CityTourismQuery = GetEntityQuery(ComponentType.ReadOnly<Game.City.City>(), ComponentType.Exclude<Tourism>());
		m_BuildingNotificationQuery = GetEntityQuery(ComponentType.ReadOnly<ResidentialProperty>(), ComponentType.Exclude<BuildingNotifications>());
		m_LaneElevationQuery = GetEntityQuery(ComponentType.ReadOnly<Lane>(), ComponentType.ReadOnly<Owner>(), ComponentType.Exclude<EdgeLane>(), ComponentType.Exclude<AreaLane>(), ComponentType.Exclude<Game.Net.ConnectionLane>(), ComponentType.Exclude<Game.Net.Elevation>());
		m_AreaElevationQuery = GetEntityQuery(ComponentType.ReadOnly<Area>(), ComponentType.ReadOnly<Owner>());
		m_BuildingLotQuery = GetEntityQuery(ComponentType.ReadOnly<Building>(), ComponentType.Exclude<Game.Buildings.Lot>());
		m_AreaTerrainQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Areas.Lot>(), ComponentType.ReadOnly<Storage>(), ComponentType.Exclude<Game.Areas.Terrain>());
		m_OwnedVehicleQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Areas.Lot>(), ComponentType.ReadOnly<Storage>(), ComponentType.Exclude<OwnedVehicle>());
		m_EdgeMappingQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Net.UtilityLane>(), ComponentType.Exclude<EdgeMapping>());
		m_SubFlowQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Net.UtilityLane>(), ComponentType.Exclude<SubFlow>());
		m_PointOfInterestQuery = GetEntityQuery(new EntityQueryDesc
		{
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Game.Vehicles.PoliceCar>(),
				ComponentType.ReadOnly<RenewableElectricityProduction>(),
				ComponentType.ReadOnly<Game.Buildings.ExtractorFacility>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<PointOfInterest>() }
		});
		m_BuildableAreaQuery = GetEntityQuery(ComponentType.ReadOnly<MapFeatureElement>(), ComponentType.Exclude<Updated>());
		m_SubAreaQuery = GetEntityQuery(ComponentType.ReadOnly<Extractor>(), ComponentType.Exclude<Game.Areas.SubArea>());
		m_CrimeVictimQuery = GetEntityQuery(ComponentType.ReadOnly<Citizen>(), ComponentType.Exclude<CrimeVictim>());
		m_ArrivedQuery = GetEntityQuery(ComponentType.ReadOnly<Citizen>(), ComponentType.Exclude<Arrived>());
		m_MailSenderQuery = GetEntityQuery(ComponentType.ReadOnly<Citizen>(), ComponentType.Exclude<MailSender>());
		m_CarKeeperQuery = GetEntityQuery(ComponentType.ReadOnly<Citizen>(), ComponentType.Exclude<CarKeeper>());
		m_NeedAddHasJobSeekerQuery = GetEntityQuery(ComponentType.ReadOnly<Citizen>(), ComponentType.Exclude<HasJobSeeker>());
		m_NeedAddPropertySeekerQuery = GetEntityQuery(new EntityQueryDesc
		{
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Household>(),
				ComponentType.ReadOnly<CompanyData>()
			},
			None = new ComponentType[1] { ComponentType.Exclude<PropertySeeker>() }
		});
		m_AgeGroupQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadWrite<Citizen>() },
			Any = new ComponentType[4]
			{
				ComponentType.ReadOnly<Child>(),
				ComponentType.ReadOnly<Teen>(),
				ComponentType.ReadOnly<Adult>(),
				ComponentType.ReadOnly<Elderly>()
			}
		});
		m_PrefabRefQuery = GetEntityQuery(ComponentType.ReadOnly<PrefabRef>());
		m_LabelMaterialQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Net.LabelExtents>(), ComponentType.Exclude<LabelMaterial>());
		m_ArrowMaterialQuery = GetEntityQuery(ComponentType.ReadOnly<ArrowPosition>(), ComponentType.Exclude<ArrowMaterial>());
		m_LockedQuery = GetEntityQuery(ComponentType.ReadOnly<UnlockRequirement>(), ComponentType.Exclude<Locked>());
		m_OutsideUpdateQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Objects.OutsideConnection>());
		m_WaitingPassengersQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<AccessLane>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<TaxiStand>(),
				ComponentType.ReadOnly<Waypoint>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<WaitingPassengers>() }
		});
		m_WaitingPassengersQuery2 = GetEntityQuery(ComponentType.ReadOnly<WaitingPassengers>(), ComponentType.Exclude<TaxiStand>(), ComponentType.Exclude<Waypoint>());
		m_PillarQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<ObjectGeometry>(),
				ComponentType.ReadOnly<PrefabRef>()
			},
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Game.Objects.UtilityObject>(),
				ComponentType.ReadOnly<Game.Objects.NetObject>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Pillar>() }
		});
		m_LegacyEfficiencyQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Buildings.BuildingEfficiency>());
		m_SignatureQuery = GetEntityQuery(ComponentType.ReadOnly<Building>(), ComponentType.ReadOnly<Game.Objects.UniqueObject>(), ComponentType.ReadOnly<Renter>(), ComponentType.Exclude<Game.Buildings.Park>(), ComponentType.Exclude<Signature>());
		m_SubObjectOwnerQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Game.Objects.Object>(),
				ComponentType.ReadOnly<Owner>()
			},
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Game.Creatures.CreatureSpawner>(),
				ComponentType.ReadOnly<Game.Tools.EditorContainer>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Vehicle>(),
				ComponentType.ReadOnly<Creature>()
			}
		});
		m_DangerLevelMissingQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Game.Events.Event>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Game.Events.WeatherPhenomenon>(),
				ComponentType.ReadOnly<WaterLevelChange>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Game.Events.DangerLevel>() }
		});
		m_MeshGroupQuery = GetEntityQuery(ComponentType.ReadOnly<Human>(), ComponentType.ReadOnly<MeshBatch>(), ComponentType.Exclude<MeshGroup>());
		m_ObjectSurfaceQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<ObjectGeometry>() },
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Building>(),
				ComponentType.ReadOnly<Creature>(),
				ComponentType.ReadOnly<Vehicle>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Game.Objects.Surface>() }
		}, new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<ObjectGeometry>() },
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Game.Objects.Surface>(),
				ComponentType.ReadOnly<Owner>()
			}
		}, new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Road>(),
				ComponentType.ReadOnly<Game.Net.Node>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Game.Objects.Surface>() }
		});
		m_UpdateFrameQuery = GetEntityQuery(ComponentType.ReadOnly<Plant>(), ComponentType.Exclude<UpdateFrame>());
		m_FenceQuery = GetEntityQuery(ComponentType.ReadOnly<LaneGeometry>(), ComponentType.ReadOnly<Game.Net.UtilityLane>(), ComponentType.Exclude<PseudoRandomSeed>(), ComponentType.Exclude<MeshColor>(), ComponentType.Exclude<UpdateFrame>());
		m_NetGeometrySectionQuery = GetEntityQuery(ComponentType.ReadOnly<NetGeometryData>(), ComponentType.Exclude<NetGeometrySection>());
		m_NetLaneArchetypeDataQuery = GetEntityQuery(ComponentType.ReadOnly<NetLaneData>(), ComponentType.Exclude<NetLaneArchetypeData>());
		m_PathfindUpdatedQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Owner>() },
			Any = new ComponentType[8]
			{
				ComponentType.ReadOnly<Game.Net.CarLane>(),
				ComponentType.ReadOnly<Game.Net.PedestrianLane>(),
				ComponentType.ReadOnly<Game.Net.TrackLane>(),
				ComponentType.ReadOnly<Game.Net.ParkingLane>(),
				ComponentType.ReadOnly<Game.Net.ConnectionLane>(),
				ComponentType.ReadOnly<Game.Routes.TransportStop>(),
				ComponentType.ReadOnly<Game.Routes.TakeoffLocation>(),
				ComponentType.ReadOnly<Game.Objects.SpawnLocation>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Game.Routes.MailBox>() }
		});
		m_RouteColorQuery = GetEntityQuery(ComponentType.ReadOnly<CurrentRoute>(), ComponentType.Exclude<Game.Routes.Color>());
		m_CitizenQuery = GetEntityQuery(ComponentType.ReadOnly<Citizen>());
		m_ServiceUpkeepQuery = GetEntityQuery(ComponentType.ReadOnly<CityServiceUpkeep>(), ComponentType.Exclude<OwnedVehicle>());
		m_MoveableBridgeQuery = GetEntityQuery(ComponentType.ReadOnly<Stack>(), ComponentType.ReadOnly<Pillar>(), ComponentType.ReadOnly<PointOfInterest>());
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

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (!m_BlockedLaneQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<BlockedLane>(m_BlockedLaneQuery);
		}
		if (!m_CarLaneQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<LaneFlow>(m_CarLaneQuery);
		}
		if (!m_BuildingEfficiencyQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<Efficiency>(m_BuildingEfficiencyQuery);
		}
		if (!m_PolicyQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<Policy>(m_PolicyQuery);
		}
		if (!m_CityModifierQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<CityModifier>(m_CityModifierQuery);
		}
		if (!m_ServiceDispatchQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<ServiceDispatch>(m_ServiceDispatchQuery);
		}
		if (!m_PathInformationQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<PathInformation>(m_PathInformationQuery);
		}
		if (!m_NodeGeometryQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<NodeGeometry>(m_NodeGeometryQuery);
		}
		if (!m_MeshBatchQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<MeshBatch>(m_MeshBatchQuery);
		}
		if (!m_RoutePolicyQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<Policy>(m_RoutePolicyQuery);
		}
		if (!m_RouteModifierQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<RouteModifier>(m_RouteModifierQuery);
		}
		if (!m_EdgeQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<Density>(m_EdgeQuery);
		}
		if (!m_StorageTaxQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.RemoveComponent<TaxPayer>(m_StorageTaxQuery);
		}
		if (!m_CityFeeQuery.IsEmptyIgnoreFilter)
		{
			ServiceFeeParameterData singleton = m_ServiceFeeParameterQuery.GetSingleton<ServiceFeeParameterData>();
			NativeArray<Entity> nativeArray = m_CityFeeQuery.ToEntityArray(Allocator.TempJob);
			for (int i = 0; i < nativeArray.Length; i++)
			{
				DynamicBuffer<ServiceFee> dynamicBuffer = base.EntityManager.AddBuffer<ServiceFee>(nativeArray[i]);
				foreach (ServiceFee defaultFee in singleton.GetDefaultFees())
				{
					dynamicBuffer.Add(defaultFee);
				}
			}
			nativeArray.Dispose();
		}
		if (!m_CityFeeQuery2.IsEmptyIgnoreFilter)
		{
			Entity singletonEntity = m_CityFeeQuery2.GetSingletonEntity();
			DynamicBuffer<ServiceFee> buffer = base.EntityManager.GetBuffer<ServiceFee>(singletonEntity);
			bool flag = false;
			for (int j = 0; j < buffer.Length; j++)
			{
				if (buffer[j].m_Resource == PlayerResource.Water)
				{
					flag = true;
				}
			}
			if (!flag)
			{
				ServiceFee elem = default(ServiceFee);
				elem.m_Resource = PlayerResource.Water;
				elem.m_Fee = elem.GetDefaultFee(elem.m_Resource);
				buffer.Add(elem);
			}
		}
		if (!m_OutsideGarbageQuery.IsEmptyIgnoreFilter)
		{
			NativeArray<Entity> nativeArray2 = m_OutsideGarbageQuery.ToEntityArray(Allocator.TempJob);
			for (int k = 0; k < nativeArray2.Length; k++)
			{
				Entity prefab = base.EntityManager.GetComponentData<PrefabRef>(nativeArray2[k]).m_Prefab;
				if (base.EntityManager.HasComponent<GarbageFacilityData>(prefab))
				{
					GarbageFacilityData componentData = base.EntityManager.GetComponentData<GarbageFacilityData>(prefab);
					if (base.EntityManager.TryGetBuffer(nativeArray2[k], isReadOnly: false, out DynamicBuffer<Game.Economy.Resources> buffer2))
					{
						EconomyUtils.SetResources(Resource.Garbage, buffer2, componentData.m_GarbageCapacity / 2);
					}
					if (!base.EntityManager.HasComponent<ServiceDispatch>(nativeArray2[k]))
					{
						base.EntityManager.AddBuffer<ServiceDispatch>(nativeArray2[k]);
					}
					if (!base.EntityManager.HasComponent<OwnedVehicle>(nativeArray2[k]))
					{
						base.EntityManager.AddBuffer<OwnedVehicle>(nativeArray2[k]);
					}
				}
			}
			nativeArray2.Dispose();
		}
		if (!m_OutsideFireStationQuery.IsEmptyIgnoreFilter)
		{
			NativeArray<Entity> nativeArray3 = m_OutsideFireStationQuery.ToEntityArray(Allocator.TempJob);
			for (int l = 0; l < nativeArray3.Length; l++)
			{
				Entity prefab2 = base.EntityManager.GetComponentData<PrefabRef>(nativeArray3[l]).m_Prefab;
				if (base.EntityManager.HasComponent<FireStationData>(prefab2))
				{
					base.EntityManager.GetComponentData<FireStationData>(prefab2);
					base.EntityManager.AddComponentData(nativeArray3[l], default(Game.Buildings.FireStation));
					if (!base.EntityManager.HasComponent<ServiceDispatch>(nativeArray3[l]))
					{
						base.EntityManager.AddBuffer<ServiceDispatch>(nativeArray3[l]);
					}
					if (!base.EntityManager.HasComponent<OwnedVehicle>(nativeArray3[l]))
					{
						base.EntityManager.AddBuffer<OwnedVehicle>(nativeArray3[l]);
					}
				}
			}
			nativeArray3.Dispose();
		}
		if (!m_OutsidePoliceStationQuery.IsEmptyIgnoreFilter)
		{
			NativeArray<Entity> nativeArray4 = m_OutsidePoliceStationQuery.ToEntityArray(Allocator.TempJob);
			for (int m = 0; m < nativeArray4.Length; m++)
			{
				Entity prefab3 = base.EntityManager.GetComponentData<PrefabRef>(nativeArray4[m]).m_Prefab;
				if (base.EntityManager.HasComponent<PoliceStationData>(prefab3))
				{
					PoliceStationData componentData2 = base.EntityManager.GetComponentData<PoliceStationData>(prefab3);
					base.EntityManager.AddComponentData(nativeArray4[m], new Game.Buildings.PoliceStation
					{
						m_PurposeMask = componentData2.m_PurposeMask
					});
					if (!base.EntityManager.HasComponent<ServiceDispatch>(nativeArray4[m]))
					{
						base.EntityManager.AddBuffer<ServiceDispatch>(nativeArray4[m]);
					}
					if (!base.EntityManager.HasComponent<OwnedVehicle>(nativeArray4[m]))
					{
						base.EntityManager.AddBuffer<OwnedVehicle>(nativeArray4[m]);
					}
				}
			}
			nativeArray4.Dispose();
		}
		if (!m_OutsideEfficiencyQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<Efficiency>(m_OutsideEfficiencyQuery);
		}
		if (!m_RouteInfoQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<RouteInfo>(m_RouteInfoQuery);
		}
		if (!m_CompanyProfitabilityQuery.IsEmptyIgnoreFilter)
		{
			NativeArray<Entity> nativeArray5 = m_CompanyProfitabilityQuery.ToEntityArray(Allocator.TempJob);
			for (int n = 0; n < nativeArray5.Length; n++)
			{
				base.EntityManager.AddComponentData(nativeArray5[n], new Profitability
				{
					m_Profitability = 127
				});
			}
			nativeArray5.Dispose();
		}
		if (!m_StorageQuery.IsEmptyIgnoreFilter)
		{
			NativeArray<Entity> nativeArray6 = m_StorageQuery.ToEntityArray(Allocator.TempJob);
			for (int num = 0; num < nativeArray6.Length; num++)
			{
				if (base.EntityManager.TryGetComponent<PrefabRef>(nativeArray6[num], out var component) && base.EntityManager.TryGetComponent<BuildingPropertyData>(component.m_Prefab, out var component2) && component2.m_AllowedStored != Resource.NoResource)
				{
					base.EntityManager.AddComponent<StorageProperty>(nativeArray6[num]);
				}
			}
			nativeArray6.Dispose();
		}
		if (!m_RouteBufferIndexQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<RouteBufferIndex>(m_RouteBufferIndexQuery);
		}
		if (!m_CurveElementQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<CurveElement>(m_CurveElementQuery);
		}
		if (!m_CitizenPrefabQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<PrefabRef>(m_CitizenPrefabQuery);
			NativeArray<Entity> nativeArray7 = m_CitizenPrefabQuery.ToEntityArray(Allocator.TempJob);
			for (int num2 = 0; num2 < nativeArray7.Length; num2++)
			{
				base.EntityManager.AddBuffer<RandomLocalizationIndex>(nativeArray7[num2]).Add(RandomLocalizationIndex.kNone);
			}
			nativeArray7.Dispose();
		}
		if (!m_CitizenNameQuery.IsEmptyIgnoreFilter)
		{
			NativeArray<Entity> nativeArray8 = m_CitizenNameQuery.ToEntityArray(Allocator.TempJob);
			for (int num3 = 0; num3 < nativeArray8.Length; num3++)
			{
				base.EntityManager.AddBuffer<RandomLocalizationIndex>(nativeArray8[num3]).Add(RandomLocalizationIndex.kNone);
			}
			nativeArray8.Dispose();
		}
		if (!m_HouseholdNameQuery.IsEmptyIgnoreFilter)
		{
			NativeArray<Entity> nativeArray9 = m_HouseholdNameQuery.ToEntityArray(Allocator.TempJob);
			for (int num4 = 0; num4 < nativeArray9.Length; num4++)
			{
				base.EntityManager.AddBuffer<RandomLocalizationIndex>(nativeArray9[num4]).Add(RandomLocalizationIndex.kNone);
			}
			nativeArray9.Dispose();
		}
		if (!m_DistrictNameQuery.IsEmptyIgnoreFilter)
		{
			NativeArray<Entity> nativeArray10 = m_DistrictNameQuery.ToEntityArray(Allocator.TempJob);
			for (int num5 = 0; num5 < nativeArray10.Length; num5++)
			{
				base.EntityManager.AddBuffer<RandomLocalizationIndex>(nativeArray10[num5]).Add(RandomLocalizationIndex.kNone);
			}
			nativeArray10.Dispose();
		}
		if (!m_AnimalNameQuery.IsEmptyIgnoreFilter)
		{
			NativeArray<Entity> nativeArray11 = m_AnimalNameQuery.ToEntityArray(Allocator.TempJob);
			for (int num6 = 0; num6 < nativeArray11.Length; num6++)
			{
				base.EntityManager.AddBuffer<RandomLocalizationIndex>(nativeArray11[num6]).Add(RandomLocalizationIndex.kNone);
			}
			nativeArray11.Dispose();
		}
		if (!m_HouseholdPetQuery.IsEmptyIgnoreFilter)
		{
			NativeArray<Entity> nativeArray12 = m_HouseholdPetQuery.ToEntityArray(Allocator.TempJob);
			for (int num7 = 0; num7 < nativeArray12.Length; num7++)
			{
				base.EntityManager.AddBuffer<RandomLocalizationIndex>(nativeArray12[num7]).Add(RandomLocalizationIndex.kNone);
			}
			nativeArray12.Dispose();
		}
		if (!m_RoadNameQuery.IsEmptyIgnoreFilter)
		{
			NativeArray<Entity> nativeArray13 = m_RoadNameQuery.ToEntityArray(Allocator.TempJob);
			for (int num8 = 0; num8 < nativeArray13.Length; num8++)
			{
				base.EntityManager.AddBuffer<RandomLocalizationIndex>(nativeArray13[num8]).Add(RandomLocalizationIndex.kNone);
			}
			nativeArray13.Dispose();
		}
		if (!m_ChirpRandomLocQuery.IsEmptyIgnoreFilter)
		{
			NativeArray<Entity> nativeArray14 = m_ChirpRandomLocQuery.ToEntityArray(Allocator.TempJob);
			for (int num9 = 0; num9 < nativeArray14.Length; num9++)
			{
				base.EntityManager.AddBuffer<RandomLocalizationIndex>(nativeArray14[num9]).Add(RandomLocalizationIndex.kNone);
			}
			nativeArray14.Dispose();
		}
		if (!m_LabelVertexQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<Game.Areas.LabelVertex>(m_LabelVertexQuery);
		}
		if (!m_RouteNumberQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<RouteNumber>(m_RouteNumberQuery);
		}
		if (!m_BlockerQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<Blocker>(m_BlockerQuery);
		}
		if (!m_CitizenPresenceQuery.IsEmptyIgnoreFilter)
		{
			NativeArray<Entity> nativeArray15 = m_CitizenPresenceQuery.ToEntityArray(Allocator.TempJob);
			for (int num10 = 0; num10 < nativeArray15.Length; num10++)
			{
				base.EntityManager.AddComponentData(nativeArray15[num10], new CitizenPresence
				{
					m_Presence = 128
				});
			}
			nativeArray15.Dispose();
		}
		if (!m_SubLaneQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<Game.Net.SubLane>(m_SubLaneQuery);
		}
		if (!m_SubObjectQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<Game.Objects.SubObject>(m_SubObjectQuery);
		}
		Context context = base.World.GetOrCreateSystemManaged<LoadGameSystem>().context;
		if (context.version < Version.netUpkeepCost && !m_NativeQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<Native>(m_NativeQuery);
		}
		if (!m_GuestVehicleQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<GuestVehicle>(m_GuestVehicleQuery);
		}
		if (!m_TravelPurposeQuery.IsEmptyIgnoreFilter)
		{
			NativeArray<Entity> nativeArray16 = m_TravelPurposeQuery.ToEntityArray(Allocator.TempJob);
			for (int num11 = 0; num11 < nativeArray16.Length; num11++)
			{
				TravelPurpose componentData3 = base.EntityManager.GetComponentData<TravelPurpose>(nativeArray16[num11]);
				if ((componentData3.m_Purpose == Game.Citizens.Purpose.GoingToWork || componentData3.m_Purpose == Game.Citizens.Purpose.Working) && !base.EntityManager.HasComponent<Worker>(nativeArray16[num11]))
				{
					base.EntityManager.RemoveComponent<TravelPurpose>(nativeArray16[num11]);
				}
				else if ((componentData3.m_Purpose == Game.Citizens.Purpose.GoingToSchool || componentData3.m_Purpose == Game.Citizens.Purpose.Studying) && !base.EntityManager.HasComponent<Game.Citizens.Student>(nativeArray16[num11]))
				{
					base.EntityManager.RemoveComponent<TravelPurpose>(nativeArray16[num11]);
				}
			}
			nativeArray16.Dispose();
		}
		if (!m_TreeEffectQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<EnabledEffect>(m_TreeEffectQuery);
		}
		if (!m_TakeoffLocationQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<Game.Routes.TakeoffLocation>(m_TakeoffLocationQuery);
		}
		if (!m_LeisureQuery.IsEmptyIgnoreFilter)
		{
			NativeArray<Entity> nativeArray17 = m_LeisureQuery.ToEntityArray(Allocator.TempJob);
			NativeArray<PrefabRef> nativeArray18 = m_LeisureQuery.ToComponentDataArray<PrefabRef>(Allocator.TempJob);
			for (int num12 = 0; num12 < nativeArray18.Length; num12++)
			{
				if (base.EntityManager.HasComponent<LeisureProviderData>(nativeArray18[num12].m_Prefab))
				{
					base.EntityManager.AddComponent<Game.Buildings.LeisureProvider>(nativeArray17[num12]);
				}
			}
			nativeArray18.Dispose();
			nativeArray17.Dispose();
		}
		if (!m_TransportDepotQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<Game.Buildings.TransportDepot>(m_TransportDepotQuery);
		}
		if (!m_ServiceUsageQuery.IsEmptyIgnoreFilter)
		{
			NativeArray<Entity> nativeArray19 = m_ServiceUsageQuery.ToEntityArray(Allocator.TempJob);
			for (int num13 = 0; num13 < nativeArray19.Length; num13++)
			{
				base.EntityManager.AddComponentData(nativeArray19[num13], new ServiceUsage
				{
					m_Usage = 1f
				});
			}
			nativeArray19.Dispose();
		}
		if (!m_OutsideSellerQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<ResourceSeller>(m_OutsideSellerQuery);
		}
		if (!m_LoadingResourcesQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<LoadingResources>(m_LoadingResourcesQuery);
		}
		if (!m_CompanyVehicleQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<OwnedVehicle>(m_CompanyVehicleQuery);
		}
		if (m_LoadGameSystem.context.version < Version.pathfindAccessRestriction && !m_LaneRestrictionQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<PathfindUpdated>(m_LaneRestrictionQuery);
		}
		if (!m_LaneOverlapQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<LaneOverlap>(m_LaneOverlapQuery);
		}
		if (!m_DispatchedRequestQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<DispatchedRequest>(m_DispatchedRequestQuery);
		}
		if (!m_HomelessShelterQuery.IsEmptyIgnoreFilter)
		{
			NativeArray<Entity> nativeArray20 = m_HomelessShelterQuery.ToEntityArray(Allocator.TempJob);
			for (int num14 = 0; num14 < nativeArray20.Length; num14++)
			{
				base.EntityManager.AddBuffer<Renter>(nativeArray20[num14]);
			}
			nativeArray20.Dispose();
		}
		if (!m_QueueQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<Queue>(m_QueueQuery);
		}
		if (!m_BoneHistoryQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<BoneHistory>(m_BoneHistoryQuery);
		}
		if (m_LoadGameSystem.context.version < Version.currentVehicleRefactoring && !m_UnspawnedQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<Unspawned>(m_UnspawnedQuery);
		}
		if (m_LoadGameSystem.context.version < Version.areaLaneComponent)
		{
			if (!m_ConnectionLaneQuery.IsEmptyIgnoreFilter)
			{
				base.EntityManager.RemoveComponent<NodeLane>(m_ConnectionLaneQuery);
			}
			if (!m_AreaLaneQuery.IsEmptyIgnoreFilter)
			{
				base.EntityManager.AddComponent<Updated>(m_AreaLaneQuery);
			}
		}
		if (m_LoadGameSystem.context.version < Version.officePropertyComponent && !m_OfficeQuery.IsEmptyIgnoreFilter)
		{
			NativeArray<Entity> nativeArray21 = m_OfficeQuery.ToEntityArray(Allocator.TempJob);
			for (int num15 = 0; num15 < nativeArray21.Length; num15++)
			{
				if (base.EntityManager.TryGetComponent<PrefabRef>(nativeArray21[num15], out var component3) && base.EntityManager.TryGetComponent<BuildingPropertyData>(component3.m_Prefab, out var component4) && EconomyUtils.IsOfficeResource(component4.m_AllowedManufactured))
				{
					base.EntityManager.AddComponent<OfficeProperty>(nativeArray21[num15]);
				}
			}
			nativeArray21.Dispose();
		}
		if (!m_PassengerTransportQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<PassengerTransport>(m_PassengerTransportQuery);
		}
		if (!m_ObjectColorQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<Game.Objects.Color>(m_ObjectColorQuery);
		}
		if (!m_OutsideConnectionQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<Game.Objects.OutsideConnection>(m_OutsideConnectionQuery);
		}
		if (!m_NetConditionQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<NetCondition>(m_NetConditionQuery);
		}
		if (m_LoadGameSystem.context.version < Version.netPollutionAccumulation && !m_NetPollutionQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<Game.Net.Pollution>(m_NetPollutionQuery);
		}
		if (!m_TrafficSpawnerQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<Game.Buildings.TrafficSpawner>(m_TrafficSpawnerQuery);
		}
		if (!m_AreaExpandQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<Expand>(m_AreaExpandQuery);
		}
		if (!m_EmissiveQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<LightState>(m_EmissiveQuery);
			base.EntityManager.AddComponent<Emissive>(m_EmissiveQuery);
		}
		if (!m_TrainBogieFrameQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<TrainBogieFrame>(m_TrainBogieFrameQuery);
		}
		if (!m_ProcessingTradeCostQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<TradeCost>(m_ProcessingTradeCostQuery);
		}
		if (context.version < Version.editorContainerFix && !m_EditorContainerQuery.IsEmptyIgnoreFilter)
		{
			if (context.purpose == Colossal.Serialization.Entities.Purpose.LoadMap)
			{
				base.EntityManager.AddComponent<CullingInfo>(m_EditorContainerQuery);
				base.EntityManager.AddComponent<Game.Tools.EditorContainer>(m_EditorContainerQuery);
			}
			else
			{
				base.EntityManager.DestroyEntity(m_EditorContainerQuery);
			}
		}
		if (!m_StorageConditionQuery.IsEmptyIgnoreFilter && context.version < Version.storageConditionReset)
		{
			NativeArray<Entity> nativeArray22 = m_StorageConditionQuery.ToEntityArray(Allocator.TempJob);
			for (int num16 = 0; num16 < nativeArray22.Length; num16++)
			{
				if (base.EntityManager.TryGetComponent<PropertyRenter>(nativeArray22[num16], out var component5) && base.EntityManager.TryGetComponent<BuildingCondition>(component5.m_Property, out var component6) && base.EntityManager.TryGetBuffer(nativeArray22[num16], isReadOnly: false, out DynamicBuffer<Game.Economy.Resources> buffer3))
				{
					component6.m_Condition = 0;
					base.EntityManager.SetComponentData(component5.m_Property, component6);
					EconomyUtils.SetResources(Resource.Money, buffer3, 0);
				}
			}
			nativeArray22.Dispose();
		}
		if (!m_LaneColorQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<LaneColor>(m_LaneColorQuery);
		}
		if (!m_CompanyNotificationQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<CompanyNotifications>(m_CompanyNotificationQuery);
		}
		if (!m_PlantQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<Plant>(m_PlantQuery);
		}
		if (!m_CityPopulationQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<Population>(m_CityPopulationQuery);
		}
		if (!m_CityTourismQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<Tourism>(m_CityTourismQuery);
		}
		if (!m_BuildingNotificationQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<BuildingNotifications>(m_BuildingNotificationQuery);
		}
		if (context.version < Version.laneElevation)
		{
			if (!m_LaneElevationQuery.IsEmptyIgnoreFilter)
			{
				NativeArray<Entity> nativeArray23 = m_LaneElevationQuery.ToEntityArray(Allocator.TempJob);
				Game.Net.Elevation componentData5 = default(Game.Net.Elevation);
				for (int num17 = 0; num17 < nativeArray23.Length; num17++)
				{
					Entity entity = nativeArray23[num17];
					Entity owner = base.EntityManager.GetComponentData<Owner>(entity).m_Owner;
					if (base.EntityManager.TryGetComponent<Game.Objects.Transform>(owner, out var component7))
					{
						Curve componentData4 = base.EntityManager.GetComponentData<Curve>(entity);
						componentData5.m_Elevation.x = componentData4.m_Bezier.a.y - component7.m_Position.y;
						componentData5.m_Elevation.y = componentData4.m_Bezier.d.y - component7.m_Position.y;
						base.EntityManager.RemoveComponent<NodeLane>(entity);
						bool2 @bool = math.abs(componentData5.m_Elevation) >= 0.1f;
						if (math.any(@bool))
						{
							componentData5.m_Elevation = math.select(float.MinValue, componentData5.m_Elevation, @bool);
							base.EntityManager.AddComponentData(entity, componentData5);
						}
					}
				}
				nativeArray23.Dispose();
			}
			if (!m_AreaElevationQuery.IsEmptyIgnoreFilter)
			{
				NativeArray<Entity> nativeArray24 = m_AreaElevationQuery.ToEntityArray(Allocator.TempJob);
				for (int num18 = 0; num18 < nativeArray24.Length; num18++)
				{
					Entity entity2 = nativeArray24[num18];
					DynamicBuffer<Game.Areas.Node> buffer4 = base.EntityManager.GetBuffer<Game.Areas.Node>(entity2);
					if (base.EntityManager.HasComponent<Game.Areas.Space>(entity2) && base.EntityManager.TryGetComponent<Owner>(entity2, out var component8) && base.EntityManager.TryGetComponent<Game.Objects.Transform>(component8.m_Owner, out var component9))
					{
						for (int num19 = 0; num19 < buffer4.Length; num19++)
						{
							ref Game.Areas.Node reference = ref buffer4.ElementAt(num19);
							reference.m_Elevation = reference.m_Position.y - component9.m_Position.y;
							reference.m_Elevation = math.select(float.MinValue, reference.m_Elevation, math.abs(reference.m_Elevation) >= 0.1f);
						}
					}
					else
					{
						for (int num20 = 0; num20 < buffer4.Length; num20++)
						{
							buffer4.ElementAt(num20).m_Elevation = float.MinValue;
						}
					}
				}
				nativeArray24.Dispose();
			}
		}
		if (!m_BuildingLotQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<Game.Buildings.Lot>(m_BuildingLotQuery);
		}
		if (!m_AreaTerrainQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<Game.Areas.Terrain>(m_AreaTerrainQuery);
		}
		if (!m_OwnedVehicleQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<OwnedVehicle>(m_OwnedVehicleQuery);
		}
		if (context.version < Version.laneSubFlow)
		{
			if (!m_EdgeMappingQuery.IsEmptyIgnoreFilter)
			{
				base.EntityManager.AddComponent<EdgeMapping>(m_EdgeMappingQuery);
			}
			if (!m_SubFlowQuery.IsEmptyIgnoreFilter)
			{
				base.EntityManager.AddComponent<SubFlow>(m_SubFlowQuery);
			}
		}
		if (!m_PointOfInterestQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<PointOfInterest>(m_PointOfInterestQuery);
		}
		if (m_LoadGameSystem.context.version < Version.buildableArea && !m_BuildableAreaQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<Updated>(m_BuildableAreaQuery);
		}
		if (context.version < Version.extractorSubAreas && !m_SubAreaQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<Game.Areas.SubArea>(m_SubAreaQuery);
		}
		if (context.version < Version.enableableCrimeVictim && !m_CrimeVictimQuery.IsEmptyIgnoreFilter)
		{
			NativeArray<Entity> nativeArray25 = m_CrimeVictimQuery.ToEntityArray(Allocator.TempJob);
			base.EntityManager.AddComponent<CrimeVictim>(m_CrimeVictimQuery);
			for (int num21 = 0; num21 < nativeArray25.Length; num21++)
			{
				base.EntityManager.SetComponentEnabled<CrimeVictim>(nativeArray25[num21], value: false);
			}
			nativeArray25.Dispose();
		}
		if (context.version < Version.enableableCrimeVictim && !m_ArrivedQuery.IsEmptyIgnoreFilter)
		{
			NativeArray<Entity> nativeArray26 = m_ArrivedQuery.ToEntityArray(Allocator.TempJob);
			base.EntityManager.AddComponent<Arrived>(m_ArrivedQuery);
			for (int num22 = 0; num22 < nativeArray26.Length; num22++)
			{
				base.EntityManager.SetComponentEnabled<Arrived>(nativeArray26[num22], value: false);
			}
			nativeArray26.Dispose();
		}
		if (context.version < Version.enableableCrimeVictim && !m_MailSenderQuery.IsEmptyIgnoreFilter)
		{
			NativeArray<Entity> nativeArray27 = m_MailSenderQuery.ToEntityArray(Allocator.TempJob);
			base.EntityManager.AddComponent<MailSender>(m_MailSenderQuery);
			for (int num23 = 0; num23 < nativeArray27.Length; num23++)
			{
				base.EntityManager.SetComponentEnabled<MailSender>(nativeArray27[num23], value: false);
			}
			nativeArray27.Dispose();
		}
		if (context.version < Version.enableableCrimeVictim && !m_CarKeeperQuery.IsEmptyIgnoreFilter)
		{
			NativeArray<Entity> nativeArray28 = m_CarKeeperQuery.ToEntityArray(Allocator.TempJob);
			base.EntityManager.AddComponent<CarKeeper>(m_CarKeeperQuery);
			for (int num24 = 0; num24 < nativeArray28.Length; num24++)
			{
				base.EntityManager.SetComponentEnabled<CarKeeper>(nativeArray28[num24], value: false);
			}
			nativeArray28.Dispose();
		}
		if (context.version < Version.findJobOptimize && !m_NeedAddHasJobSeekerQuery.IsEmpty)
		{
			NativeArray<Entity> nativeArray29 = m_NeedAddHasJobSeekerQuery.ToEntityArray(Allocator.TempJob);
			base.EntityManager.AddComponent<HasJobSeeker>(m_NeedAddHasJobSeekerQuery);
			for (int num25 = 0; num25 < nativeArray29.Length; num25++)
			{
				base.EntityManager.SetComponentEnabled<HasJobSeeker>(nativeArray29[num25], value: false);
			}
			nativeArray29.Dispose();
		}
		if (!m_AgeGroupQuery.IsEmptyIgnoreFilter)
		{
			NativeArray<Entity> nativeArray30 = m_AgeGroupQuery.ToEntityArray(Allocator.TempJob);
			for (int num26 = 0; num26 < nativeArray30.Length; num26++)
			{
				Entity entity3 = nativeArray30[num26];
				Citizen componentData6 = base.EntityManager.GetComponentData<Citizen>(entity3);
				CitizenAge age;
				if (base.EntityManager.HasComponent<Child>(entity3))
				{
					age = CitizenAge.Child;
					base.EntityManager.RemoveComponent<Child>(entity3);
				}
				else if (base.EntityManager.HasComponent<Teen>(entity3))
				{
					age = CitizenAge.Teen;
					base.EntityManager.RemoveComponent<Teen>(entity3);
				}
				else if (base.EntityManager.HasComponent<Adult>(entity3))
				{
					age = CitizenAge.Adult;
					base.EntityManager.RemoveComponent<Adult>(entity3);
				}
				else
				{
					age = CitizenAge.Elderly;
					base.EntityManager.RemoveComponent<Elderly>(entity3);
				}
				componentData6.SetAge(age);
				base.EntityManager.SetComponentData(entity3, componentData6);
			}
			nativeArray30.Dispose();
		}
		if (context.version < Version.prefabRefAbuseFix)
		{
			NativeArray<Entity> nativeArray31 = m_PrefabRefQuery.ToEntityArray(Allocator.TempJob);
			NativeArray<PrefabRef> nativeArray32 = m_PrefabRefQuery.ToComponentDataArray<PrefabRef>(Allocator.TempJob);
			for (int num27 = 0; num27 < nativeArray32.Length; num27++)
			{
				if (!base.EntityManager.HasComponent<PrefabData>(nativeArray32[num27]))
				{
					base.EntityManager.DestroyEntity(nativeArray31[num27]);
				}
			}
			nativeArray31.Dispose();
			nativeArray32.Dispose();
		}
		if (!m_LabelMaterialQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<LabelMaterial>(m_LabelMaterialQuery);
		}
		if (!m_ArrowMaterialQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<ArrowMaterial>(m_ArrowMaterialQuery);
		}
		if (context.version < Version.trainRouteSecondaryModelFix && !m_VehicleModelQuery.IsEmptyIgnoreFilter)
		{
			NativeArray<Entity> nativeArray33 = m_VehicleModelQuery.ToEntityArray(Allocator.TempJob);
			for (int num28 = 0; num28 < nativeArray33.Length; num28++)
			{
				if (base.EntityManager.TryGetComponent<VehicleModel>(nativeArray33[num28], out var component10))
				{
					if (component10.m_SecondaryPrefab != Entity.Null && base.EntityManager.HasComponent<TrainEngineData>(component10.m_PrimaryPrefab))
					{
						component10.m_SecondaryPrefab = Entity.Null;
						base.EntityManager.SetComponentData(nativeArray33[num28], component10);
					}
				}
				else
				{
					base.EntityManager.AddComponentData(nativeArray33[num28], default(VehicleModel));
				}
			}
			nativeArray33.Dispose();
		}
		if (context.version < Version.enableableLocked && !m_LockedQuery.IsEmptyIgnoreFilter)
		{
			NativeArray<Entity> nativeArray34 = m_LockedQuery.ToEntityArray(Allocator.TempJob);
			for (int num29 = 0; num29 < nativeArray34.Length; num29++)
			{
				if (!base.EntityManager.HasComponent<Locked>(nativeArray34[num29]))
				{
					base.EntityManager.AddComponent<Locked>(nativeArray34[num29]);
					base.EntityManager.SetComponentEnabled<Locked>(nativeArray34[num29], value: false);
				}
			}
			nativeArray34.Dispose();
		}
		if (context.version < Version.pedestrianBorderCost && !m_OutsideUpdateQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<Updated>(m_OutsideUpdateQuery);
		}
		if (context.version < Version.passengerWaitTimeCost)
		{
			if (!m_WaitingPassengersQuery.IsEmptyIgnoreFilter)
			{
				base.EntityManager.AddComponent<WaitingPassengers>(m_WaitingPassengersQuery);
			}
			if (!m_WaitingPassengersQuery2.IsEmptyIgnoreFilter)
			{
				base.EntityManager.RemoveComponent<WaitingPassengers>(m_WaitingPassengersQuery2);
			}
		}
		if (context.version < Version.pillarTerrainModification && !m_PillarQuery.IsEmptyIgnoreFilter)
		{
			NativeArray<Entity> nativeArray35 = m_PillarQuery.ToEntityArray(Allocator.TempJob);
			NativeArray<PrefabRef> nativeArray36 = m_PillarQuery.ToComponentDataArray<PrefabRef>(Allocator.TempJob);
			for (int num30 = 0; num30 < nativeArray35.Length; num30++)
			{
				if (base.EntityManager.HasComponent<PillarData>(nativeArray36[num30].m_Prefab))
				{
					base.EntityManager.AddComponent<Pillar>(nativeArray35[num30]);
				}
			}
			nativeArray35.Dispose();
			nativeArray36.Dispose();
		}
		if (context.version < Version.buildingEfficiencyRework && !m_LegacyEfficiencyQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<Efficiency>(m_LegacyEfficiencyQuery);
			base.EntityManager.RemoveComponent<Game.Buildings.BuildingEfficiency>(m_LegacyEfficiencyQuery);
			NativeArray<Entity> nativeArray37 = m_LegacyEfficiencyQuery.ToEntityArray(Allocator.TempJob);
			for (int num31 = 0; num31 < nativeArray37.Length; num31++)
			{
				if (base.EntityManager.TryGetComponent<PrefabRef>(nativeArray37[num31], out var component11) && base.EntityManager.TryGetComponent<ConsumptionData>(component11, out var component12) && component12.m_TelecomNeed > 0f)
				{
					base.EntityManager.AddComponent<TelecomConsumer>(nativeArray37[num31]);
				}
			}
			nativeArray37.Dispose();
		}
		if (context.version < Version.signatureBuildingComponent && !m_SignatureQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<Signature>(m_SignatureQuery);
		}
		if (context.version < Version.missingOwnerFix && !m_SubObjectOwnerQuery.IsEmptyIgnoreFilter)
		{
			int num32 = 0;
			NativeArray<Entity> nativeArray38 = m_SubObjectOwnerQuery.ToEntityArray(Allocator.TempJob);
			for (int num33 = 0; num33 < nativeArray38.Length; num33++)
			{
				if (base.EntityManager.TryGetComponent<Owner>(nativeArray38[num33], out var component13) && !base.EntityManager.Exists(component13.m_Owner))
				{
					base.EntityManager.DestroyEntity(nativeArray38[num33]);
					num32++;
				}
			}
			nativeArray38.Dispose();
			if (num32 != 0)
			{
				UnityEngine.Debug.LogWarning($"Destroyed {num32} entities with missing owners");
			}
		}
		if (context.version < Version.dangerLevel && !m_DangerLevelMissingQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<Game.Events.DangerLevel>(m_DangerLevelMissingQuery);
		}
		if (context.version < Version.meshGroups && !m_MeshGroupQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<MeshGroup>(m_MeshGroupQuery);
		}
		if (context.version < Version.surfaceStates && !m_ObjectSurfaceQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<Game.Objects.Surface>(m_ObjectSurfaceQuery);
		}
		if (context.version < Version.meshColors && !m_MeshColorQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<MeshColor>(m_MeshColorQuery);
		}
		if (context.version < Version.plantUpdateFrame && !m_UpdateFrameQuery.IsEmptyIgnoreFilter)
		{
			NativeArray<Entity> nativeArray39 = m_UpdateFrameQuery.ToEntityArray(Allocator.TempJob);
			for (int num34 = 0; num34 < nativeArray39.Length; num34++)
			{
				base.EntityManager.AddSharedComponent(nativeArray39[num34], new UpdateFrame((uint)(num34 & 0xF)));
			}
			nativeArray39.Dispose();
		}
		if (context.version < Version.fenceColors && !m_PseudoRandomSeedQuery.IsEmptyIgnoreFilter)
		{
			NativeArray<Entity> nativeArray40 = m_PseudoRandomSeedQuery.ToEntityArray(Allocator.TempJob);
			Unity.Mathematics.Random random = new Unity.Mathematics.Random(math.max(1u, (uint)DateTime.Now.Ticks));
			for (int num35 = 0; num35 < nativeArray40.Length; num35++)
			{
				base.EntityManager.AddComponentData(nativeArray40[num35], new PseudoRandomSeed(ref random));
			}
			nativeArray40.Dispose();
		}
		if (context.version < Version.fenceColors && !m_FenceQuery.IsEmptyIgnoreFilter)
		{
			NativeArray<Entity> nativeArray41 = m_FenceQuery.ToEntityArray(Allocator.TempJob);
			for (int num36 = 0; num36 < nativeArray41.Length; num36++)
			{
				Entity entity4 = nativeArray41[num36];
				if (!base.EntityManager.TryGetComponent<PrefabRef>(entity4, out var component14))
				{
					continue;
				}
				if (base.EntityManager.TryGetComponent<NetLaneData>(component14.m_Prefab, out var component15) && (component15.m_Flags & LaneFlags.PseudoRandom) != 0)
				{
					PseudoRandomSeed component16 = default(PseudoRandomSeed);
					Entity entity5 = entity4;
					Owner component17;
					while (base.EntityManager.TryGetComponent<Owner>(entity5, out component17) && !base.EntityManager.TryGetComponent<PseudoRandomSeed>(component17.m_Owner, out component16))
					{
						entity5 = component17.m_Owner;
					}
					base.EntityManager.AddComponentData(entity4, component16);
					base.EntityManager.AddComponent<MeshColor>(entity4);
				}
				if (base.EntityManager.HasComponent<PlantData>(component14.m_Prefab))
				{
					base.EntityManager.AddComponent<Plant>(entity4);
					base.EntityManager.AddSharedComponent(entity4, new UpdateFrame((uint)(num36 & 0xF)));
				}
			}
			nativeArray41.Dispose();
		}
		if (context.version < Version.obsoleteNetPrefabs && !m_NetGeometrySectionQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<NetGeometryComposition>(m_NetGeometrySectionQuery);
			base.EntityManager.AddComponent<NetGeometrySection>(m_NetGeometrySectionQuery);
		}
		if (context.version < Version.obsoleteNetLanePrefabs && !m_NetLaneArchetypeDataQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<NetLaneArchetypeData>(m_NetLaneArchetypeDataQuery);
		}
		if (context.version < Version.pathfindRestrictions && !m_PathfindUpdatedQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<PathfindUpdated>(m_PathfindUpdatedQuery);
		}
		if (context.version < Version.cacheRouteColors && !m_RouteColorQuery.IsEmptyIgnoreFilter)
		{
			NativeArray<Entity> nativeArray42 = m_RouteColorQuery.ToEntityArray(Allocator.TempJob);
			for (int num37 = 0; num37 < nativeArray42.Length; num37++)
			{
				if (base.EntityManager.TryGetComponent<CurrentRoute>(nativeArray42[num37], out var component18) && base.EntityManager.TryGetComponent<Game.Routes.Color>(component18.m_Route, out var component19))
				{
					base.EntityManager.AddComponentData(nativeArray42[num37], component19);
				}
			}
			nativeArray42.Dispose();
		}
		if (context.version < Version.deathWaveMitigation && !m_CitizenQuery.IsEmptyIgnoreFilter)
		{
			Unity.Mathematics.Random random2 = RandomSeed.Next().GetRandom(0);
			NativeArray<Entity> nativeArray43 = m_CitizenQuery.ToEntityArray(Allocator.TempJob);
			TimeData singleton2 = GetEntityQuery(ComponentType.ReadOnly<TimeData>()).GetSingleton<TimeData>();
			uint frameIndex = base.World.GetOrCreateSystemManaged<SimulationSystem>().frameIndex;
			int day = TimeSystem.GetDay(frameIndex, __query_1938549531_0.GetSingleton<TimeData>());
			for (int num38 = 0; num38 < nativeArray43.Length; num38++)
			{
				Citizen component21;
				if (base.EntityManager.TryGetComponent<HealthProblem>(nativeArray43[num38], out var component20) && CitizenUtils.IsDead(component20) && (component20.m_HealthcareRequest == Entity.Null || !base.EntityManager.HasComponent<Dispatched>(component20.m_HealthcareRequest)))
				{
					base.EntityManager.AddComponent<Deleted>(nativeArray43[num38]);
				}
				else if (base.EntityManager.TryGetComponent<Citizen>(nativeArray43[num38], out component21) && component21.GetAgeInDays(frameIndex, singleton2) >= (float)AgingSystem.GetElderAgeLimitInDays() && random2.NextInt(100) > 1)
				{
					switch (random2.NextInt(3))
					{
					case 0:
						component21.m_BirthDay = (short)(day - 54 + random2.NextInt(18));
						break;
					case 1:
						component21.m_BirthDay = (short)(day - 69 + random2.NextInt(21));
						break;
					default:
						component21.m_BirthDay = (short)(day - 84 + random2.NextInt(21));
						break;
					}
					component21.SetAge(CitizenAge.Adult);
					base.EntityManager.SetComponentData(nativeArray43[num38], component21);
				}
			}
			nativeArray43.Dispose();
		}
		if (!m_ServiceUpkeepQuery.IsEmptyIgnoreFilter)
		{
			base.EntityManager.AddComponent<OwnedVehicle>(m_ServiceUpkeepQuery);
		}
		if (context.format.Has(FormatTags.StandingLegOffset) || m_MoveableBridgeQuery.IsEmptyIgnoreFilter)
		{
			return;
		}
		NativeArray<Entity> nativeArray44 = m_MoveableBridgeQuery.ToEntityArray(Allocator.TempJob);
		for (int num39 = 0; num39 < nativeArray44.Length; num39++)
		{
			if (base.EntityManager.TryGetComponent<Stack>(nativeArray44[num39], out var component22) && base.EntityManager.TryGetComponent<PrefabRef>(nativeArray44[num39], out var component23) && base.EntityManager.TryGetComponent<ObjectGeometryData>(component23.m_Prefab, out var component24))
			{
				component22.m_Range.max = math.max(component22.m_Range.max, component24.m_Bounds.max.y);
				base.EntityManager.SetComponentData(nativeArray44[num39], component22);
			}
		}
		nativeArray44.Dispose();
	}
```


## Nested types

- `Game.Serialization.RequiredComponentSystem+TypeHandle`  

