# Game.Prefabs.NetStatusInfomodePrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.GradientInfomodeBasePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`, `Game.Prefabs.IGradientInfomode`  

**Attributes:** `ComponentMenu`  

## Fields

- `public Game.Prefabs.NetStatusType m_Type`  
- `public Colossal.Mathematics.Bounds1 m_Range`  
- `public System.Single m_FlowSpeed`  
- `public System.Single m_FlowTiling`  
- `public System.Single m_MinFlow`  

## Properties

- `public System.String infomodeTypeLocaleKey { get }`  

## Constructors

- `public NetStatusInfomodePrefab()`  

## Methods

- `public virtual CanActivateBoth(Game.Prefabs.InfomodePrefab other) : System.Boolean`  
- `public virtual GetColors(UnityEngine.Color& color0, UnityEngine.Color& color1, UnityEngine.Color& color2, System.Single& steps, System.Single& speed, System.Single& tiling, System.Single& fill) : System.Void`  
- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  
- `private VisibleOnRoadSurface() : System.Boolean`  

