# Game.Effects.EffectControlData

**Assembly:** `Game`  
**Namespace:** `Game.Effects`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct EffectControlData
{
    public Unity.Entities.ComponentLookup<Game.Common.Owner> m_Owners;
    public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_Transforms;
    public Unity.Entities.ComponentLookup<Game.Tools.Hidden> m_Hidden;
    public Unity.Entities.ComponentLookup<Game.Prefabs.EffectData> m_EffectDatas;
    public Unity.Entities.ComponentLookup<Game.Prefabs.LightEffectData> m_LightEffectDatas;
    public Unity.Entities.ComponentLookup<Game.Buildings.Building> m_Buildings;
    public Unity.Entities.ComponentLookup<Game.Buildings.Signature> m_SignatureBuildings;
    public Unity.Entities.ComponentLookup<Game.Vehicles.Vehicle> m_Vehicles;
    public Unity.Entities.ComponentLookup<Game.Vehicles.Car> m_Cars;
    public Unity.Entities.ComponentLookup<Game.Vehicles.Aircraft> m_Aircraft;
    public Unity.Entities.ComponentLookup<Game.Vehicles.Watercraft> m_Watercraft;
    public Unity.Entities.ComponentLookup<Game.Vehicles.ParkedCar> m_ParkedCars;
    public Unity.Entities.ComponentLookup<Game.Vehicles.ParkedTrain> m_ParkedTrains;
    public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_Prefabs;
    public Unity.Entities.ComponentLookup<Game.Events.OnFire> m_OnFires;
    public Unity.Entities.ComponentLookup<Game.Vehicles.FireEngine> m_FireEngines;
    public Unity.Entities.ComponentLookup<Game.Tools.Temp> m_Temps;
    public Unity.Entities.ComponentLookup<Game.Vehicles.PublicTransport> m_PublicTransports;
    public Unity.Entities.ComponentLookup<Game.Vehicles.Taxi> m_Taxis;
    public Unity.Entities.ComponentLookup<Game.Vehicles.CargoTransport> m_CargoTransports;
    public Unity.Entities.ComponentLookup<Game.Vehicles.PersonalCar> m_PersonalCars;
    public Unity.Entities.ComponentLookup<Game.Buildings.ServiceUpgrade> m_ServiceUpgrades;
    public Unity.Entities.ComponentLookup<Game.Buildings.Extension> m_Extensions;
    public Unity.Entities.ComponentLookup<Game.Events.WeatherPhenomenon> m_WeatherPhenomenonData;
    public Unity.Entities.ComponentLookup<Game.Common.PseudoRandomSeed> m_PseudoRandomSeeds;
    public Unity.Entities.ComponentLookup<Game.Common.Destroyed> m_Destroyeds;
    public Unity.Entities.ComponentLookup<Game.Buildings.EarlyDisasterWarningDuration> m_EarlyDisasterWarningDurations;
    public Unity.Entities.ComponentLookup<Game.Buildings.WaterPumpingStation> m_WaterPumpingStations;
    public Unity.Entities.ComponentLookup<Game.Buildings.SewageOutlet> m_SewageOutlets;
    public Unity.Entities.ComponentLookup<Game.Buildings.WaterTower> m_WaterTowers;
    public Unity.Entities.ComponentLookup<Game.Objects.StreetLight> m_StreetLights;
    public Unity.Entities.ComponentLookup<Game.Objects.Stopped> m_Stoppeds;
    public Unity.Entities.ComponentLookup<Game.Net.Composition> m_Composition;
    public Unity.Entities.ComponentLookup<Game.Prefabs.NetCompositionData> m_NetCompositionData;
    public Unity.Entities.ComponentLookup<Game.Buildings.ExtractorFacility> m_ExtractorData;
    public Unity.Entities.ComponentLookup<Game.Objects.Attachment> m_AttachmentData;
    public Unity.Entities.BufferLookup<Game.Objects.TransformFrame> m_TransformFrames;
    public Unity.Entities.BufferLookup<Game.Buildings.Renter> m_Renter;
    public Unity.Entities.ComponentLookup<Game.Net.TrafficLights> m_TrafficLights;
    public Game.Effects.EffectFlagSystem+EffectFlagData m_EffectFlagData;
    public System.UInt32 m_SimulationFrame;
    public Unity.Entities.Entity m_Selected;

    public EffectControlData(Unity.Entities.SystemBase system);

    private System.Boolean CheckConditions(Unity.Entities.Entity owner, Unity.Entities.Entity buildingOwner, Unity.Entities.Entity topOwner, Unity.Entities.Entity effect);
    private System.Boolean CheckTrigger(Unity.Entities.Entity owner, Unity.Entities.Entity buildingOwner, Unity.Entities.Entity topOwner, Game.Prefabs.EffectConditionFlags flag, System.Boolean forbidden);
    private System.Boolean CheckTriggers(Unity.Entities.Entity owner, Unity.Entities.Entity buildingOwner, Unity.Entities.Entity topOwner, Game.Prefabs.EffectCondition condition);
    private Unity.Mathematics.Random GetRandom(Unity.Entities.Entity owner);
    private Unity.Entities.Entity GetRealOwner(Unity.Entities.Entity owner, Unity.Entities.Entity& buildingOwner);
    public System.Boolean ShouldBeEnabled(Unity.Entities.Entity owner, Unity.Entities.Entity prefab, System.Boolean checkEnabled, System.Boolean isEditorContainer);
    public System.Void Update(Unity.Entities.SystemBase system, Game.Effects.EffectFlagSystem+EffectFlagData effectFlagData, System.UInt32 simulationFrame, Unity.Entities.Entity selected);
}
```


## Fields

- `public Unity.Entities.ComponentLookup<Game.Common.Owner> m_Owners`  

```csharp
public Unity.Entities.ComponentLookup<Game.Common.Owner> m_Owners;
```

- `public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_Transforms`  

```csharp
public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_Transforms;
```

- `public Unity.Entities.ComponentLookup<Game.Tools.Hidden> m_Hidden`  

```csharp
public Unity.Entities.ComponentLookup<Game.Tools.Hidden> m_Hidden;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.EffectData> m_EffectDatas`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.EffectData> m_EffectDatas;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.LightEffectData> m_LightEffectDatas`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.LightEffectData> m_LightEffectDatas;
```

- `public Unity.Entities.ComponentLookup<Game.Buildings.Building> m_Buildings`  

```csharp
public Unity.Entities.ComponentLookup<Game.Buildings.Building> m_Buildings;
```

- `public Unity.Entities.ComponentLookup<Game.Buildings.Signature> m_SignatureBuildings`  

```csharp
public Unity.Entities.ComponentLookup<Game.Buildings.Signature> m_SignatureBuildings;
```

- `public Unity.Entities.ComponentLookup<Game.Vehicles.Vehicle> m_Vehicles`  

```csharp
public Unity.Entities.ComponentLookup<Game.Vehicles.Vehicle> m_Vehicles;
```

- `public Unity.Entities.ComponentLookup<Game.Vehicles.Car> m_Cars`  

```csharp
public Unity.Entities.ComponentLookup<Game.Vehicles.Car> m_Cars;
```

- `public Unity.Entities.ComponentLookup<Game.Vehicles.Aircraft> m_Aircraft`  

```csharp
public Unity.Entities.ComponentLookup<Game.Vehicles.Aircraft> m_Aircraft;
```

- `public Unity.Entities.ComponentLookup<Game.Vehicles.Watercraft> m_Watercraft`  

```csharp
public Unity.Entities.ComponentLookup<Game.Vehicles.Watercraft> m_Watercraft;
```

- `public Unity.Entities.ComponentLookup<Game.Vehicles.ParkedCar> m_ParkedCars`  

```csharp
public Unity.Entities.ComponentLookup<Game.Vehicles.ParkedCar> m_ParkedCars;
```

- `public Unity.Entities.ComponentLookup<Game.Vehicles.ParkedTrain> m_ParkedTrains`  

```csharp
public Unity.Entities.ComponentLookup<Game.Vehicles.ParkedTrain> m_ParkedTrains;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_Prefabs`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_Prefabs;
```

- `public Unity.Entities.ComponentLookup<Game.Events.OnFire> m_OnFires`  

```csharp
public Unity.Entities.ComponentLookup<Game.Events.OnFire> m_OnFires;
```

- `public Unity.Entities.ComponentLookup<Game.Vehicles.FireEngine> m_FireEngines`  

```csharp
public Unity.Entities.ComponentLookup<Game.Vehicles.FireEngine> m_FireEngines;
```

- `public Unity.Entities.ComponentLookup<Game.Tools.Temp> m_Temps`  

```csharp
public Unity.Entities.ComponentLookup<Game.Tools.Temp> m_Temps;
```

- `public Unity.Entities.ComponentLookup<Game.Vehicles.PublicTransport> m_PublicTransports`  

```csharp
public Unity.Entities.ComponentLookup<Game.Vehicles.PublicTransport> m_PublicTransports;
```

- `public Unity.Entities.ComponentLookup<Game.Vehicles.Taxi> m_Taxis`  

```csharp
public Unity.Entities.ComponentLookup<Game.Vehicles.Taxi> m_Taxis;
```

- `public Unity.Entities.ComponentLookup<Game.Vehicles.CargoTransport> m_CargoTransports`  

```csharp
public Unity.Entities.ComponentLookup<Game.Vehicles.CargoTransport> m_CargoTransports;
```

- `public Unity.Entities.ComponentLookup<Game.Vehicles.PersonalCar> m_PersonalCars`  

```csharp
public Unity.Entities.ComponentLookup<Game.Vehicles.PersonalCar> m_PersonalCars;
```

- `public Unity.Entities.ComponentLookup<Game.Buildings.ServiceUpgrade> m_ServiceUpgrades`  

```csharp
public Unity.Entities.ComponentLookup<Game.Buildings.ServiceUpgrade> m_ServiceUpgrades;
```

- `public Unity.Entities.ComponentLookup<Game.Buildings.Extension> m_Extensions`  

```csharp
public Unity.Entities.ComponentLookup<Game.Buildings.Extension> m_Extensions;
```

- `public Unity.Entities.ComponentLookup<Game.Events.WeatherPhenomenon> m_WeatherPhenomenonData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Events.WeatherPhenomenon> m_WeatherPhenomenonData;
```

- `public Unity.Entities.ComponentLookup<Game.Common.PseudoRandomSeed> m_PseudoRandomSeeds`  

```csharp
public Unity.Entities.ComponentLookup<Game.Common.PseudoRandomSeed> m_PseudoRandomSeeds;
```

- `public Unity.Entities.ComponentLookup<Game.Common.Destroyed> m_Destroyeds`  

```csharp
public Unity.Entities.ComponentLookup<Game.Common.Destroyed> m_Destroyeds;
```

- `public Unity.Entities.ComponentLookup<Game.Buildings.EarlyDisasterWarningDuration> m_EarlyDisasterWarningDurations`  

```csharp
public Unity.Entities.ComponentLookup<Game.Buildings.EarlyDisasterWarningDuration> m_EarlyDisasterWarningDurations;
```

- `public Unity.Entities.ComponentLookup<Game.Buildings.WaterPumpingStation> m_WaterPumpingStations`  

```csharp
public Unity.Entities.ComponentLookup<Game.Buildings.WaterPumpingStation> m_WaterPumpingStations;
```

- `public Unity.Entities.ComponentLookup<Game.Buildings.SewageOutlet> m_SewageOutlets`  

```csharp
public Unity.Entities.ComponentLookup<Game.Buildings.SewageOutlet> m_SewageOutlets;
```

- `public Unity.Entities.ComponentLookup<Game.Buildings.WaterTower> m_WaterTowers`  

```csharp
public Unity.Entities.ComponentLookup<Game.Buildings.WaterTower> m_WaterTowers;
```

- `public Unity.Entities.ComponentLookup<Game.Objects.StreetLight> m_StreetLights`  

```csharp
public Unity.Entities.ComponentLookup<Game.Objects.StreetLight> m_StreetLights;
```

- `public Unity.Entities.ComponentLookup<Game.Objects.Stopped> m_Stoppeds`  

```csharp
public Unity.Entities.ComponentLookup<Game.Objects.Stopped> m_Stoppeds;
```

- `public Unity.Entities.ComponentLookup<Game.Net.Composition> m_Composition`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.Composition> m_Composition;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.NetCompositionData> m_NetCompositionData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.NetCompositionData> m_NetCompositionData;
```

- `public Unity.Entities.ComponentLookup<Game.Buildings.ExtractorFacility> m_ExtractorData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Buildings.ExtractorFacility> m_ExtractorData;
```

- `public Unity.Entities.ComponentLookup<Game.Objects.Attachment> m_AttachmentData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Objects.Attachment> m_AttachmentData;
```

- `public Unity.Entities.BufferLookup<Game.Objects.TransformFrame> m_TransformFrames`  

```csharp
public Unity.Entities.BufferLookup<Game.Objects.TransformFrame> m_TransformFrames;
```

- `public Unity.Entities.BufferLookup<Game.Buildings.Renter> m_Renter`  

```csharp
public Unity.Entities.BufferLookup<Game.Buildings.Renter> m_Renter;
```

- `public Unity.Entities.ComponentLookup<Game.Net.TrafficLights> m_TrafficLights`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.TrafficLights> m_TrafficLights;
```

- `public Game.Effects.EffectFlagSystem+EffectFlagData m_EffectFlagData`  

```csharp
public Game.Effects.EffectFlagSystem+EffectFlagData m_EffectFlagData;
```

- `public System.UInt32 m_SimulationFrame`  

```csharp
public System.UInt32 m_SimulationFrame;
```

- `public Unity.Entities.Entity m_Selected`  

```csharp
public Unity.Entities.Entity m_Selected;
```


## Constructors

- `public EffectControlData(Unity.Entities.SystemBase system)`  

```csharp
public EffectControlData(SystemBase system)
	{
		m_Owners = system.GetComponentLookup<Owner>(isReadOnly: true);
		m_Temps = system.GetComponentLookup<Temp>(isReadOnly: true);
		m_Buildings = system.GetComponentLookup<Building>(isReadOnly: true);
		m_EffectDatas = system.GetComponentLookup<EffectData>(isReadOnly: true);
		m_LightEffectDatas = system.GetComponentLookup<LightEffectData>(isReadOnly: true);
		m_Hidden = system.GetComponentLookup<Hidden>(isReadOnly: true);
		m_ParkedCars = system.GetComponentLookup<ParkedCar>(isReadOnly: true);
		m_ParkedTrains = system.GetComponentLookup<ParkedTrain>(isReadOnly: true);
		m_Transforms = system.GetComponentLookup<Transform>(isReadOnly: true);
		m_Vehicles = system.GetComponentLookup<Vehicle>(isReadOnly: true);
		m_Cars = system.GetComponentLookup<Car>(isReadOnly: true);
		m_Aircraft = system.GetComponentLookup<Aircraft>(isReadOnly: true);
		m_Watercraft = system.GetComponentLookup<Watercraft>(isReadOnly: true);
		m_Prefabs = system.GetComponentLookup<PrefabRef>(isReadOnly: true);
		m_OnFires = system.GetComponentLookup<OnFire>(isReadOnly: true);
		m_FireEngines = system.GetComponentLookup<Game.Vehicles.FireEngine>(isReadOnly: true);
		m_PublicTransports = system.GetComponentLookup<Game.Vehicles.PublicTransport>(isReadOnly: true);
		m_ServiceUpgrades = system.GetComponentLookup<Game.Buildings.ServiceUpgrade>(isReadOnly: true);
		m_Extensions = system.GetComponentLookup<Extension>(isReadOnly: true);
		m_WeatherPhenomenonData = system.GetComponentLookup<Game.Events.WeatherPhenomenon>(isReadOnly: true);
		m_PseudoRandomSeeds = system.GetComponentLookup<PseudoRandomSeed>(isReadOnly: true);
		m_Destroyeds = system.GetComponentLookup<Destroyed>(isReadOnly: true);
		m_CargoTransports = system.GetComponentLookup<Game.Vehicles.CargoTransport>(isReadOnly: true);
		m_PersonalCars = system.GetComponentLookup<Game.Vehicles.PersonalCar>(isReadOnly: true);
		m_Taxis = system.GetComponentLookup<Game.Vehicles.Taxi>(isReadOnly: true);
		m_EarlyDisasterWarningDurations = system.GetComponentLookup<EarlyDisasterWarningDuration>(isReadOnly: true);
		m_WaterPumpingStations = system.GetComponentLookup<Game.Buildings.WaterPumpingStation>(isReadOnly: true);
		m_SewageOutlets = system.GetComponentLookup<Game.Buildings.SewageOutlet>(isReadOnly: true);
		m_WaterTowers = system.GetComponentLookup<Game.Buildings.WaterTower>(isReadOnly: true);
		m_StreetLights = system.GetComponentLookup<StreetLight>(isReadOnly: true);
		m_Stoppeds = system.GetComponentLookup<Stopped>(isReadOnly: true);
		m_Composition = system.GetComponentLookup<Composition>(isReadOnly: true);
		m_NetCompositionData = system.GetComponentLookup<NetCompositionData>(isReadOnly: true);
		m_TransformFrames = system.GetBufferLookup<TransformFrame>(isReadOnly: true);
		m_Renter = system.GetBufferLookup<Renter>(isReadOnly: true);
		m_SignatureBuildings = system.GetComponentLookup<Signature>(isReadOnly: true);
		m_ExtractorData = system.GetComponentLookup<Game.Buildings.ExtractorFacility>(isReadOnly: true);
		m_AttachmentData = system.GetComponentLookup<Attachment>(isReadOnly: true);
		m_TrafficLights = system.GetComponentLookup<TrafficLights>(isReadOnly: true);
		m_EffectFlagData = default(EffectFlagSystem.EffectFlagData);
		m_SimulationFrame = 0u;
		m_Selected = default(Entity);
	}
```


## Methods

- `private CheckConditions(Unity.Entities.Entity owner, Unity.Entities.Entity buildingOwner, Unity.Entities.Entity topOwner, Unity.Entities.Entity effect) : System.Boolean`  

```csharp
private bool CheckConditions(Entity owner, Entity buildingOwner, Entity topOwner, Entity effect)
	{
		if (m_EffectDatas.TryGetComponent(effect, out var componentData))
		{
			return !CheckTriggers(owner, buildingOwner, topOwner, componentData.m_Flags);
		}
		return true;
	}
```

- `private CheckTrigger(Unity.Entities.Entity owner, Unity.Entities.Entity buildingOwner, Unity.Entities.Entity topOwner, Game.Prefabs.EffectConditionFlags flag, System.Boolean forbidden) : System.Boolean`  

```csharp
private bool CheckTrigger(Entity owner, Entity buildingOwner, Entity topOwner, EffectConditionFlags flag, bool forbidden)
	{
		switch (flag)
		{
		case EffectConditionFlags.Operational:
		{
			if (m_Buildings.TryGetComponent(buildingOwner, out var componentData11))
			{
				if (BuildingUtils.CheckOption(componentData11, BuildingOption.Inactive))
				{
					return false;
				}
				if (m_OnFires.HasComponent(buildingOwner))
				{
					return false;
				}
			}
			if (m_Extensions.TryGetComponent(owner, out var componentData12) && (componentData12.m_Flags & ExtensionFlags.Disabled) != ExtensionFlags.None)
			{
				return false;
			}
			if (m_Destroyeds.HasComponent(owner))
			{
				return false;
			}
			if (m_SignatureBuildings.HasComponent(buildingOwner))
			{
				if (m_Renter.TryGetBuffer(buildingOwner, out var bufferData8) && bufferData8.Length > 0)
				{
					return true;
				}
				return false;
			}
			if (m_Buildings.TryGetComponent(topOwner, out var componentData13))
			{
				return (componentData13.m_Flags & Game.Buildings.BuildingFlags.LowEfficiency) == 0;
			}
			return true;
		}
		case EffectConditionFlags.Parked:
			if (m_Vehicles.HasComponent(topOwner))
			{
				if (!m_ParkedCars.HasComponent(topOwner))
				{
					return m_ParkedTrains.HasComponent(topOwner);
				}
				return true;
			}
			return true;
		case EffectConditionFlags.OnFire:
			return m_OnFires.HasComponent(buildingOwner);
		case EffectConditionFlags.Emergency:
		{
			if (m_Cars.TryGetComponent(topOwner, out var componentData9))
			{
				return (componentData9.m_Flags & CarFlags.Emergency) != 0;
			}
			if (m_Aircraft.TryGetComponent(topOwner, out var componentData10))
			{
				return (componentData10.m_Flags & AircraftFlags.Emergency) != 0;
			}
			return false;
		}
		case EffectConditionFlags.Extinguishing:
			if (m_FireEngines.HasComponent(topOwner))
			{
				return (m_FireEngines[topOwner].m_State & FireEngineFlags.Extinguishing) != 0;
			}
			return false;
		case EffectConditionFlags.TakingOff:
		{
			if (m_TransformFrames.TryGetBuffer(topOwner, out var bufferData3))
			{
				if (forbidden)
				{
					for (int m = 0; m < bufferData3.Length; m++)
					{
						if ((bufferData3[m].m_Flags & TransformFlags.TakingOff) == 0)
						{
							return false;
						}
					}
					return true;
				}
				for (int n = 0; n < bufferData3.Length; n++)
				{
					if ((bufferData3[n].m_Flags & TransformFlags.TakingOff) != 0)
					{
						return true;
					}
				}
				return false;
			}
			return false;
		}
		case EffectConditionFlags.Landing:
		{
			if (m_TransformFrames.TryGetBuffer(topOwner, out var bufferData5))
			{
				if (forbidden)
				{
					for (int num3 = 0; num3 < bufferData5.Length; num3++)
					{
						if ((bufferData5[num3].m_Flags & TransformFlags.Landing) == 0)
						{
							return false;
						}
					}
					return true;
				}
				for (int num4 = 0; num4 < bufferData5.Length; num4++)
				{
					if ((bufferData5[num4].m_Flags & TransformFlags.Landing) != 0)
					{
						return true;
					}
				}
				return false;
			}
			return false;
		}
		case EffectConditionFlags.Flying:
		{
			if (m_TransformFrames.TryGetBuffer(topOwner, out var bufferData7))
			{
				if (forbidden)
				{
					for (int num7 = 0; num7 < bufferData7.Length; num7++)
					{
						if ((bufferData7[num7].m_Flags & TransformFlags.Flying) == 0)
						{
							return false;
						}
					}
					return true;
				}
				for (int num8 = 0; num8 < bufferData7.Length; num8++)
				{
					if ((bufferData7[num8].m_Flags & TransformFlags.Flying) != 0)
					{
						return true;
					}
				}
				return false;
			}
			return false;
		}
		case EffectConditionFlags.Stopped:
			return m_Stoppeds.HasComponent(topOwner);
		case EffectConditionFlags.Processing:
		{
			bool flag2 = false;
			if (m_WaterPumpingStations.HasComponent(topOwner))
			{
				flag2 = m_WaterPumpingStations[topOwner].m_LastProduction != 0;
			}
			if (m_SewageOutlets.HasComponent(topOwner))
			{
				flag2 = flag2 || m_SewageOutlets[topOwner].m_LastProcessed != 0;
			}
			if (m_WaterTowers.HasComponent(topOwner))
			{
				flag2 = flag2 || m_WaterTowers[topOwner].m_LastStoredWater != m_WaterTowers[topOwner].m_StoredWater;
			}
			return flag2;
		}
		case EffectConditionFlags.Boarding:
			if (m_PublicTransports.HasComponent(topOwner))
			{
				return (m_PublicTransports[topOwner].m_State & PublicTransportFlags.Boarding) != 0;
			}
			if (m_Taxis.HasComponent(topOwner))
			{
				return (m_Taxis[topOwner].m_State & TaxiFlags.Boarding) != 0;
			}
			if (m_CargoTransports.HasComponent(topOwner))
			{
				return (m_CargoTransports[topOwner].m_State & CargoTransportFlags.Boarding) != 0;
			}
			if (m_PersonalCars.HasComponent(topOwner))
			{
				return (m_PersonalCars[topOwner].m_State & PersonalCarFlags.Boarding) != 0;
			}
			return false;
		case EffectConditionFlags.Disaster:
			if (m_EarlyDisasterWarningDurations.HasComponent(topOwner))
			{
				return m_SimulationFrame < m_EarlyDisasterWarningDurations[topOwner].m_EndFrame;
			}
			return false;
		case EffectConditionFlags.Occurring:
			if (m_WeatherPhenomenonData.HasComponent(topOwner))
			{
				return m_WeatherPhenomenonData[topOwner].m_Intensity != 0f;
			}
			return false;
		case EffectConditionFlags.Night:
		case EffectConditionFlags.Cold:
		{
			Random random = GetRandom(topOwner);
			return EffectFlagSystem.IsEnabled(flag, random, m_EffectFlagData, m_SimulationFrame);
		}
		case EffectConditionFlags.LightsOff:
		{
			if (m_StreetLights.TryGetComponent(topOwner, out var componentData7))
			{
				return (componentData7.m_State & StreetLightState.TurnedOff) != 0;
			}
			if (m_Watercraft.TryGetComponent(topOwner, out var componentData8))
			{
				return (componentData8.m_Flags & WatercraftFlags.LightsOff) != 0;
			}
			return false;
		}
		case EffectConditionFlags.MainLights:
		{
			if (m_TransformFrames.TryGetBuffer(topOwner, out var bufferData))
			{
				if (forbidden)
				{
					for (int i = 0; i < bufferData.Length; i++)
					{
						if ((bufferData[i].m_Flags & TransformFlags.MainLights) == 0)
						{
							return false;
						}
					}
					return true;
				}
				for (int j = 0; j < bufferData.Length; j++)
				{
					if ((bufferData[j].m_Flags & TransformFlags.MainLights) != 0)
					{
						return true;
					}
				}
				return false;
			}
			return false;
		}
		case EffectConditionFlags.ExtraLights:
		{
			if (m_TransformFrames.TryGetBuffer(topOwner, out var bufferData6))
			{
				if (forbidden)
				{
					for (int num5 = 0; num5 < bufferData6.Length; num5++)
					{
						if ((bufferData6[num5].m_Flags & TransformFlags.ExtraLights) == 0)
						{
							return false;
						}
					}
					return true;
				}
				for (int num6 = 0; num6 < bufferData6.Length; num6++)
				{
					if ((bufferData6[num6].m_Flags & TransformFlags.ExtraLights) != 0)
					{
						return true;
					}
				}
				return false;
			}
			return false;
		}
		case EffectConditionFlags.WarningLights:
		{
			if (m_TransformFrames.TryGetBuffer(topOwner, out var bufferData2))
			{
				if (forbidden)
				{
					for (int k = 0; k < bufferData2.Length; k++)
					{
						if ((bufferData2[k].m_Flags & TransformFlags.WarningLights) == 0)
						{
							return false;
						}
					}
					return true;
				}
				for (int l = 0; l < bufferData2.Length; l++)
				{
					if ((bufferData2[l].m_Flags & TransformFlags.WarningLights) != 0)
					{
						return true;
					}
				}
				return false;
			}
			if (m_Cars.TryGetComponent(topOwner, out var componentData2))
			{
				return (componentData2.m_Flags & (CarFlags.Emergency | CarFlags.Warning)) != 0;
			}
			return false;
		}
		case EffectConditionFlags.WorkLights:
		{
			if (m_TransformFrames.TryGetBuffer(topOwner, out var bufferData4))
			{
				if (forbidden)
				{
					for (int num = 0; num < bufferData4.Length; num++)
					{
						if ((bufferData4[num].m_Flags & TransformFlags.WorkLights) == 0)
						{
							return false;
						}
					}
					return true;
				}
				for (int num2 = 0; num2 < bufferData4.Length; num2++)
				{
					if ((bufferData4[num2].m_Flags & TransformFlags.WorkLights) != 0)
					{
						return true;
					}
				}
				return false;
			}
			if (m_Cars.TryGetComponent(topOwner, out var componentData6))
			{
				return (componentData6.m_Flags & (CarFlags.Sign | CarFlags.Working)) != 0;
			}
			return false;
		}
		case EffectConditionFlags.Spillway:
		{
			if (m_Composition.TryGetComponent(topOwner, out var componentData4) && m_NetCompositionData.TryGetComponent(componentData4.m_Edge, out var componentData5))
			{
				return (componentData5.m_Flags.m_General & CompositionFlags.General.Spillway) != 0;
			}
			return false;
		}
		case EffectConditionFlags.Collapsing:
		{
			if (m_Destroyeds.TryGetComponent(owner, out var componentData3))
			{
				return componentData3.m_Cleared < 0f;
			}
			return false;
		}
		case EffectConditionFlags.MoveableBridgeWorking:
		{
			if (m_TrafficLights.TryGetComponent(owner, out var componentData) && (componentData.m_Flags & TrafficLightFlags.MoveableBridge) != 0)
			{
				return componentData.m_State != Game.Net.TrafficLightState.Ongoing;
			}
			return false;
		}
		default:
			return false;
		}
	}
```

- `private CheckTriggers(Unity.Entities.Entity owner, Unity.Entities.Entity buildingOwner, Unity.Entities.Entity topOwner, Game.Prefabs.EffectCondition condition) : System.Boolean`  

```csharp
private bool CheckTriggers(Entity owner, Entity buildingOwner, Entity topOwner, EffectCondition condition)
	{
		EffectConditionFlags effectConditionFlags = EffectConditionFlags.Emergency;
		while (true)
		{
			bool flag = (condition.m_RequiredFlags & effectConditionFlags) != 0;
			bool flag2 = (condition.m_ForbiddenFlags & effectConditionFlags) != 0;
			if (flag || flag2)
			{
				bool flag3 = CheckTrigger(owner, buildingOwner, topOwner, effectConditionFlags, flag2);
				if ((flag && !flag3) || (flag2 && flag3))
				{
					return true;
				}
			}
			if (effectConditionFlags == EffectConditionFlags.MoveableBridgeWorking)
			{
				break;
			}
			effectConditionFlags = (EffectConditionFlags)((int)effectConditionFlags << 1);
		}
		return false;
	}
```

- `private GetRandom(Unity.Entities.Entity owner) : Unity.Mathematics.Random`  

```csharp
private Random GetRandom(Entity owner)
	{
		if (m_PseudoRandomSeeds.TryGetComponent(owner, out var componentData))
		{
			return componentData.GetRandom(PseudoRandomSeed.kEffectCondition);
		}
		if (m_Transforms.TryGetComponent(owner, out var componentData2))
		{
			return Random.CreateFromIndex((uint)math.dot(new float3(67f, 83f, 97f), componentData2.m_Position));
		}
		return Random.CreateFromIndex((uint)owner.Index);
	}
```

- `private GetRealOwner(Unity.Entities.Entity owner, Unity.Entities.Entity& buildingOwner) : Unity.Entities.Entity`  

```csharp
private Entity GetRealOwner(Entity owner, out Entity buildingOwner)
	{
		if (m_Temps.TryGetComponent(owner, out var componentData))
		{
			buildingOwner = ((componentData.m_Original != Entity.Null) ? componentData.m_Original : owner);
			return buildingOwner;
		}
		if (m_ServiceUpgrades.HasComponent(owner) && m_Owners.TryGetComponent(owner, out var componentData2))
		{
			buildingOwner = (m_Buildings.HasComponent(owner) ? owner : componentData2.m_Owner);
			return componentData2.m_Owner;
		}
		if (m_ExtractorData.HasComponent(owner) && m_Owners.TryGetComponent(owner, out var componentData3))
		{
			buildingOwner = owner;
			Entity entity = componentData3.m_Owner;
			Owner componentData4;
			while (m_Owners.TryGetComponent(entity, out componentData4))
			{
				entity = componentData4.m_Owner;
			}
			if (m_AttachmentData.TryGetComponent(entity, out var componentData5))
			{
				entity = componentData5.m_Attached;
			}
			return entity;
		}
		buildingOwner = owner;
		return owner;
	}
```

- `public ShouldBeEnabled(Unity.Entities.Entity owner, Unity.Entities.Entity prefab, System.Boolean checkEnabled, System.Boolean isEditorContainer) : System.Boolean`  

```csharp
public bool ShouldBeEnabled(Entity owner, Entity prefab, bool checkEnabled, bool isEditorContainer)
	{
		if (isEditorContainer)
		{
			if (m_Hidden.HasComponent(owner))
			{
				return false;
			}
			if (!m_LightEffectDatas.HasComponent(prefab))
			{
				if (m_Temps.TryGetComponent(owner, out var componentData))
				{
					if (m_Selected == Entity.Null || componentData.m_Original != m_Selected)
					{
						if ((componentData.m_Flags & TempFlags.Essential) == 0)
						{
							return false;
						}
						if (m_Owners.TryGetComponent(owner, out var componentData2) && m_Temps.TryGetComponent(componentData2.m_Owner, out var componentData3) && (componentData3.m_Flags & (TempFlags.Create | TempFlags.Delete | TempFlags.Select | TempFlags.Modify | TempFlags.Duplicate)) != 0)
						{
							return false;
						}
					}
				}
				else if (owner != m_Selected)
				{
					return false;
				}
			}
		}
		else
		{
			if (m_LightEffectDatas.HasComponent(prefab))
			{
				if (m_Hidden.HasComponent(owner))
				{
					return false;
				}
			}
			else if (m_Temps.HasComponent(owner))
			{
				return false;
			}
			if (checkEnabled)
			{
				Entity buildingOwner;
				Entity realOwner = GetRealOwner(owner, out buildingOwner);
				if (!CheckConditions(owner, buildingOwner, realOwner, prefab))
				{
					return false;
				}
			}
		}
		return true;
	}
```

- `public Update(Unity.Entities.SystemBase system, Game.Effects.EffectFlagSystem+EffectFlagData effectFlagData, System.UInt32 simulationFrame, Unity.Entities.Entity selected) : System.Void`  

```csharp
public void Update(SystemBase system, EffectFlagSystem.EffectFlagData effectFlagData, uint simulationFrame, Entity selected)
	{
		m_Owners.Update(system);
		m_Temps.Update(system);
		m_Buildings.Update(system);
		m_EffectDatas.Update(system);
		m_LightEffectDatas.Update(system);
		m_Hidden.Update(system);
		m_ParkedCars.Update(system);
		m_ParkedTrains.Update(system);
		m_Transforms.Update(system);
		m_Vehicles.Update(system);
		m_Cars.Update(system);
		m_Aircraft.Update(system);
		m_Watercraft.Update(system);
		m_Prefabs.Update(system);
		m_OnFires.Update(system);
		m_FireEngines.Update(system);
		m_PublicTransports.Update(system);
		m_ServiceUpgrades.Update(system);
		m_Extensions.Update(system);
		m_WeatherPhenomenonData.Update(system);
		m_PseudoRandomSeeds.Update(system);
		m_Destroyeds.Update(system);
		m_CargoTransports.Update(system);
		m_PersonalCars.Update(system);
		m_Taxis.Update(system);
		m_EarlyDisasterWarningDurations.Update(system);
		m_WaterPumpingStations.Update(system);
		m_SewageOutlets.Update(system);
		m_WaterTowers.Update(system);
		m_StreetLights.Update(system);
		m_Stoppeds.Update(system);
		m_Composition.Update(system);
		m_NetCompositionData.Update(system);
		m_TransformFrames.Update(system);
		m_Renter.Update(system);
		m_SignatureBuildings.Update(system);
		m_ExtractorData.Update(system);
		m_AttachmentData.Update(system);
		m_TrafficLights.Update(system);
		m_EffectFlagData = effectFlagData;
		m_SimulationFrame = simulationFrame;
		m_Selected = selected;
	}
```


