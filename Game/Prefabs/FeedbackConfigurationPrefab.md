# Game.Prefabs.FeedbackConfigurationPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class FeedbackConfigurationPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.NotificationIconPrefab m_HappyFaceNotification;
    public Game.Prefabs.NotificationIconPrefab m_SadFaceNotification;
    public System.Single m_GarbageProducerGarbageFactor;
    public System.Single m_GarbageVehicleFactor;
    public System.Single m_HospitalAmbulanceFactor;
    public System.Single m_HospitalHelicopterFactor;
    public System.Single m_HospitalCapacityFactor;
    public System.Single m_DeathcareHearseFactor;
    public System.Single m_DeathcareCapacityFactor;
    public System.Single m_DeathcareProcessingFactor;
    public System.Single m_ElectricityConsumptionFactor;
    public System.Single m_ElectricityProductionFactor;
    public System.Single m_TransformerRadius;
    public System.Single m_WaterConsumptionFactor;
    public System.Single m_WaterCapacityFactor;
    public System.Single m_WaterConsumerSewageFactor;
    public System.Single m_SewageCapacityFactor;
    public System.Single m_TransportVehicleCapacityFactor;
    public System.Single m_TransportDispatchCenterFactor;
    public System.Single m_TransportStationRange;
    public System.Single m_TransportStopRange;
    public System.Single m_MailProducerMailFactor;
    public System.Single m_PostFacilityVanFactor;
    public System.Single m_PostFacilityTruckFactor;
    public System.Single m_PostFacilityCapacityFactor;
    public System.Single m_PostFacilityProcessingFactor;
    public System.Single m_TelecomCapacityFactor;
    public System.Single m_ElementarySchoolCapacityFactor;
    public System.Single m_HighSchoolCapacityFactor;
    public System.Single m_CollegeCapacityFactor;
    public System.Single m_UniversityCapacityFactor;
    public System.Single m_ParkingFacilityRange;
    public System.Single m_MaintenanceVehicleFactor;
    public System.Single m_FireStationEngineFactor;
    public System.Single m_FireStationHelicopterFactor;
    public System.Single m_CrimeProducerCrimeFactor;
    public System.Single m_PoliceStationCarFactor;
    public System.Single m_PoliceStationHelicopterFactor;
    public System.Single m_PoliceStationCapacityFactor;
    public System.Single m_PrisonVehicleFactor;
    public System.Single m_PrisonCapacityFactor;
    public System.Single m_GroundPollutionFactor;
    public System.Single m_AirPollutionFactor;
    public System.Single m_NoisePollutionFactor;
    public System.Single m_GroundPollutionRadius;
    public System.Single m_AirPollutionRadius;
    public System.Single m_NoisePollutionRadius;
    public System.Single m_AttractivenessFactor;
    public System.Single[] m_LocalModifierFactors;
    public System.Single[] m_CityModifierFactors;

    public FeedbackConfigurationPrefab();

    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.NotificationIconPrefab m_HappyFaceNotification`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_HappyFaceNotification;
```

- `public Game.Prefabs.NotificationIconPrefab m_SadFaceNotification`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_SadFaceNotification;
```

- `public System.Single m_GarbageProducerGarbageFactor`  

```csharp
public System.Single m_GarbageProducerGarbageFactor;
```

- `public System.Single m_GarbageVehicleFactor`  

```csharp
public System.Single m_GarbageVehicleFactor;
```

- `public System.Single m_HospitalAmbulanceFactor`  

```csharp
public System.Single m_HospitalAmbulanceFactor;
```

- `public System.Single m_HospitalHelicopterFactor`  

```csharp
public System.Single m_HospitalHelicopterFactor;
```

- `public System.Single m_HospitalCapacityFactor`  

```csharp
public System.Single m_HospitalCapacityFactor;
```

- `public System.Single m_DeathcareHearseFactor`  

```csharp
public System.Single m_DeathcareHearseFactor;
```

- `public System.Single m_DeathcareCapacityFactor`  

```csharp
public System.Single m_DeathcareCapacityFactor;
```

- `public System.Single m_DeathcareProcessingFactor`  

```csharp
public System.Single m_DeathcareProcessingFactor;
```

- `public System.Single m_ElectricityConsumptionFactor`  

```csharp
public System.Single m_ElectricityConsumptionFactor;
```

- `public System.Single m_ElectricityProductionFactor`  

```csharp
public System.Single m_ElectricityProductionFactor;
```

- `public System.Single m_TransformerRadius`  

```csharp
public System.Single m_TransformerRadius;
```

- `public System.Single m_WaterConsumptionFactor`  

```csharp
public System.Single m_WaterConsumptionFactor;
```

- `public System.Single m_WaterCapacityFactor`  

```csharp
public System.Single m_WaterCapacityFactor;
```

- `public System.Single m_WaterConsumerSewageFactor`  

```csharp
public System.Single m_WaterConsumerSewageFactor;
```

- `public System.Single m_SewageCapacityFactor`  

```csharp
public System.Single m_SewageCapacityFactor;
```

- `public System.Single m_TransportVehicleCapacityFactor`  

```csharp
public System.Single m_TransportVehicleCapacityFactor;
```

- `public System.Single m_TransportDispatchCenterFactor`  

```csharp
public System.Single m_TransportDispatchCenterFactor;
```

- `public System.Single m_TransportStationRange`  

```csharp
public System.Single m_TransportStationRange;
```

- `public System.Single m_TransportStopRange`  

```csharp
public System.Single m_TransportStopRange;
```

- `public System.Single m_MailProducerMailFactor`  

```csharp
public System.Single m_MailProducerMailFactor;
```

- `public System.Single m_PostFacilityVanFactor`  

```csharp
public System.Single m_PostFacilityVanFactor;
```

- `public System.Single m_PostFacilityTruckFactor`  

```csharp
public System.Single m_PostFacilityTruckFactor;
```

- `public System.Single m_PostFacilityCapacityFactor`  

```csharp
public System.Single m_PostFacilityCapacityFactor;
```

- `public System.Single m_PostFacilityProcessingFactor`  

```csharp
public System.Single m_PostFacilityProcessingFactor;
```

- `public System.Single m_TelecomCapacityFactor`  

```csharp
public System.Single m_TelecomCapacityFactor;
```

- `public System.Single m_ElementarySchoolCapacityFactor`  

```csharp
public System.Single m_ElementarySchoolCapacityFactor;
```

- `public System.Single m_HighSchoolCapacityFactor`  

```csharp
public System.Single m_HighSchoolCapacityFactor;
```

- `public System.Single m_CollegeCapacityFactor`  

```csharp
public System.Single m_CollegeCapacityFactor;
```

- `public System.Single m_UniversityCapacityFactor`  

```csharp
public System.Single m_UniversityCapacityFactor;
```

- `public System.Single m_ParkingFacilityRange`  

```csharp
public System.Single m_ParkingFacilityRange;
```

- `public System.Single m_MaintenanceVehicleFactor`  

```csharp
public System.Single m_MaintenanceVehicleFactor;
```

- `public System.Single m_FireStationEngineFactor`  

```csharp
public System.Single m_FireStationEngineFactor;
```

- `public System.Single m_FireStationHelicopterFactor`  

```csharp
public System.Single m_FireStationHelicopterFactor;
```

- `public System.Single m_CrimeProducerCrimeFactor`  

```csharp
public System.Single m_CrimeProducerCrimeFactor;
```

- `public System.Single m_PoliceStationCarFactor`  

```csharp
public System.Single m_PoliceStationCarFactor;
```

- `public System.Single m_PoliceStationHelicopterFactor`  

```csharp
public System.Single m_PoliceStationHelicopterFactor;
```

- `public System.Single m_PoliceStationCapacityFactor`  

```csharp
public System.Single m_PoliceStationCapacityFactor;
```

- `public System.Single m_PrisonVehicleFactor`  

```csharp
public System.Single m_PrisonVehicleFactor;
```

- `public System.Single m_PrisonCapacityFactor`  

```csharp
public System.Single m_PrisonCapacityFactor;
```

- `public System.Single m_GroundPollutionFactor`  

```csharp
public System.Single m_GroundPollutionFactor;
```

- `public System.Single m_AirPollutionFactor`  

```csharp
public System.Single m_AirPollutionFactor;
```

- `public System.Single m_NoisePollutionFactor`  

```csharp
public System.Single m_NoisePollutionFactor;
```

- `public System.Single m_GroundPollutionRadius`  

```csharp
public System.Single m_GroundPollutionRadius;
```

- `public System.Single m_AirPollutionRadius`  

```csharp
public System.Single m_AirPollutionRadius;
```

- `public System.Single m_NoisePollutionRadius`  

```csharp
public System.Single m_NoisePollutionRadius;
```

- `public System.Single m_AttractivenessFactor`  

```csharp
public System.Single m_AttractivenessFactor;
```

- `public System.Single[] m_LocalModifierFactors`  

```csharp
public System.Single[] m_LocalModifierFactors;
```

- `public System.Single[] m_CityModifierFactors`  

```csharp
public System.Single[] m_CityModifierFactors;
```


## Constructors

- `public FeedbackConfigurationPrefab()`  

```csharp
public FeedbackConfigurationPrefab();
```


## Methods

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


