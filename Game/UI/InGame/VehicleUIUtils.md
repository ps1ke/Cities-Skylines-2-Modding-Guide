# Game.UI.InGame.VehicleUIUtils

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class VehicleUIUtils
{
    public static System.Int32 GetAvailableVehicles(Unity.Entities.Entity vehicleOwnerEntity, Unity.Entities.EntityManager entityManager);
    public static Unity.Entities.Entity GetDestination(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity vehicleEntity);
    public static Game.UI.InGame.VehicleLocaleKey GetPoliceVehicleLocaleKey(Game.Prefabs.PolicePurpose purposeMask);
    public static Game.UI.InGame.VehicleStateLocaleKey GetStateKey(Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager);
    public static Game.UI.InGame.VehicleStateLocaleKey GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.PublicTransport publicTransportVehicle, Unity.Entities.EntityManager entityManager);
    public static Game.UI.InGame.VehicleStateLocaleKey GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.PersonalCar personalCar, Unity.Entities.EntityManager entityManager);
    public static Game.UI.InGame.VehicleStateLocaleKey GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.PostVan postVan, Unity.Entities.EntityManager entityManager);
    public static Game.UI.InGame.VehicleStateLocaleKey GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.PoliceCar policeCar, Unity.Entities.DynamicBuffer<Game.Simulation.ServiceDispatch> dispatches, Unity.Entities.EntityManager entityManager);
    public static Game.UI.InGame.VehicleStateLocaleKey GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.MaintenanceVehicle maintenanceVehicle, Unity.Entities.EntityManager entityManager);
    public static Game.UI.InGame.VehicleStateLocaleKey GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.Ambulance ambulance, Unity.Entities.EntityManager entityManager);
    public static Game.UI.InGame.VehicleStateLocaleKey GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.GarbageTruck garbageTruck, Unity.Entities.EntityManager entityManager);
    public static Game.UI.InGame.VehicleStateLocaleKey GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.FireEngine fireEngine, Unity.Entities.DynamicBuffer<Game.Simulation.ServiceDispatch> dispatches, Unity.Entities.EntityManager entityManager);
    public static Game.UI.InGame.VehicleStateLocaleKey GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.DeliveryTruck truck, Unity.Entities.EntityManager entityManager);
    public static Game.UI.InGame.VehicleStateLocaleKey GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.Hearse hearse, Unity.Entities.EntityManager entityManager);
    public static Game.UI.InGame.VehicleStateLocaleKey GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.CargoTransport cargoTransport, Unity.Entities.EntityManager entityManager);
    public static Game.UI.InGame.VehicleStateLocaleKey GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.Taxi taxi, Unity.Entities.EntityManager entityManager);
}
```


## Methods

- `public static GetAvailableVehicles(Unity.Entities.Entity vehicleOwnerEntity, Unity.Entities.EntityManager entityManager) : System.Int32`  

```csharp
public static int GetAvailableVehicles(Entity vehicleOwnerEntity, EntityManager entityManager)
	{
		float efficiency = 1f;
		if (entityManager.TryGetBuffer(vehicleOwnerEntity, isReadOnly: true, out DynamicBuffer<Efficiency> buffer))
		{
			efficiency = Mathf.Min(BuildingUtils.GetEfficiency(buffer), 1f);
		}
		int num = 0;
		if (entityManager.TryGetComponent<PrefabRef>(vehicleOwnerEntity, out var component))
		{
			DeathcareFacilityData data2;
			EmergencyShelterData data3;
			FireStationData data4;
			HospitalData data5;
			MaintenanceDepotData data6;
			PoliceStationData data7;
			PrisonData data8;
			TransportDepotData data9;
			PostFacilityData data10;
			TransportCompanyData component2;
			if (UpgradeUtils.TryGetCombinedComponent<GarbageFacilityData>(entityManager, vehicleOwnerEntity, component.m_Prefab, out var data))
			{
				num += BuildingUtils.GetVehicleCapacity(efficiency, data.m_VehicleCapacity);
			}
			else if (UpgradeUtils.TryGetCombinedComponent<DeathcareFacilityData>(entityManager, vehicleOwnerEntity, component.m_Prefab, out data2))
			{
				num += BuildingUtils.GetVehicleCapacity(efficiency, data2.m_HearseCapacity);
			}
			else if (UpgradeUtils.TryGetCombinedComponent<EmergencyShelterData>(entityManager, vehicleOwnerEntity, component.m_Prefab, out data3))
			{
				num += BuildingUtils.GetVehicleCapacity(efficiency, data3.m_VehicleCapacity);
			}
			else if (UpgradeUtils.TryGetCombinedComponent<FireStationData>(entityManager, vehicleOwnerEntity, component.m_Prefab, out data4))
			{
				num += BuildingUtils.GetVehicleCapacity(efficiency, data4.m_FireEngineCapacity);
				num += BuildingUtils.GetVehicleCapacity(efficiency, data4.m_FireHelicopterCapacity);
			}
			else if (UpgradeUtils.TryGetCombinedComponent<HospitalData>(entityManager, vehicleOwnerEntity, component.m_Prefab, out data5))
			{
				num += BuildingUtils.GetVehicleCapacity(efficiency, data5.m_AmbulanceCapacity);
				num += BuildingUtils.GetVehicleCapacity(efficiency, data5.m_MedicalHelicopterCapacity);
			}
			else if (UpgradeUtils.TryGetCombinedComponent<MaintenanceDepotData>(entityManager, vehicleOwnerEntity, component.m_Prefab, out data6))
			{
				num += BuildingUtils.GetVehicleCapacity(efficiency, data6.m_VehicleCapacity);
			}
			else if (UpgradeUtils.TryGetCombinedComponent<PoliceStationData>(entityManager, vehicleOwnerEntity, component.m_Prefab, out data7))
			{
				num += BuildingUtils.GetVehicleCapacity(efficiency, data7.m_PatrolCarCapacity);
				num += BuildingUtils.GetVehicleCapacity(efficiency, data7.m_PoliceHelicopterCapacity);
			}
			else if (UpgradeUtils.TryGetCombinedComponent<PrisonData>(entityManager, vehicleOwnerEntity, component.m_Prefab, out data8))
			{
				num += BuildingUtils.GetVehicleCapacity(efficiency, data8.m_PrisonVanCapacity);
			}
			else if (UpgradeUtils.TryGetCombinedComponent<TransportDepotData>(entityManager, vehicleOwnerEntity, component.m_Prefab, out data9))
			{
				num += BuildingUtils.GetVehicleCapacity(efficiency, data9.m_VehicleCapacity);
			}
			else if (UpgradeUtils.TryGetCombinedComponent<PostFacilityData>(entityManager, vehicleOwnerEntity, component.m_Prefab, out data10))
			{
				num += BuildingUtils.GetVehicleCapacity(efficiency, data10.m_PostVanCapacity);
				num += BuildingUtils.GetVehicleCapacity(efficiency, data10.m_PostTruckCapacity);
			}
			else if (entityManager.TryGetComponent<TransportCompanyData>(component.m_Prefab, out component2))
			{
				num += BuildingUtils.GetVehicleCapacity(efficiency, component2.m_MaxTransports);
			}
		}
		return num;
	}
```

- `public static GetDestination(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity vehicleEntity) : Unity.Entities.Entity`  

```csharp
public static Entity GetDestination(EntityManager entityManager, Entity vehicleEntity)
	{
		Entity entity = Entity.Null;
		if (entityManager.TryGetComponent<Target>(vehicleEntity, out var component))
		{
			entity = component.m_Target;
			if (entityManager.TryGetComponent<Connected>(entity, out var component2))
			{
				entity = component2.m_Connected;
			}
			if (entityManager.HasComponent<Game.Objects.OutsideConnection>(entity))
			{
				return entity;
			}
			if (entityManager.HasComponent<Vehicle>(entity))
			{
				return entity;
			}
			if (entityManager.HasComponent<CompanyData>(entity) && entityManager.TryGetComponent<PropertyRenter>(entity, out var component3))
			{
				return component3.m_Property;
			}
			if (entityManager.TryGetComponent<Owner>(entity, out var component4))
			{
				entity = component4.m_Owner;
			}
			if (entityManager.TryGetComponent<Game.Creatures.Resident>(entity, out var component5))
			{
				entity = component5.m_Citizen;
			}
			if (!entityManager.HasComponent<Connected>(component.m_Target) && entityManager.TryGetComponent<Waypoint>(component.m_Target, out var component6) && entityManager.TryGetBuffer(entity, isReadOnly: true, out DynamicBuffer<RouteWaypoint> buffer))
			{
				int num = component6.m_Index + 1;
				for (int i = 0; i < buffer.Length; i++)
				{
					num += i;
					num = math.select(num, 0, num >= buffer.Length);
					if (entityManager.TryGetComponent<Connected>(buffer[num].m_Waypoint, out component2))
					{
						entity = component2.m_Connected;
						break;
					}
				}
			}
		}
		return entity;
	}
```

- `public static GetPoliceVehicleLocaleKey(Game.Prefabs.PolicePurpose purposeMask) : Game.UI.InGame.VehicleLocaleKey`  

```csharp
public static VehicleLocaleKey GetPoliceVehicleLocaleKey(PolicePurpose purposeMask)
	{
		if ((purposeMask & PolicePurpose.Intelligence) != 0)
		{
			return VehicleLocaleKey.PoliceIntelligenceCar;
		}
		if ((purposeMask & PolicePurpose.Patrol) != 0)
		{
			return VehicleLocaleKey.PolicePatrolCar;
		}
		return VehicleLocaleKey.Vehicle;
	}
```

- `public static GetStateKey(Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager) : Game.UI.InGame.VehicleStateLocaleKey`  

```csharp
public static VehicleStateLocaleKey GetStateKey(Entity entity, Game.Vehicles.Taxi taxi, EntityManager entityManager)
	{
		if (entityManager.HasComponent<InvolvedInAccident>(entity))
		{
			return VehicleStateLocaleKey.InvolvedInAccident;
		}
		if (entityManager.HasComponent<ParkedCar>(entity))
		{
			return VehicleStateLocaleKey.Parked;
		}
		if ((taxi.m_State & TaxiFlags.Returning) != 0)
		{
			return VehicleStateLocaleKey.Returning;
		}
		if ((taxi.m_State & TaxiFlags.Dispatched) != 0)
		{
			return VehicleStateLocaleKey.Dispatched;
		}
		if ((taxi.m_State & TaxiFlags.Boarding) != 0)
		{
			return VehicleStateLocaleKey.Boarding;
		}
		if ((taxi.m_State & TaxiFlags.Transporting) != 0)
		{
			return VehicleStateLocaleKey.Transporting;
		}
		return VehicleStateLocaleKey.EnRoute;
	}
```

- `public static GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.PublicTransport publicTransportVehicle, Unity.Entities.EntityManager entityManager) : Game.UI.InGame.VehicleStateLocaleKey`  

```csharp
public static VehicleStateLocaleKey GetStateKey(Entity entity, Game.Vehicles.Taxi taxi, EntityManager entityManager)
	{
		if (entityManager.HasComponent<InvolvedInAccident>(entity))
		{
			return VehicleStateLocaleKey.InvolvedInAccident;
		}
		if (entityManager.HasComponent<ParkedCar>(entity))
		{
			return VehicleStateLocaleKey.Parked;
		}
		if ((taxi.m_State & TaxiFlags.Returning) != 0)
		{
			return VehicleStateLocaleKey.Returning;
		}
		if ((taxi.m_State & TaxiFlags.Dispatched) != 0)
		{
			return VehicleStateLocaleKey.Dispatched;
		}
		if ((taxi.m_State & TaxiFlags.Boarding) != 0)
		{
			return VehicleStateLocaleKey.Boarding;
		}
		if ((taxi.m_State & TaxiFlags.Transporting) != 0)
		{
			return VehicleStateLocaleKey.Transporting;
		}
		return VehicleStateLocaleKey.EnRoute;
	}
```

- `public static GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.PersonalCar personalCar, Unity.Entities.EntityManager entityManager) : Game.UI.InGame.VehicleStateLocaleKey`  

```csharp
public static VehicleStateLocaleKey GetStateKey(Entity entity, Game.Vehicles.Taxi taxi, EntityManager entityManager)
	{
		if (entityManager.HasComponent<InvolvedInAccident>(entity))
		{
			return VehicleStateLocaleKey.InvolvedInAccident;
		}
		if (entityManager.HasComponent<ParkedCar>(entity))
		{
			return VehicleStateLocaleKey.Parked;
		}
		if ((taxi.m_State & TaxiFlags.Returning) != 0)
		{
			return VehicleStateLocaleKey.Returning;
		}
		if ((taxi.m_State & TaxiFlags.Dispatched) != 0)
		{
			return VehicleStateLocaleKey.Dispatched;
		}
		if ((taxi.m_State & TaxiFlags.Boarding) != 0)
		{
			return VehicleStateLocaleKey.Boarding;
		}
		if ((taxi.m_State & TaxiFlags.Transporting) != 0)
		{
			return VehicleStateLocaleKey.Transporting;
		}
		return VehicleStateLocaleKey.EnRoute;
	}
```

- `public static GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.PostVan postVan, Unity.Entities.EntityManager entityManager) : Game.UI.InGame.VehicleStateLocaleKey`  

```csharp
public static VehicleStateLocaleKey GetStateKey(Entity entity, Game.Vehicles.Taxi taxi, EntityManager entityManager)
	{
		if (entityManager.HasComponent<InvolvedInAccident>(entity))
		{
			return VehicleStateLocaleKey.InvolvedInAccident;
		}
		if (entityManager.HasComponent<ParkedCar>(entity))
		{
			return VehicleStateLocaleKey.Parked;
		}
		if ((taxi.m_State & TaxiFlags.Returning) != 0)
		{
			return VehicleStateLocaleKey.Returning;
		}
		if ((taxi.m_State & TaxiFlags.Dispatched) != 0)
		{
			return VehicleStateLocaleKey.Dispatched;
		}
		if ((taxi.m_State & TaxiFlags.Boarding) != 0)
		{
			return VehicleStateLocaleKey.Boarding;
		}
		if ((taxi.m_State & TaxiFlags.Transporting) != 0)
		{
			return VehicleStateLocaleKey.Transporting;
		}
		return VehicleStateLocaleKey.EnRoute;
	}
```

- `public static GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.PoliceCar policeCar, Unity.Entities.DynamicBuffer<Game.Simulation.ServiceDispatch> dispatches, Unity.Entities.EntityManager entityManager) : Game.UI.InGame.VehicleStateLocaleKey`  

```csharp
public static VehicleStateLocaleKey GetStateKey(Entity entity, Game.Vehicles.Taxi taxi, EntityManager entityManager)
	{
		if (entityManager.HasComponent<InvolvedInAccident>(entity))
		{
			return VehicleStateLocaleKey.InvolvedInAccident;
		}
		if (entityManager.HasComponent<ParkedCar>(entity))
		{
			return VehicleStateLocaleKey.Parked;
		}
		if ((taxi.m_State & TaxiFlags.Returning) != 0)
		{
			return VehicleStateLocaleKey.Returning;
		}
		if ((taxi.m_State & TaxiFlags.Dispatched) != 0)
		{
			return VehicleStateLocaleKey.Dispatched;
		}
		if ((taxi.m_State & TaxiFlags.Boarding) != 0)
		{
			return VehicleStateLocaleKey.Boarding;
		}
		if ((taxi.m_State & TaxiFlags.Transporting) != 0)
		{
			return VehicleStateLocaleKey.Transporting;
		}
		return VehicleStateLocaleKey.EnRoute;
	}
```

- `public static GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.MaintenanceVehicle maintenanceVehicle, Unity.Entities.EntityManager entityManager) : Game.UI.InGame.VehicleStateLocaleKey`  

```csharp
public static VehicleStateLocaleKey GetStateKey(Entity entity, Game.Vehicles.Taxi taxi, EntityManager entityManager)
	{
		if (entityManager.HasComponent<InvolvedInAccident>(entity))
		{
			return VehicleStateLocaleKey.InvolvedInAccident;
		}
		if (entityManager.HasComponent<ParkedCar>(entity))
		{
			return VehicleStateLocaleKey.Parked;
		}
		if ((taxi.m_State & TaxiFlags.Returning) != 0)
		{
			return VehicleStateLocaleKey.Returning;
		}
		if ((taxi.m_State & TaxiFlags.Dispatched) != 0)
		{
			return VehicleStateLocaleKey.Dispatched;
		}
		if ((taxi.m_State & TaxiFlags.Boarding) != 0)
		{
			return VehicleStateLocaleKey.Boarding;
		}
		if ((taxi.m_State & TaxiFlags.Transporting) != 0)
		{
			return VehicleStateLocaleKey.Transporting;
		}
		return VehicleStateLocaleKey.EnRoute;
	}
```

- `public static GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.Ambulance ambulance, Unity.Entities.EntityManager entityManager) : Game.UI.InGame.VehicleStateLocaleKey`  

```csharp
public static VehicleStateLocaleKey GetStateKey(Entity entity, Game.Vehicles.Taxi taxi, EntityManager entityManager)
	{
		if (entityManager.HasComponent<InvolvedInAccident>(entity))
		{
			return VehicleStateLocaleKey.InvolvedInAccident;
		}
		if (entityManager.HasComponent<ParkedCar>(entity))
		{
			return VehicleStateLocaleKey.Parked;
		}
		if ((taxi.m_State & TaxiFlags.Returning) != 0)
		{
			return VehicleStateLocaleKey.Returning;
		}
		if ((taxi.m_State & TaxiFlags.Dispatched) != 0)
		{
			return VehicleStateLocaleKey.Dispatched;
		}
		if ((taxi.m_State & TaxiFlags.Boarding) != 0)
		{
			return VehicleStateLocaleKey.Boarding;
		}
		if ((taxi.m_State & TaxiFlags.Transporting) != 0)
		{
			return VehicleStateLocaleKey.Transporting;
		}
		return VehicleStateLocaleKey.EnRoute;
	}
```

- `public static GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.GarbageTruck garbageTruck, Unity.Entities.EntityManager entityManager) : Game.UI.InGame.VehicleStateLocaleKey`  

```csharp
public static VehicleStateLocaleKey GetStateKey(Entity entity, Game.Vehicles.Taxi taxi, EntityManager entityManager)
	{
		if (entityManager.HasComponent<InvolvedInAccident>(entity))
		{
			return VehicleStateLocaleKey.InvolvedInAccident;
		}
		if (entityManager.HasComponent<ParkedCar>(entity))
		{
			return VehicleStateLocaleKey.Parked;
		}
		if ((taxi.m_State & TaxiFlags.Returning) != 0)
		{
			return VehicleStateLocaleKey.Returning;
		}
		if ((taxi.m_State & TaxiFlags.Dispatched) != 0)
		{
			return VehicleStateLocaleKey.Dispatched;
		}
		if ((taxi.m_State & TaxiFlags.Boarding) != 0)
		{
			return VehicleStateLocaleKey.Boarding;
		}
		if ((taxi.m_State & TaxiFlags.Transporting) != 0)
		{
			return VehicleStateLocaleKey.Transporting;
		}
		return VehicleStateLocaleKey.EnRoute;
	}
```

- `public static GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.FireEngine fireEngine, Unity.Entities.DynamicBuffer<Game.Simulation.ServiceDispatch> dispatches, Unity.Entities.EntityManager entityManager) : Game.UI.InGame.VehicleStateLocaleKey`  

```csharp
public static VehicleStateLocaleKey GetStateKey(Entity entity, Game.Vehicles.Taxi taxi, EntityManager entityManager)
	{
		if (entityManager.HasComponent<InvolvedInAccident>(entity))
		{
			return VehicleStateLocaleKey.InvolvedInAccident;
		}
		if (entityManager.HasComponent<ParkedCar>(entity))
		{
			return VehicleStateLocaleKey.Parked;
		}
		if ((taxi.m_State & TaxiFlags.Returning) != 0)
		{
			return VehicleStateLocaleKey.Returning;
		}
		if ((taxi.m_State & TaxiFlags.Dispatched) != 0)
		{
			return VehicleStateLocaleKey.Dispatched;
		}
		if ((taxi.m_State & TaxiFlags.Boarding) != 0)
		{
			return VehicleStateLocaleKey.Boarding;
		}
		if ((taxi.m_State & TaxiFlags.Transporting) != 0)
		{
			return VehicleStateLocaleKey.Transporting;
		}
		return VehicleStateLocaleKey.EnRoute;
	}
```

- `public static GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.DeliveryTruck truck, Unity.Entities.EntityManager entityManager) : Game.UI.InGame.VehicleStateLocaleKey`  

```csharp
public static VehicleStateLocaleKey GetStateKey(Entity entity, Game.Vehicles.Taxi taxi, EntityManager entityManager)
	{
		if (entityManager.HasComponent<InvolvedInAccident>(entity))
		{
			return VehicleStateLocaleKey.InvolvedInAccident;
		}
		if (entityManager.HasComponent<ParkedCar>(entity))
		{
			return VehicleStateLocaleKey.Parked;
		}
		if ((taxi.m_State & TaxiFlags.Returning) != 0)
		{
			return VehicleStateLocaleKey.Returning;
		}
		if ((taxi.m_State & TaxiFlags.Dispatched) != 0)
		{
			return VehicleStateLocaleKey.Dispatched;
		}
		if ((taxi.m_State & TaxiFlags.Boarding) != 0)
		{
			return VehicleStateLocaleKey.Boarding;
		}
		if ((taxi.m_State & TaxiFlags.Transporting) != 0)
		{
			return VehicleStateLocaleKey.Transporting;
		}
		return VehicleStateLocaleKey.EnRoute;
	}
```

- `public static GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.Hearse hearse, Unity.Entities.EntityManager entityManager) : Game.UI.InGame.VehicleStateLocaleKey`  

```csharp
public static VehicleStateLocaleKey GetStateKey(Entity entity, Game.Vehicles.Taxi taxi, EntityManager entityManager)
	{
		if (entityManager.HasComponent<InvolvedInAccident>(entity))
		{
			return VehicleStateLocaleKey.InvolvedInAccident;
		}
		if (entityManager.HasComponent<ParkedCar>(entity))
		{
			return VehicleStateLocaleKey.Parked;
		}
		if ((taxi.m_State & TaxiFlags.Returning) != 0)
		{
			return VehicleStateLocaleKey.Returning;
		}
		if ((taxi.m_State & TaxiFlags.Dispatched) != 0)
		{
			return VehicleStateLocaleKey.Dispatched;
		}
		if ((taxi.m_State & TaxiFlags.Boarding) != 0)
		{
			return VehicleStateLocaleKey.Boarding;
		}
		if ((taxi.m_State & TaxiFlags.Transporting) != 0)
		{
			return VehicleStateLocaleKey.Transporting;
		}
		return VehicleStateLocaleKey.EnRoute;
	}
```

- `public static GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.CargoTransport cargoTransport, Unity.Entities.EntityManager entityManager) : Game.UI.InGame.VehicleStateLocaleKey`  

```csharp
public static VehicleStateLocaleKey GetStateKey(Entity entity, Game.Vehicles.Taxi taxi, EntityManager entityManager)
	{
		if (entityManager.HasComponent<InvolvedInAccident>(entity))
		{
			return VehicleStateLocaleKey.InvolvedInAccident;
		}
		if (entityManager.HasComponent<ParkedCar>(entity))
		{
			return VehicleStateLocaleKey.Parked;
		}
		if ((taxi.m_State & TaxiFlags.Returning) != 0)
		{
			return VehicleStateLocaleKey.Returning;
		}
		if ((taxi.m_State & TaxiFlags.Dispatched) != 0)
		{
			return VehicleStateLocaleKey.Dispatched;
		}
		if ((taxi.m_State & TaxiFlags.Boarding) != 0)
		{
			return VehicleStateLocaleKey.Boarding;
		}
		if ((taxi.m_State & TaxiFlags.Transporting) != 0)
		{
			return VehicleStateLocaleKey.Transporting;
		}
		return VehicleStateLocaleKey.EnRoute;
	}
```

- `public static GetStateKey(Unity.Entities.Entity entity, Game.Vehicles.Taxi taxi, Unity.Entities.EntityManager entityManager) : Game.UI.InGame.VehicleStateLocaleKey`  

```csharp
public static VehicleStateLocaleKey GetStateKey(Entity entity, Game.Vehicles.Taxi taxi, EntityManager entityManager)
	{
		if (entityManager.HasComponent<InvolvedInAccident>(entity))
		{
			return VehicleStateLocaleKey.InvolvedInAccident;
		}
		if (entityManager.HasComponent<ParkedCar>(entity))
		{
			return VehicleStateLocaleKey.Parked;
		}
		if ((taxi.m_State & TaxiFlags.Returning) != 0)
		{
			return VehicleStateLocaleKey.Returning;
		}
		if ((taxi.m_State & TaxiFlags.Dispatched) != 0)
		{
			return VehicleStateLocaleKey.Dispatched;
		}
		if ((taxi.m_State & TaxiFlags.Boarding) != 0)
		{
			return VehicleStateLocaleKey.Boarding;
		}
		if ((taxi.m_State & TaxiFlags.Transporting) != 0)
		{
			return VehicleStateLocaleKey.Transporting;
		}
		return VehicleStateLocaleKey.EnRoute;
	}
```


## Nested types

- `Game.UI.InGame.VehicleUIUtils+EntityWrapper`  

