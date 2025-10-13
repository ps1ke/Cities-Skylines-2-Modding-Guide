# Game.Prefabs.HospitalData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Game.Prefabs.ICombineData<Game.Prefabs.HospitalData>`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct HospitalData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Game.Prefabs.ICombineData<Game.Prefabs.HospitalData>, Colossal.Serialization.Entities.ISerializable
{
    public System.Int32 m_AmbulanceCapacity;
    public System.Int32 m_MedicalHelicopterCapacity;
    public System.Int32 m_PatientCapacity;
    public System.Int32 m_TreatmentBonus;
    public Unity.Mathematics.int2 m_HealthRange;
    public System.Boolean m_TreatDiseases;
    public System.Boolean m_TreatInjuries;

    public System.Void Combine(Game.Prefabs.HospitalData otherData);
    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Int32 m_AmbulanceCapacity`  

```csharp
public System.Int32 m_AmbulanceCapacity;
```

- `public System.Int32 m_MedicalHelicopterCapacity`  

```csharp
public System.Int32 m_MedicalHelicopterCapacity;
```

- `public System.Int32 m_PatientCapacity`  

```csharp
public System.Int32 m_PatientCapacity;
```

- `public System.Int32 m_TreatmentBonus`  

```csharp
public System.Int32 m_TreatmentBonus;
```

- `public Unity.Mathematics.int2 m_HealthRange`  

```csharp
public Unity.Mathematics.int2 m_HealthRange;
```

- `public System.Boolean m_TreatDiseases`  

```csharp
public System.Boolean m_TreatDiseases;
```

- `public System.Boolean m_TreatInjuries`  

```csharp
public System.Boolean m_TreatInjuries;
```


## Methods

- `public Combine(Game.Prefabs.HospitalData otherData) : System.Void`  

```csharp
public System.Void Combine(Game.Prefabs.HospitalData otherData);
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


