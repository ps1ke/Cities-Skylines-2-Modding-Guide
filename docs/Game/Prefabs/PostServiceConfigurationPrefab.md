# Game.Prefabs.PostServiceConfigurationPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Fields

- `public Game.Prefabs.ServicePrefab m_PostServicePrefab`  
- `public System.Int32 m_MaxMailAccumulation`  
- `public System.Int32 m_MailAccumulationTolerance`  
- `public System.Int32 m_OutgoingMailPercentage`  

## Properties

- `public System.Boolean ignoreUnlockDependencies { get }`  

## Constructors

- `public PostServiceConfigurationPrefab()`  

## Methods

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  
- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

