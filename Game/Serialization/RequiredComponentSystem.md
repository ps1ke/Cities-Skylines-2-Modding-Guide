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
public RequiredComponentSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
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


## Nested types

- `Game.Serialization.RequiredComponentSystem+TypeHandle`  

