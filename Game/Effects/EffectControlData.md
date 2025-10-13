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
public EffectControlData(Unity.Entities.SystemBase system);
```


## Methods

- `private CheckConditions(Unity.Entities.Entity owner, Unity.Entities.Entity buildingOwner, Unity.Entities.Entity topOwner, Unity.Entities.Entity effect) : System.Boolean`  

```csharp
private System.Boolean CheckConditions(Unity.Entities.Entity owner, Unity.Entities.Entity buildingOwner, Unity.Entities.Entity topOwner, Unity.Entities.Entity effect);
```

- `private CheckTrigger(Unity.Entities.Entity owner, Unity.Entities.Entity buildingOwner, Unity.Entities.Entity topOwner, Game.Prefabs.EffectConditionFlags flag, System.Boolean forbidden) : System.Boolean`  

```csharp
private System.Boolean CheckTrigger(Unity.Entities.Entity owner, Unity.Entities.Entity buildingOwner, Unity.Entities.Entity topOwner, Game.Prefabs.EffectConditionFlags flag, System.Boolean forbidden);
```

- `private CheckTriggers(Unity.Entities.Entity owner, Unity.Entities.Entity buildingOwner, Unity.Entities.Entity topOwner, Game.Prefabs.EffectCondition condition) : System.Boolean`  

```csharp
private System.Boolean CheckTriggers(Unity.Entities.Entity owner, Unity.Entities.Entity buildingOwner, Unity.Entities.Entity topOwner, Game.Prefabs.EffectCondition condition);
```

- `private GetRandom(Unity.Entities.Entity owner) : Unity.Mathematics.Random`  

```csharp
private Unity.Mathematics.Random GetRandom(Unity.Entities.Entity owner);
```

- `private GetRealOwner(Unity.Entities.Entity owner, Unity.Entities.Entity& buildingOwner) : Unity.Entities.Entity`  

```csharp
private Unity.Entities.Entity GetRealOwner(Unity.Entities.Entity owner, Unity.Entities.Entity& buildingOwner);
```

- `public ShouldBeEnabled(Unity.Entities.Entity owner, Unity.Entities.Entity prefab, System.Boolean checkEnabled, System.Boolean isEditorContainer) : System.Boolean`  

```csharp
public System.Boolean ShouldBeEnabled(Unity.Entities.Entity owner, Unity.Entities.Entity prefab, System.Boolean checkEnabled, System.Boolean isEditorContainer);
```

- `public Update(Unity.Entities.SystemBase system, Game.Effects.EffectFlagSystem+EffectFlagData effectFlagData, System.UInt32 simulationFrame, Unity.Entities.Entity selected) : System.Void`  

```csharp
public System.Void Update(Unity.Entities.SystemBase system, Game.Effects.EffectFlagSystem+EffectFlagData effectFlagData, System.UInt32 simulationFrame, Unity.Entities.Entity selected);
```


