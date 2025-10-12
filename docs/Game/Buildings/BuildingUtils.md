# Game.Buildings.BuildingUtils

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** class static public  

**Base:** `System.Object`  

## Fields

- `public static const System.Single MAX_ROAD_CONNECTION_DISTANCE`  
- `public static const System.Single GEOMETRY_SIZE_OFFSET`  
- `public static const System.Single MIN_BUILDING_HEIGHT`  
- `public static const System.Single MIN_CONSTRUCTION_HEIGHT`  
- `public static const System.Single RANDOM_CONSTRUCTION_HEIGHT`  
- `public static const System.Single COLLAPSE_ACCELERATION`  

## Methods

- `public static ApplyModifier(System.Single& value, Unity.Entities.DynamicBuffer<Game.Buildings.BuildingModifier> modifiers, Game.Buildings.BuildingModifierType type) : System.Void`  
- `public static ApproximateEfficiencyFactors(System.Single targetEfficiency, Unity.Mathematics.float2 weights) : Unity.Mathematics.float2`  
- `public static ApproximateEfficiencyFactors(System.Single targetEfficiency, Unity.Mathematics.float4 weights) : Unity.Mathematics.float4`  
- `public static CalculateCorners(Game.Objects.Transform transform, Unity.Mathematics.int2 lotSize) : Colossal.Mathematics.Quad3`  
- `public static CalculateCorners(Unity.Mathematics.float3 position, Unity.Mathematics.quaternion rotation, Unity.Mathematics.float2 halfLotSize) : Colossal.Mathematics.Quad3`  
- `public static CalculateFrontPosition(Game.Objects.Transform transform, System.Int32 lotDepth) : Unity.Mathematics.float3`  
- `public static CalculateLotInfo(Unity.Mathematics.float2 extents, Game.Objects.Transform transform, Game.Objects.Elevation elevation, Game.Buildings.Lot lot, Game.Prefabs.PrefabRef prefabRef, Unity.Entities.DynamicBuffer<Game.Buildings.InstalledUpgrade> upgrades, Unity.Entities.ComponentLookup<Game.Objects.Transform> transforms, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabRefs, Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> objectGeometryDatas, Unity.Entities.ComponentLookup<Game.Prefabs.BuildingTerraformData> buildingTerraformDatas, Unity.Entities.ComponentLookup<Game.Prefabs.BuildingExtensionData> buildingExtensionDatas, System.Boolean defaultNoSmooth, System.Boolean& hasExtensionLots) : Game.Buildings.BuildingUtils+LotInfo`  
- `public static CalculateUpgradeRangeValues(Unity.Mathematics.quaternion rotation, Game.Prefabs.BuildingData ownerBuildingData, Game.Prefabs.BuildingData buildingData, Game.Prefabs.ServiceUpgradeData serviceUpgradeData, Unity.Mathematics.float3& forward, System.Single& width, System.Single& length, System.Single& roundness, System.Boolean& circular) : System.Void`  
- `public static CheckOption(Game.Buildings.Building building, Game.Buildings.BuildingOption option) : System.Boolean`  
- `public static CheckOption(Game.Buildings.InstalledUpgrade installedUpgrade, Game.Buildings.BuildingOption option) : System.Boolean`  
- `public static GetAddress(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Unity.Entities.Entity& road, System.Int32& number) : System.Boolean`  
- `public static GetAddress(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Unity.Entities.Entity edge, System.Single curvePos, Unity.Entities.Entity& road, System.Int32& number) : System.Boolean`  
- `public static GetAreaType(Unity.Entities.Entity buildPrefab, Unity.Entities.ComponentLookup`1[[Game.Prefabs.SpawnableBuildingData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& spawnableBuildingDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ZoneData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& zoneDatas) : Game.Zones.AreaType`  
- `public static GetCollapseHeight(System.Single time) : System.Single`  
- `public static GetCollapseTime(System.Single height) : System.Single`  
- `public static GetEfficiency(Unity.Entities.BufferAccessor<Game.Buildings.Efficiency> bufferAccessor, System.Int32 i) : System.Single`  
- `public static GetEfficiency(Unity.Entities.Entity entity, Unity.Entities.BufferLookup`1[[Game.Buildings.Efficiency, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& bufferLookup) : System.Single`  
- `public static GetEfficiency(Unity.Entities.DynamicBuffer<Game.Buildings.Efficiency> buffer) : System.Single`  
- `public static GetEfficiency(System.Span<System.Single> factors) : System.Single`  
- `public static GetEfficiency(System.Byte rawValue) : System.Single`  
- `public static GetEfficiencyFactors(Unity.Entities.DynamicBuffer<Game.Buildings.Efficiency> buffer, System.Span<System.Single> factors) : System.Void`  
- `public static GetHouseholdHomeBuilding(Unity.Entities.Entity householdEntity, Unity.Entities.ComponentLookup`1[[Game.Buildings.PropertyRenter, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& propertyRenters, Unity.Entities.ComponentLookup`1[[Game.Citizens.HomelessHousehold, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& homelessHouseholds) : Unity.Entities.Entity`  
- `public static GetHouseholdHomeBuilding(Unity.Entities.Entity householdEntity, Unity.Entities.ComponentLookup`1[[Game.Buildings.PropertyRenter, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& propertyRenters, Unity.Entities.ComponentLookup`1[[Game.Citizens.HomelessHousehold, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& homelessHouseholds, Unity.Entities.ComponentLookup`1[[Game.Citizens.TouristHousehold, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& touristHouseholds) : Unity.Entities.Entity`  
- `public static GetImmediateEfficiency(Unity.Entities.BufferAccessor<Game.Buildings.Efficiency> bufferAccessor, System.Int32 i) : System.Single`  
- `public static GetImmediateEfficiency(Unity.Entities.DynamicBuffer<Game.Buildings.Efficiency> buffer) : System.Single`  
- `public static GetLevelingCost(Game.Zones.AreaType areaType, Game.Prefabs.BuildingPropertyData propertyData, System.Int32 currentlevel, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityEffects) : System.Int32`  
- `public static GetMaintenanceType(Unity.Entities.Entity entity, Unity.Entities.ComponentLookup`1[[Game.Buildings.Park, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parks, Unity.Entities.ComponentLookup`1[[Game.Net.NetCondition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& netConditions, Unity.Entities.ComponentLookup`1[[Game.Net.Edge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edges, Unity.Entities.ComponentLookup`1[[Game.Objects.Surface, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& surfaces, Unity.Entities.ComponentLookup`1[[Game.Vehicles.Vehicle, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& vehicles) : Game.Simulation.MaintenanceType`  
- `public static GetOutsideConnectionType(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.OutsideConnectionData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& outsideConnectionDatas) : Game.Prefabs.OutsideConnectionTransferType`  
- `public static GetPropertyFromRenter(Unity.Entities.Entity renter, Unity.Entities.ComponentLookup`1[[Game.Citizens.HomelessHousehold, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& homelessHouseholds, Unity.Entities.ComponentLookup`1[[Game.Buildings.PropertyRenter, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& propertyRenters) : Unity.Entities.Entity`  
- `public static GetRandomOutsideConnectionByParameters(Unity.Collections.NativeList`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& outsideConnections, Unity.Entities.ComponentLookup`1[[Game.Prefabs.OutsideConnectionData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& outsideConnectionDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Unity.Mathematics.Random random, Unity.Mathematics.float4 outsideConnectionSpawnParameters, Unity.Entities.Entity& result) : System.Boolean`  
- `public static GetRandomOutsideConnectionByTransferType(Unity.Collections.NativeList`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& outsideConnections, Unity.Entities.ComponentLookup`1[[Game.Prefabs.OutsideConnectionData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& outsideConnectionDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Unity.Mathematics.Random random, Game.Prefabs.OutsideConnectionTransferType ocTransferType, Unity.Entities.Entity& result) : System.Boolean`  
- `public static GetShelterHomelessCapacity(Unity.Entities.Entity buildingPrefabEntity, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildingDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingPropertyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildingPropertyDatas) : System.Int32`  
- `public static GetVehicleCapacity(System.Single efficiency, System.Int32 capacity) : System.Int32`  
- `public static HasOption(Game.Prefabs.BuildingOptionData optionData, Game.Buildings.BuildingOption option) : System.Boolean`  
- `public static IsHomelessHousehold(Game.Citizens.Household household, Unity.Entities.Entity propertyEntity, Unity.Entities.ComponentLookup`1[[Game.Buildings.Park, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parks, Unity.Entities.ComponentLookup`1[[Game.Buildings.Abandoned, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& abandoneds) : System.Boolean`  
- `public static IsHomelessHousehold(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity householdEntity) : System.Boolean`  
- `public static IsHomelessShelterBuilding(Unity.Entities.Entity propertyEntity, Unity.Entities.ComponentLookup`1[[Game.Buildings.Park, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parks, Unity.Entities.ComponentLookup`1[[Game.Buildings.Abandoned, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& abandoneds) : System.Boolean`  
- `public static IsHomelessShelterBuilding(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity propertyEntity) : System.Boolean`  
- `public static SampleHeight(Game.Buildings.BuildingUtils+LotInfo& lotInfo, Unity.Mathematics.float3 position) : System.Single`  
- `public static SetEfficiencyFactor(Unity.Entities.DynamicBuffer<Game.Buildings.Efficiency> buffer, Game.Buildings.EfficiencyFactor factor, System.Single efficiency) : System.Void`  
- `public static SetEfficiencyFactors(Unity.Entities.DynamicBuffer<Game.Buildings.Efficiency> buffer, System.Span<System.Single> factors) : System.Void`  

## Nested types

- `Game.Buildings.BuildingUtils+LotInfo`  

