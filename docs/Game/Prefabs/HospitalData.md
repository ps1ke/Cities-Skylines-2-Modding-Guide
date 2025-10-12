# Game.Prefabs.HospitalData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Game.Prefabs.ICombineData<Game.Prefabs.HospitalData>`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `public System.Int32 m_AmbulanceCapacity`  
- `public System.Int32 m_MedicalHelicopterCapacity`  
- `public System.Int32 m_PatientCapacity`  
- `public System.Int32 m_TreatmentBonus`  
- `public Unity.Mathematics.int2 m_HealthRange`  
- `public System.Boolean m_TreatDiseases`  
- `public System.Boolean m_TreatInjuries`  

## Methods

- `public Combine(Game.Prefabs.HospitalData otherData) : System.Void`  
- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  

