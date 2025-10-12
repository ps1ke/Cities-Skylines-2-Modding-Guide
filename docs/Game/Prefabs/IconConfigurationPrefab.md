# Game.Prefabs.IconConfigurationPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Fields

- `public UnityEngine.Material m_Material`  
- `public Game.Prefabs.NotificationIconPrefab m_SelectedMarker`  
- `public Game.Prefabs.NotificationIconPrefab m_FollowedMarker`  
- `public Game.Prefabs.IconAnimationInfo[] m_Animations`  
- `public UnityEngine.Texture2D m_MissingIcon`  

## Constructors

- `public IconConfigurationPrefab()`  

## Methods

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  
- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

