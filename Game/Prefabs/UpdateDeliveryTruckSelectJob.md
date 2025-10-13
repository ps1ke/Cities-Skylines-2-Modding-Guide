# Game.Prefabs.UpdateDeliveryTruckSelectJob

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJob`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct UpdateDeliveryTruckSelectJob : Unity.Jobs.IJob
{
    public Unity.Entities.EntityTypeHandle m_EntityType;
    public Unity.Entities.ComponentTypeHandle<Game.Prefabs.DeliveryTruckData> m_DeliveryTruckDataType;
    public Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarTrailerData> m_CarTrailerDataType;
    public Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarTractorData> m_CarTractorDataType;
    public Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> m_PrefabChunks;
    public Game.Prefabs.VehicleSelectRequirementData m_RequirementData;
    public Unity.Collections.NativeList<Game.Prefabs.DeliveryTruckSelectItem> m_DeliveryTruckItems;

    private System.Void CheckTractors(Game.Economy.Resource resourceMask, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData secondData);
    private System.Void CheckTractors(Game.Economy.Resource resourceMask, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData secondData, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData thirdData);
    private System.Void CheckTractors(Game.Economy.Resource resourceMask, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData secondData, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData thirdData, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData forthData);
    private System.Void CheckTrailers(Game.Economy.Resource resourceMask, System.Boolean firstIsTrailer, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData firstData);
    private System.Void CheckTrailers(Game.Economy.Resource resourceMask, System.Boolean firstIsTrailer, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData firstData, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData secondData);
    private System.Void CheckTrailers(Game.Economy.Resource resourceMask, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData firstData, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData secondData, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData thirdData);
    public System.Void Execute();
}
```


## Fields

- `public Unity.Entities.EntityTypeHandle m_EntityType`  

```csharp
public Unity.Entities.EntityTypeHandle m_EntityType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Prefabs.DeliveryTruckData> m_DeliveryTruckDataType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Prefabs.DeliveryTruckData> m_DeliveryTruckDataType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarTrailerData> m_CarTrailerDataType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarTrailerData> m_CarTrailerDataType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarTractorData> m_CarTractorDataType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Prefabs.CarTractorData> m_CarTractorDataType;
```

- `public Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> m_PrefabChunks`  

```csharp
public Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> m_PrefabChunks;
```

- `public Game.Prefabs.VehicleSelectRequirementData m_RequirementData`  

```csharp
public Game.Prefabs.VehicleSelectRequirementData m_RequirementData;
```

- `public Unity.Collections.NativeList<Game.Prefabs.DeliveryTruckSelectItem> m_DeliveryTruckItems`  

```csharp
public Unity.Collections.NativeList<Game.Prefabs.DeliveryTruckSelectItem> m_DeliveryTruckItems;
```


## Methods

- `private CheckTractors(Game.Economy.Resource resourceMask, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData secondData) : System.Void`  

```csharp
private void CheckTractors(Resource resourceMask, TruckData secondData, TruckData thirdData, TruckData forthData)
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
			NativeArray<DeliveryTruckData> nativeArray3 = chunk.GetNativeArray(ref m_DeliveryTruckDataType);
			VehicleSelectRequirementData.Chunk chunk2 = m_RequirementData.GetChunk(chunk);
			for (int j = 0; j < nativeArray.Length; j++)
			{
				TruckData truckData = new TruckData
				{
					m_DeliveryTruckData = nativeArray3[j]
				};
				Resource resource = resourceMask;
				if (truckData.m_DeliveryTruckData.m_CargoCapacity != 0)
				{
					resource &= truckData.m_DeliveryTruckData.m_TransportedResources;
					if (resource == Resource.NoResource)
					{
						continue;
					}
				}
				if (m_RequirementData.CheckRequirements(ref chunk2, j))
				{
					truckData.m_Entity = nativeArray2[j];
					truckData.m_TractorData = nativeArray[j];
					if (truckData.m_TractorData.m_TrailerType == secondData.m_TrailerData.m_TrailerType && (!(truckData.m_TractorData.m_FixedTrailer != Entity.Null) || !(truckData.m_TractorData.m_FixedTrailer != secondData.m_Entity)) && (!(secondData.m_TrailerData.m_FixedTractor != Entity.Null) || !(secondData.m_TrailerData.m_FixedTractor != truckData.m_Entity)))
					{
						ref NativeList<DeliveryTruckSelectItem> deliveryTruckItems = ref m_DeliveryTruckItems;
						DeliveryTruckSelectItem value = new DeliveryTruckSelectItem
						{
							m_Capacity = truckData.m_DeliveryTruckData.m_CargoCapacity + secondData.m_DeliveryTruckData.m_CargoCapacity + thirdData.m_DeliveryTruckData.m_CargoCapacity + forthData.m_DeliveryTruckData.m_CargoCapacity,
							m_Cost = truckData.m_DeliveryTruckData.m_CostToDrive + secondData.m_DeliveryTruckData.m_CostToDrive + thirdData.m_DeliveryTruckData.m_CostToDrive + forthData.m_DeliveryTruckData.m_CostToDrive,
							m_Resources = resource,
							m_Prefab1 = truckData.m_Entity,
							m_Prefab2 = secondData.m_Entity,
							m_Prefab3 = thirdData.m_Entity,
							m_Prefab4 = forthData.m_Entity
						};
						deliveryTruckItems.Add(in value);
					}
				}
			}
		}
	}
```

- `private CheckTractors(Game.Economy.Resource resourceMask, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData secondData, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData thirdData) : System.Void`  

```csharp
private void CheckTractors(Resource resourceMask, TruckData secondData, TruckData thirdData, TruckData forthData)
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
			NativeArray<DeliveryTruckData> nativeArray3 = chunk.GetNativeArray(ref m_DeliveryTruckDataType);
			VehicleSelectRequirementData.Chunk chunk2 = m_RequirementData.GetChunk(chunk);
			for (int j = 0; j < nativeArray.Length; j++)
			{
				TruckData truckData = new TruckData
				{
					m_DeliveryTruckData = nativeArray3[j]
				};
				Resource resource = resourceMask;
				if (truckData.m_DeliveryTruckData.m_CargoCapacity != 0)
				{
					resource &= truckData.m_DeliveryTruckData.m_TransportedResources;
					if (resource == Resource.NoResource)
					{
						continue;
					}
				}
				if (m_RequirementData.CheckRequirements(ref chunk2, j))
				{
					truckData.m_Entity = nativeArray2[j];
					truckData.m_TractorData = nativeArray[j];
					if (truckData.m_TractorData.m_TrailerType == secondData.m_TrailerData.m_TrailerType && (!(truckData.m_TractorData.m_FixedTrailer != Entity.Null) || !(truckData.m_TractorData.m_FixedTrailer != secondData.m_Entity)) && (!(secondData.m_TrailerData.m_FixedTractor != Entity.Null) || !(secondData.m_TrailerData.m_FixedTractor != truckData.m_Entity)))
					{
						ref NativeList<DeliveryTruckSelectItem> deliveryTruckItems = ref m_DeliveryTruckItems;
						DeliveryTruckSelectItem value = new DeliveryTruckSelectItem
						{
							m_Capacity = truckData.m_DeliveryTruckData.m_CargoCapacity + secondData.m_DeliveryTruckData.m_CargoCapacity + thirdData.m_DeliveryTruckData.m_CargoCapacity + forthData.m_DeliveryTruckData.m_CargoCapacity,
							m_Cost = truckData.m_DeliveryTruckData.m_CostToDrive + secondData.m_DeliveryTruckData.m_CostToDrive + thirdData.m_DeliveryTruckData.m_CostToDrive + forthData.m_DeliveryTruckData.m_CostToDrive,
							m_Resources = resource,
							m_Prefab1 = truckData.m_Entity,
							m_Prefab2 = secondData.m_Entity,
							m_Prefab3 = thirdData.m_Entity,
							m_Prefab4 = forthData.m_Entity
						};
						deliveryTruckItems.Add(in value);
					}
				}
			}
		}
	}
```

- `private CheckTractors(Game.Economy.Resource resourceMask, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData secondData, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData thirdData, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData forthData) : System.Void`  

```csharp
private void CheckTractors(Resource resourceMask, TruckData secondData, TruckData thirdData, TruckData forthData)
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
			NativeArray<DeliveryTruckData> nativeArray3 = chunk.GetNativeArray(ref m_DeliveryTruckDataType);
			VehicleSelectRequirementData.Chunk chunk2 = m_RequirementData.GetChunk(chunk);
			for (int j = 0; j < nativeArray.Length; j++)
			{
				TruckData truckData = new TruckData
				{
					m_DeliveryTruckData = nativeArray3[j]
				};
				Resource resource = resourceMask;
				if (truckData.m_DeliveryTruckData.m_CargoCapacity != 0)
				{
					resource &= truckData.m_DeliveryTruckData.m_TransportedResources;
					if (resource == Resource.NoResource)
					{
						continue;
					}
				}
				if (m_RequirementData.CheckRequirements(ref chunk2, j))
				{
					truckData.m_Entity = nativeArray2[j];
					truckData.m_TractorData = nativeArray[j];
					if (truckData.m_TractorData.m_TrailerType == secondData.m_TrailerData.m_TrailerType && (!(truckData.m_TractorData.m_FixedTrailer != Entity.Null) || !(truckData.m_TractorData.m_FixedTrailer != secondData.m_Entity)) && (!(secondData.m_TrailerData.m_FixedTractor != Entity.Null) || !(secondData.m_TrailerData.m_FixedTractor != truckData.m_Entity)))
					{
						ref NativeList<DeliveryTruckSelectItem> deliveryTruckItems = ref m_DeliveryTruckItems;
						DeliveryTruckSelectItem value = new DeliveryTruckSelectItem
						{
							m_Capacity = truckData.m_DeliveryTruckData.m_CargoCapacity + secondData.m_DeliveryTruckData.m_CargoCapacity + thirdData.m_DeliveryTruckData.m_CargoCapacity + forthData.m_DeliveryTruckData.m_CargoCapacity,
							m_Cost = truckData.m_DeliveryTruckData.m_CostToDrive + secondData.m_DeliveryTruckData.m_CostToDrive + thirdData.m_DeliveryTruckData.m_CostToDrive + forthData.m_DeliveryTruckData.m_CostToDrive,
							m_Resources = resource,
							m_Prefab1 = truckData.m_Entity,
							m_Prefab2 = secondData.m_Entity,
							m_Prefab3 = thirdData.m_Entity,
							m_Prefab4 = forthData.m_Entity
						};
						deliveryTruckItems.Add(in value);
					}
				}
			}
		}
	}
```

- `private CheckTrailers(Game.Economy.Resource resourceMask, System.Boolean firstIsTrailer, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData firstData) : System.Void`  

```csharp
private void CheckTrailers(Resource resourceMask, TruckData firstData, TruckData secondData, TruckData thirdData)
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
			NativeArray<DeliveryTruckData> nativeArray3 = chunk.GetNativeArray(ref m_DeliveryTruckDataType);
			NativeArray<CarTractorData> nativeArray4 = chunk.GetNativeArray(ref m_CarTractorDataType);
			VehicleSelectRequirementData.Chunk chunk2 = m_RequirementData.GetChunk(chunk);
			for (int j = 0; j < nativeArray.Length; j++)
			{
				TruckData truckData = new TruckData
				{
					m_DeliveryTruckData = nativeArray3[j]
				};
				if (truckData.m_DeliveryTruckData.m_CargoCapacity != 0 || !m_RequirementData.CheckRequirements(ref chunk2, j))
				{
					continue;
				}
				truckData.m_Entity = nativeArray2[j];
				truckData.m_TrailerData = nativeArray[j];
				if (thirdData.m_TractorData.m_TrailerType != truckData.m_TrailerData.m_TrailerType || (thirdData.m_TractorData.m_FixedTrailer != Entity.Null && thirdData.m_TractorData.m_FixedTrailer != truckData.m_Entity) || (truckData.m_TrailerData.m_FixedTractor != Entity.Null && truckData.m_TrailerData.m_FixedTractor != thirdData.m_Entity))
				{
					continue;
				}
				if (nativeArray4.Length != 0)
				{
					truckData.m_TractorData = nativeArray4[j];
					if (truckData.m_TractorData.m_FixedTrailer != Entity.Null)
					{
						continue;
					}
				}
				m_DeliveryTruckItems.Add(new DeliveryTruckSelectItem
				{
					m_Capacity = firstData.m_DeliveryTruckData.m_CargoCapacity + secondData.m_DeliveryTruckData.m_CargoCapacity + thirdData.m_DeliveryTruckData.m_CargoCapacity + truckData.m_DeliveryTruckData.m_CargoCapacity,
					m_Cost = firstData.m_DeliveryTruckData.m_CostToDrive + secondData.m_DeliveryTruckData.m_CostToDrive + thirdData.m_DeliveryTruckData.m_CostToDrive + truckData.m_DeliveryTruckData.m_CostToDrive,
					m_Resources = resourceMask,
					m_Prefab1 = firstData.m_Entity,
					m_Prefab2 = secondData.m_Entity,
					m_Prefab3 = thirdData.m_Entity,
					m_Prefab4 = truckData.m_Entity
				});
			}
		}
	}
```

- `private CheckTrailers(Game.Economy.Resource resourceMask, System.Boolean firstIsTrailer, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData firstData, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData secondData) : System.Void`  

```csharp
private void CheckTrailers(Resource resourceMask, TruckData firstData, TruckData secondData, TruckData thirdData)
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
			NativeArray<DeliveryTruckData> nativeArray3 = chunk.GetNativeArray(ref m_DeliveryTruckDataType);
			NativeArray<CarTractorData> nativeArray4 = chunk.GetNativeArray(ref m_CarTractorDataType);
			VehicleSelectRequirementData.Chunk chunk2 = m_RequirementData.GetChunk(chunk);
			for (int j = 0; j < nativeArray.Length; j++)
			{
				TruckData truckData = new TruckData
				{
					m_DeliveryTruckData = nativeArray3[j]
				};
				if (truckData.m_DeliveryTruckData.m_CargoCapacity != 0 || !m_RequirementData.CheckRequirements(ref chunk2, j))
				{
					continue;
				}
				truckData.m_Entity = nativeArray2[j];
				truckData.m_TrailerData = nativeArray[j];
				if (thirdData.m_TractorData.m_TrailerType != truckData.m_TrailerData.m_TrailerType || (thirdData.m_TractorData.m_FixedTrailer != Entity.Null && thirdData.m_TractorData.m_FixedTrailer != truckData.m_Entity) || (truckData.m_TrailerData.m_FixedTractor != Entity.Null && truckData.m_TrailerData.m_FixedTractor != thirdData.m_Entity))
				{
					continue;
				}
				if (nativeArray4.Length != 0)
				{
					truckData.m_TractorData = nativeArray4[j];
					if (truckData.m_TractorData.m_FixedTrailer != Entity.Null)
					{
						continue;
					}
				}
				m_DeliveryTruckItems.Add(new DeliveryTruckSelectItem
				{
					m_Capacity = firstData.m_DeliveryTruckData.m_CargoCapacity + secondData.m_DeliveryTruckData.m_CargoCapacity + thirdData.m_DeliveryTruckData.m_CargoCapacity + truckData.m_DeliveryTruckData.m_CargoCapacity,
					m_Cost = firstData.m_DeliveryTruckData.m_CostToDrive + secondData.m_DeliveryTruckData.m_CostToDrive + thirdData.m_DeliveryTruckData.m_CostToDrive + truckData.m_DeliveryTruckData.m_CostToDrive,
					m_Resources = resourceMask,
					m_Prefab1 = firstData.m_Entity,
					m_Prefab2 = secondData.m_Entity,
					m_Prefab3 = thirdData.m_Entity,
					m_Prefab4 = truckData.m_Entity
				});
			}
		}
	}
```

- `private CheckTrailers(Game.Economy.Resource resourceMask, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData firstData, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData secondData, Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData thirdData) : System.Void`  

```csharp
private void CheckTrailers(Resource resourceMask, TruckData firstData, TruckData secondData, TruckData thirdData)
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
			NativeArray<DeliveryTruckData> nativeArray3 = chunk.GetNativeArray(ref m_DeliveryTruckDataType);
			NativeArray<CarTractorData> nativeArray4 = chunk.GetNativeArray(ref m_CarTractorDataType);
			VehicleSelectRequirementData.Chunk chunk2 = m_RequirementData.GetChunk(chunk);
			for (int j = 0; j < nativeArray.Length; j++)
			{
				TruckData truckData = new TruckData
				{
					m_DeliveryTruckData = nativeArray3[j]
				};
				if (truckData.m_DeliveryTruckData.m_CargoCapacity != 0 || !m_RequirementData.CheckRequirements(ref chunk2, j))
				{
					continue;
				}
				truckData.m_Entity = nativeArray2[j];
				truckData.m_TrailerData = nativeArray[j];
				if (thirdData.m_TractorData.m_TrailerType != truckData.m_TrailerData.m_TrailerType || (thirdData.m_TractorData.m_FixedTrailer != Entity.Null && thirdData.m_TractorData.m_FixedTrailer != truckData.m_Entity) || (truckData.m_TrailerData.m_FixedTractor != Entity.Null && truckData.m_TrailerData.m_FixedTractor != thirdData.m_Entity))
				{
					continue;
				}
				if (nativeArray4.Length != 0)
				{
					truckData.m_TractorData = nativeArray4[j];
					if (truckData.m_TractorData.m_FixedTrailer != Entity.Null)
					{
						continue;
					}
				}
				m_DeliveryTruckItems.Add(new DeliveryTruckSelectItem
				{
					m_Capacity = firstData.m_DeliveryTruckData.m_CargoCapacity + secondData.m_DeliveryTruckData.m_CargoCapacity + thirdData.m_DeliveryTruckData.m_CargoCapacity + truckData.m_DeliveryTruckData.m_CargoCapacity,
					m_Cost = firstData.m_DeliveryTruckData.m_CostToDrive + secondData.m_DeliveryTruckData.m_CostToDrive + thirdData.m_DeliveryTruckData.m_CostToDrive + truckData.m_DeliveryTruckData.m_CostToDrive,
					m_Resources = resourceMask,
					m_Prefab1 = firstData.m_Entity,
					m_Prefab2 = secondData.m_Entity,
					m_Prefab3 = thirdData.m_Entity,
					m_Prefab4 = truckData.m_Entity
				});
			}
		}
	}
```

- `public Execute() : System.Void`  

```csharp
public void Execute()
	{
		m_DeliveryTruckItems.Clear();
		for (int i = 0; i < m_PrefabChunks.Length; i++)
		{
			ArchetypeChunk chunk = m_PrefabChunks[i];
			NativeArray<Entity> nativeArray = chunk.GetNativeArray(m_EntityType);
			NativeArray<DeliveryTruckData> nativeArray2 = chunk.GetNativeArray(ref m_DeliveryTruckDataType);
			NativeArray<CarTrailerData> nativeArray3 = chunk.GetNativeArray(ref m_CarTrailerDataType);
			NativeArray<CarTractorData> nativeArray4 = chunk.GetNativeArray(ref m_CarTractorDataType);
			VehicleSelectRequirementData.Chunk chunk2 = m_RequirementData.GetChunk(chunk);
			for (int j = 0; j < nativeArray2.Length; j++)
			{
				TruckData truckData = new TruckData
				{
					m_DeliveryTruckData = nativeArray2[j]
				};
				if (truckData.m_DeliveryTruckData.m_CargoCapacity == 0 || truckData.m_DeliveryTruckData.m_TransportedResources == Resource.NoResource || !m_RequirementData.CheckRequirements(ref chunk2, j))
				{
					continue;
				}
				Resource transportedResources = truckData.m_DeliveryTruckData.m_TransportedResources;
				truckData.m_Entity = nativeArray[j];
				bool flag = false;
				if (nativeArray3.Length != 0)
				{
					truckData.m_TrailerData = nativeArray3[j];
					flag = true;
				}
				if (nativeArray4.Length != 0)
				{
					truckData.m_TractorData = nativeArray4[j];
					if (truckData.m_TractorData.m_FixedTrailer != Entity.Null)
					{
						CheckTrailers(transportedResources, flag, truckData);
						continue;
					}
				}
				if (flag)
				{
					CheckTractors(transportedResources, truckData);
					continue;
				}
				ref NativeList<DeliveryTruckSelectItem> deliveryTruckItems = ref m_DeliveryTruckItems;
				DeliveryTruckSelectItem value = new DeliveryTruckSelectItem
				{
					m_Capacity = truckData.m_DeliveryTruckData.m_CargoCapacity,
					m_Cost = truckData.m_DeliveryTruckData.m_CostToDrive,
					m_Resources = transportedResources,
					m_Prefab1 = truckData.m_Entity
				};
				deliveryTruckItems.Add(in value);
			}
		}
		if (m_DeliveryTruckItems.Length >= 2)
		{
			m_DeliveryTruckItems.Sort();
			DeliveryTruckSelectItem deliveryTruckSelectItem = default(DeliveryTruckSelectItem);
			DeliveryTruckSelectItem deliveryTruckSelectItem2 = m_DeliveryTruckItems[0];
			int num = 0;
			for (int k = 1; k < m_DeliveryTruckItems.Length; k++)
			{
				DeliveryTruckSelectItem deliveryTruckSelectItem3 = m_DeliveryTruckItems[k];
				if (deliveryTruckSelectItem2.m_Resources != Resource.NoResource && deliveryTruckSelectItem2.m_Cost > deliveryTruckSelectItem3.m_Cost)
				{
					deliveryTruckSelectItem2.m_Resources &= ~deliveryTruckSelectItem3.m_Resources;
					for (int l = k + 1; l < m_DeliveryTruckItems.Length; l++)
					{
						if (deliveryTruckSelectItem2.m_Resources == Resource.NoResource)
						{
							break;
						}
						DeliveryTruckSelectItem deliveryTruckSelectItem4 = m_DeliveryTruckItems[l];
						if (deliveryTruckSelectItem2.m_Cost <= deliveryTruckSelectItem4.m_Cost)
						{
							break;
						}
						deliveryTruckSelectItem2.m_Resources &= ~deliveryTruckSelectItem4.m_Resources;
					}
				}
				if (deliveryTruckSelectItem2.m_Resources != Resource.NoResource)
				{
					m_DeliveryTruckItems[num++] = deliveryTruckSelectItem2;
					deliveryTruckSelectItem = deliveryTruckSelectItem2;
				}
				deliveryTruckSelectItem2 = deliveryTruckSelectItem3;
				if (deliveryTruckSelectItem2.m_Resources == Resource.NoResource || deliveryTruckSelectItem2.m_Cost * deliveryTruckSelectItem.m_Capacity <= deliveryTruckSelectItem.m_Cost * deliveryTruckSelectItem2.m_Capacity)
				{
					continue;
				}
				deliveryTruckSelectItem2.m_Resources &= ~deliveryTruckSelectItem.m_Resources;
				int num2 = num - 2;
				while (num2 >= 0 && deliveryTruckSelectItem2.m_Resources != Resource.NoResource)
				{
					DeliveryTruckSelectItem deliveryTruckSelectItem5 = m_DeliveryTruckItems[num2];
					if (deliveryTruckSelectItem2.m_Cost * deliveryTruckSelectItem5.m_Capacity <= deliveryTruckSelectItem5.m_Cost * deliveryTruckSelectItem2.m_Capacity)
					{
						break;
					}
					deliveryTruckSelectItem2.m_Resources &= ~deliveryTruckSelectItem5.m_Resources;
					num2--;
				}
			}
			if (deliveryTruckSelectItem2.m_Resources != Resource.NoResource)
			{
				m_DeliveryTruckItems[num++] = deliveryTruckSelectItem2;
			}
			if (num < m_DeliveryTruckItems.Length)
			{
				m_DeliveryTruckItems.RemoveRange(num, m_DeliveryTruckItems.Length - num);
			}
		}
		m_DeliveryTruckItems.TrimExcess();
	}
```


## Nested types

- `Game.Prefabs.UpdateDeliveryTruckSelectJob+TruckData`  

