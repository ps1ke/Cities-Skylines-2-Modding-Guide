# Game.Prefabs.TrainPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class abstract public  

**Base:** `Game.Prefabs.VehiclePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ExcludeGeneratedModTag`  

## Fields

- `public Game.Net.TrackTypes m_TrackType`  
- `public Game.Vehicles.EnergyTypes m_EnergyType`  
- `public System.Single m_MaxSpeed`  
- `public System.Single m_Acceleration`  
- `public System.Single m_Braking`  
- `public Unity.Mathematics.float2 m_Turning`  
- `public Unity.Mathematics.float2 m_BogieOffset`  
- `public Unity.Mathematics.float2 m_AttachOffset`  

## Properties

- `public System.Collections.Generic.IEnumerable<System.String> modTags { get }`  

## Constructors

- `protected TrainPrefab()`  

## Methods

- `private <>n__0() : System.Collections.Generic.IEnumerable<System.String>`  
- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  
- `protected virtual RefreshArchetype(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

## Nested types

- `Game.Prefabs.TrainPrefab+<get_modTags>d__13`  

