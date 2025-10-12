# Game.Prefabs.Crime

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Fields

- `public Game.Prefabs.EventTargetType m_RandomTargetType`  
- `public Game.Prefabs.CrimeType m_CrimeType`  
- `public Colossal.Mathematics.Bounds1 m_OccurenceProbability`  
- `public Colossal.Mathematics.Bounds1 m_RecurrenceProbability`  
- `public Colossal.Mathematics.Bounds1 m_AlarmDelay`  
- `public Colossal.Mathematics.Bounds1 m_CrimeDuration`  
- `public Colossal.Mathematics.Bounds1 m_CrimeIncomeAbsolute`  
- `public Colossal.Mathematics.Bounds1 m_CrimeIncomeRelative`  
- `public Colossal.Mathematics.Bounds1 m_JailTimeRange`  
- `public Colossal.Mathematics.Bounds1 m_PrisonTimeRange`  
- `public System.Single m_PrisonProbability`  

## Constructors

- `public Crime()`  

## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

