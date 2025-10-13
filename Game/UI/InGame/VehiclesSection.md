# Game.UI.InGame.VehiclesSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class VehiclesSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Game.UI.InGame.VehicleLocaleKey <vehicleKey>k__BackingField;
    private System.Int32 <vehicleCount>k__BackingField;
    private System.Int32 <availableVehicleCount>k__BackingField;
    private System.Int32 <vehicleCapacity>k__BackingField;
    private Unity.Collections.NativeList<Game.UI.InGame.VehiclesSection+UIVehicle> <vehicleList>k__BackingField;
    private Unity.Entities.DynamicBuffer<Game.Vehicles.OwnedVehicle> m_Buffer;
    private Unity.Entities.Entity m_CompanyEntity;

    protected System.String group { protected get; }
    private Game.UI.InGame.VehicleLocaleKey vehicleKey { private get; private set; }
    private System.Int32 vehicleCount { private get; private set; }
    private System.Int32 availableVehicleCount { private get; private set; }
    private System.Int32 vehicleCapacity { private get; private set; }
    private Unity.Collections.NativeList<Game.UI.InGame.VehiclesSection+UIVehicle> vehicleList { private get; private set; }

    public VehiclesSection();

    public static System.Void AddVehicle(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity vehicle, Unity.Collections.NativeList<Game.UI.InGame.VehiclesSection+UIVehicle> vehicleList);
    public static System.Void BindVehicle(Game.UI.NameSystem nameSystem, Colossal.UI.Binding.IJsonWriter binder, Game.UI.InGame.VehiclesSection+UIVehicle vehicle);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private Game.UI.InGame.VehicleLocaleKey <vehicleKey>k__BackingField`  

```csharp
private Game.UI.InGame.VehicleLocaleKey <vehicleKey>k__BackingField;
```

- `private System.Int32 <vehicleCount>k__BackingField`  

```csharp
private System.Int32 <vehicleCount>k__BackingField;
```

- `private System.Int32 <availableVehicleCount>k__BackingField`  

```csharp
private System.Int32 <availableVehicleCount>k__BackingField;
```

- `private System.Int32 <vehicleCapacity>k__BackingField`  

```csharp
private System.Int32 <vehicleCapacity>k__BackingField;
```

- `private Unity.Collections.NativeList<Game.UI.InGame.VehiclesSection+UIVehicle> <vehicleList>k__BackingField`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.VehiclesSection+UIVehicle> <vehicleList>k__BackingField;
```

- `private Unity.Entities.DynamicBuffer<Game.Vehicles.OwnedVehicle> m_Buffer`  

```csharp
private Unity.Entities.DynamicBuffer<Game.Vehicles.OwnedVehicle> m_Buffer;
```

- `private Unity.Entities.Entity m_CompanyEntity`  

```csharp
private Unity.Entities.Entity m_CompanyEntity;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private Game.UI.InGame.VehicleLocaleKey vehicleKey { private get; private set }`  

```csharp
private Game.UI.InGame.VehicleLocaleKey vehicleKey { private get; private set; }
```

- `private System.Int32 vehicleCount { private get; private set }`  

```csharp
private System.Int32 vehicleCount { private get; private set; }
```

- `private System.Int32 availableVehicleCount { private get; private set }`  

```csharp
private System.Int32 availableVehicleCount { private get; private set; }
```

- `private System.Int32 vehicleCapacity { private get; private set }`  

```csharp
private System.Int32 vehicleCapacity { private get; private set; }
```

- `private Unity.Collections.NativeList<Game.UI.InGame.VehiclesSection+UIVehicle> vehicleList { private get; private set }`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.VehiclesSection+UIVehicle> vehicleList { private get; private set; }
```


## Constructors

- `public VehiclesSection()`  

```csharp
[Preserve]
	public VehiclesSection()
	{
	}
```


## Methods

- `public static AddVehicle(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity vehicle, Unity.Collections.NativeList<Game.UI.InGame.VehiclesSection+UIVehicle> vehicleList) : System.Void`  

```csharp
public static void AddVehicle(EntityManager entityManager, Entity vehicle, NativeList<UIVehicle> vehicleList)
	{
		VehicleStateLocaleKey stateKey = VehicleUIUtils.GetStateKey(vehicle, entityManager);
		PrefabRef componentData = entityManager.GetComponentData<PrefabRef>(vehicle);
		VehicleLocaleKey vehicleLocaleKey = VehicleLocaleKey.Vehicle;
		if (entityManager.HasComponent<Car>(vehicle))
		{
			if (entityManager.HasComponent<Game.Vehicles.Ambulance>(vehicle))
			{
				vehicleLocaleKey = VehicleLocaleKey.Ambulance;
			}
			if (entityManager.TryGetComponent<PoliceCarData>(componentData.m_Prefab, out var component))
			{
				vehicleLocaleKey = VehicleUIUtils.GetPoliceVehicleLocaleKey(component.m_PurposeMask);
			}
			if (entityManager.HasComponent<Game.Vehicles.FireEngine>(vehicle))
			{
				vehicleLocaleKey = VehicleLocaleKey.FireEngine;
			}
			if (entityManager.HasComponent<Game.Vehicles.PostVan>(vehicle))
			{
				vehicleLocaleKey = VehicleLocaleKey.PostVan;
			}
			if (entityManager.HasComponent<Game.Vehicles.DeliveryTruck>(vehicle))
			{
				vehicleLocaleKey = VehicleLocaleKey.DeliveryTruck;
			}
			if (entityManager.HasComponent<Game.Vehicles.Hearse>(vehicle))
			{
				vehicleLocaleKey = VehicleLocaleKey.Hearse;
			}
			if (entityManager.HasComponent<Game.Vehicles.GarbageTruck>(vehicle))
			{
				vehicleLocaleKey = VehicleLocaleKey.GarbageTruck;
			}
			if (entityManager.HasComponent<Game.Vehicles.Taxi>(vehicle))
			{
				vehicleLocaleKey = VehicleLocaleKey.Taxi;
			}
			if (entityManager.HasComponent<Game.Vehicles.MaintenanceVehicle>(vehicle))
			{
				vehicleLocaleKey = VehicleLocaleKey.MaintenanceVehicle;
			}
			if (entityManager.HasComponent<Game.Vehicles.PublicTransport>(vehicle) && entityManager.TryGetComponent<PublicTransportVehicleData>(componentData.m_Prefab, out var component2))
			{
				vehicleLocaleKey = (((component2.m_PurposeMask & PublicTransportPurpose.PrisonerTransport) != 0) ? VehicleLocaleKey.PrisonVan : (((component2.m_PurposeMask & PublicTransportPurpose.Evacuation) != 0) ? VehicleLocaleKey.EvacuationBus : VehicleLocaleKey.PublicTransportVehicle));
			}
		}
		if (entityManager.HasComponent<Helicopter>(vehicle))
		{
			if (entityManager.HasComponent<Game.Vehicles.Ambulance>(vehicle))
			{
				vehicleLocaleKey = VehicleLocaleKey.MedicalHelicopter;
			}
			if (entityManager.HasComponent<Game.Vehicles.PoliceCar>(vehicle))
			{
				vehicleLocaleKey = VehicleLocaleKey.PoliceHelicopter;
			}
			if (entityManager.HasComponent<Game.Vehicles.FireEngine>(vehicle))
			{
				vehicleLocaleKey = VehicleLocaleKey.FireHelicopter;
			}
		}
		vehicleList.Add(new UIVehicle(vehicle, vehicleLocaleKey, stateKey));
	}
```

- `public static BindVehicle(Game.UI.NameSystem nameSystem, Colossal.UI.Binding.IJsonWriter binder, Game.UI.InGame.VehiclesSection+UIVehicle vehicle) : System.Void`  

```csharp
public static void BindVehicle(NameSystem nameSystem, IJsonWriter binder, UIVehicle vehicle)
	{
		binder.TypeBegin("Game.UI.InGame.VehiclesSection.Vehicle");
		binder.PropertyName("entity");
		binder.Write(vehicle.entity);
		binder.PropertyName("name");
		nameSystem.BindName(binder, vehicle.entity);
		binder.PropertyName("vehicleKey");
		binder.Write(Enum.GetName(typeof(VehicleLocaleKey), vehicle.vehicleKey));
		binder.PropertyName("stateKey");
		binder.Write(Enum.GetName(typeof(VehicleStateLocaleKey), vehicle.stateKey));
		binder.TypeEnd();
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		vehicleList = new NativeList<UIVehicle>(50, Allocator.Persistent);
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		vehicleList.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		vehicleKey = VehicleLocaleKey.Vehicle;
		string item = VehicleLocaleKey.Vehicle.ToString();
		Entity entity = selectedEntity;
		Entity entity2 = selectedPrefab;
		if (m_CompanyEntity != Entity.Null)
		{
			entity = m_CompanyEntity;
			entity2 = (base.EntityManager.TryGetComponent<PrefabRef>(m_CompanyEntity, out var component) ? component.m_Prefab : Entity.Null);
		}
		if (TryGetComponentWithUpgrades<HospitalData>(entity, entity2, out var data))
		{
			int ambulanceCapacity = data.m_AmbulanceCapacity;
			int medicalHelicopterCapacity = data.m_MedicalHelicopterCapacity;
			vehicleCapacity += ambulanceCapacity + medicalHelicopterCapacity;
		}
		if (TryGetComponentWithUpgrades<PoliceStationData>(entity, entity2, out var data2))
		{
			int patrolCarCapacity = data2.m_PatrolCarCapacity;
			int policeHelicopterCapacity = data2.m_PoliceHelicopterCapacity;
			vehicleCapacity += patrolCarCapacity + policeHelicopterCapacity;
		}
		if (TryGetComponentWithUpgrades<FireStationData>(entity, entity2, out var data3))
		{
			int fireEngineCapacity = data3.m_FireEngineCapacity;
			int fireHelicopterCapacity = data3.m_FireHelicopterCapacity;
			vehicleCapacity += fireEngineCapacity + fireHelicopterCapacity;
		}
		if (TryGetComponentWithUpgrades<PostFacilityData>(entity, entity2, out var data4))
		{
			int postVanCapacity = data4.m_PostVanCapacity;
			int postTruckCapacity = data4.m_PostTruckCapacity;
			vehicleCapacity += postVanCapacity + postTruckCapacity;
		}
		if (TryGetComponentWithUpgrades<MaintenanceDepotData>(entity, entity2, out var data5))
		{
			vehicleCapacity += data5.m_VehicleCapacity;
		}
		if (TryGetComponentWithUpgrades<TransportDepotData>(entity, entity2, out var data6))
		{
			vehicleCapacity += data6.m_VehicleCapacity;
			item = VehicleLocaleKey.PublicTransportVehicle.ToString();
		}
		if (TryGetComponentWithUpgrades<DeathcareFacilityData>(entity, entity2, out var data7))
		{
			vehicleCapacity += data7.m_HearseCapacity;
		}
		if (TryGetComponentWithUpgrades<GarbageFacilityData>(entity, entity2, out var data8))
		{
			vehicleCapacity += data8.m_VehicleCapacity;
		}
		if (TryGetComponentWithUpgrades<PrisonData>(entity, entity2, out var data9))
		{
			vehicleCapacity += data9.m_PrisonVanCapacity;
		}
		if (TryGetComponentWithUpgrades<EmergencyShelterData>(entity, entity2, out var data10))
		{
			vehicleCapacity += data10.m_VehicleCapacity;
		}
		if (base.EntityManager.TryGetComponent<TransportCompanyData>(entity2, out var component2))
		{
			vehicleCapacity += component2.m_MaxTransports;
		}
		bool flag = m_Buffer.Length > 0 && vehicleCapacity == 0;
		if (base.EntityManager.HasComponent<Household>(selectedEntity))
		{
			item = VehicleLocaleKey.HouseholdVehicle.ToString();
		}
		for (int i = 0; i < m_Buffer.Length; i++)
		{
			Entity vehicle = m_Buffer[i].m_Vehicle;
			if (!base.EntityManager.HasComponent<ParkedCar>(vehicle) && !base.EntityManager.HasComponent<ParkedTrain>(vehicle))
			{
				AddVehicle(base.EntityManager, vehicle, vehicleList);
			}
		}
		base.tooltipKeys.Add(item);
		vehicleCount = vehicleList.Length;
		if (flag)
		{
			vehicleCapacity = m_Buffer.Length;
			availableVehicleCount = vehicleCapacity;
		}
		else
		{
			availableVehicleCount = VehicleUIUtils.GetAvailableVehicles(entity, base.EntityManager);
		}
		vehicleList.Sort();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		base.visible = Visible();
	}
```

- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public override void OnWriteProperties(IJsonWriter writer)
	{
		writer.PropertyName("vehicleKey");
		writer.Write(Enum.GetName(typeof(VehicleLocaleKey), vehicleKey));
		writer.PropertyName("vehicleCount");
		writer.Write(vehicleCount);
		writer.PropertyName("availableVehicleCount");
		writer.Write(availableVehicleCount);
		writer.PropertyName("vehicleCapacity");
		writer.Write(vehicleCapacity);
		vehicleList.Sort();
		writer.PropertyName("vehicleList");
		writer.ArrayBegin(vehicleList.Length);
		for (int i = 0; i < vehicleList.Length; i++)
		{
			BindVehicle(m_NameSystem, writer, vehicleList[i]);
		}
		writer.ArrayEnd();
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		vehicleCount = 0;
		vehicleCapacity = 0;
		vehicleList.Clear();
		m_Buffer = default(DynamicBuffer<OwnedVehicle>);
		m_CompanyEntity = Entity.Null;
	}
```

- `private Visible() : System.Boolean`  

```csharp
private bool Visible()
	{
		if (!base.EntityManager.TryGetBuffer(selectedEntity, isReadOnly: true, out m_Buffer))
		{
			if (CompanyUIUtils.HasCompany(base.EntityManager, selectedEntity, selectedPrefab, out m_CompanyEntity) && base.EntityManager.TryGetComponent<PrefabRef>(m_CompanyEntity, out var component) && base.EntityManager.HasComponent<TransportCompanyData>(component.m_Prefab))
			{
				return base.EntityManager.TryGetBuffer(m_CompanyEntity, isReadOnly: true, out m_Buffer);
			}
			return false;
		}
		return true;
	}
```


## Nested types

- `Game.UI.InGame.VehiclesSection+UIVehicle`  

