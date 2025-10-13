# Game.Prefabs.BuildingStateInfomodePrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ColorInfomodeBasePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`, `Game.Prefabs.IColorInfomode`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class BuildingStateInfomodePrefab : Game.Prefabs.ColorInfomodeBasePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase, Game.Prefabs.IColorInfomode
{
    public Game.Prefabs.BuildingStatusType m_Type;

    public System.String infomodeTypeLocaleKey { get; }

    public BuildingStateInfomodePrefab();

    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.BuildingStatusType m_Type`  

```csharp
public Game.Prefabs.BuildingStatusType m_Type;
```


## Properties

- `public System.String infomodeTypeLocaleKey { get }`  

```csharp
public System.String infomodeTypeLocaleKey { get; }
```


## Constructors

- `public BuildingStateInfomodePrefab()`  

```csharp
public BuildingStateInfomodePrefab();
```


## Methods

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<InfoviewBuildingStatusData>());
		if (m_Type == BuildingStatusType.LeisureProvider)
		{
			components.Add(ComponentType.ReadWrite<InfoviewNetStatusData>());
		}
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		entityManager.SetComponentData(entity, new InfoviewBuildingStatusData
		{
			m_Type = m_Type
		});
		if (m_Type == BuildingStatusType.LeisureProvider)
		{
			entityManager.SetComponentData(entity, new InfoviewNetStatusData
			{
				m_Type = NetStatusType.LeisureProvider
			});
		}
	}
```


