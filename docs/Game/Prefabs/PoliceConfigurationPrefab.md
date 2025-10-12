# Game.Prefabs.PoliceConfigurationPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Fields

- `public Game.Prefabs.PrefabBase m_PoliceServicePrefab`  
- `public Game.Prefabs.NotificationIconPrefab m_TrafficAccidentNotificationPrefab`  
- `public Game.Prefabs.NotificationIconPrefab m_CrimeSceneNotificationPrefab`  
- `public System.Single m_MaxCrimeAccumulation`  
- `public System.Single m_CrimeAccumulationTolerance`  
- `public System.Int32 m_HomeCrimeEffect`  
- `public System.Int32 m_WorkplaceCrimeEffect`  
- `public System.Single m_WelfareCrimeRecurrenceFactor`  
- `public System.Single m_CrimePoliceCoverageFactor`  
- `public System.Single m_CrimePopulationReduction`  

## Properties

- `public System.Boolean ignoreUnlockDependencies { get }`  

## Constructors

- `public PoliceConfigurationPrefab()`  

## Methods

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  
- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

