# Game.UI.InGame.TransportUIUtils

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class TransportUIUtils
{
    private static System.Void AddCargo(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, System.Int32& cargo, System.Int32& capacity);
    private static System.Void AddVehicleCargo(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, System.Int32& cargo, System.Int32& capacity);
    public static Game.UI.InGame.UITransportLineData BuildTransportLine(Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem m_PrefabSystem);
    public static System.Int32 CountLines(Unity.Collections.NativeArray<Game.UI.InGame.UITransportLineData> lines, Game.Prefabs.TransportType type, System.Boolean cargo);
    public static System.Single GetRouteLength(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public static System.Int32 GetRouteVehiclesCount(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, System.Int32& cargo, System.Int32& capacity);
    public static Unity.Collections.NativeArray<Game.UI.InGame.UITransportLineData> GetSortedLines(Unity.Entities.EntityQuery query, Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
    public static System.Int32 GetStopCount(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Methods

- `private static AddCargo(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, System.Int32& cargo, System.Int32& capacity) : System.Void`  

```csharp
private static void AddCargo(EntityManager entityManager, Entity entity, ref int cargo, ref int capacity)
	{
		if (entityManager.TryGetBuffer(entity, isReadOnly: true, out DynamicBuffer<LayoutElement> buffer))
		{
			for (int i = 0; i < buffer.Length; i++)
			{
				AddVehicleCargo(entityManager, buffer[i].m_Vehicle, ref cargo, ref capacity);
			}
		}
		else
		{
			AddVehicleCargo(entityManager, entity, ref cargo, ref capacity);
		}
	}
```

- `private static AddVehicleCargo(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, System.Int32& cargo, System.Int32& capacity) : System.Void`  

```csharp
private static void AddVehicleCargo(EntityManager entityManager, Entity entity, ref int cargo, ref int capacity)
	{
		if (!entityManager.TryGetComponent<PrefabRef>(entity, out var component))
		{
			return;
		}
		if (entityManager.TryGetComponent<PublicTransportVehicleData>(component.m_Prefab, out var component2))
		{
			if (entityManager.TryGetBuffer(entity, isReadOnly: true, out DynamicBuffer<Passenger> buffer))
			{
				cargo += buffer.Length;
			}
			capacity += component2.m_PassengerCapacity;
		}
		else
		{
			if (!entityManager.TryGetComponent<CargoTransportVehicleData>(component.m_Prefab, out var component3))
			{
				return;
			}
			if (entityManager.TryGetBuffer(entity, isReadOnly: true, out DynamicBuffer<Resources> buffer2))
			{
				for (int i = 0; i < buffer2.Length; i++)
				{
					cargo += buffer2[i].m_Amount;
				}
			}
			capacity += component3.m_CargoCapacity;
		}
	}
```

- `public static BuildTransportLine(Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem m_PrefabSystem) : Game.UI.InGame.UITransportLineData`  

```csharp
public static UITransportLineData BuildTransportLine(Entity entity, EntityManager entityManager, PrefabSystem m_PrefabSystem)
	{
		Route componentData = entityManager.GetComponentData<Route>(entity);
		PrefabRef componentData2 = entityManager.GetComponentData<PrefabRef>(entity);
		TransportLinePrefab prefab = m_PrefabSystem.GetPrefab<TransportLinePrefab>(componentData2.m_Prefab);
		TransportLineData componentData3 = entityManager.GetComponentData<TransportLineData>(componentData2.m_Prefab);
		bool visible = !entityManager.HasComponent<HiddenRoute>(entity);
		Color componentData4 = entityManager.GetComponentData<Color>(entity);
		int cargo = 0;
		int capacity = 0;
		int stopCount = GetStopCount(entityManager, entity);
		int routeVehiclesCount = GetRouteVehiclesCount(entityManager, entity, ref cargo, ref capacity);
		float routeLength = GetRouteLength(entityManager, entity);
		float usage = ((capacity > 0) ? ((float)cargo / (float)capacity) : 0f);
		RouteSchedule schedule = ((!RouteUtils.CheckOption(componentData, RouteOption.Day)) ? (RouteUtils.CheckOption(componentData, RouteOption.Night) ? RouteSchedule.Night : RouteSchedule.DayAndNight) : RouteSchedule.Day);
		bool active = !RouteUtils.CheckOption(componentData, RouteOption.Inactive);
		return new UITransportLineData(entity, active, visible, prefab.m_CargoTransport, componentData4, schedule, componentData3.m_TransportType, routeLength, stopCount, routeVehiclesCount, cargo, usage);
	}
```

- `public static CountLines(Unity.Collections.NativeArray<Game.UI.InGame.UITransportLineData> lines, Game.Prefabs.TransportType type, System.Boolean cargo = False) : System.Int32`  

```csharp
public static int CountLines(NativeArray<UITransportLineData> lines, TransportType type, bool cargo = false)
	{
		int num = 0;
		for (int i = 0; i < lines.Length; i++)
		{
			if (lines[i].type == type && lines[i].isCargo == cargo)
			{
				num++;
			}
		}
		return num;
	}
```

- `public static GetRouteLength(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Single`  

```csharp
public static float GetRouteLength(EntityManager entityManager, Entity entity)
	{
		DynamicBuffer<RouteSegment> buffer = entityManager.GetBuffer<RouteSegment>(entity, isReadOnly: true);
		float num = 0f;
		for (int i = 0; i < buffer.Length; i++)
		{
			if (entityManager.TryGetComponent<PathInformation>(buffer[i].m_Segment, out var component))
			{
				num += component.m_Distance;
			}
		}
		return num;
	}
```

- `public static GetRouteVehiclesCount(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, System.Int32& cargo, System.Int32& capacity) : System.Int32`  

```csharp
public static int GetRouteVehiclesCount(EntityManager entityManager, Entity entity, ref int cargo, ref int capacity)
	{
		DynamicBuffer<RouteVehicle> buffer = entityManager.GetBuffer<RouteVehicle>(entity, isReadOnly: true);
		for (int i = 0; i < buffer.Length; i++)
		{
			AddCargo(entityManager, buffer[i].m_Vehicle, ref cargo, ref capacity);
		}
		return buffer.Length;
	}
```

- `public static GetSortedLines(Unity.Entities.EntityQuery query, Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem) : Unity.Collections.NativeArray<Game.UI.InGame.UITransportLineData>`  

```csharp
public static NativeArray<UITransportLineData> GetSortedLines(EntityQuery query, EntityManager entityManager, PrefabSystem prefabSystem)
	{
		NativeArray<Entity> nativeArray = query.ToEntityArray(Allocator.TempJob);
		int length = nativeArray.Length;
		NativeArray<UITransportLineData> nativeArray2 = new NativeArray<UITransportLineData>(length, Allocator.Temp);
		for (int i = 0; i < length; i++)
		{
			nativeArray2[i] = BuildTransportLine(nativeArray[i], entityManager, prefabSystem);
		}
		nativeArray2.Sort();
		nativeArray.Dispose();
		return nativeArray2;
	}
```

- `public static GetStopCount(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Int32`  

```csharp
public static int GetStopCount(EntityManager entityManager, Entity entity)
	{
		DynamicBuffer<RouteWaypoint> buffer = entityManager.GetBuffer<RouteWaypoint>(entity, isReadOnly: true);
		int num = 0;
		for (int i = 0; i < buffer.Length; i++)
		{
			if (entityManager.TryGetComponent<Connected>(buffer[i].m_Waypoint, out var component) && entityManager.HasComponent<Game.Routes.TransportStop>(component.m_Connected) && !entityManager.HasComponent<TaxiStand>(component.m_Connected))
			{
				num++;
			}
		}
		return num;
	}
```


