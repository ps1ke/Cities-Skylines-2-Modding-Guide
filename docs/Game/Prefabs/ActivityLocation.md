# Game.Prefabs.ActivityLocation

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Fields

- `public Game.Prefabs.ActivityLocation+LocationInfo[] m_Locations`  
- `public Game.Prefabs.NetInvertMode m_InvertWhen`  
- `public System.String m_AnimatedPropName`  
- `public System.Boolean m_RequireAuthorization`  

## Properties

- `public System.Boolean ignoreUnlockDependencies { get }`  

## Constructors

- `public ActivityLocation()`  

## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  
- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

## Nested types

- `Game.Prefabs.ActivityLocation+LocationInfo`  

