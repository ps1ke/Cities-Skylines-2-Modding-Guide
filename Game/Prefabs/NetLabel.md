# Game.Prefabs.NetLabel

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class NetLabel : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public UnityEngine.Material m_NameMaterial;
    public UnityEngine.Color m_NameColor;
    public UnityEngine.Color m_SelectedNameColor;

    public NetLabel();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public UnityEngine.Material m_NameMaterial`  

```csharp
public UnityEngine.Material m_NameMaterial;
```

- `public UnityEngine.Color m_NameColor`  

```csharp
public UnityEngine.Color m_NameColor;
```

- `public UnityEngine.Color m_SelectedNameColor`  

```csharp
public UnityEngine.Color m_SelectedNameColor;
```


## Constructors

- `public NetLabel()`  

```csharp
public NetLabel();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<LabelMaterial>());
		components.Add(ComponentType.ReadWrite<LabelExtents>());
		components.Add(ComponentType.ReadWrite<LabelPosition>());
		components.Add(ComponentType.ReadWrite<LabelVertex>());
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<NetNameData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		entityManager.SetComponentData(entity, new NetNameData
		{
			m_Color = m_NameColor.linear,
			m_SelectedColor = m_SelectedNameColor.linear
		});
	}
```


