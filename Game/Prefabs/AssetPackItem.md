# Game.Prefabs.AssetPackItem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class AssetPackItem : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.AssetPackPrefab[] m_Packs;

    public AssetPackItem();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.AssetPackPrefab[] m_Packs`  

```csharp
public Game.Prefabs.AssetPackPrefab[] m_Packs;
```


## Constructors

- `public AssetPackItem()`  

```csharp
public AssetPackItem();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
	}
```

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		base.GetDependencies(prefabs);
		if (m_Packs == null)
		{
			return;
		}
		for (int i = 0; i < m_Packs.Length; i++)
		{
			if (m_Packs[i] != null)
			{
				prefabs.Add(m_Packs[i]);
			}
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<AssetPackElement>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		DynamicBuffer<AssetPackElement> buffer = entityManager.GetBuffer<AssetPackElement>(entity);
		buffer.Clear();
		if (m_Packs == null || m_Packs.Length == 0)
		{
			return;
		}
		PrefabSystem existingSystemManaged = entityManager.World.GetExistingSystemManaged<PrefabSystem>();
		AssetPackElement elem = default(AssetPackElement);
		for (int i = 0; i < m_Packs.Length; i++)
		{
			AssetPackPrefab assetPackPrefab = m_Packs[i];
			if (!(assetPackPrefab == null))
			{
				elem.m_Pack = existingSystemManaged.GetEntity(assetPackPrefab);
				buffer.Add(elem);
			}
		}
	}
```


