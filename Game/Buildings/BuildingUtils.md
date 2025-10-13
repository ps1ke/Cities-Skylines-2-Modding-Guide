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
public static void ApplyModifier(ref float value, DynamicBuffer<BuildingModifier> modifiers, BuildingModifierType type)
	{
		if (modifiers.Length > (int)type)
		{
			float2 delta = modifiers[(int)type].m_Delta;
			value += delta.x;
			value += value * delta.y;
		}
	}
```

- `public static ApproximateEfficiencyFactors(System.Single targetEfficiency, Unity.Mathematics.float2 weights) : Unity.Mathematics.float2`  

```csharp
public static float4 ApproximateEfficiencyFactors(float targetEfficiency, float4 weights)
	{
		Assert.IsTrue(targetEfficiency >= 0f && targetEfficiency <= 1f);
		Assert.IsTrue(math.cmin(weights) >= 0f);
		float num = math.cmax(weights);
		if (targetEfficiency == 1f || num == 0f)
		{
			return 1f;
		}
		if (targetEfficiency == 0f)
		{
			return math.select(1f, 0f, weights > 1.1920929E-07f);
		}
		float num2 = -1f / num;
		float num3 = 0f;
		float4 result = default(float4);
		for (int i = 0; i < 16; i++)
		{
			float num4 = (num2 + num3) / 2f;
			result = num4 * weights + 1f;
			float num5 = result.x * result.y * result.z * result.w;
			num2 = math.select(num2, num4, num5 < targetEfficiency);
			num3 = math.select(num3, num4, num5 > targetEfficiency);
		}
		return result;
	}
```

- `public static ApproximateEfficiencyFactors(System.Single targetEfficiency, Unity.Mathematics.float4 weights) : Unity.Mathematics.float4`  

```csharp
public static float4 ApproximateEfficiencyFactors(float targetEfficiency, float4 weights)
	{
		Assert.IsTrue(targetEfficiency >= 0f && targetEfficiency <= 1f);
		Assert.IsTrue(math.cmin(weights) >= 0f);
		float num = math.cmax(weights);
		if (targetEfficiency == 1f || num == 0f)
		{
			return 1f;
		}
		if (targetEfficiency == 0f)
		{
			return math.select(1f, 0f, weights > 1.1920929E-07f);
		}
		float num2 = -1f / num;
		float num3 = 0f;
		float4 result = default(float4);
		for (int i = 0; i < 16; i++)
		{
			float num4 = (num2 + num3) / 2f;
			result = num4 * weights + 1f;
			float num5 = result.x * result.y * result.z * result.w;
			num2 = math.select(num2, num4, num5 < targetEfficiency);
			num3 = math.select(num3, num4, num5 > targetEfficiency);
		}
		return result;
	}
```

- `public static CalculateCorners(Game.Objects.Transform transform, Unity.Mathematics.int2 lotSize) : Colossal.Mathematics.Quad3`  

```csharp
public static Quad3 CalculateCorners(float3 position, quaternion rotation, float2 halfLotSize)
	{
		float3 @float = math.mul(rotation, new float3(0f, 0f, -1f));
		float3 float2 = math.mul(rotation, new float3(-1f, 0f, 0f));
		float3 float3 = @float * halfLotSize.y;
		float3 float4 = float2 * halfLotSize.x;
		float3 float5 = position + float3;
		float3 float6 = position - float3;
		return new Quad3(float5 - float4, float5 + float4, float6 + float4, float6 - float4);
	}
```

- `public static CalculateCorners(Unity.Mathematics.float3 position, Unity.Mathematics.quaternion rotation, Unity.Mathematics.float2 halfLotSize) : Colossal.Mathematics.Quad3`  

```csharp
public static Quad3 CalculateCorners(float3 position, quaternion rotation, float2 halfLotSize)
	{
		float3 @float = math.mul(rotation, new float3(0f, 0f, -1f));
		float3 float2 = math.mul(rotation, new float3(-1f, 0f, 0f));
		float3 float3 = @float * halfLotSize.y;
		float3 float4 = float2 * halfLotSize.x;
		float3 float5 = position + float3;
		float3 float6 = position - float3;
		return new Quad3(float5 - float4, float5 + float4, float6 + float4, float6 - float4);
	}
```

- `public static CalculateFrontPosition(Game.Objects.Transform transform, System.Int32 lotDepth) : Unity.Mathematics.float3`  

```csharp
public static float3 CalculateFrontPosition(Game.Objects.Transform transform, int lotDepth)
	{
		float3 position = new float3(0f, 0f, (float)lotDepth * 4f);
		return ObjectUtils.LocalToWorld(transform, position);
	}
```

- `public static CalculateLotInfo(Unity.Mathematics.float2 extents, Game.Objects.Transform transform, Game.Objects.Elevation elevation, Game.Buildings.Lot lot, Game.Prefabs.PrefabRef prefabRef, Unity.Entities.DynamicBuffer<Game.Buildings.InstalledUpgrade> upgrades, Unity.Entities.ComponentLookup<Game.Objects.Transform> transforms, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabRefs, Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> objectGeometryDatas, Unity.Entities.ComponentLookup<Game.Prefabs.BuildingTerraformData> buildingTerraformDatas, Unity.Entities.ComponentLookup<Game.Prefabs.BuildingExtensionData> buildingExtensionDatas, System.Boolean defaultNoSmooth, System.Boolean& hasExtensionLots) : Game.Buildings.BuildingUtils+LotInfo`  

```csharp
public static LotInfo CalculateLotInfo(float2 extents, Game.Objects.Transform transform, Game.Objects.Elevation elevation, Lot lot, PrefabRef prefabRef, DynamicBuffer<InstalledUpgrade> upgrades, ComponentLookup<Game.Objects.Transform> transforms, ComponentLookup<PrefabRef> prefabRefs, ComponentLookup<ObjectGeometryData> objectGeometryDatas, ComponentLookup<BuildingTerraformData> buildingTerraformDatas, ComponentLookup<BuildingExtensionData> buildingExtensionDatas, bool defaultNoSmooth, out bool hasExtensionLots)
	{
		LotInfo result = new LotInfo
		{
			m_Position = transform.m_Position,
			m_Extents = extents,
			m_Rotation = transform.m_Rotation,
			m_Radius = math.length(extents),
			m_Circular = 0f,
			m_FrontHeights = lot.m_FrontHeights,
			m_RightHeights = lot.m_RightHeights,
			m_BackHeights = lot.m_BackHeights,
			m_LeftHeights = lot.m_LeftHeights,
			m_FlatX0 = 0f - extents.x,
			m_FlatZ0 = 0f - extents.y,
			m_FlatX1 = extents.x,
			m_FlatZ1 = extents.y,
			m_MinLimit = new float4(-extents.xy, extents.xy),
			m_MaxLimit = new float4(-extents.xy, extents.xy)
		};
		if (objectGeometryDatas.TryGetComponent(prefabRef.m_Prefab, out var componentData))
		{
			bool flag = (componentData.m_Flags & Game.Objects.GeometryFlags.Standing) != 0;
			bool test = ((uint)componentData.m_Flags & (uint)((!flag) ? 1 : 256)) != 0;
			result.m_Circular = math.select(0f, 1f, test);
		}
		if (buildingTerraformDatas.TryGetComponent(prefabRef.m_Prefab, out var componentData2))
		{
			result.m_Position.y += componentData2.m_HeightOffset;
			result.m_FlatX0 = componentData2.m_FlatX0;
			result.m_FlatZ0 = componentData2.m_FlatZ0;
			result.m_FlatX1 = componentData2.m_FlatX1;
			result.m_FlatZ1 = componentData2.m_FlatZ1;
			result.m_MinLimit = componentData2.m_Smooth;
			result.m_MaxLimit = componentData2.m_Smooth;
		}
		else
		{
			componentData2.m_DontLower = defaultNoSmooth;
			componentData2.m_DontRaise = defaultNoSmooth;
		}
		hasExtensionLots = false;
		if (upgrades.IsCreated)
		{
			for (int i = 0; i < upgrades.Length; i++)
			{
				Entity upgrade = upgrades[i].m_Upgrade;
				PrefabRef prefabRef2 = prefabRefs[upgrade];
				if (buildingExtensionDatas.TryGetComponent(prefabRef2.m_Prefab, out var componentData3) && !componentData3.m_External && buildingTerraformDatas.TryGetComponent(prefabRef2.m_Prefab, out var componentData4))
				{
					float3 @float = transforms[upgrade].m_Position - transform.m_Position;
					float num = 0f;
					if (objectGeometryDatas.TryGetComponent(prefabRef2.m_Prefab, out var componentData5))
					{
						bool flag2 = (componentData5.m_Flags & Game.Objects.GeometryFlags.Standing) != 0;
						bool test2 = ((uint)componentData5.m_Flags & (uint)((!flag2) ? 1 : 256)) != 0;
						num = math.select(0f, 1f, test2);
					}
					result.m_FlatX0 = math.min(result.m_FlatX0, componentData4.m_FlatX0 + @float.x);
					result.m_FlatZ0 = math.min(result.m_FlatZ0, componentData4.m_FlatZ0 + @float.z);
					result.m_FlatX1 = math.max(result.m_FlatX1, componentData4.m_FlatX1 + @float.x);
					result.m_FlatZ1 = math.max(result.m_FlatZ1, componentData4.m_FlatZ1 + @float.z);
					if (!math.all(componentData4.m_Smooth + @float.xzxz == result.m_MaxLimit) || num != result.m_Circular)
					{
						hasExtensionLots = true;
					}
				}
			}
		}
		result.m_MinLimit.xy = math.min(new float2(result.m_FlatX0.y, result.m_FlatZ0.y), result.m_MinLimit.xy);
		result.m_MinLimit.zw = math.max(new float2(result.m_FlatX1.y, result.m_FlatZ1.y), result.m_MinLimit.zw);
		extents = math.max(extents, 8f);
		if (componentData2.m_DontLower)
		{
			result.m_MinLimit = new float4(extents.xy, -extents.xy);
		}
		if (elevation.m_Elevation > 0f || componentData2.m_DontRaise)
		{
			result.m_MaxLimit = new float4(extents.xy, -extents.xy);
		}
		return result;
	}
```

- `public static CalculateUpgradeRangeValues(Unity.Mathematics.quaternion rotation, Game.Prefabs.BuildingData ownerBuildingData, Game.Prefabs.BuildingData buildingData, Game.Prefabs.ServiceUpgradeData serviceUpgradeData, Unity.Mathematics.float3& forward, System.Single& width, System.Single& length, System.Single& roundness, System.Boolean& circular) : System.Void`  

```csharp
public static void CalculateUpgradeRangeValues(quaternion rotation, BuildingData ownerBuildingData, BuildingData buildingData, ServiceUpgradeData serviceUpgradeData, out float3 forward, out float width, out float length, out float roundness, out bool circular)
	{
		forward = math.forward(rotation);
		if (ownerBuildingData.m_LotSize.y < ownerBuildingData.m_LotSize.x)
		{
			ownerBuildingData.m_LotSize = ownerBuildingData.m_LotSize.yx;
			forward.xz = MathUtils.Right(forward.xz);
		}
		float num = serviceUpgradeData.m_MaxPlacementDistance + (float)buildingData.m_LotSize.y * 8f;
		width = (float)ownerBuildingData.m_LotSize.x * 8f + num * 2f;
		length = (float)ownerBuildingData.m_LotSize.y * 8f + num * 2f;
		roundness = math.max(0f, num - 40f) * 1.2f + 8f;
		width = math.min(length, math.max(width, roundness * 2f));
		roundness = math.min(roundness, width * 0.5f);
		circular = length * 0.5f - roundness < 1f;
	}
```

- `public static CheckOption(Game.Buildings.Building building, Game.Buildings.BuildingOption option) : System.Boolean`  

```csharp
public static bool CheckOption(InstalledUpgrade installedUpgrade, BuildingOption option)
	{
		return (installedUpgrade.m_OptionMask & (uint)(1 << (int)option)) != 0;
	}
```

- `public static CheckOption(Game.Buildings.InstalledUpgrade installedUpgrade, Game.Buildings.BuildingOption option) : System.Boolean`  

```csharp
public static bool CheckOption(InstalledUpgrade installedUpgrade, BuildingOption option)
	{
		return (installedUpgrade.m_OptionMask & (uint)(1 << (int)option)) != 0;
	}
```

- `public static GetAddress(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Unity.Entities.Entity& road, System.Int32& number) : System.Boolean`  

```csharp
public static bool GetAddress(EntityManager entityManager, Entity entity, Entity edge, float curvePos, out Entity road, out int number)
	{
		if (entityManager.TryGetComponent<Aggregated>(edge, out var component) && entityManager.TryGetBuffer(component.m_Aggregate, isReadOnly: true, out DynamicBuffer<AggregateElement> buffer))
		{
			float num = 0f;
			for (int i = 0; i < buffer.Length; i++)
			{
				AggregateElement aggregateElement = buffer[i];
				float num2 = num;
				if (entityManager.TryGetComponent<Curve>(aggregateElement.m_Edge, out var component2) && entityManager.TryGetComponent<Composition>(aggregateElement.m_Edge, out var component3) && entityManager.TryGetComponent<NetCompositionData>(component3.m_Edge, out var component4))
				{
					float2 x = math.normalizesafe(MathUtils.StartTangent(component2.m_Bezier).xz);
					float2 y = math.normalizesafe(MathUtils.EndTangent(component2.m_Bezier).xz);
					float num3 = ZoneUtils.GetCellWidth(component4.m_Width);
					float num4 = math.acos(math.clamp(math.dot(x, y), -1f, 1f));
					num2 += component2.m_Length + num3 * num4 * 0.5f;
				}
				bool flag = i == 0;
				bool flag2 = i == buffer.Length - 1;
				bool flag3 = aggregateElement.m_Edge == edge;
				bool flag4 = false;
				if (flag3 || flag || flag2)
				{
					Edge component7;
					Edge component8;
					if (!flag)
					{
						if (entityManager.TryGetComponent<Edge>(aggregateElement.m_Edge, out var component5) && entityManager.TryGetComponent<Edge>(buffer[i - 1].m_Edge, out var component6) && (component5.m_End == component6.m_Start || component5.m_End == component6.m_End))
						{
							flag4 = true;
						}
					}
					else if (!flag2 && entityManager.TryGetComponent<Edge>(aggregateElement.m_Edge, out component7) && entityManager.TryGetComponent<Edge>(buffer[i + 1].m_Edge, out component8) && (component7.m_Start == component8.m_Start || component7.m_Start == component8.m_End))
					{
						flag4 = true;
					}
					if (flag && entityManager.TryGetComponent<Edge>(aggregateElement.m_Edge, out var component9) && entityManager.TryGetComponent<Roundabout>(flag4 ? component9.m_End : component9.m_Start, out var component10))
					{
						num += component10.m_Radius;
					}
					if (flag3)
					{
						Bounds1 t = new Bounds1(flag4 ? curvePos : 0f, flag4 ? 1f : curvePos);
						float num5 = math.saturate(MathUtils.Length(component2.m_Bezier, t) / math.max(1f, component2.m_Length));
						float num6 = math.lerp(num, num2, num5);
						bool flag5 = false;
						if (entityManager.TryGetComponent<Game.Objects.Transform>(entity, out var component11))
						{
							if (num5 < 0.01f && entityManager.TryGetComponent<Edge>(aggregateElement.m_Edge, out var component12) && entityManager.TryGetComponent<Roundabout>(component12.m_Start, out var component13) && entityManager.TryGetComponent<PrefabRef>(entity, out var component14) && entityManager.TryGetComponent<BuildingData>(component14.m_Prefab, out var component15))
							{
								float3 @float = CalculateFrontPosition(component11, component15.m_LotSize.y);
								float2 value = MathUtils.StartTangent(component2.m_Bezier).xz;
								if (MathUtils.TryNormalize(ref value))
								{
									float valueToClamp = math.dot(value, component2.m_Bezier.a.xz - @float.xz);
									valueToClamp = math.clamp(valueToClamp, 0f, component13.m_Radius);
									num6 += math.select(0f - valueToClamp, valueToClamp, flag4);
								}
							}
							if (num5 > 0.99f && entityManager.TryGetComponent<Edge>(aggregateElement.m_Edge, out var component16) && entityManager.TryGetComponent<Roundabout>(component16.m_End, out var component17) && entityManager.TryGetComponent<PrefabRef>(entity, out var component18) && entityManager.TryGetComponent<BuildingData>(component18.m_Prefab, out var component19))
							{
								float3 float2 = CalculateFrontPosition(component11, component19.m_LotSize.y);
								float2 value2 = MathUtils.EndTangent(component2.m_Bezier).xz;
								if (MathUtils.TryNormalize(ref value2))
								{
									float valueToClamp2 = math.dot(value2, float2.xz - component2.m_Bezier.d.xz);
									valueToClamp2 = math.clamp(valueToClamp2, 0f, component17.m_Radius);
									num6 += math.select(valueToClamp2, 0f - valueToClamp2, flag4);
								}
							}
							float2 x2 = component11.m_Position.xz - MathUtils.Position(component2.m_Bezier, curvePos).xz;
							float2 y2 = MathUtils.Right(MathUtils.Tangent(component2.m_Bezier, curvePos).xz);
							flag5 = math.dot(x2, y2) > 0f != flag4;
						}
						road = component.m_Aggregate;
						number = Mathf.RoundToInt(num6 / 8f) * 2 + ((!flag5) ? 1 : 2);
						return true;
					}
				}
				num = num2;
			}
		}
		road = Entity.Null;
		number = 0;
		return false;
	}
```

- `public static GetAddress(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Unity.Entities.Entity edge, System.Single curvePos, Unity.Entities.Entity& road, System.Int32& number) : System.Boolean`  

```csharp
public static bool GetAddress(EntityManager entityManager, Entity entity, Entity edge, float curvePos, out Entity road, out int number)
	{
		if (entityManager.TryGetComponent<Aggregated>(edge, out var component) && entityManager.TryGetBuffer(component.m_Aggregate, isReadOnly: true, out DynamicBuffer<AggregateElement> buffer))
		{
			float num = 0f;
			for (int i = 0; i < buffer.Length; i++)
			{
				AggregateElement aggregateElement = buffer[i];
				float num2 = num;
				if (entityManager.TryGetComponent<Curve>(aggregateElement.m_Edge, out var component2) && entityManager.TryGetComponent<Composition>(aggregateElement.m_Edge, out var component3) && entityManager.TryGetComponent<NetCompositionData>(component3.m_Edge, out var component4))
				{
					float2 x = math.normalizesafe(MathUtils.StartTangent(component2.m_Bezier).xz);
					float2 y = math.normalizesafe(MathUtils.EndTangent(component2.m_Bezier).xz);
					float num3 = ZoneUtils.GetCellWidth(component4.m_Width);
					float num4 = math.acos(math.clamp(math.dot(x, y), -1f, 1f));
					num2 += component2.m_Length + num3 * num4 * 0.5f;
				}
				bool flag = i == 0;
				bool flag2 = i == buffer.Length - 1;
				bool flag3 = aggregateElement.m_Edge == edge;
				bool flag4 = false;
				if (flag3 || flag || flag2)
				{
					Edge component7;
					Edge component8;
					if (!flag)
					{
						if (entityManager.TryGetComponent<Edge>(aggregateElement.m_Edge, out var component5) && entityManager.TryGetComponent<Edge>(buffer[i - 1].m_Edge, out var component6) && (component5.m_End == component6.m_Start || component5.m_End == component6.m_End))
						{
							flag4 = true;
						}
					}
					else if (!flag2 && entityManager.TryGetComponent<Edge>(aggregateElement.m_Edge, out component7) && entityManager.TryGetComponent<Edge>(buffer[i + 1].m_Edge, out component8) && (component7.m_Start == component8.m_Start || component7.m_Start == component8.m_End))
					{
						flag4 = true;
					}
					if (flag && entityManager.TryGetComponent<Edge>(aggregateElement.m_Edge, out var component9) && entityManager.TryGetComponent<Roundabout>(flag4 ? component9.m_End : component9.m_Start, out var component10))
					{
						num += component10.m_Radius;
					}
					if (flag3)
					{
						Bounds1 t = new Bounds1(flag4 ? curvePos : 0f, flag4 ? 1f : curvePos);
						float num5 = math.saturate(MathUtils.Length(component2.m_Bezier, t) / math.max(1f, component2.m_Length));
						float num6 = math.lerp(num, num2, num5);
						bool flag5 = false;
						if (entityManager.TryGetComponent<Game.Objects.Transform>(entity, out var component11))
						{
							if (num5 < 0.01f && entityManager.TryGetComponent<Edge>(aggregateElement.m_Edge, out var component12) && entityManager.TryGetComponent<Roundabout>(component12.m_Start, out var component13) && entityManager.TryGetComponent<PrefabRef>(entity, out var component14) && entityManager.TryGetComponent<BuildingData>(component14.m_Prefab, out var component15))
							{
								float3 @float = CalculateFrontPosition(component11, component15.m_LotSize.y);
								float2 value = MathUtils.StartTangent(component2.m_Bezier).xz;
								if (MathUtils.TryNormalize(ref value))
								{
									float valueToClamp = math.dot(value, component2.m_Bezier.a.xz - @float.xz);
									valueToClamp = math.clamp(valueToClamp, 0f, component13.m_Radius);
									num6 += math.select(0f - valueToClamp, valueToClamp, flag4);
								}
							}
							if (num5 > 0.99f && entityManager.TryGetComponent<Edge>(aggregateElement.m_Edge, out var component16) && entityManager.TryGetComponent<Roundabout>(component16.m_End, out var component17) && entityManager.TryGetComponent<PrefabRef>(entity, out var component18) && entityManager.TryGetComponent<BuildingData>(component18.m_Prefab, out var component19))
							{
								float3 float2 = CalculateFrontPosition(component11, component19.m_LotSize.y);
								float2 value2 = MathUtils.EndTangent(component2.m_Bezier).xz;
								if (MathUtils.TryNormalize(ref value2))
								{
									float valueToClamp2 = math.dot(value2, float2.xz - component2.m_Bezier.d.xz);
									valueToClamp2 = math.clamp(valueToClamp2, 0f, component17.m_Radius);
									num6 += math.select(valueToClamp2, 0f - valueToClamp2, flag4);
								}
							}
							float2 x2 = component11.m_Position.xz - MathUtils.Position(component2.m_Bezier, curvePos).xz;
							float2 y2 = MathUtils.Right(MathUtils.Tangent(component2.m_Bezier, curvePos).xz);
							flag5 = math.dot(x2, y2) > 0f != flag4;
						}
						road = component.m_Aggregate;
						number = Mathf.RoundToInt(num6 / 8f) * 2 + ((!flag5) ? 1 : 2);
						return true;
					}
				}
				num = num2;
			}
		}
		road = Entity.Null;
		number = 0;
		return false;
	}
```

- `public static GetAreaType(Unity.Entities.Entity buildPrefab, Unity.Entities.ComponentLookup`1[[Game.Prefabs.SpawnableBuildingData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& spawnableBuildingDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ZoneData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& zoneDatas) : Game.Zones.AreaType`  

```csharp
public static AreaType GetAreaType(Entity buildPrefab, ref ComponentLookup<SpawnableBuildingData> spawnableBuildingDatas, ref ComponentLookup<ZoneData> zoneDatas)
	{
		if (spawnableBuildingDatas.HasComponent(buildPrefab) && zoneDatas.HasComponent(spawnableBuildingDatas[buildPrefab].m_ZonePrefab))
		{
			return zoneDatas[spawnableBuildingDatas[buildPrefab].m_ZonePrefab].m_AreaType;
		}
		return AreaType.None;
	}
```

- `public static GetCollapseHeight(System.Single time) : System.Single`  

```csharp
public static float GetCollapseHeight(float time)
	{
		return 2.5f * math.lengthsq(time);
	}
```

- `public static GetCollapseTime(System.Single height) : System.Single`  

```csharp
public static float GetCollapseTime(float height)
	{
		return math.sqrt(math.max(0f, height) * 0.4f);
	}
```

- `public static GetEfficiency(Unity.Entities.BufferAccessor<Game.Buildings.Efficiency> bufferAccessor, System.Int32 i) : System.Single`  

```csharp
public static float GetEfficiency(byte rawValue)
	{
		return (float)(int)rawValue / 100f;
	}
```

- `public static GetEfficiency(Unity.Entities.Entity entity, Unity.Entities.BufferLookup`1[[Game.Buildings.Efficiency, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& bufferLookup) : System.Single`  

```csharp
public static float GetEfficiency(byte rawValue)
	{
		return (float)(int)rawValue / 100f;
	}
```

- `public static GetEfficiency(Unity.Entities.DynamicBuffer<Game.Buildings.Efficiency> buffer) : System.Single`  

```csharp
public static float GetEfficiency(byte rawValue)
	{
		return (float)(int)rawValue / 100f;
	}
```

- `public static GetEfficiency(System.Span<System.Single> factors) : System.Single`  

```csharp
public static float GetEfficiency(byte rawValue)
	{
		return (float)(int)rawValue / 100f;
	}
```

- `public static GetEfficiency(System.Byte rawValue) : System.Single`  

```csharp
public static float GetEfficiency(byte rawValue)
	{
		return (float)(int)rawValue / 100f;
	}
```

- `public static GetEfficiencyFactors(Unity.Entities.DynamicBuffer<Game.Buildings.Efficiency> buffer, System.Span<System.Single> factors) : System.Void`  

```csharp
public static void GetEfficiencyFactors(DynamicBuffer<Efficiency> buffer, Span<float> factors)
	{
		factors.Fill(1f);
		foreach (Efficiency item in buffer)
		{
			factors[(int)item.m_Factor] = item.m_Efficiency;
		}
	}
```

- `public static GetHouseholdHomeBuilding(Unity.Entities.Entity householdEntity, Unity.Entities.ComponentLookup`1[[Game.Buildings.PropertyRenter, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& propertyRenters, Unity.Entities.ComponentLookup`1[[Game.Citizens.HomelessHousehold, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& homelessHouseholds) : Unity.Entities.Entity`  

```csharp
public static Entity GetHouseholdHomeBuilding(Entity householdEntity, ref ComponentLookup<PropertyRenter> propertyRenters, ref ComponentLookup<HomelessHousehold> homelessHouseholds, ref ComponentLookup<TouristHousehold> touristHouseholds)
	{
		if (propertyRenters.TryGetComponent(householdEntity, out var componentData))
		{
			return componentData.m_Property;
		}
		if (touristHouseholds.TryGetComponent(householdEntity, out var componentData2) && propertyRenters.TryGetComponent(componentData2.m_Hotel, out componentData))
		{
			return componentData.m_Property;
		}
		if (homelessHouseholds.TryGetComponent(householdEntity, out var componentData3))
		{
			return componentData3.m_TempHome;
		}
		return Entity.Null;
	}
```

- `public static GetHouseholdHomeBuilding(Unity.Entities.Entity householdEntity, Unity.Entities.ComponentLookup`1[[Game.Buildings.PropertyRenter, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& propertyRenters, Unity.Entities.ComponentLookup`1[[Game.Citizens.HomelessHousehold, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& homelessHouseholds, Unity.Entities.ComponentLookup`1[[Game.Citizens.TouristHousehold, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& touristHouseholds) : Unity.Entities.Entity`  

```csharp
public static Entity GetHouseholdHomeBuilding(Entity householdEntity, ref ComponentLookup<PropertyRenter> propertyRenters, ref ComponentLookup<HomelessHousehold> homelessHouseholds, ref ComponentLookup<TouristHousehold> touristHouseholds)
	{
		if (propertyRenters.TryGetComponent(householdEntity, out var componentData))
		{
			return componentData.m_Property;
		}
		if (touristHouseholds.TryGetComponent(householdEntity, out var componentData2) && propertyRenters.TryGetComponent(componentData2.m_Hotel, out componentData))
		{
			return componentData.m_Property;
		}
		if (homelessHouseholds.TryGetComponent(householdEntity, out var componentData3))
		{
			return componentData3.m_TempHome;
		}
		return Entity.Null;
	}
```

- `public static GetImmediateEfficiency(Unity.Entities.BufferAccessor<Game.Buildings.Efficiency> bufferAccessor, System.Int32 i) : System.Single`  

```csharp
public static float GetImmediateEfficiency(DynamicBuffer<Efficiency> buffer)
	{
		float num = 1f;
		foreach (Efficiency item in buffer)
		{
			EfficiencyFactor factor = item.m_Factor;
			if (factor <= EfficiencyFactor.Disabled || factor == EfficiencyFactor.ServiceBudget)
			{
				num *= math.max(0f, item.m_Efficiency);
			}
		}
		if (!(num > 0f))
		{
			return 0f;
		}
		return math.max(0.01f, math.round(100f * num) / 100f);
	}
```

- `public static GetImmediateEfficiency(Unity.Entities.DynamicBuffer<Game.Buildings.Efficiency> buffer) : System.Single`  

```csharp
public static float GetImmediateEfficiency(DynamicBuffer<Efficiency> buffer)
	{
		float num = 1f;
		foreach (Efficiency item in buffer)
		{
			EfficiencyFactor factor = item.m_Factor;
			if (factor <= EfficiencyFactor.Disabled || factor == EfficiencyFactor.ServiceBudget)
			{
				num *= math.max(0f, item.m_Efficiency);
			}
		}
		if (!(num > 0f))
		{
			return 0f;
		}
		return math.max(0.01f, math.round(100f * num) / 100f);
	}
```

- `public static GetLevelingCost(Game.Zones.AreaType areaType, Game.Prefabs.BuildingPropertyData propertyData, System.Int32 currentlevel, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityEffects) : System.Int32`  

```csharp
public static int GetLevelingCost(AreaType areaType, BuildingPropertyData propertyData, int currentlevel, DynamicBuffer<CityModifier> cityEffects)
	{
		int num = propertyData.CountProperties();
		float num2 = 0f;
		switch (areaType)
		{
		case AreaType.Residential:
			num2 = ((currentlevel <= 4) ? (num * Mathf.RoundToInt(math.pow(2f, 2 * currentlevel) * 40f)) : 1073741823);
			break;
		case AreaType.Commercial:
		case AreaType.Industrial:
			num2 = ((currentlevel <= 4) ? (num * Mathf.RoundToInt(math.pow(2f, 2 * currentlevel) * 160f)) : 1073741823);
			if (propertyData.m_AllowedStored != Resource.NoResource)
			{
				num2 *= 4f;
			}
			break;
		default:
			num2 = 1.0737418E+09f;
			break;
		}
		CityUtils.ApplyModifier(ref num2, cityEffects, CityModifierType.BuildingLevelingCost);
		return Mathf.RoundToInt(num2);
	}
```

- `public static GetMaintenanceType(Unity.Entities.Entity entity, Unity.Entities.ComponentLookup`1[[Game.Buildings.Park, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parks, Unity.Entities.ComponentLookup`1[[Game.Net.NetCondition, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& netConditions, Unity.Entities.ComponentLookup`1[[Game.Net.Edge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edges, Unity.Entities.ComponentLookup`1[[Game.Objects.Surface, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& surfaces, Unity.Entities.ComponentLookup`1[[Game.Vehicles.Vehicle, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& vehicles) : Game.Simulation.MaintenanceType`  

```csharp
public static MaintenanceType GetMaintenanceType(Entity entity, ref ComponentLookup<Park> parks, ref ComponentLookup<NetCondition> netConditions, ref ComponentLookup<Edge> edges, ref ComponentLookup<Surface> surfaces, ref ComponentLookup<Vehicle> vehicles)
	{
		if (parks.HasComponent(entity))
		{
			return MaintenanceType.Park;
		}
		if (netConditions.HasComponent(entity))
		{
			if (!surfaces.TryGetComponent(entity, out var componentData) && edges.TryGetComponent(entity, out var componentData2) && surfaces.TryGetComponent(componentData2.m_Start, out var componentData3) && surfaces.TryGetComponent(componentData2.m_End, out var componentData4))
			{
				componentData.m_AccumulatedSnow = (byte)(componentData3.m_AccumulatedSnow + componentData4.m_AccumulatedSnow + 1 >> 1);
			}
			if (componentData.m_AccumulatedSnow >= 15)
			{
				return MaintenanceType.Snow;
			}
			return MaintenanceType.Road;
		}
		if (vehicles.HasComponent(entity))
		{
			return MaintenanceType.Vehicle;
		}
		return MaintenanceType.None;
	}
```

- `public static GetOutsideConnectionType(Unity.Entities.Entity building, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.OutsideConnectionData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& outsideConnectionDatas) : Game.Prefabs.OutsideConnectionTransferType`  

```csharp
public static OutsideConnectionTransferType GetOutsideConnectionType(Entity building, ref ComponentLookup<PrefabRef> prefabRefs, ref ComponentLookup<OutsideConnectionData> outsideConnectionDatas)
	{
		if (outsideConnectionDatas.HasComponent(prefabRefs[building].m_Prefab))
		{
			return outsideConnectionDatas[prefabRefs[building].m_Prefab].m_Type;
		}
		return OutsideConnectionTransferType.None;
	}
```

- `public static GetPropertyFromRenter(Unity.Entities.Entity renter, Unity.Entities.ComponentLookup`1[[Game.Citizens.HomelessHousehold, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& homelessHouseholds, Unity.Entities.ComponentLookup`1[[Game.Buildings.PropertyRenter, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& propertyRenters) : Unity.Entities.Entity`  

```csharp
public static Entity GetPropertyFromRenter(Entity renter, ref ComponentLookup<HomelessHousehold> homelessHouseholds, ref ComponentLookup<PropertyRenter> propertyRenters)
	{
		if (homelessHouseholds.HasComponent(renter))
		{
			return homelessHouseholds[renter].m_TempHome;
		}
		if (propertyRenters.HasComponent(renter))
		{
			return propertyRenters[renter].m_Property;
		}
		return Entity.Null;
	}
```

- `public static GetRandomOutsideConnectionByParameters(Unity.Collections.NativeList`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& outsideConnections, Unity.Entities.ComponentLookup`1[[Game.Prefabs.OutsideConnectionData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& outsideConnectionDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Unity.Mathematics.Random random, Unity.Mathematics.float4 outsideConnectionSpawnParameters, Unity.Entities.Entity& result) : System.Boolean`  

```csharp
public static bool GetRandomOutsideConnectionByParameters(ref NativeList<Entity> outsideConnections, ref ComponentLookup<OutsideConnectionData> outsideConnectionDatas, ref ComponentLookup<PrefabRef> prefabRefs, Unity.Mathematics.Random random, float4 outsideConnectionSpawnParameters, out Entity result)
	{
		OutsideConnectionTransferType ocTransferType = OutsideConnectionTransferType.None;
		float num = random.NextFloat(1f);
		if (num < outsideConnectionSpawnParameters.x)
		{
			ocTransferType = OutsideConnectionTransferType.Road;
		}
		else if (num < outsideConnectionSpawnParameters.x + outsideConnectionSpawnParameters.y)
		{
			ocTransferType = OutsideConnectionTransferType.Train;
		}
		else if (num < outsideConnectionSpawnParameters.x + outsideConnectionSpawnParameters.y + outsideConnectionSpawnParameters.z)
		{
			ocTransferType = OutsideConnectionTransferType.Air;
		}
		else if (num < outsideConnectionSpawnParameters.x + outsideConnectionSpawnParameters.y + outsideConnectionSpawnParameters.z + outsideConnectionSpawnParameters.w)
		{
			ocTransferType = OutsideConnectionTransferType.Ship;
		}
		return GetRandomOutsideConnectionByTransferType(ref outsideConnections, ref outsideConnectionDatas, ref prefabRefs, random, ocTransferType, out result);
	}
```

- `public static GetRandomOutsideConnectionByTransferType(Unity.Collections.NativeList`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& outsideConnections, Unity.Entities.ComponentLookup`1[[Game.Prefabs.OutsideConnectionData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& outsideConnectionDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Unity.Mathematics.Random random, Game.Prefabs.OutsideConnectionTransferType ocTransferType, Unity.Entities.Entity& result) : System.Boolean`  

```csharp
public static bool GetRandomOutsideConnectionByTransferType(ref NativeList<Entity> outsideConnections, ref ComponentLookup<OutsideConnectionData> outsideConnectionDatas, ref ComponentLookup<PrefabRef> prefabRefs, Unity.Mathematics.Random random, OutsideConnectionTransferType ocTransferType, out Entity result)
	{
		NativeList<Entity> nativeList = new NativeList<Entity>(Allocator.Temp);
		if (ocTransferType != OutsideConnectionTransferType.None)
		{
			for (int i = 0; i < outsideConnections.Length; i++)
			{
				Entity prefab = prefabRefs[outsideConnections[i]].m_Prefab;
				if (outsideConnectionDatas.HasComponent(prefab) && (ocTransferType & outsideConnectionDatas[prefab].m_Type) != OutsideConnectionTransferType.None)
				{
					nativeList.Add(outsideConnections[i]);
				}
			}
		}
		result = Entity.Null;
		if (nativeList.Length > 0)
		{
			result = nativeList[random.NextInt(nativeList.Length)];
			return true;
		}
		return false;
	}
```

- `public static GetShelterHomelessCapacity(Unity.Entities.Entity buildingPrefabEntity, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildingDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingPropertyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildingPropertyDatas) : System.Int32`  

```csharp
public static int GetShelterHomelessCapacity(Entity buildingPrefabEntity, ref ComponentLookup<BuildingData> buildingDatas, ref ComponentLookup<BuildingPropertyData> buildingPropertyDatas)
	{
		if (!buildingDatas.HasComponent(buildingPrefabEntity))
		{
			return 0;
		}
		BuildingData buildingData = buildingDatas[buildingPrefabEntity];
		int num = buildingData.m_LotSize.x * buildingData.m_LotSize.y;
		if (!buildingPropertyDatas.HasComponent(buildingPrefabEntity))
		{
			return num / 4;
		}
		BuildingPropertyData buildingPropertyData = buildingPropertyDatas[buildingPrefabEntity];
		float num2 = buildingPropertyData.m_ResidentialProperties;
		if (buildingPropertyData.m_AllowedSold != Resource.NoResource || buildingPropertyData.m_AllowedManufactured != Resource.NoResource || buildingPropertyData.m_AllowedStored != Resource.NoResource)
		{
			num2 += buildingPropertyData.m_SpaceMultiplier * (float)num;
		}
		return Mathf.CeilToInt(num2 / 2f);
	}
```

- `public static GetVehicleCapacity(System.Single efficiency, System.Int32 capacity) : System.Int32`  

```csharp
public static int GetVehicleCapacity(float efficiency, int capacity)
	{
		return math.select(0, math.clamp(Mathf.RoundToInt(efficiency * (float)capacity), 1, capacity), efficiency > 0.001f && capacity > 0);
	}
```

- `public static HasOption(Game.Prefabs.BuildingOptionData optionData, Game.Buildings.BuildingOption option) : System.Boolean`  

```csharp
public static bool HasOption(BuildingOptionData optionData, BuildingOption option)
	{
		return (optionData.m_OptionMask & (uint)(1 << (int)option)) != 0;
	}
```

- `public static IsHomelessHousehold(Game.Citizens.Household household, Unity.Entities.Entity propertyEntity, Unity.Entities.ComponentLookup`1[[Game.Buildings.Park, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parks, Unity.Entities.ComponentLookup`1[[Game.Buildings.Abandoned, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& abandoneds) : System.Boolean`  

```csharp
public static bool IsHomelessHousehold(EntityManager entityManager, Entity householdEntity)
	{
		if (entityManager.TryGetComponent<Household>(householdEntity, out var component) && (component.m_Flags & HouseholdFlags.MovedIn) != HouseholdFlags.None && !entityManager.HasComponent<MovingAway>(householdEntity))
		{
			if (entityManager.TryGetComponent<PropertyRenter>(householdEntity, out var component2) && !(component2.m_Property == Entity.Null) && !entityManager.HasComponent<Park>(component2.m_Property))
			{
				return entityManager.HasComponent<Abandoned>(component2.m_Property);
			}
			return true;
		}
		return false;
	}
```

- `public static IsHomelessHousehold(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity householdEntity) : System.Boolean`  

```csharp
public static bool IsHomelessHousehold(EntityManager entityManager, Entity householdEntity)
	{
		if (entityManager.TryGetComponent<Household>(householdEntity, out var component) && (component.m_Flags & HouseholdFlags.MovedIn) != HouseholdFlags.None && !entityManager.HasComponent<MovingAway>(householdEntity))
		{
			if (entityManager.TryGetComponent<PropertyRenter>(householdEntity, out var component2) && !(component2.m_Property == Entity.Null) && !entityManager.HasComponent<Park>(component2.m_Property))
			{
				return entityManager.HasComponent<Abandoned>(component2.m_Property);
			}
			return true;
		}
		return false;
	}
```

- `public static IsHomelessShelterBuilding(Unity.Entities.Entity propertyEntity, Unity.Entities.ComponentLookup`1[[Game.Buildings.Park, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parks, Unity.Entities.ComponentLookup`1[[Game.Buildings.Abandoned, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& abandoneds) : System.Boolean`  

```csharp
public static bool IsHomelessShelterBuilding(EntityManager entityManager, Entity propertyEntity)
	{
		if (!entityManager.HasComponent<Park>(propertyEntity))
		{
			return entityManager.HasComponent<Abandoned>(propertyEntity);
		}
		return true;
	}
```

- `public static IsHomelessShelterBuilding(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity propertyEntity) : System.Boolean`  

```csharp
public static bool IsHomelessShelterBuilding(EntityManager entityManager, Entity propertyEntity)
	{
		if (!entityManager.HasComponent<Park>(propertyEntity))
		{
			return entityManager.HasComponent<Abandoned>(propertyEntity);
		}
		return true;
	}
```

- `public static SampleHeight(Game.Buildings.BuildingUtils+LotInfo& lotInfo, Unity.Mathematics.float3 position) : System.Single`  

```csharp
public static float SampleHeight(ref LotInfo lotInfo, float3 position)
	{
		position = math.mul(math.inverse(lotInfo.m_Rotation), position - lotInfo.m_Position);
		Bezier4x2 curve = new Bezier4x2(new float2(lotInfo.m_RightHeights.x, lotInfo.m_FrontHeights.x), new float2(lotInfo.m_RightHeights.y, lotInfo.m_LeftHeights.z), new float2(lotInfo.m_RightHeights.z, lotInfo.m_LeftHeights.y), new float2(lotInfo.m_BackHeights.x, lotInfo.m_LeftHeights.x));
		Bezier4x2 curve2 = new Bezier4x2(new float2(lotInfo.m_RightHeights.x, lotInfo.m_BackHeights.x), new float2(lotInfo.m_FrontHeights.z, lotInfo.m_BackHeights.y), new float2(lotInfo.m_FrontHeights.y, lotInfo.m_BackHeights.z), new float2(lotInfo.m_FrontHeights.x, lotInfo.m_LeftHeights.x));
		float2 @float = math.clamp(position.xz, -lotInfo.m_Extents, lotInfo.m_Extents);
		float2 float2 = 0.5f / math.max(0.01f, lotInfo.m_Extents);
		float2 float3 = position.xz * float2 + 0.5f;
		float2 float4 = math.saturate(float3);
		float2 x = position.xz - @float;
		float2 float5 = float3 - math.sign(x) * float2 * 2f;
		float2 float6 = (float5 - 0.5f) * (lotInfo.m_Extents * 2f);
		x = 8f - 8f / (1f + math.abs(x) * 0.125f);
		float4 falseValue = new float4(lotInfo.m_FlatX0.xy, lotInfo.m_FlatZ0.yx);
		float4 falseValue2 = new float4(lotInfo.m_FlatZ0.xy, lotInfo.m_FlatX0.yx);
		float4 falseValue3 = new float4(lotInfo.m_FlatX1.xy, lotInfo.m_FlatZ0.yz);
		float4 falseValue4 = new float4(lotInfo.m_FlatZ1.xy, lotInfo.m_FlatX0.yz);
		falseValue = math.select(falseValue, new float4(lotInfo.m_FlatX0.yy, lotInfo.m_FlatZ0.x, lotInfo.m_FlatZ1.x), @float.y > falseValue.w);
		falseValue2 = math.select(falseValue2, new float4(lotInfo.m_FlatZ0.yy, lotInfo.m_FlatX0.x, lotInfo.m_FlatX1.x), @float.x > falseValue2.w);
		falseValue3 = math.select(falseValue3, new float4(lotInfo.m_FlatX1.yy, lotInfo.m_FlatZ0.z, lotInfo.m_FlatZ1.z), @float.y > falseValue3.w);
		falseValue4 = math.select(falseValue4, new float4(lotInfo.m_FlatZ1.yy, lotInfo.m_FlatX0.z, lotInfo.m_FlatX1.z), @float.x > falseValue4.w);
		falseValue = math.select(falseValue, new float4(lotInfo.m_FlatX0.yz, lotInfo.m_FlatZ1.xy), @float.y > falseValue.w);
		falseValue2 = math.select(falseValue2, new float4(lotInfo.m_FlatZ0.yz, lotInfo.m_FlatX1.xy), @float.x > falseValue2.w);
		falseValue3 = math.select(falseValue3, new float4(lotInfo.m_FlatX1.yz, lotInfo.m_FlatZ1.zy), @float.y > falseValue3.w);
		falseValue4 = math.select(falseValue4, new float4(lotInfo.m_FlatZ1.yz, lotInfo.m_FlatX1.zy), @float.x > falseValue4.w);
		float4 start = new float4(falseValue.x, falseValue2.x, falseValue3.x, falseValue4.x);
		float4 end = new float4(falseValue.y, falseValue2.y, falseValue3.y, falseValue4.y);
		float4 float7 = new float4(falseValue.z, falseValue2.z, falseValue3.z, falseValue4.z);
		float4 float8 = new float4(falseValue.w, falseValue2.w, falseValue3.w, falseValue4.w);
		float4 t = (@float.yxyx - float7) / math.max(float8 - float7, 0.1f);
		t = math.lerp(start, end, t);
		t = math.saturate(new float4(t.xy - @float, @float - t.zw) / math.max(new float4(t.xy + lotInfo.m_Extents, lotInfo.m_Extents - t.zw), 0.1f));
		float4 t2 = (float6.yxyx - float7) / math.max(float8 - float7, 0.1f);
		t2 = math.lerp(start, end, t2);
		t2 = math.saturate(new float4(t2.xy - float6, float6 - t2.zw) / math.max(new float4(t2.xy + lotInfo.m_Extents, lotInfo.m_Extents - t2.zw), 0.1f));
		float4 float9 = new float4
		{
			xz = MathUtils.Position(curve, float4.y),
			yw = MathUtils.Position(curve2, float4.x)
		};
		float9 *= t;
		float9.xy += float9.zw;
		float4 float10 = new float4
		{
			xz = MathUtils.Position(curve, float5.y),
			yw = MathUtils.Position(curve2, float5.x)
		};
		float10 *= t2;
		float10.xy += float10.zw;
		float9.xy += (float9.xy - float10.xy) * x.xy * 0.5f;
		t.xy = math.max(t.xy, t.zw);
		t.xy /= math.max(1f, t.x + t.y);
		t.x = math.select(t.y, 1f - t.x, t.x > t.y);
		float9.x = math.lerp(float9.x, float9.y, t.x);
		position.y = float9.x;
		return lotInfo.m_Position.y + position.y;
	}
```

- `public static SetEfficiencyFactor(Unity.Entities.DynamicBuffer<Game.Buildings.Efficiency> buffer, Game.Buildings.EfficiencyFactor factor, System.Single efficiency) : System.Void`  

```csharp
public static void SetEfficiencyFactor(DynamicBuffer<Efficiency> buffer, EfficiencyFactor factor, float efficiency)
	{
		for (int i = 0; i < buffer.Length; i++)
		{
			if (buffer[i].m_Factor == factor)
			{
				if (math.abs(efficiency - 1f) > 0.001f)
				{
					buffer[i] = new Efficiency(factor, efficiency);
				}
				else
				{
					buffer.RemoveAt(i);
				}
				return;
			}
		}
		if (math.abs(efficiency - 1f) > 0.001f)
		{
			buffer.Add(new Efficiency(factor, efficiency));
		}
	}
```

- `public static SetEfficiencyFactors(Unity.Entities.DynamicBuffer<Game.Buildings.Efficiency> buffer, System.Span<System.Single> factors) : System.Void`  

```csharp
public static void SetEfficiencyFactors(DynamicBuffer<Efficiency> buffer, Span<float> factors)
	{
		buffer.Clear();
		for (int i = 0; i < factors.Length; i++)
		{
			if ((double)math.abs(factors[i] - 1f) > 0.001)
			{
				buffer.Add(new Efficiency((EfficiencyFactor)i, factors[i]));
			}
		}
	}
```


## Nested types

- `Game.Buildings.BuildingUtils+LotInfo`  

