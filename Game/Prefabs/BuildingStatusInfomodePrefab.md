# Game.Prefabs.BuildingStatusInfomodePrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.GradientInfomodeBasePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`, `Game.Prefabs.IGradientInfomode`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class BuildingStatusInfomodePrefab : Game.Prefabs.GradientInfomodeBasePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase, Game.Prefabs.IGradientInfomode
{
    public Game.Prefabs.BuildingStatusType m_Type;
    public Colossal.Mathematics.Bounds1 m_Range;

    public System.String infomodeTypeLocaleKey { get; }

    public BuildingStatusInfomodePrefab();

    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.BuildingStatusType m_Type`  

```csharp
public Game.Prefabs.BuildingStatusType m_Type;
```

- `public Colossal.Mathematics.Bounds1 m_Range`  

```csharp
public Colossal.Mathematics.Bounds1 m_Range;
```


## Properties

- `public System.String infomodeTypeLocaleKey { get }`  

```csharp
public System.String infomodeTypeLocaleKey { get; }
```


## Constructors

- `public BuildingStatusInfomodePrefab()`  

```csharp
public BuildingStatusInfomodePrefab();
```


## Methods

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<InfoviewBuildingStatusData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		entityManager.SetComponentData(entity, new InfoviewBuildingStatusData
		{
			m_Type = m_Type,
			m_Range = m_Range
		});
	}
```


