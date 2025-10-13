# Game.Prefabs.WorkVehicleSelectData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct WorkVehicleSelectData
{
    private Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> m_PrefabChunks;
    private Game.Prefabs.VehicleSelectRequirementData m_RequirementData;
    private Unity.Entities.EntityTypeHandle m_EntityType;
    private Unity.Entities.ComponentTypeHandle<Game.Prefabs.WorkVehicleData> m_WorkVehicleDataType;
    private Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarTrailerData> m_CarTrailerDataType;
    private Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarTractorData> m_CarTractorDataType;
    private Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarData> m_CarDataType;
    private Unity.Entities.ComponentTypeHandle<Game.Prefabs.WatercraftData> m_WatercraftDataType;
    private Unity.Entities.ComponentTypeHandle<Game.Prefabs.ObjectData> m_ObjectDataType;

    public WorkVehicleSelectData(Unity.Entities.SystemBase system);

    private System.Void CheckTractors(Game.Vehicles.VehicleWorkType workType, Game.Areas.MapFeature mapFeature, Game.Economy.Resource resource, Game.Prefabs.WorkVehicleSelectData+VehicleData secondData, Unity.Mathematics.Random& random, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestFirst, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestSecond, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestThird, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestForth, System.Int32& totalProbability);
    private System.Void CheckTractors(Game.Vehicles.VehicleWorkType workType, Game.Areas.MapFeature mapFeature, Game.Economy.Resource resource, Game.Prefabs.WorkVehicleSelectData+VehicleData secondData, Game.Prefabs.WorkVehicleSelectData+VehicleData thirdData, Unity.Mathematics.Random& random, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestFirst, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestSecond, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestThird, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestForth, System.Int32& totalProbability);
    private System.Void CheckTractors(Game.Vehicles.VehicleWorkType workType, Game.Areas.MapFeature mapFeature, Game.Economy.Resource resource, Game.Prefabs.WorkVehicleSelectData+VehicleData secondData, Game.Prefabs.WorkVehicleSelectData+VehicleData thirdData, Game.Prefabs.WorkVehicleSelectData+VehicleData forthData, Unity.Mathematics.Random& random, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestFirst, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestSecond, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestThird, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestForth, System.Int32& totalProbability);
    private System.Void CheckTrailers(Game.Vehicles.VehicleWorkType workType, Game.Areas.MapFeature mapFeature, Game.Economy.Resource resource, System.Boolean firstIsTrailer, Game.Prefabs.WorkVehicleSelectData+VehicleData firstData, Unity.Mathematics.Random& random, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestFirst, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestSecond, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestThird, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestForth, System.Int32& totalProbability);
    private System.Void CheckTrailers(Game.Vehicles.VehicleWorkType workType, Game.Areas.MapFeature mapFeature, Game.Economy.Resource resource, System.Boolean firstIsTrailer, Game.Prefabs.WorkVehicleSelectData+VehicleData firstData, Game.Prefabs.WorkVehicleSelectData+VehicleData secondData, Unity.Mathematics.Random& random, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestFirst, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestSecond, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestThird, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestForth, System.Int32& totalProbability);
    private System.Void CheckTrailers(Game.Vehicles.VehicleWorkType workType, Game.Areas.MapFeature mapFeature, Game.Economy.Resource resource, Game.Prefabs.WorkVehicleSelectData+VehicleData firstData, Game.Prefabs.WorkVehicleSelectData+VehicleData secondData, Game.Prefabs.WorkVehicleSelectData+VehicleData thirdData, Unity.Mathematics.Random& random, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestFirst, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestSecond, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestThird, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestForth, System.Int32& totalProbability);
    public Unity.Entities.Entity CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, Game.Net.RoadTypes roadTypes, Game.Vehicles.SizeClass sizeClass, Game.Vehicles.VehicleWorkType workType, Game.Areas.MapFeature mapFeature, Game.Economy.Resource resource, System.Single& workAmount, Game.Objects.Transform transform, Unity.Entities.Entity source, Game.Vehicles.WorkVehicleFlags state);
    private Unity.Entities.Entity CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, Game.Prefabs.WorkVehicleSelectData+VehicleData data, Game.Vehicles.VehicleWorkType workType, System.Single& workAmount, Game.Objects.Transform transform, Unity.Entities.Entity source, Game.Vehicles.WorkVehicleFlags state);
    public static Unity.Entities.EntityQueryDesc GetEntityQueryDesc();
    private System.Boolean PickVehicle(Unity.Mathematics.Random& random, System.Int32 probability, System.Int32& totalProbability);
    public System.Void PostUpdate(Unity.Jobs.JobHandle jobHandle);
    public System.Void PreUpdate(Unity.Entities.SystemBase system, Game.City.CityConfigurationSystem cityConfigurationSystem, Unity.Entities.EntityQuery query, Unity.Collections.Allocator allocator, Unity.Jobs.JobHandle& jobHandle);
}
```


## Fields

- `private Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> m_PrefabChunks`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> m_PrefabChunks;
```

- `private Game.Prefabs.VehicleSelectRequirementData m_RequirementData`  

```csharp
private Game.Prefabs.VehicleSelectRequirementData m_RequirementData;
```

- `private Unity.Entities.EntityTypeHandle m_EntityType`  

```csharp
private Unity.Entities.EntityTypeHandle m_EntityType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.WorkVehicleData> m_WorkVehicleDataType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Prefabs.WorkVehicleData> m_WorkVehicleDataType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarTrailerData> m_CarTrailerDataType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarTrailerData> m_CarTrailerDataType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarTractorData> m_CarTractorDataType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarTractorData> m_CarTractorDataType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarData> m_CarDataType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarData> m_CarDataType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.WatercraftData> m_WatercraftDataType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Prefabs.WatercraftData> m_WatercraftDataType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.ObjectData> m_ObjectDataType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Prefabs.ObjectData> m_ObjectDataType;
```


## Constructors

- `public WorkVehicleSelectData(Unity.Entities.SystemBase system)`  

```csharp
public WorkVehicleSelectData(SystemBase system)
	{
		m_PrefabChunks = default(NativeList<ArchetypeChunk>);
		m_RequirementData = new VehicleSelectRequirementData(system);
		m_EntityType = system.GetEntityTypeHandle();
		m_WorkVehicleDataType = system.GetComponentTypeHandle<WorkVehicleData>(isReadOnly: true);
		m_CarTrailerDataType = system.GetComponentTypeHandle<CarTrailerData>(isReadOnly: true);
		m_CarTractorDataType = system.GetComponentTypeHandle<CarTractorData>(isReadOnly: true);
		m_CarDataType = system.GetComponentTypeHandle<CarData>(isReadOnly: true);
		m_WatercraftDataType = system.GetComponentTypeHandle<WatercraftData>(isReadOnly: true);
		m_ObjectDataType = system.GetComponentTypeHandle<ObjectData>(isReadOnly: true);
	}
```


## Methods

- `private CheckTractors(Game.Vehicles.VehicleWorkType workType, Game.Areas.MapFeature mapFeature, Game.Economy.Resource resource, Game.Prefabs.WorkVehicleSelectData+VehicleData secondData, Unity.Mathematics.Random& random, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestFirst, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestSecond, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestThird, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestForth, System.Int32& totalProbability) : System.Void`  

```csharp
private void CheckTractors(VehicleWorkType workType, MapFeature mapFeature, Resource resource, VehicleData secondData, VehicleData thirdData, VehicleData forthData, ref Random random, ref VehicleData bestFirst, ref VehicleData bestSecond, ref VehicleData bestThird, ref VehicleData bestForth, ref int totalProbability)
	{
		for (int i = 0; i < m_PrefabChunks.Length; i++)
		{
			ArchetypeChunk chunk = m_PrefabChunks[i];
			NativeArray<CarTractorData> nativeArray = chunk.GetNativeArray(ref m_CarTractorDataType);
			if (nativeArray.Length == 0 || chunk.Has(ref m_CarTrailerDataType))
			{
				continue;
			}
			NativeArray<Entity> nativeArray2 = chunk.GetNativeArray(m_EntityType);
			NativeArray<WorkVehicleData> nativeArray3 = chunk.GetNativeArray(ref m_WorkVehicleDataType);
			NativeArray<ObjectData> nativeArray4 = chunk.GetNativeArray(ref m_ObjectDataType);
			VehicleSelectRequirementData.Chunk chunk2 = m_RequirementData.GetChunk(chunk);
			for (int j = 0; j < nativeArray.Length; j++)
			{
				VehicleData vehicleData = new VehicleData
				{
					m_WorkVehicleData = nativeArray3[j]
				};
				if ((vehicleData.m_WorkVehicleData.m_WorkType != VehicleWorkType.None && vehicleData.m_WorkVehicleData.m_WorkType != workType) || ((vehicleData.m_WorkVehicleData.m_MapFeature != MapFeature.None || vehicleData.m_WorkVehicleData.m_Resources != Resource.NoResource) && vehicleData.m_WorkVehicleData.m_MapFeature != mapFeature && (vehicleData.m_WorkVehicleData.m_Resources & resource) == Resource.NoResource) || !m_RequirementData.CheckRequirements(ref chunk2, j))
				{
					continue;
				}
				vehicleData.m_Entity = nativeArray2[j];
				vehicleData.m_TractorData = nativeArray[j];
				if (vehicleData.m_TractorData.m_TrailerType == secondData.m_TrailerData.m_TrailerType && (!(vehicleData.m_TractorData.m_FixedTrailer != Entity.Null) || !(vehicleData.m_TractorData.m_FixedTrailer != secondData.m_Entity)) && (!(secondData.m_TrailerData.m_FixedTractor != Entity.Null) || !(secondData.m_TrailerData.m_FixedTractor != vehicleData.m_Entity)))
				{
					vehicleData.m_ObjectData = nativeArray4[j];
					if (PickVehicle(ref random, 100, ref totalProbability))
					{
						bestFirst = vehicleData;
						bestSecond = secondData;
						bestThird = thirdData;
						bestForth = forthData;
					}
				}
			}
		}
	}
```

- `private CheckTractors(Game.Vehicles.VehicleWorkType workType, Game.Areas.MapFeature mapFeature, Game.Economy.Resource resource, Game.Prefabs.WorkVehicleSelectData+VehicleData secondData, Game.Prefabs.WorkVehicleSelectData+VehicleData thirdData, Unity.Mathematics.Random& random, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestFirst, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestSecond, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestThird, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestForth, System.Int32& totalProbability) : System.Void`  

```csharp
private void CheckTractors(VehicleWorkType workType, MapFeature mapFeature, Resource resource, VehicleData secondData, VehicleData thirdData, VehicleData forthData, ref Random random, ref VehicleData bestFirst, ref VehicleData bestSecond, ref VehicleData bestThird, ref VehicleData bestForth, ref int totalProbability)
	{
		for (int i = 0; i < m_PrefabChunks.Length; i++)
		{
			ArchetypeChunk chunk = m_PrefabChunks[i];
			NativeArray<CarTractorData> nativeArray = chunk.GetNativeArray(ref m_CarTractorDataType);
			if (nativeArray.Length == 0 || chunk.Has(ref m_CarTrailerDataType))
			{
				continue;
			}
			NativeArray<Entity> nativeArray2 = chunk.GetNativeArray(m_EntityType);
			NativeArray<WorkVehicleData> nativeArray3 = chunk.GetNativeArray(ref m_WorkVehicleDataType);
			NativeArray<ObjectData> nativeArray4 = chunk.GetNativeArray(ref m_ObjectDataType);
			VehicleSelectRequirementData.Chunk chunk2 = m_RequirementData.GetChunk(chunk);
			for (int j = 0; j < nativeArray.Length; j++)
			{
				VehicleData vehicleData = new VehicleData
				{
					m_WorkVehicleData = nativeArray3[j]
				};
				if ((vehicleData.m_WorkVehicleData.m_WorkType != VehicleWorkType.None && vehicleData.m_WorkVehicleData.m_WorkType != workType) || ((vehicleData.m_WorkVehicleData.m_MapFeature != MapFeature.None || vehicleData.m_WorkVehicleData.m_Resources != Resource.NoResource) && vehicleData.m_WorkVehicleData.m_MapFeature != mapFeature && (vehicleData.m_WorkVehicleData.m_Resources & resource) == Resource.NoResource) || !m_RequirementData.CheckRequirements(ref chunk2, j))
				{
					continue;
				}
				vehicleData.m_Entity = nativeArray2[j];
				vehicleData.m_TractorData = nativeArray[j];
				if (vehicleData.m_TractorData.m_TrailerType == secondData.m_TrailerData.m_TrailerType && (!(vehicleData.m_TractorData.m_FixedTrailer != Entity.Null) || !(vehicleData.m_TractorData.m_FixedTrailer != secondData.m_Entity)) && (!(secondData.m_TrailerData.m_FixedTractor != Entity.Null) || !(secondData.m_TrailerData.m_FixedTractor != vehicleData.m_Entity)))
				{
					vehicleData.m_ObjectData = nativeArray4[j];
					if (PickVehicle(ref random, 100, ref totalProbability))
					{
						bestFirst = vehicleData;
						bestSecond = secondData;
						bestThird = thirdData;
						bestForth = forthData;
					}
				}
			}
		}
	}
```

- `private CheckTractors(Game.Vehicles.VehicleWorkType workType, Game.Areas.MapFeature mapFeature, Game.Economy.Resource resource, Game.Prefabs.WorkVehicleSelectData+VehicleData secondData, Game.Prefabs.WorkVehicleSelectData+VehicleData thirdData, Game.Prefabs.WorkVehicleSelectData+VehicleData forthData, Unity.Mathematics.Random& random, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestFirst, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestSecond, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestThird, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestForth, System.Int32& totalProbability) : System.Void`  

```csharp
private void CheckTractors(VehicleWorkType workType, MapFeature mapFeature, Resource resource, VehicleData secondData, VehicleData thirdData, VehicleData forthData, ref Random random, ref VehicleData bestFirst, ref VehicleData bestSecond, ref VehicleData bestThird, ref VehicleData bestForth, ref int totalProbability)
	{
		for (int i = 0; i < m_PrefabChunks.Length; i++)
		{
			ArchetypeChunk chunk = m_PrefabChunks[i];
			NativeArray<CarTractorData> nativeArray = chunk.GetNativeArray(ref m_CarTractorDataType);
			if (nativeArray.Length == 0 || chunk.Has(ref m_CarTrailerDataType))
			{
				continue;
			}
			NativeArray<Entity> nativeArray2 = chunk.GetNativeArray(m_EntityType);
			NativeArray<WorkVehicleData> nativeArray3 = chunk.GetNativeArray(ref m_WorkVehicleDataType);
			NativeArray<ObjectData> nativeArray4 = chunk.GetNativeArray(ref m_ObjectDataType);
			VehicleSelectRequirementData.Chunk chunk2 = m_RequirementData.GetChunk(chunk);
			for (int j = 0; j < nativeArray.Length; j++)
			{
				VehicleData vehicleData = new VehicleData
				{
					m_WorkVehicleData = nativeArray3[j]
				};
				if ((vehicleData.m_WorkVehicleData.m_WorkType != VehicleWorkType.None && vehicleData.m_WorkVehicleData.m_WorkType != workType) || ((vehicleData.m_WorkVehicleData.m_MapFeature != MapFeature.None || vehicleData.m_WorkVehicleData.m_Resources != Resource.NoResource) && vehicleData.m_WorkVehicleData.m_MapFeature != mapFeature && (vehicleData.m_WorkVehicleData.m_Resources & resource) == Resource.NoResource) || !m_RequirementData.CheckRequirements(ref chunk2, j))
				{
					continue;
				}
				vehicleData.m_Entity = nativeArray2[j];
				vehicleData.m_TractorData = nativeArray[j];
				if (vehicleData.m_TractorData.m_TrailerType == secondData.m_TrailerData.m_TrailerType && (!(vehicleData.m_TractorData.m_FixedTrailer != Entity.Null) || !(vehicleData.m_TractorData.m_FixedTrailer != secondData.m_Entity)) && (!(secondData.m_TrailerData.m_FixedTractor != Entity.Null) || !(secondData.m_TrailerData.m_FixedTractor != vehicleData.m_Entity)))
				{
					vehicleData.m_ObjectData = nativeArray4[j];
					if (PickVehicle(ref random, 100, ref totalProbability))
					{
						bestFirst = vehicleData;
						bestSecond = secondData;
						bestThird = thirdData;
						bestForth = forthData;
					}
				}
			}
		}
	}
```

- `private CheckTrailers(Game.Vehicles.VehicleWorkType workType, Game.Areas.MapFeature mapFeature, Game.Economy.Resource resource, System.Boolean firstIsTrailer, Game.Prefabs.WorkVehicleSelectData+VehicleData firstData, Unity.Mathematics.Random& random, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestFirst, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestSecond, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestThird, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestForth, System.Int32& totalProbability) : System.Void`  

```csharp
private void CheckTrailers(VehicleWorkType workType, MapFeature mapFeature, Resource resource, VehicleData firstData, VehicleData secondData, VehicleData thirdData, ref Random random, ref VehicleData bestFirst, ref VehicleData bestSecond, ref VehicleData bestThird, ref VehicleData bestForth, ref int totalProbability)
	{
		for (int i = 0; i < m_PrefabChunks.Length; i++)
		{
			ArchetypeChunk chunk = m_PrefabChunks[i];
			NativeArray<CarTrailerData> nativeArray = chunk.GetNativeArray(ref m_CarTrailerDataType);
			if (nativeArray.Length == 0)
			{
				continue;
			}
			NativeArray<Entity> nativeArray2 = chunk.GetNativeArray(m_EntityType);
			NativeArray<WorkVehicleData> nativeArray3 = chunk.GetNativeArray(ref m_WorkVehicleDataType);
			NativeArray<CarTractorData> nativeArray4 = chunk.GetNativeArray(ref m_CarTractorDataType);
			NativeArray<ObjectData> nativeArray5 = chunk.GetNativeArray(ref m_ObjectDataType);
			VehicleSelectRequirementData.Chunk chunk2 = m_RequirementData.GetChunk(chunk);
			for (int j = 0; j < nativeArray.Length; j++)
			{
				VehicleData vehicleData = new VehicleData
				{
					m_WorkVehicleData = nativeArray3[j]
				};
				if ((vehicleData.m_WorkVehicleData.m_WorkType != VehicleWorkType.None && vehicleData.m_WorkVehicleData.m_WorkType != workType) || ((vehicleData.m_WorkVehicleData.m_MapFeature != MapFeature.None || vehicleData.m_WorkVehicleData.m_Resources != Resource.NoResource) && vehicleData.m_WorkVehicleData.m_MapFeature != mapFeature && (vehicleData.m_WorkVehicleData.m_Resources & resource) == Resource.NoResource) || vehicleData.m_WorkVehicleData.m_MaxWorkAmount != 0f || !m_RequirementData.CheckRequirements(ref chunk2, j))
				{
					continue;
				}
				vehicleData.m_Entity = nativeArray2[j];
				vehicleData.m_TrailerData = nativeArray[j];
				if (thirdData.m_TractorData.m_TrailerType != vehicleData.m_TrailerData.m_TrailerType || (thirdData.m_TractorData.m_FixedTrailer != Entity.Null && thirdData.m_TractorData.m_FixedTrailer != vehicleData.m_Entity) || (vehicleData.m_TrailerData.m_FixedTractor != Entity.Null && vehicleData.m_TrailerData.m_FixedTractor != thirdData.m_Entity))
				{
					continue;
				}
				vehicleData.m_ObjectData = nativeArray5[j];
				if (nativeArray4.Length != 0)
				{
					vehicleData.m_TractorData = nativeArray4[j];
					if (vehicleData.m_TractorData.m_FixedTrailer != Entity.Null)
					{
						continue;
					}
				}
				if (PickVehicle(ref random, 100, ref totalProbability))
				{
					bestFirst = firstData;
					bestSecond = secondData;
					bestThird = thirdData;
					bestForth = vehicleData;
				}
			}
		}
	}
```

- `private CheckTrailers(Game.Vehicles.VehicleWorkType workType, Game.Areas.MapFeature mapFeature, Game.Economy.Resource resource, System.Boolean firstIsTrailer, Game.Prefabs.WorkVehicleSelectData+VehicleData firstData, Game.Prefabs.WorkVehicleSelectData+VehicleData secondData, Unity.Mathematics.Random& random, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestFirst, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestSecond, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestThird, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestForth, System.Int32& totalProbability) : System.Void`  

```csharp
private void CheckTrailers(VehicleWorkType workType, MapFeature mapFeature, Resource resource, VehicleData firstData, VehicleData secondData, VehicleData thirdData, ref Random random, ref VehicleData bestFirst, ref VehicleData bestSecond, ref VehicleData bestThird, ref VehicleData bestForth, ref int totalProbability)
	{
		for (int i = 0; i < m_PrefabChunks.Length; i++)
		{
			ArchetypeChunk chunk = m_PrefabChunks[i];
			NativeArray<CarTrailerData> nativeArray = chunk.GetNativeArray(ref m_CarTrailerDataType);
			if (nativeArray.Length == 0)
			{
				continue;
			}
			NativeArray<Entity> nativeArray2 = chunk.GetNativeArray(m_EntityType);
			NativeArray<WorkVehicleData> nativeArray3 = chunk.GetNativeArray(ref m_WorkVehicleDataType);
			NativeArray<CarTractorData> nativeArray4 = chunk.GetNativeArray(ref m_CarTractorDataType);
			NativeArray<ObjectData> nativeArray5 = chunk.GetNativeArray(ref m_ObjectDataType);
			VehicleSelectRequirementData.Chunk chunk2 = m_RequirementData.GetChunk(chunk);
			for (int j = 0; j < nativeArray.Length; j++)
			{
				VehicleData vehicleData = new VehicleData
				{
					m_WorkVehicleData = nativeArray3[j]
				};
				if ((vehicleData.m_WorkVehicleData.m_WorkType != VehicleWorkType.None && vehicleData.m_WorkVehicleData.m_WorkType != workType) || ((vehicleData.m_WorkVehicleData.m_MapFeature != MapFeature.None || vehicleData.m_WorkVehicleData.m_Resources != Resource.NoResource) && vehicleData.m_WorkVehicleData.m_MapFeature != mapFeature && (vehicleData.m_WorkVehicleData.m_Resources & resource) == Resource.NoResource) || vehicleData.m_WorkVehicleData.m_MaxWorkAmount != 0f || !m_RequirementData.CheckRequirements(ref chunk2, j))
				{
					continue;
				}
				vehicleData.m_Entity = nativeArray2[j];
				vehicleData.m_TrailerData = nativeArray[j];
				if (thirdData.m_TractorData.m_TrailerType != vehicleData.m_TrailerData.m_TrailerType || (thirdData.m_TractorData.m_FixedTrailer != Entity.Null && thirdData.m_TractorData.m_FixedTrailer != vehicleData.m_Entity) || (vehicleData.m_TrailerData.m_FixedTractor != Entity.Null && vehicleData.m_TrailerData.m_FixedTractor != thirdData.m_Entity))
				{
					continue;
				}
				vehicleData.m_ObjectData = nativeArray5[j];
				if (nativeArray4.Length != 0)
				{
					vehicleData.m_TractorData = nativeArray4[j];
					if (vehicleData.m_TractorData.m_FixedTrailer != Entity.Null)
					{
						continue;
					}
				}
				if (PickVehicle(ref random, 100, ref totalProbability))
				{
					bestFirst = firstData;
					bestSecond = secondData;
					bestThird = thirdData;
					bestForth = vehicleData;
				}
			}
		}
	}
```

- `private CheckTrailers(Game.Vehicles.VehicleWorkType workType, Game.Areas.MapFeature mapFeature, Game.Economy.Resource resource, Game.Prefabs.WorkVehicleSelectData+VehicleData firstData, Game.Prefabs.WorkVehicleSelectData+VehicleData secondData, Game.Prefabs.WorkVehicleSelectData+VehicleData thirdData, Unity.Mathematics.Random& random, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestFirst, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestSecond, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestThird, Game.Prefabs.WorkVehicleSelectData+VehicleData& bestForth, System.Int32& totalProbability) : System.Void`  

```csharp
private void CheckTrailers(VehicleWorkType workType, MapFeature mapFeature, Resource resource, VehicleData firstData, VehicleData secondData, VehicleData thirdData, ref Random random, ref VehicleData bestFirst, ref VehicleData bestSecond, ref VehicleData bestThird, ref VehicleData bestForth, ref int totalProbability)
	{
		for (int i = 0; i < m_PrefabChunks.Length; i++)
		{
			ArchetypeChunk chunk = m_PrefabChunks[i];
			NativeArray<CarTrailerData> nativeArray = chunk.GetNativeArray(ref m_CarTrailerDataType);
			if (nativeArray.Length == 0)
			{
				continue;
			}
			NativeArray<Entity> nativeArray2 = chunk.GetNativeArray(m_EntityType);
			NativeArray<WorkVehicleData> nativeArray3 = chunk.GetNativeArray(ref m_WorkVehicleDataType);
			NativeArray<CarTractorData> nativeArray4 = chunk.GetNativeArray(ref m_CarTractorDataType);
			NativeArray<ObjectData> nativeArray5 = chunk.GetNativeArray(ref m_ObjectDataType);
			VehicleSelectRequirementData.Chunk chunk2 = m_RequirementData.GetChunk(chunk);
			for (int j = 0; j < nativeArray.Length; j++)
			{
				VehicleData vehicleData = new VehicleData
				{
					m_WorkVehicleData = nativeArray3[j]
				};
				if ((vehicleData.m_WorkVehicleData.m_WorkType != VehicleWorkType.None && vehicleData.m_WorkVehicleData.m_WorkType != workType) || ((vehicleData.m_WorkVehicleData.m_MapFeature != MapFeature.None || vehicleData.m_WorkVehicleData.m_Resources != Resource.NoResource) && vehicleData.m_WorkVehicleData.m_MapFeature != mapFeature && (vehicleData.m_WorkVehicleData.m_Resources & resource) == Resource.NoResource) || vehicleData.m_WorkVehicleData.m_MaxWorkAmount != 0f || !m_RequirementData.CheckRequirements(ref chunk2, j))
				{
					continue;
				}
				vehicleData.m_Entity = nativeArray2[j];
				vehicleData.m_TrailerData = nativeArray[j];
				if (thirdData.m_TractorData.m_TrailerType != vehicleData.m_TrailerData.m_TrailerType || (thirdData.m_TractorData.m_FixedTrailer != Entity.Null && thirdData.m_TractorData.m_FixedTrailer != vehicleData.m_Entity) || (vehicleData.m_TrailerData.m_FixedTractor != Entity.Null && vehicleData.m_TrailerData.m_FixedTractor != thirdData.m_Entity))
				{
					continue;
				}
				vehicleData.m_ObjectData = nativeArray5[j];
				if (nativeArray4.Length != 0)
				{
					vehicleData.m_TractorData = nativeArray4[j];
					if (vehicleData.m_TractorData.m_FixedTrailer != Entity.Null)
					{
						continue;
					}
				}
				if (PickVehicle(ref random, 100, ref totalProbability))
				{
					bestFirst = firstData;
					bestSecond = secondData;
					bestThird = thirdData;
					bestForth = vehicleData;
				}
			}
		}
	}
```

- `public CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, Game.Net.RoadTypes roadTypes, Game.Vehicles.SizeClass sizeClass, Game.Vehicles.VehicleWorkType workType, Game.Areas.MapFeature mapFeature, Game.Economy.Resource resource, System.Single& workAmount, Game.Objects.Transform transform, Unity.Entities.Entity source, Game.Vehicles.WorkVehicleFlags state) : Unity.Entities.Entity`  

```csharp
private Entity CreateVehicle(EntityCommandBuffer.ParallelWriter commandBuffer, int jobIndex, ref Random random, VehicleData data, VehicleWorkType workType, ref float workAmount, Transform transform, Entity source, WorkVehicleFlags state)
	{
		Game.Vehicles.WorkVehicle component = new Game.Vehicles.WorkVehicle
		{
			m_State = state
		};
		if (workType == data.m_WorkVehicleData.m_WorkType && workAmount > 0f)
		{
			component.m_WorkAmount = math.min(workAmount, data.m_WorkVehicleData.m_MaxWorkAmount);
			workAmount -= component.m_WorkAmount;
		}
		Entity entity = commandBuffer.CreateEntity(jobIndex, data.m_ObjectData.m_Archetype);
		commandBuffer.SetComponent(jobIndex, entity, transform);
		commandBuffer.SetComponent(jobIndex, entity, component);
		commandBuffer.SetComponent(jobIndex, entity, new PrefabRef(data.m_Entity));
		commandBuffer.SetComponent(jobIndex, entity, new PseudoRandomSeed(ref random));
		commandBuffer.AddComponent(jobIndex, entity, new TripSource(source));
		commandBuffer.AddComponent(jobIndex, entity, default(Unspawned));
		return entity;
	}
```

- `private CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, Game.Prefabs.WorkVehicleSelectData+VehicleData data, Game.Vehicles.VehicleWorkType workType, System.Single& workAmount, Game.Objects.Transform transform, Unity.Entities.Entity source, Game.Vehicles.WorkVehicleFlags state) : Unity.Entities.Entity`  

```csharp
private Entity CreateVehicle(EntityCommandBuffer.ParallelWriter commandBuffer, int jobIndex, ref Random random, VehicleData data, VehicleWorkType workType, ref float workAmount, Transform transform, Entity source, WorkVehicleFlags state)
	{
		Game.Vehicles.WorkVehicle component = new Game.Vehicles.WorkVehicle
		{
			m_State = state
		};
		if (workType == data.m_WorkVehicleData.m_WorkType && workAmount > 0f)
		{
			component.m_WorkAmount = math.min(workAmount, data.m_WorkVehicleData.m_MaxWorkAmount);
			workAmount -= component.m_WorkAmount;
		}
		Entity entity = commandBuffer.CreateEntity(jobIndex, data.m_ObjectData.m_Archetype);
		commandBuffer.SetComponent(jobIndex, entity, transform);
		commandBuffer.SetComponent(jobIndex, entity, component);
		commandBuffer.SetComponent(jobIndex, entity, new PrefabRef(data.m_Entity));
		commandBuffer.SetComponent(jobIndex, entity, new PseudoRandomSeed(ref random));
		commandBuffer.AddComponent(jobIndex, entity, new TripSource(source));
		commandBuffer.AddComponent(jobIndex, entity, default(Unspawned));
		return entity;
	}
```

- `public static GetEntityQueryDesc() : Unity.Entities.EntityQueryDesc`  

```csharp
public static EntityQueryDesc GetEntityQueryDesc()
	{
		EntityQueryDesc entityQueryDesc = new EntityQueryDesc();
		entityQueryDesc.All = new ComponentType[3]
		{
			ComponentType.ReadOnly<WorkVehicleData>(),
			ComponentType.ReadOnly<ObjectData>(),
			ComponentType.ReadOnly<PrefabData>()
		};
		entityQueryDesc.Any = new ComponentType[2]
		{
			ComponentType.ReadOnly<CarData>(),
			ComponentType.ReadOnly<WatercraftData>()
		};
		entityQueryDesc.None = new ComponentType[1] { ComponentType.ReadOnly<Locked>() };
		return entityQueryDesc;
	}
```

- `private PickVehicle(Unity.Mathematics.Random& random, System.Int32 probability, System.Int32& totalProbability) : System.Boolean`  

```csharp
private bool PickVehicle(ref Random random, int probability, ref int totalProbability)
	{
		totalProbability += probability;
		return random.NextInt(totalProbability) < probability;
	}
```

- `public PostUpdate(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public void PostUpdate(JobHandle jobHandle)
	{
		m_PrefabChunks.Dispose(jobHandle);
	}
```

- `public PreUpdate(Unity.Entities.SystemBase system, Game.City.CityConfigurationSystem cityConfigurationSystem, Unity.Entities.EntityQuery query, Unity.Collections.Allocator allocator, Unity.Jobs.JobHandle& jobHandle) : System.Void`  

```csharp
public void PreUpdate(SystemBase system, CityConfigurationSystem cityConfigurationSystem, EntityQuery query, Allocator allocator, out JobHandle jobHandle)
	{
		m_PrefabChunks = query.ToArchetypeChunkListAsync(allocator, out jobHandle);
		m_RequirementData.Update(system, cityConfigurationSystem);
		m_EntityType.Update(system);
		m_WorkVehicleDataType.Update(system);
		m_CarTrailerDataType.Update(system);
		m_CarTractorDataType.Update(system);
		m_CarDataType.Update(system);
		m_WatercraftDataType.Update(system);
		m_ObjectDataType.Update(system);
	}
```


## Nested types

- `Game.Prefabs.WorkVehicleSelectData+VehicleData`  

