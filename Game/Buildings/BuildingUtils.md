# Game.Buildings.BuildingUtils

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class BuildingUtils
{
    public static const System.Single MAX_ROAD_CONNECTION_DISTANCE;
    public static const System.Single GEOMETRY_SIZE_OFFSET;
    public static const System.Single MIN_BUILDING_HEIGHT;
    public static const System.Single MIN_CONSTRUCTION_HEIGHT;
    public static const System.Single RANDOM_CONSTRUCTION_HEIGHT;
    public static const System.Single COLLAPSE_ACCELERATION;

    public static System.Void ApplyModifier(System.Single& value, Unity.Entities.DynamicBuffer<Game.Buildings.BuildingModifier> modifiers, Game.Buildings.BuildingModifierType type);
    public static Unity.Mathematics.float2 ApproximateEfficiencyFactors(System.Single targetEfficiency, Unity.Mathematics.float2 weights);
    public static Unity.Mathematics.float4 ApproximateEfficiencyFactors(System.Single targetEfficiency, Unity.Mathematics.float4 weights);
    public static Colossal.Mathematics.Quad3 CalculateCorners(Game.Objects.Transform transform, Unity.Mathematics.int2 lotSize);
    public static Colossal.Mathematics.Quad3 CalculateCorners(Unity.Mathematics.float3 position, Unity.Mathematics.quaternion rotation, Unity.Mathematics.float2 halfLotSize);
    public static Unity.Mathematics.float3 CalculateFrontPosition(Game.Objects.Transform transform, System.Int32 lotDepth);
    public static Game.Buildings.BuildingUtils+LotInfo CalculateLotInfo(Unity.Mathematics.float2 extents, Game.Objects.Transform transform, Game.Objects.Elevation elevation, Game.Buildings.Lot lot, Game.Prefabs.PrefabRef prefabRef, Unity.Entities.DynamicBuffer<Game.Buildings.InstalledUpgrade> upgrades, Unity.Entities.ComponentLookup<Game.Objects.Transform> transforms, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabRefs, Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> objectGeometryDatas, Unity.Entities.ComponentLookup<Game.Prefabs.BuildingTerraformData> buildingTerraformDatas, Unity.Entities.ComponentLookup<Game.Prefabs.BuildingExtensionData> buildingExtensionDatas, System.Boolean defaultNoSmooth, System.Boolean& hasExtensionLots);
    public static System.Void CalculateUpgradeRangeValues(Unity.Mathematics.quaternion rotation, Game.Prefabs.BuildingData ownerBuildingData, Game.Prefabs.BuildingData buildingData, Game.Prefabs.ServiceUpgradeData serviceUpgradeData, Unity.Mathematics.float3& forward, System.Single& width, System.Single& length, System.Single& roundness, System.Boolean& circular);
    public static System.Boolean CheckOption(Game.Buildings.Building building, Game.Buildings.BuildingOption option);
    public static System.Boolean CheckOption(Game.Buildings.InstalledUpgrade installedUpgrade, Game.Buildings.BuildingOption option);
    public static System.Boolean GetAddress(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Unity.Entities.Entity& road, System.Int32& number);
    public static System.Boolean GetAddress(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Unity.Entities.Entity edge, System.Single curvePos, Unity.Entities.Entity& road, System.Int32& number);
    public static Game.Zones.AreaType GetAreaType(Unity.Entities.Entity buildPrefab, Unity.Entities.ComponentLookup`1[[Game.Prefabs.SpawnableBuildingData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& spawnableBuildingDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ZoneData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& zoneDatas);
    public static System.Single GetCollapseHeight(System.Single time);
    public static System.Single GetCollapseTime(System.Single height);
    public static System.Single GetEfficiency(Unity.Entities.BufferAccessor<Game.Buildings.Efficiency> bufferAccessor, System.Int32 i);
    public static System.Single GetEfficiency(Unity.Entities.Entity entity, Unity.Entities.BufferLookup`1[[Game.Buildings.Efficiency, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& bufferLookup);
    public static System.Single GetEfficiency(Unity.Entities.DynamicBuffer<Game.Buildings.Efficiency> buffer);
    public static System.Single GetEfficiency(System.Span<System.Single> factors);
    public static System.Single GetEfficiency(System.Byte rawValue);
    public static System.Void GetEfficiencyFactors(Unity.Entities.DynamicBuffer<Game.Buildings.Efficiency> buffer, System.Span<System.Single> factors);
    public static Unity.Entities.Entity GetHouseholdHomeBuilding(Unity.Entities.Entity householdEntity, Unity.Entities.ComponentLookup`1[[Game.Buildings.PropertyRenter, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& propertyRenters, Unity.Entities.ComponentLookup`1[[Game.Citizens.HomelessHousehold, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& homelessHouseholds);
    public static Unity.Entities.Entity GetHouseholdHomeBuilding(Unity.Entities.Entity householdEntity, Unity.Entities.ComponentLookup`1[[Game.Buildings.PropertyRenter, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& propertyRenters, Unity.Entities.ComponentLookup`1[[Game.Citizens.HomelessHousehold, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& homelessHouseholds, Unity.Entities.ComponentLookup`1[[Game.Citizens.TouristHousehold, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& touristHouseholds);
    public static System.Single GetImmediateEfficiency(Unity.Entities.BufferAccessor<Game.Buildings.Efficiency> bufferAccessor, System.Int32 i);
    public static System.Single GetImmediateEfficiency(Unity.Entities.DynamicBuffer<Game.Buildings.Efficiency> buffer);
    public static System.Int32 GetLevelingCost(Game.Zones.AreaType areaType, Game.Prefabs.BuildingPropertyData propertyData, System.Int32 currentlevel, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityEffects);
    public static Game.Simulation.MaintenanceType GetMaintenanceType(Unity.Entities.Entity entity, Unity.Entities.ComponentLookup`1[[Game.Buildings.Park, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parks, Unity.Entities.ComponentLookup`1[[Game.Net.NetCondition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& netConditions, Unity.Entities.ComponentLookup`1[[Game.Net.Edge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edges, Unity.Entities.ComponentLookup`1[[Game.Objects.Surface, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& surfaces, Unity.Entities.ComponentLookup`1[[Game.Vehicles.Vehicle, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& vehicles);
    public static Game.Prefabs.OutsideConnectionTransferType GetOutsideConnectionType(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.OutsideConnectionData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& outsideConnectionDatas);
    public static Unity.Entities.Entity GetPropertyFromRenter(Unity.Entities.Entity renter, Unity.Entities.ComponentLookup`1[[Game.Citizens.HomelessHousehold, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& homelessHouseholds, Unity.Entities.ComponentLookup`1[[Game.Buildings.PropertyRenter, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& propertyRenters);
    public static System.Boolean GetRandomOutsideConnectionByParameters(Unity.Collections.NativeList`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& outsideConnections, Unity.Entities.ComponentLookup`1[[Game.Prefabs.OutsideConnectionData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& outsideConnectionDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Unity.Mathematics.Random random, Unity.Mathematics.float4 outsideConnectionSpawnParameters, Unity.Entities.Entity& result);
    public static System.Boolean GetRandomOutsideConnectionByTransferType(Unity.Collections.NativeList`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& outsideConnections, Unity.Entities.ComponentLookup`1[[Game.Prefabs.OutsideConnectionData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& outsideConnectionDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Unity.Mathematics.Random random, Game.Prefabs.OutsideConnectionTransferType ocTransferType, Unity.Entities.Entity& result);
    public static System.Int32 GetShelterHomelessCapacity(Unity.Entities.Entity buildingPrefabEntity, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildingDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingPropertyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildingPropertyDatas);
    public static System.Int32 GetVehicleCapacity(System.Single efficiency, System.Int32 capacity);
    public static System.Boolean HasOption(Game.Prefabs.BuildingOptionData optionData, Game.Buildings.BuildingOption option);
    public static System.Boolean IsHomelessHousehold(Game.Citizens.Household household, Unity.Entities.Entity propertyEntity, Unity.Entities.ComponentLookup`1[[Game.Buildings.Park, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parks, Unity.Entities.ComponentLookup`1[[Game.Buildings.Abandoned, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& abandoneds);
    public static System.Boolean IsHomelessHousehold(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity householdEntity);
    public static System.Boolean IsHomelessShelterBuilding(Unity.Entities.Entity propertyEntity, Unity.Entities.ComponentLookup`1[[Game.Buildings.Park, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parks, Unity.Entities.ComponentLookup`1[[Game.Buildings.Abandoned, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& abandoneds);
    public static System.Boolean IsHomelessShelterBuilding(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity propertyEntity);
    public static System.Single SampleHeight(Game.Buildings.BuildingUtils+LotInfo& lotInfo, Unity.Mathematics.float3 position);
    public static System.Void SetEfficiencyFactor(Unity.Entities.DynamicBuffer<Game.Buildings.Efficiency> buffer, Game.Buildings.EfficiencyFactor factor, System.Single efficiency);
    public static System.Void SetEfficiencyFactors(Unity.Entities.DynamicBuffer<Game.Buildings.Efficiency> buffer, System.Span<System.Single> factors);
}
```


## Fields

- `public static const System.Single MAX_ROAD_CONNECTION_DISTANCE`  

```csharp
public static const System.Single MAX_ROAD_CONNECTION_DISTANCE;
```

- `public static const System.Single GEOMETRY_SIZE_OFFSET`  

```csharp
public static const System.Single GEOMETRY_SIZE_OFFSET;
```

- `public static const System.Single MIN_BUILDING_HEIGHT`  

```csharp
public static const System.Single MIN_BUILDING_HEIGHT;
```

- `public static const System.Single MIN_CONSTRUCTION_HEIGHT`  

```csharp
public static const System.Single MIN_CONSTRUCTION_HEIGHT;
```

- `public static const System.Single RANDOM_CONSTRUCTION_HEIGHT`  

```csharp
public static const System.Single RANDOM_CONSTRUCTION_HEIGHT;
```

- `public static const System.Single COLLAPSE_ACCELERATION`  

```csharp
public static const System.Single COLLAPSE_ACCELERATION;
```


## Methods

- `public static ApplyModifier(System.Single& value, Unity.Entities.DynamicBuffer<Game.Buildings.BuildingModifier> modifiers, Game.Buildings.BuildingModifierType type) : System.Void`  

```csharp
public static System.Void ApplyModifier(System.Single& value, Unity.Entities.DynamicBuffer<Game.Buildings.BuildingModifier> modifiers, Game.Buildings.BuildingModifierType type);
```

- `public static ApproximateEfficiencyFactors(System.Single targetEfficiency, Unity.Mathematics.float2 weights) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 ApproximateEfficiencyFactors(System.Single targetEfficiency, Unity.Mathematics.float2 weights);
```

- `public static ApproximateEfficiencyFactors(System.Single targetEfficiency, Unity.Mathematics.float4 weights) : Unity.Mathematics.float4`  

```csharp
public static Unity.Mathematics.float4 ApproximateEfficiencyFactors(System.Single targetEfficiency, Unity.Mathematics.float4 weights);
```

- `public static CalculateCorners(Game.Objects.Transform transform, Unity.Mathematics.int2 lotSize) : Colossal.Mathematics.Quad3`  

```csharp
public static Colossal.Mathematics.Quad3 CalculateCorners(Game.Objects.Transform transform, Unity.Mathematics.int2 lotSize);
```

- `public static CalculateCorners(Unity.Mathematics.float3 position, Unity.Mathematics.quaternion rotation, Unity.Mathematics.float2 halfLotSize) : Colossal.Mathematics.Quad3`  

```csharp
public static Colossal.Mathematics.Quad3 CalculateCorners(Unity.Mathematics.float3 position, Unity.Mathematics.quaternion rotation, Unity.Mathematics.float2 halfLotSize);
```

- `public static CalculateFrontPosition(Game.Objects.Transform transform, System.Int32 lotDepth) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 CalculateFrontPosition(Game.Objects.Transform transform, System.Int32 lotDepth);
```

- `public static CalculateLotInfo(Unity.Mathematics.float2 extents, Game.Objects.Transform transform, Game.Objects.Elevation elevation, Game.Buildings.Lot lot, Game.Prefabs.PrefabRef prefabRef, Unity.Entities.DynamicBuffer<Game.Buildings.InstalledUpgrade> upgrades, Unity.Entities.ComponentLookup<Game.Objects.Transform> transforms, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabRefs, Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> objectGeometryDatas, Unity.Entities.ComponentLookup<Game.Prefabs.BuildingTerraformData> buildingTerraformDatas, Unity.Entities.ComponentLookup<Game.Prefabs.BuildingExtensionData> buildingExtensionDatas, System.Boolean defaultNoSmooth, System.Boolean& hasExtensionLots) : Game.Buildings.BuildingUtils+LotInfo`  

```csharp
public static Game.Buildings.BuildingUtils+LotInfo CalculateLotInfo(Unity.Mathematics.float2 extents, Game.Objects.Transform transform, Game.Objects.Elevation elevation, Game.Buildings.Lot lot, Game.Prefabs.PrefabRef prefabRef, Unity.Entities.DynamicBuffer<Game.Buildings.InstalledUpgrade> upgrades, Unity.Entities.ComponentLookup<Game.Objects.Transform> transforms, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabRefs, Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> objectGeometryDatas, Unity.Entities.ComponentLookup<Game.Prefabs.BuildingTerraformData> buildingTerraformDatas, Unity.Entities.ComponentLookup<Game.Prefabs.BuildingExtensionData> buildingExtensionDatas, System.Boolean defaultNoSmooth, System.Boolean& hasExtensionLots);
```

- `public static CalculateUpgradeRangeValues(Unity.Mathematics.quaternion rotation, Game.Prefabs.BuildingData ownerBuildingData, Game.Prefabs.BuildingData buildingData, Game.Prefabs.ServiceUpgradeData serviceUpgradeData, Unity.Mathematics.float3& forward, System.Single& width, System.Single& length, System.Single& roundness, System.Boolean& circular) : System.Void`  

```csharp
public static System.Void CalculateUpgradeRangeValues(Unity.Mathematics.quaternion rotation, Game.Prefabs.BuildingData ownerBuildingData, Game.Prefabs.BuildingData buildingData, Game.Prefabs.ServiceUpgradeData serviceUpgradeData, Unity.Mathematics.float3& forward, System.Single& width, System.Single& length, System.Single& roundness, System.Boolean& circular);
```

- `public static CheckOption(Game.Buildings.Building building, Game.Buildings.BuildingOption option) : System.Boolean`  

```csharp
public static System.Boolean CheckOption(Game.Buildings.Building building, Game.Buildings.BuildingOption option);
```

- `public static CheckOption(Game.Buildings.InstalledUpgrade installedUpgrade, Game.Buildings.BuildingOption option) : System.Boolean`  

```csharp
public static System.Boolean CheckOption(Game.Buildings.InstalledUpgrade installedUpgrade, Game.Buildings.BuildingOption option);
```

- `public static GetAddress(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Unity.Entities.Entity& road, System.Int32& number) : System.Boolean`  

```csharp
public static System.Boolean GetAddress(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Unity.Entities.Entity& road, System.Int32& number);
```

- `public static GetAddress(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Unity.Entities.Entity edge, System.Single curvePos, Unity.Entities.Entity& road, System.Int32& number) : System.Boolean`  

```csharp
public static System.Boolean GetAddress(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Unity.Entities.Entity edge, System.Single curvePos, Unity.Entities.Entity& road, System.Int32& number);
```

- `public static GetAreaType(Unity.Entities.Entity buildPrefab, Unity.Entities.ComponentLookup`1[[Game.Prefabs.SpawnableBuildingData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& spawnableBuildingDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ZoneData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& zoneDatas) : Game.Zones.AreaType`  

```csharp
public static Game.Zones.AreaType GetAreaType(Unity.Entities.Entity buildPrefab, Unity.Entities.ComponentLookup`1[[Game.Prefabs.SpawnableBuildingData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& spawnableBuildingDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ZoneData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& zoneDatas);
```

- `public static GetCollapseHeight(System.Single time) : System.Single`  

```csharp
public static System.Single GetCollapseHeight(System.Single time);
```

- `public static GetCollapseTime(System.Single height) : System.Single`  

```csharp
public static System.Single GetCollapseTime(System.Single height);
```

- `public static GetEfficiency(Unity.Entities.BufferAccessor<Game.Buildings.Efficiency> bufferAccessor, System.Int32 i) : System.Single`  

```csharp
public static System.Single GetEfficiency(Unity.Entities.BufferAccessor<Game.Buildings.Efficiency> bufferAccessor, System.Int32 i);
```

- `public static GetEfficiency(Unity.Entities.Entity entity, Unity.Entities.BufferLookup`1[[Game.Buildings.Efficiency, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& bufferLookup) : System.Single`  

```csharp
public static System.Single GetEfficiency(Unity.Entities.Entity entity, Unity.Entities.BufferLookup`1[[Game.Buildings.Efficiency, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& bufferLookup);
```

- `public static GetEfficiency(Unity.Entities.DynamicBuffer<Game.Buildings.Efficiency> buffer) : System.Single`  

```csharp
public static System.Single GetEfficiency(Unity.Entities.DynamicBuffer<Game.Buildings.Efficiency> buffer);
```

- `public static GetEfficiency(System.Span<System.Single> factors) : System.Single`  

```csharp
public static System.Single GetEfficiency(System.Span<System.Single> factors);
```

- `public static GetEfficiency(System.Byte rawValue) : System.Single`  

```csharp
public static System.Single GetEfficiency(System.Byte rawValue);
```

- `public static GetEfficiencyFactors(Unity.Entities.DynamicBuffer<Game.Buildings.Efficiency> buffer, System.Span<System.Single> factors) : System.Void`  

```csharp
public static System.Void GetEfficiencyFactors(Unity.Entities.DynamicBuffer<Game.Buildings.Efficiency> buffer, System.Span<System.Single> factors);
```

- `public static GetHouseholdHomeBuilding(Unity.Entities.Entity householdEntity, Unity.Entities.ComponentLookup`1[[Game.Buildings.PropertyRenter, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& propertyRenters, Unity.Entities.ComponentLookup`1[[Game.Citizens.HomelessHousehold, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& homelessHouseholds) : Unity.Entities.Entity`  

```csharp
public static Unity.Entities.Entity GetHouseholdHomeBuilding(Unity.Entities.Entity householdEntity, Unity.Entities.ComponentLookup`1[[Game.Buildings.PropertyRenter, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& propertyRenters, Unity.Entities.ComponentLookup`1[[Game.Citizens.HomelessHousehold, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& homelessHouseholds);
```

- `public static GetHouseholdHomeBuilding(Unity.Entities.Entity householdEntity, Unity.Entities.ComponentLookup`1[[Game.Buildings.PropertyRenter, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& propertyRenters, Unity.Entities.ComponentLookup`1[[Game.Citizens.HomelessHousehold, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& homelessHouseholds, Unity.Entities.ComponentLookup`1[[Game.Citizens.TouristHousehold, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& touristHouseholds) : Unity.Entities.Entity`  

```csharp
public static Unity.Entities.Entity GetHouseholdHomeBuilding(Unity.Entities.Entity householdEntity, Unity.Entities.ComponentLookup`1[[Game.Buildings.PropertyRenter, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& propertyRenters, Unity.Entities.ComponentLookup`1[[Game.Citizens.HomelessHousehold, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& homelessHouseholds, Unity.Entities.ComponentLookup`1[[Game.Citizens.TouristHousehold, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& touristHouseholds);
```

- `public static GetImmediateEfficiency(Unity.Entities.BufferAccessor<Game.Buildings.Efficiency> bufferAccessor, System.Int32 i) : System.Single`  

```csharp
public static System.Single GetImmediateEfficiency(Unity.Entities.BufferAccessor<Game.Buildings.Efficiency> bufferAccessor, System.Int32 i);
```

- `public static GetImmediateEfficiency(Unity.Entities.DynamicBuffer<Game.Buildings.Efficiency> buffer) : System.Single`  

```csharp
public static System.Single GetImmediateEfficiency(Unity.Entities.DynamicBuffer<Game.Buildings.Efficiency> buffer);
```

- `public static GetLevelingCost(Game.Zones.AreaType areaType, Game.Prefabs.BuildingPropertyData propertyData, System.Int32 currentlevel, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityEffects) : System.Int32`  

```csharp
public static System.Int32 GetLevelingCost(Game.Zones.AreaType areaType, Game.Prefabs.BuildingPropertyData propertyData, System.Int32 currentlevel, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityEffects);
```

- `public static GetMaintenanceType(Unity.Entities.Entity entity, Unity.Entities.ComponentLookup`1[[Game.Buildings.Park, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parks, Unity.Entities.ComponentLookup`1[[Game.Net.NetCondition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& netConditions, Unity.Entities.ComponentLookup`1[[Game.Net.Edge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edges, Unity.Entities.ComponentLookup`1[[Game.Objects.Surface, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& surfaces, Unity.Entities.ComponentLookup`1[[Game.Vehicles.Vehicle, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& vehicles) : Game.Simulation.MaintenanceType`  

```csharp
public static Game.Simulation.MaintenanceType GetMaintenanceType(Unity.Entities.Entity entity, Unity.Entities.ComponentLookup`1[[Game.Buildings.Park, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parks, Unity.Entities.ComponentLookup`1[[Game.Net.NetCondition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& netConditions, Unity.Entities.ComponentLookup`1[[Game.Net.Edge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edges, Unity.Entities.ComponentLookup`1[[Game.Objects.Surface, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& surfaces, Unity.Entities.ComponentLookup`1[[Game.Vehicles.Vehicle, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& vehicles);
```

- `public static GetOutsideConnectionType(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.OutsideConnectionData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& outsideConnectionDatas) : Game.Prefabs.OutsideConnectionTransferType`  

```csharp
public static Game.Prefabs.OutsideConnectionTransferType GetOutsideConnectionType(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.OutsideConnectionData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& outsideConnectionDatas);
```

- `public static GetPropertyFromRenter(Unity.Entities.Entity renter, Unity.Entities.ComponentLookup`1[[Game.Citizens.HomelessHousehold, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& homelessHouseholds, Unity.Entities.ComponentLookup`1[[Game.Buildings.PropertyRenter, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& propertyRenters) : Unity.Entities.Entity`  

```csharp
public static Unity.Entities.Entity GetPropertyFromRenter(Unity.Entities.Entity renter, Unity.Entities.ComponentLookup`1[[Game.Citizens.HomelessHousehold, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& homelessHouseholds, Unity.Entities.ComponentLookup`1[[Game.Buildings.PropertyRenter, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& propertyRenters);
```

- `public static GetRandomOutsideConnectionByParameters(Unity.Collections.NativeList`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& outsideConnections, Unity.Entities.ComponentLookup`1[[Game.Prefabs.OutsideConnectionData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& outsideConnectionDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Unity.Mathematics.Random random, Unity.Mathematics.float4 outsideConnectionSpawnParameters, Unity.Entities.Entity& result) : System.Boolean`  

```csharp
public static System.Boolean GetRandomOutsideConnectionByParameters(Unity.Collections.NativeList`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& outsideConnections, Unity.Entities.ComponentLookup`1[[Game.Prefabs.OutsideConnectionData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& outsideConnectionDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Unity.Mathematics.Random random, Unity.Mathematics.float4 outsideConnectionSpawnParameters, Unity.Entities.Entity& result);
```

- `public static GetRandomOutsideConnectionByTransferType(Unity.Collections.NativeList`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& outsideConnections, Unity.Entities.ComponentLookup`1[[Game.Prefabs.OutsideConnectionData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& outsideConnectionDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Unity.Mathematics.Random random, Game.Prefabs.OutsideConnectionTransferType ocTransferType, Unity.Entities.Entity& result) : System.Boolean`  

```csharp
public static System.Boolean GetRandomOutsideConnectionByTransferType(Unity.Collections.NativeList`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& outsideConnections, Unity.Entities.ComponentLookup`1[[Game.Prefabs.OutsideConnectionData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& outsideConnectionDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Unity.Mathematics.Random random, Game.Prefabs.OutsideConnectionTransferType ocTransferType, Unity.Entities.Entity& result);
```

- `public static GetShelterHomelessCapacity(Unity.Entities.Entity buildingPrefabEntity, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildingDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingPropertyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildingPropertyDatas) : System.Int32`  

```csharp
public static System.Int32 GetShelterHomelessCapacity(Unity.Entities.Entity buildingPrefabEntity, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildingDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingPropertyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildingPropertyDatas);
```

- `public static GetVehicleCapacity(System.Single efficiency, System.Int32 capacity) : System.Int32`  

```csharp
public static System.Int32 GetVehicleCapacity(System.Single efficiency, System.Int32 capacity);
```

- `public static HasOption(Game.Prefabs.BuildingOptionData optionData, Game.Buildings.BuildingOption option) : System.Boolean`  

```csharp
public static System.Boolean HasOption(Game.Prefabs.BuildingOptionData optionData, Game.Buildings.BuildingOption option);
```

- `public static IsHomelessHousehold(Game.Citizens.Household household, Unity.Entities.Entity propertyEntity, Unity.Entities.ComponentLookup`1[[Game.Buildings.Park, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parks, Unity.Entities.ComponentLookup`1[[Game.Buildings.Abandoned, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& abandoneds) : System.Boolean`  

```csharp
public static System.Boolean IsHomelessHousehold(Game.Citizens.Household household, Unity.Entities.Entity propertyEntity, Unity.Entities.ComponentLookup`1[[Game.Buildings.Park, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parks, Unity.Entities.ComponentLookup`1[[Game.Buildings.Abandoned, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& abandoneds);
```

- `public static IsHomelessHousehold(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity householdEntity) : System.Boolean`  

```csharp
public static System.Boolean IsHomelessHousehold(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity householdEntity);
```

- `public static IsHomelessShelterBuilding(Unity.Entities.Entity propertyEntity, Unity.Entities.ComponentLookup`1[[Game.Buildings.Park, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parks, Unity.Entities.ComponentLookup`1[[Game.Buildings.Abandoned, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& abandoneds) : System.Boolean`  

```csharp
public static System.Boolean IsHomelessShelterBuilding(Unity.Entities.Entity propertyEntity, Unity.Entities.ComponentLookup`1[[Game.Buildings.Park, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parks, Unity.Entities.ComponentLookup`1[[Game.Buildings.Abandoned, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& abandoneds);
```

- `public static IsHomelessShelterBuilding(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity propertyEntity) : System.Boolean`  

```csharp
public static System.Boolean IsHomelessShelterBuilding(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity propertyEntity);
```

- `public static SampleHeight(Game.Buildings.BuildingUtils+LotInfo& lotInfo, Unity.Mathematics.float3 position) : System.Single`  

```csharp
public static System.Single SampleHeight(Game.Buildings.BuildingUtils+LotInfo& lotInfo, Unity.Mathematics.float3 position);
```

- `public static SetEfficiencyFactor(Unity.Entities.DynamicBuffer<Game.Buildings.Efficiency> buffer, Game.Buildings.EfficiencyFactor factor, System.Single efficiency) : System.Void`  

```csharp
public static System.Void SetEfficiencyFactor(Unity.Entities.DynamicBuffer<Game.Buildings.Efficiency> buffer, Game.Buildings.EfficiencyFactor factor, System.Single efficiency);
```

- `public static SetEfficiencyFactors(Unity.Entities.DynamicBuffer<Game.Buildings.Efficiency> buffer, System.Span<System.Single> factors) : System.Void`  

```csharp
public static System.Void SetEfficiencyFactors(Unity.Entities.DynamicBuffer<Game.Buildings.Efficiency> buffer, System.Span<System.Single> factors);
```


## Nested types

- `Game.Buildings.BuildingUtils+LotInfo`  

