# Game.Prefabs.Hospital

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `Game.Prefabs.IServiceUpgrade`  

**Attributes:** `ComponentMenu`  

## Fields

- `public System.Int32 m_AmbulanceCapacity`  
- `public System.Int32 m_MedicalHelicopterCapacity`  
- `public System.Int32 m_PatientCapacity`  
- `public System.Int32 m_TreatmentBonus`  
- `public Unity.Mathematics.int2 m_HealthRange`  
- `public System.Boolean m_TreatDiseases`  
- `public System.Boolean m_TreatInjuries`  

## Constructors

- `public Hospital()`  

## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public GetUpgradeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

