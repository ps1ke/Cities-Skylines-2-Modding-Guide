# Game.Prefabs.CalendarEvent

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Fields

- `public Game.Prefabs.EventTargetType m_RandomTargetType`  
- `public Colossal.Mathematics.Bounds1 m_AffectedProbability`  
- `public Colossal.Mathematics.Bounds1 m_OccurenceProbability`  
- `public Game.Prefabs.CalendarEventMonths m_AllowedMonths`  
- `public Game.Prefabs.CalendarEventTimes m_AllowedTimes`  
- `public System.Int32 m_Duration`  

## Constructors

- `public CalendarEvent()`  

## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

