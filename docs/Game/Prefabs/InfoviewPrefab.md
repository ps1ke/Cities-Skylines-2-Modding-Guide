# Game.Prefabs.InfoviewPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Fields

- `public Game.Prefabs.InfomodeInfo[] m_Infomodes`  
- `public UnityEngine.Color m_DefaultColor`  
- `public UnityEngine.Color m_SecondaryColor`  
- `public System.String m_IconPath`  
- `public System.Int32 m_Priority`  
- `public System.Int32 m_Group`  
- `public Game.Prefabs.IconCategory[] m_WarningCategories`  
- `public System.Boolean m_Editor`  
- `private System.Boolean <isValid>k__BackingField`  

## Properties

- `public System.Boolean isValid { get; private set }`  
- `public System.Boolean ignoreUnlockDependencies { get }`  

## Constructors

- `public InfoviewPrefab()`  

## Methods

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  
- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

