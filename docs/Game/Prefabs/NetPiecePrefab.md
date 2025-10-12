# Game.Prefabs.NetPiecePrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.RenderPrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Fields

- `public Game.Prefabs.NetPieceLayer m_Layer`  
- `public System.Single m_Width`  
- `public System.Single m_Length`  
- `public Colossal.Mathematics.Bounds1 m_HeightRange`  
- `public System.Single m_WidthOffset`  
- `public System.Single m_NodeOffset`  
- `public System.Single m_SideConnectionOffset`  
- `public Unity.Mathematics.float4 m_SurfaceHeights`  

## Constructors

- `public NetPiecePrefab()`  

## Methods

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

