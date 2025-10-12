# Game.Prefabs.NetObject

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Fields

- `public Game.Prefabs.NetPieceRequirements[] m_SetCompositionState`  
- `public Game.Net.RoadTypes m_RequireRoad`  
- `public Game.Net.RoadTypes m_RoadPassThrough`  
- `public Game.Net.TrackTypes m_TrackPassThrough`  
- `public System.Single m_NodeOffset`  
- `public System.Boolean m_Attached`  

## Constructors

- `public NetObject()`  

## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

