# Game.Prefabs.BuildingPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.StaticObjectPrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Fields

- `public Game.Prefabs.BuildingAccessType m_AccessType`  
- `public System.Int32 m_LotWidth`  
- `public System.Int32 m_LotDepth`  

## Properties

- `public System.Int32 lotSize { get }`  

## Constructors

- `public BuildingPrefab()`  

## Methods

- `public AddUpgrade(Unity.Entities.EntityManager entityManager, Game.Prefabs.ServiceUpgrade upgrade) : System.Void`  
- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `protected virtual RefreshArchetype(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

