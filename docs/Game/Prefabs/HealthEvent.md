# Game.Prefabs.HealthEvent

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Fields

- `public Game.Prefabs.EventTargetType m_RandomTargetType`  
- `public Game.Prefabs.HealthEventType m_HealthEventType`  
- `public Colossal.Mathematics.Bounds1 m_OccurenceProbability`  
- `public Colossal.Mathematics.Bounds1 m_TransportProbability`  
- `public System.Boolean m_RequireTracking`  

## Constructors

- `public HealthEvent()`  

## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

