# Game.Prefabs.WeatherPhenomenon

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Fields

- `public System.Single m_OccurrenceProbability`  
- `public Colossal.Mathematics.Bounds1 m_OccurenceTemperature`  
- `public Colossal.Mathematics.Bounds1 m_OccurenceRain`  
- `public Colossal.Mathematics.Bounds1 m_Duration`  
- `public Colossal.Mathematics.Bounds1 m_PhenomenonRadius`  
- `public Colossal.Mathematics.Bounds1 m_HotspotRadius`  
- `public Colossal.Mathematics.Bounds1 m_LightningInterval`  
- `public System.Single m_HotspotInstability`  
- `public System.Single m_DamageSeverity`  
- `public System.Single m_DangerLevel`  
- `public System.Boolean m_Evacuate`  
- `public System.Boolean m_StayIndoors`  

## Constructors

- `public WeatherPhenomenon()`  

## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

