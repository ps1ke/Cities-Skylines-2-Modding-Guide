# Game.Buildings.ValidationHelpers

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class ValidationHelpers
{
    public static System.Void ValidateBuilding(Unity.Entities.Entity entity, Game.Buildings.Building building, Game.Objects.Transform transform, Game.Prefabs.PrefabRef prefabRef, Game.Tools.ValidationSystem+EntityData data, Unity.Collections.NativeArray<Game.Simulation.GroundWater> groundWaterMap, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue);
    public static System.Void ValidateUpgrade(Unity.Entities.Entity entity, Game.Common.Owner owner, Game.Prefabs.PrefabRef prefabRef, Game.Tools.ValidationSystem+EntityData data, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue);
}
```


## Methods

- `public static ValidateBuilding(Unity.Entities.Entity entity, Game.Buildings.Building building, Game.Objects.Transform transform, Game.Prefabs.PrefabRef prefabRef, Game.Tools.ValidationSystem+EntityData data, Unity.Collections.NativeArray<Game.Simulation.GroundWater> groundWaterMap, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue) : System.Void`  

```csharp
public static void ValidateBuilding(Entity entity, Building building, Transform transform, PrefabRef prefabRef, ValidationSystem.EntityData data, NativeArray<GroundWater> groundWaterMap, NativeQueue<ErrorData>.ParallelWriter errorQueue)
	{
		if (building.m_RoadEdge == Entity.Null)
		{
			BuildingData buildingData = data.m_PrefabBuilding[prefabRef.m_Prefab];
			if ((buildingData.m_Flags & Game.Prefabs.BuildingFlags.RequireRoad) != 0)
			{
				float3 position = BuildingUtils.CalculateFrontPosition(transform, buildingData.m_LotSize.y);
				errorQueue.Enqueue(new ErrorData
				{
					m_ErrorSeverity = ErrorSeverity.Warning,
					m_ErrorType = ErrorType.NoRoadAccess,
					m_TempEntity = entity,
					m_Position = position
				});
			}
		}
		if (((data.m_WaterPumpingStationData.TryGetComponent(prefabRef.m_Prefab, out var componentData) && (componentData.m_Types & AllowedWaterTypes.Groundwater) != AllowedWaterTypes.None) || data.m_GroundWaterPoweredData.HasComponent(prefabRef.m_Prefab)) && GroundWaterSystem.GetGroundWater(transform.m_Position, groundWaterMap).m_Max <= 500)
		{
			errorQueue.Enqueue(new ErrorData
			{
				m_ErrorSeverity = ErrorSeverity.Error,
				m_ErrorType = ErrorType.NoGroundWater,
				m_TempEntity = entity,
				m_Position = transform.m_Position
			});
		}
	}
```

- `public static ValidateUpgrade(Unity.Entities.Entity entity, Game.Common.Owner owner, Game.Prefabs.PrefabRef prefabRef, Game.Tools.ValidationSystem+EntityData data, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue) : System.Void`  

```csharp
public static void ValidateUpgrade(Entity entity, Owner owner, PrefabRef prefabRef, ValidationSystem.EntityData data, NativeQueue<ErrorData>.ParallelWriter errorQueue)
	{
		if (data.m_PrefabBuilding.HasComponent(prefabRef.m_Prefab) || !data.m_Upgrades.HasBuffer(owner.m_Owner))
		{
			return;
		}
		DynamicBuffer<InstalledUpgrade> dynamicBuffer = data.m_Upgrades[owner.m_Owner];
		for (int i = 0; i < dynamicBuffer.Length; i++)
		{
			Entity upgrade = dynamicBuffer[i].m_Upgrade;
			if (upgrade != entity && data.m_PrefabRef[upgrade].m_Prefab == prefabRef.m_Prefab)
			{
				errorQueue.Enqueue(new ErrorData
				{
					m_ErrorSeverity = ErrorSeverity.Error,
					m_ErrorType = ErrorType.AlreadyUpgraded,
					m_TempEntity = entity,
					m_PermanentEntity = owner.m_Owner,
					m_Position = data.m_Transform[owner.m_Owner].m_Position
				});
			}
		}
	}
```


