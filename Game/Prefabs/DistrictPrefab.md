# Game.Prefabs.DistrictPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.AreaPrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class DistrictPrefab : Game.Prefabs.AreaPrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public UnityEngine.Color m_NameColor;
    public UnityEngine.Color m_SelectedNameColor;

    public DistrictPrefab();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public UnityEngine.Color m_NameColor`  

```csharp
public UnityEngine.Color m_NameColor;
```

- `public UnityEngine.Color m_SelectedNameColor`  

```csharp
public UnityEngine.Color m_SelectedNameColor;
```


## Constructors

- `public DistrictPrefab()`  

```csharp
public DistrictPrefab();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		base.GetArchetypeComponents(components);
		components.Add(ComponentType.ReadWrite<District>());
		components.Add(ComponentType.ReadWrite<Geometry>());
		components.Add(ComponentType.ReadWrite<LabelExtents>());
		components.Add(ComponentType.ReadWrite<LabelVertex>());
		components.Add(ComponentType.ReadWrite<DistrictModifier>());
		components.Add(ComponentType.ReadWrite<Policy>());
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<DistrictData>());
		components.Add(ComponentType.ReadWrite<AreaNameData>());
		components.Add(ComponentType.ReadWrite<AreaGeometryData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		entityManager.SetComponentData(entity, new AreaNameData
		{
			m_Color = m_NameColor,
			m_SelectedColor = m_SelectedNameColor
		});
	}
```


