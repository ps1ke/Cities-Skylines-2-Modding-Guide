# Game.Effects.EffectControlData

**Assembly:** `Game`  
**Namespace:** `Game.Effects`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `public Unity.Entities.ComponentLookup<Game.Common.Owner> m_Owners`  
- `public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_Transforms`  
- `public Unity.Entities.ComponentLookup<Game.Tools.Hidden> m_Hidden`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.EffectData> m_EffectDatas`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.LightEffectData> m_LightEffectDatas`  
- `public Unity.Entities.ComponentLookup<Game.Buildings.Building> m_Buildings`  
- `public Unity.Entities.ComponentLookup<Game.Buildings.Signature> m_SignatureBuildings`  
- `public Unity.Entities.ComponentLookup<Game.Vehicles.Vehicle> m_Vehicles`  
- `public Unity.Entities.ComponentLookup<Game.Vehicles.Car> m_Cars`  
- `public Unity.Entities.ComponentLookup<Game.Vehicles.Aircraft> m_Aircraft`  
- `public Unity.Entities.ComponentLookup<Game.Vehicles.Watercraft> m_Watercraft`  
- `public Unity.Entities.ComponentLookup<Game.Vehicles.ParkedCar> m_ParkedCars`  
- `public Unity.Entities.ComponentLookup<Game.Vehicles.ParkedTrain> m_ParkedTrains`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_Prefabs`  
- `public Unity.Entities.ComponentLookup<Game.Events.OnFire> m_OnFires`  
- `public Unity.Entities.ComponentLookup<Game.Vehicles.FireEngine> m_FireEngines`  
- `public Unity.Entities.ComponentLookup<Game.Tools.Temp> m_Temps`  
- `public Unity.Entities.ComponentLookup<Game.Vehicles.PublicTransport> m_PublicTransports`  
- `public Unity.Entities.ComponentLookup<Game.Vehicles.Taxi> m_Taxis`  
- `public Unity.Entities.ComponentLookup<Game.Vehicles.CargoTransport> m_CargoTransports`  
- `public Unity.Entities.ComponentLookup<Game.Vehicles.PersonalCar> m_PersonalCars`  
- `public Unity.Entities.ComponentLookup<Game.Buildings.ServiceUpgrade> m_ServiceUpgrades`  
- `public Unity.Entities.ComponentLookup<Game.Buildings.Extension> m_Extensions`  
- `public Unity.Entities.ComponentLookup<Game.Events.WeatherPhenomenon> m_WeatherPhenomenonData`  
- `public Unity.Entities.ComponentLookup<Game.Common.PseudoRandomSeed> m_PseudoRandomSeeds`  
- `public Unity.Entities.ComponentLookup<Game.Common.Destroyed> m_Destroyeds`  
- `public Unity.Entities.ComponentLookup<Game.Buildings.EarlyDisasterWarningDuration> m_EarlyDisasterWarningDurations`  
- `public Unity.Entities.ComponentLookup<Game.Buildings.WaterPumpingStation> m_WaterPumpingStations`  
- `public Unity.Entities.ComponentLookup<Game.Buildings.SewageOutlet> m_SewageOutlets`  
- `public Unity.Entities.ComponentLookup<Game.Buildings.WaterTower> m_WaterTowers`  
- `public Unity.Entities.ComponentLookup<Game.Objects.StreetLight> m_StreetLights`  
- `public Unity.Entities.ComponentLookup<Game.Objects.Stopped> m_Stoppeds`  
- `public Unity.Entities.ComponentLookup<Game.Net.Composition> m_Composition`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.NetCompositionData> m_NetCompositionData`  
- `public Unity.Entities.ComponentLookup<Game.Buildings.ExtractorFacility> m_ExtractorData`  
- `public Unity.Entities.ComponentLookup<Game.Objects.Attachment> m_AttachmentData`  
- `public Unity.Entities.BufferLookup<Game.Objects.TransformFrame> m_TransformFrames`  
- `public Unity.Entities.BufferLookup<Game.Buildings.Renter> m_Renter`  
- `public Unity.Entities.ComponentLookup<Game.Net.TrafficLights> m_TrafficLights`  
- `public Game.Effects.EffectFlagSystem+EffectFlagData m_EffectFlagData`  
- `public System.UInt32 m_SimulationFrame`  
- `public Unity.Entities.Entity m_Selected`  

## Constructors

- `public EffectControlData(Unity.Entities.SystemBase system)`  

## Methods

- `private CheckConditions(Unity.Entities.Entity owner, Unity.Entities.Entity buildingOwner, Unity.Entities.Entity topOwner, Unity.Entities.Entity effect) : System.Boolean`  
- `private CheckTrigger(Unity.Entities.Entity owner, Unity.Entities.Entity buildingOwner, Unity.Entities.Entity topOwner, Game.Prefabs.EffectConditionFlags flag, System.Boolean forbidden) : System.Boolean`  
- `private CheckTriggers(Unity.Entities.Entity owner, Unity.Entities.Entity buildingOwner, Unity.Entities.Entity topOwner, Game.Prefabs.EffectCondition condition) : System.Boolean`  
- `private GetRandom(Unity.Entities.Entity owner) : Unity.Mathematics.Random`  
- `private GetRealOwner(Unity.Entities.Entity owner, Unity.Entities.Entity& buildingOwner) : Unity.Entities.Entity`  
- `public ShouldBeEnabled(Unity.Entities.Entity owner, Unity.Entities.Entity prefab, System.Boolean checkEnabled, System.Boolean isEditorContainer) : System.Boolean`  
- `public Update(Unity.Entities.SystemBase system, Game.Effects.EffectFlagSystem+EffectFlagData effectFlagData, System.UInt32 simulationFrame, Unity.Entities.Entity selected) : System.Void`  

