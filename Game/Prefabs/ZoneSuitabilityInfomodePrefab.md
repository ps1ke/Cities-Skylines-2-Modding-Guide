# Game.Prefabs.ZoneSuitabilityInfomodePrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.GradientInfomodeBasePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`, `Game.Prefabs.IGradientInfomode`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ZoneSuitabilityInfomodePrefab : Game.Prefabs.GradientInfomodeBasePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase, Game.Prefabs.IGradientInfomode
{
    public Game.Zones.AreaType m_AreaType;
    public System.Boolean m_Office;

    public System.String infomodeTypeLocaleKey { get; }

    public ZoneSuitabilityInfomodePrefab();

    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Zones.AreaType m_AreaType`  

```csharp
public Game.Zones.AreaType m_AreaType;
```

- `public System.Boolean m_Office`  

```csharp
public System.Boolean m_Office;
```


## Properties

- `public System.String infomodeTypeLocaleKey { get }`  

```csharp
public System.String infomodeTypeLocaleKey { get; }
```


## Constructors

- `public ZoneSuitabilityInfomodePrefab()`  

```csharp
public ZoneSuitabilityInfomodePrefab();
```


## Methods

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<InfoviewAvailabilityData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		entityManager.SetComponentData(entity, new InfoviewAvailabilityData
		{
			m_AreaType = m_AreaType,
			m_Office = m_Office
		});
	}
```


