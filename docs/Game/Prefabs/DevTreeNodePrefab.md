# Game.Prefabs.DevTreeNodePrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `RequireComponent`  

## Fields

- `public Game.Prefabs.ServicePrefab m_Service`  
- `public Game.Prefabs.DevTreeNodePrefab[] m_Requirements`  
- `public System.Int32 m_Cost`  
- `public System.Int32 m_HorizontalPosition`  
- `public System.Single m_VerticalPosition`  
- `public System.String m_IconPath`  
- `public Game.Prefabs.PrefabBase m_IconPrefab`  

## Constructors

- `public DevTreeNodePrefab()`  

## Methods

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  
- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `private HasRequirements() : System.Boolean`  
- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

