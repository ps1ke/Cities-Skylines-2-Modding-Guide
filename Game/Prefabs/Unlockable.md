# Game.Prefabs.Unlockable

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.UnlockableBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class Unlockable : Game.Prefabs.UnlockableBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.PrefabBase[] m_RequireAll;
    public Game.Prefabs.PrefabBase[] m_RequireAny;
    public System.Boolean m_IgnoreDependencies;

    public Unlockable();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, System.Collections.Generic.List<Game.Prefabs.PrefabBase> dependencies);
}
```


## Fields

- `public Game.Prefabs.PrefabBase[] m_RequireAll`  

```csharp
public Game.Prefabs.PrefabBase[] m_RequireAll;
```

- `public Game.Prefabs.PrefabBase[] m_RequireAny`  

```csharp
public Game.Prefabs.PrefabBase[] m_RequireAny;
```

- `public System.Boolean m_IgnoreDependencies`  

```csharp
public System.Boolean m_IgnoreDependencies;
```


## Constructors

- `public Unlockable()`  

```csharp
public Unlockable();
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
		if (m_RequireAll != null)
		{
			for (int i = 0; i < m_RequireAll.Length; i++)
			{
				prefabs.Add(m_RequireAll[i]);
			}
		}
		if (m_RequireAny != null)
		{
			for (int j = 0; j < m_RequireAny.Length; j++)
			{
				prefabs.Add(m_RequireAny[j]);
			}
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, System.Collections.Generic.List<Game.Prefabs.PrefabBase> dependencies) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity, List<PrefabBase> dependencies)
	{
		base.LateInitialize(entityManager, entity, dependencies);
		PrefabSystem existingSystemManaged = entityManager.World.GetExistingSystemManaged<PrefabSystem>();
		DynamicBuffer<UnlockRequirement> buffer = entityManager.GetBuffer<UnlockRequirement>(entity);
		if (!m_IgnoreDependencies)
		{
			for (int i = 0; i < dependencies.Count; i++)
			{
				PrefabBase prefabBase = dependencies[i];
				if (existingSystemManaged.IsUnlockable(prefabBase))
				{
					Entity entity2 = existingSystemManaged.GetEntity(prefabBase);
					buffer.Add(new UnlockRequirement(entity2, UnlockFlags.RequireAll));
				}
			}
		}
		if (m_RequireAll != null)
		{
			for (int j = 0; j < m_RequireAll.Length; j++)
			{
				PrefabBase prefabBase2 = m_RequireAll[j];
				if (existingSystemManaged.IsUnlockable(prefabBase2))
				{
					Entity entity3 = existingSystemManaged.GetEntity(prefabBase2);
					buffer.Add(new UnlockRequirement(entity3, UnlockFlags.RequireAll));
				}
			}
		}
		if (m_RequireAny == null)
		{
			return;
		}
		for (int k = 0; k < m_RequireAny.Length; k++)
		{
			PrefabBase prefabBase3 = m_RequireAny[k];
			if (existingSystemManaged.IsUnlockable(prefabBase3))
			{
				Entity entity4 = existingSystemManaged.GetEntity(prefabBase3);
				buffer.Add(new UnlockRequirement(entity4, UnlockFlags.RequireAny));
			}
		}
	}
```


