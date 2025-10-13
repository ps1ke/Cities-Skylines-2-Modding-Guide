# Game.Prefabs.DeliveryTruckSelectData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct DeliveryTruckSelectData
{
    private Unity.Collections.NativeArray<Game.Prefabs.DeliveryTruckSelectItem> m_Items;

    public DeliveryTruckSelectData(Unity.Collections.NativeArray<Game.Prefabs.DeliveryTruckSelectItem> items);

    public Unity.Entities.Entity CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, Unity.Entities.ComponentLookup`1[[Game.Prefabs.DeliveryTruckData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& deliveryTruckDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ObjectData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& objectDatas, Game.Economy.Resource resource, Game.Economy.Resource returnResource, System.Int32& amount, System.Int32& returnAmount, Game.Objects.Transform transform, Unity.Entities.Entity source, Game.Vehicles.DeliveryTruckFlags state, System.UInt32 delay);
    public Unity.Entities.Entity CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, Unity.Entities.ComponentLookup`1[[Game.Prefabs.DeliveryTruckData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& deliveryTruckDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ObjectData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& objectDatas, Game.Prefabs.DeliveryTruckSelectItem selectItem, Game.Economy.Resource resource, Game.Economy.Resource returnResource, System.Int32& amount, System.Int32& returnAmount, Game.Objects.Transform transform, Unity.Entities.Entity source, Game.Vehicles.DeliveryTruckFlags state, System.UInt32 delay);
    private Unity.Entities.Entity CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, Unity.Entities.ComponentLookup`1[[Game.Prefabs.DeliveryTruckData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& deliveryTruckDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ObjectData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& objectDatas, Unity.Entities.Entity prefab, Game.Economy.Resource resource, Game.Economy.Resource returnResource, System.Int32& amount, System.Int32& returnAmount, Game.Objects.Transform transform, Unity.Entities.Entity source, Game.Vehicles.DeliveryTruckFlags state, System.UInt32 delay);
    public System.Void GetCapacityRange(Game.Economy.Resource resources, System.Int32& min, System.Int32& max);
    public System.Boolean TrySelectItem(Unity.Mathematics.Random& random, Game.Economy.Resource resources, System.Int32 capacity, Game.Prefabs.DeliveryTruckSelectItem& item);
}
```


## Fields

- `private Unity.Collections.NativeArray<Game.Prefabs.DeliveryTruckSelectItem> m_Items`  

```csharp
private Unity.Collections.NativeArray<Game.Prefabs.DeliveryTruckSelectItem> m_Items;
```


## Constructors

- `public DeliveryTruckSelectData(Unity.Collections.NativeArray<Game.Prefabs.DeliveryTruckSelectItem> items)`  

```csharp
public DeliveryTruckSelectData(NativeArray<DeliveryTruckSelectItem> items)
	{
		m_Items = items;
	}
```


## Methods

- `public CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, Unity.Entities.ComponentLookup`1[[Game.Prefabs.DeliveryTruckData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& deliveryTruckDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ObjectData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& objectDatas, Game.Economy.Resource resource, Game.Economy.Resource returnResource, System.Int32& amount, System.Int32& returnAmount, Game.Objects.Transform transform, Unity.Entities.Entity source, Game.Vehicles.DeliveryTruckFlags state, System.UInt32 delay = 0) : Unity.Entities.Entity`  

```csharp
private Entity CreateVehicle(EntityCommandBuffer.ParallelWriter commandBuffer, int jobIndex, ref Random random, ref ComponentLookup<DeliveryTruckData> deliveryTruckDatas, ref ComponentLookup<ObjectData> objectDatas, Entity prefab, Resource resource, Resource returnResource, ref int amount, ref int returnAmount, Transform transform, Entity source, DeliveryTruckFlags state, uint delay)
	{
		DeliveryTruckData deliveryTruckData = deliveryTruckDatas[prefab];
		ObjectData objectData = objectDatas[prefab];
		Game.Vehicles.DeliveryTruck component = new Game.Vehicles.DeliveryTruck
		{
			m_State = state
		};
		if ((resource & deliveryTruckData.m_TransportedResources) != Resource.NoResource && amount > 0)
		{
			component.m_Amount = math.min(amount, deliveryTruckData.m_CargoCapacity);
			if (component.m_Amount > 0)
			{
				component.m_Resource = resource;
				amount -= component.m_Amount;
			}
		}
		Entity entity = commandBuffer.CreateEntity(jobIndex, objectData.m_Archetype);
		commandBuffer.SetComponent(jobIndex, entity, transform);
		commandBuffer.SetComponent(jobIndex, entity, component);
		commandBuffer.SetComponent(jobIndex, entity, new PrefabRef(prefab));
		commandBuffer.SetComponent(jobIndex, entity, new PseudoRandomSeed(ref random));
		if (source != Entity.Null)
		{
			commandBuffer.AddComponent(jobIndex, entity, new TripSource(source, delay));
			commandBuffer.AddComponent(jobIndex, entity, default(Unspawned));
		}
		if ((returnResource & deliveryTruckData.m_TransportedResources) != Resource.NoResource)
		{
			ReturnLoad component2 = new ReturnLoad
			{
				m_Amount = math.min(returnAmount, deliveryTruckData.m_CargoCapacity)
			};
			if (component2.m_Amount > 0)
			{
				component2.m_Resource = returnResource;
				returnAmount -= component2.m_Amount;
				commandBuffer.AddComponent(jobIndex, entity, component2);
			}
		}
		return entity;
	}
```

- `public CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, Unity.Entities.ComponentLookup`1[[Game.Prefabs.DeliveryTruckData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& deliveryTruckDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ObjectData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& objectDatas, Game.Prefabs.DeliveryTruckSelectItem selectItem, Game.Economy.Resource resource, Game.Economy.Resource returnResource, System.Int32& amount, System.Int32& returnAmount, Game.Objects.Transform transform, Unity.Entities.Entity source, Game.Vehicles.DeliveryTruckFlags state, System.UInt32 delay = 0) : Unity.Entities.Entity`  

```csharp
private Entity CreateVehicle(EntityCommandBuffer.ParallelWriter commandBuffer, int jobIndex, ref Random random, ref ComponentLookup<DeliveryTruckData> deliveryTruckDatas, ref ComponentLookup<ObjectData> objectDatas, Entity prefab, Resource resource, Resource returnResource, ref int amount, ref int returnAmount, Transform transform, Entity source, DeliveryTruckFlags state, uint delay)
	{
		DeliveryTruckData deliveryTruckData = deliveryTruckDatas[prefab];
		ObjectData objectData = objectDatas[prefab];
		Game.Vehicles.DeliveryTruck component = new Game.Vehicles.DeliveryTruck
		{
			m_State = state
		};
		if ((resource & deliveryTruckData.m_TransportedResources) != Resource.NoResource && amount > 0)
		{
			component.m_Amount = math.min(amount, deliveryTruckData.m_CargoCapacity);
			if (component.m_Amount > 0)
			{
				component.m_Resource = resource;
				amount -= component.m_Amount;
			}
		}
		Entity entity = commandBuffer.CreateEntity(jobIndex, objectData.m_Archetype);
		commandBuffer.SetComponent(jobIndex, entity, transform);
		commandBuffer.SetComponent(jobIndex, entity, component);
		commandBuffer.SetComponent(jobIndex, entity, new PrefabRef(prefab));
		commandBuffer.SetComponent(jobIndex, entity, new PseudoRandomSeed(ref random));
		if (source != Entity.Null)
		{
			commandBuffer.AddComponent(jobIndex, entity, new TripSource(source, delay));
			commandBuffer.AddComponent(jobIndex, entity, default(Unspawned));
		}
		if ((returnResource & deliveryTruckData.m_TransportedResources) != Resource.NoResource)
		{
			ReturnLoad component2 = new ReturnLoad
			{
				m_Amount = math.min(returnAmount, deliveryTruckData.m_CargoCapacity)
			};
			if (component2.m_Amount > 0)
			{
				component2.m_Resource = returnResource;
				returnAmount -= component2.m_Amount;
				commandBuffer.AddComponent(jobIndex, entity, component2);
			}
		}
		return entity;
	}
```

- `private CreateVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Mathematics.Random& random, Unity.Entities.ComponentLookup`1[[Game.Prefabs.DeliveryTruckData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& deliveryTruckDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ObjectData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& objectDatas, Unity.Entities.Entity prefab, Game.Economy.Resource resource, Game.Economy.Resource returnResource, System.Int32& amount, System.Int32& returnAmount, Game.Objects.Transform transform, Unity.Entities.Entity source, Game.Vehicles.DeliveryTruckFlags state, System.UInt32 delay) : Unity.Entities.Entity`  

```csharp
private Entity CreateVehicle(EntityCommandBuffer.ParallelWriter commandBuffer, int jobIndex, ref Random random, ref ComponentLookup<DeliveryTruckData> deliveryTruckDatas, ref ComponentLookup<ObjectData> objectDatas, Entity prefab, Resource resource, Resource returnResource, ref int amount, ref int returnAmount, Transform transform, Entity source, DeliveryTruckFlags state, uint delay)
	{
		DeliveryTruckData deliveryTruckData = deliveryTruckDatas[prefab];
		ObjectData objectData = objectDatas[prefab];
		Game.Vehicles.DeliveryTruck component = new Game.Vehicles.DeliveryTruck
		{
			m_State = state
		};
		if ((resource & deliveryTruckData.m_TransportedResources) != Resource.NoResource && amount > 0)
		{
			component.m_Amount = math.min(amount, deliveryTruckData.m_CargoCapacity);
			if (component.m_Amount > 0)
			{
				component.m_Resource = resource;
				amount -= component.m_Amount;
			}
		}
		Entity entity = commandBuffer.CreateEntity(jobIndex, objectData.m_Archetype);
		commandBuffer.SetComponent(jobIndex, entity, transform);
		commandBuffer.SetComponent(jobIndex, entity, component);
		commandBuffer.SetComponent(jobIndex, entity, new PrefabRef(prefab));
		commandBuffer.SetComponent(jobIndex, entity, new PseudoRandomSeed(ref random));
		if (source != Entity.Null)
		{
			commandBuffer.AddComponent(jobIndex, entity, new TripSource(source, delay));
			commandBuffer.AddComponent(jobIndex, entity, default(Unspawned));
		}
		if ((returnResource & deliveryTruckData.m_TransportedResources) != Resource.NoResource)
		{
			ReturnLoad component2 = new ReturnLoad
			{
				m_Amount = math.min(returnAmount, deliveryTruckData.m_CargoCapacity)
			};
			if (component2.m_Amount > 0)
			{
				component2.m_Resource = returnResource;
				returnAmount -= component2.m_Amount;
				commandBuffer.AddComponent(jobIndex, entity, component2);
			}
		}
		return entity;
	}
```

- `public GetCapacityRange(Game.Economy.Resource resources, System.Int32& min, System.Int32& max) : System.Void`  

```csharp
public void GetCapacityRange(Resource resources, out int min, out int max)
	{
		min = 0;
		max = 0;
		for (int i = 0; i < m_Items.Length; i++)
		{
			DeliveryTruckSelectItem deliveryTruckSelectItem = m_Items[i];
			if ((deliveryTruckSelectItem.m_Resources & resources) == resources)
			{
				min = deliveryTruckSelectItem.m_Capacity;
				break;
			}
		}
		for (int num = m_Items.Length - 1; num >= 0; num--)
		{
			DeliveryTruckSelectItem deliveryTruckSelectItem2 = m_Items[num];
			if ((deliveryTruckSelectItem2.m_Resources & resources) == resources)
			{
				max = deliveryTruckSelectItem2.m_Capacity;
				break;
			}
		}
	}
```

- `public TrySelectItem(Unity.Mathematics.Random& random, Game.Economy.Resource resources, System.Int32 capacity, Game.Prefabs.DeliveryTruckSelectItem& item) : System.Boolean`  

```csharp
public bool TrySelectItem(ref Random random, Resource resources, int capacity, out DeliveryTruckSelectItem item)
	{
		int2 x = new int2(0, m_Items.Length);
		while (x.y > x.x)
		{
			int num = math.csum(x) >> 1;
			DeliveryTruckSelectItem deliveryTruckSelectItem = m_Items[num];
			if (deliveryTruckSelectItem.m_Capacity == capacity)
			{
				x = num;
				break;
			}
			x = math.select(new int2(num + 1, x.y), new int2(x.x, num), deliveryTruckSelectItem.m_Capacity > capacity);
		}
		item = default(DeliveryTruckSelectItem);
		int num2 = 0;
		while (x.y < m_Items.Length)
		{
			DeliveryTruckSelectItem deliveryTruckSelectItem2 = m_Items[x.y++];
			int2 @int = new int2(deliveryTruckSelectItem2.m_Cost, item.m_Cost) * math.min(capacity, new int2(item.m_Capacity, deliveryTruckSelectItem2.m_Capacity));
			if (@int.x > @int.y)
			{
				break;
			}
			bool flag = (deliveryTruckSelectItem2.m_Resources & resources) == resources;
			int num3 = math.select(0, 100, flag);
			num2 = num3 + math.select(num2, 0, flag & (@int.x < @int.y));
			if (random.NextInt(num2) < num3)
			{
				item = deliveryTruckSelectItem2;
			}
		}
		while (x.x > 0)
		{
			DeliveryTruckSelectItem deliveryTruckSelectItem3 = m_Items[--x.x];
			int2 int2 = new int2(deliveryTruckSelectItem3.m_Cost, item.m_Cost) * math.min(capacity, new int2(item.m_Capacity, deliveryTruckSelectItem3.m_Capacity));
			if (int2.x > int2.y)
			{
				break;
			}
			bool flag2 = (deliveryTruckSelectItem3.m_Resources & resources) == resources;
			int num4 = math.select(0, 100, flag2);
			num2 = num4 + math.select(num2, 0, flag2 & (int2.x < int2.y));
			if (random.NextInt(num2) < num4)
			{
				item = deliveryTruckSelectItem3;
			}
		}
		return item.m_Prefab1 != Entity.Null;
	}
```


