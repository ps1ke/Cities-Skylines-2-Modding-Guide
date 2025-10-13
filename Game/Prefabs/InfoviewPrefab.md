# Game.Prefabs.InfoviewPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class InfoviewPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.InfomodeInfo[] m_Infomodes;
    public UnityEngine.Color m_DefaultColor;
    public UnityEngine.Color m_SecondaryColor;
    public System.String m_IconPath;
    public System.Int32 m_Priority;
    public System.Int32 m_Group;
    public Game.Prefabs.IconCategory[] m_WarningCategories;
    public System.Boolean m_Editor;
    private System.Boolean <isValid>k__BackingField;

    public System.Boolean isValid { get; private set; }
    public System.Boolean ignoreUnlockDependencies { get; }

    public InfoviewPrefab();

    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.InfomodeInfo[] m_Infomodes`  

```csharp
public Game.Prefabs.InfomodeInfo[] m_Infomodes;
```

- `public UnityEngine.Color m_DefaultColor`  

```csharp
public UnityEngine.Color m_DefaultColor;
```

- `public UnityEngine.Color m_SecondaryColor`  

```csharp
public UnityEngine.Color m_SecondaryColor;
```

- `public System.String m_IconPath`  

```csharp
public System.String m_IconPath;
```

- `public System.Int32 m_Priority`  

```csharp
public System.Int32 m_Priority;
```

- `public System.Int32 m_Group`  

```csharp
public System.Int32 m_Group;
```

- `public Game.Prefabs.IconCategory[] m_WarningCategories`  

```csharp
public Game.Prefabs.IconCategory[] m_WarningCategories;
```

- `public System.Boolean m_Editor`  

```csharp
public System.Boolean m_Editor;
```

- `private System.Boolean <isValid>k__BackingField`  

```csharp
private System.Boolean <isValid>k__BackingField;
```


## Properties

- `public System.Boolean isValid { get; private set }`  

```csharp
public System.Boolean isValid { get; private set; }
```

- `public System.Boolean ignoreUnlockDependencies { get }`  

```csharp
public System.Boolean ignoreUnlockDependencies { get; }
```


## Constructors

- `public InfoviewPrefab()`  

```csharp
public InfoviewPrefab();
```


## Methods

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		base.GetDependencies(prefabs);
		if (m_Infomodes != null)
		{
			for (int i = 0; i < m_Infomodes.Length; i++)
			{
				prefabs.Add(m_Infomodes[i].m_Mode);
			}
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<InfoviewData>());
		components.Add(ComponentType.ReadWrite<InfoviewMode>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		InfoviewData componentData = default(InfoviewData);
		componentData.m_NotificationMask = 0u;
		if (m_WarningCategories != null)
		{
			for (int i = 0; i < m_WarningCategories.Length; i++)
			{
				componentData.m_NotificationMask |= (uint)(1 << (int)m_WarningCategories[i]);
			}
		}
		entityManager.SetComponentData(entity, componentData);
		isValid = m_Infomodes != null && m_Infomodes.Length != 0;
	}
```


