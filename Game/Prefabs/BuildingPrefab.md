# Game.Prefabs.BuildingPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.StaticObjectPrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class BuildingPrefab : Game.Prefabs.StaticObjectPrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.BuildingAccessType m_AccessType;
    public System.Int32 m_LotWidth;
    public System.Int32 m_LotDepth;

    public System.Int32 lotSize { get; }

    public BuildingPrefab();

    public System.Void AddUpgrade(Unity.Entities.EntityManager entityManager, Game.Prefabs.ServiceUpgrade upgrade);
    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    protected virtual System.Void RefreshArchetype(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.BuildingAccessType m_AccessType`  

```csharp
public Game.Prefabs.BuildingAccessType m_AccessType;
```

- `public System.Int32 m_LotWidth`  

```csharp
public System.Int32 m_LotWidth;
```

- `public System.Int32 m_LotDepth`  

```csharp
public System.Int32 m_LotDepth;
```


## Properties

- `public System.Int32 lotSize { get }`  

```csharp
public System.Int32 lotSize { get; }
```


## Constructors

- `public BuildingPrefab()`  

```csharp
public BuildingPrefab();
```


## Methods

- `public AddUpgrade(Unity.Entities.EntityManager entityManager, Game.Prefabs.ServiceUpgrade upgrade) : System.Void`  

```csharp
public void AddUpgrade(EntityManager entityManager, ServiceUpgrade upgrade)
	{
		if (entityManager.World.GetExistingSystemManaged<PrefabSystem>().TryGetEntity(this, out var entity))
		{
			if (!entityManager.HasComponent<BuildingUpgradeElement>(entity))
			{
				entityManager.AddBuffer<BuildingUpgradeElement>(entity);
				if (entityManager.GetComponentData<ObjectData>(entity).m_Archetype.Valid)
				{
					RefreshArchetype(entityManager, entity);
				}
			}
			return;
		}
		throw new Exception("Building prefab entity not found for upgrade!");
	}
```

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		base.GetArchetypeComponents(components);
		components.Add(ComponentType.ReadWrite<Building>());
		components.Add(ComponentType.ReadWrite<CitizenPresence>());
		components.Add(ComponentType.ReadWrite<SpawnLocationElement>());
		components.Add(ComponentType.ReadWrite<CurrentDistrict>());
		components.Add(ComponentType.ReadWrite<UpdateFrame>());
		components.Add(ComponentType.ReadWrite<Game.Objects.Color>());
		components.Add(ComponentType.ReadWrite<Game.Objects.Surface>());
		components.Add(ComponentType.ReadWrite<BuildingModifier>());
		components.Add(ComponentType.ReadWrite<Policy>());
		components.Add(ComponentType.ReadWrite<Game.Net.SubLane>());
		components.Add(ComponentType.ReadWrite<Game.Objects.SubObject>());
		components.Add(ComponentType.ReadWrite<Game.Buildings.Lot>());
		components.Add(ComponentType.ReadWrite<EnabledEffect>());
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<BuildingData>());
		components.Add(ComponentType.ReadWrite<PlaceableObjectData>());
		components.Add(ComponentType.ReadWrite<BuildingTerraformData>());
		components.Add(ComponentType.ReadWrite<Effect>());
	}
```

- `protected virtual RefreshArchetype(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
protected override void RefreshArchetype(EntityManager entityManager, Entity entity)
	{
		List<ComponentBase> list = new List<ComponentBase>();
		GetComponents(list);
		HashSet<ComponentType> hashSet = new HashSet<ComponentType>();
		if (entityManager.HasComponent<BuildingUpgradeElement>(entity))
		{
			hashSet.Add(ComponentType.ReadWrite<InstalledUpgrade>());
			hashSet.Add(ComponentType.ReadWrite<Game.Net.SubNet>());
			hashSet.Add(ComponentType.ReadWrite<SubRoute>());
		}
		for (int i = 0; i < list.Count; i++)
		{
			list[i].GetArchetypeComponents(hashSet);
		}
		hashSet.Add(ComponentType.ReadWrite<Created>());
		hashSet.Add(ComponentType.ReadWrite<Updated>());
		entityManager.SetComponentData(entity, new ObjectData
		{
			m_Archetype = entityManager.CreateArchetype(PrefabUtils.ToArray(hashSet))
		});
	}
```


