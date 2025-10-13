# Game.Prefabs.UnlockableBase

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class abstract public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

## Code

```csharp
public abstract class UnlockableBase : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    protected UnlockableBase();

    public static System.Void DefaultLateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, System.Collections.Generic.List<Game.Prefabs.PrefabBase> dependencies);
    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, System.Collections.Generic.List<Game.Prefabs.PrefabBase> dependencies);
}
```


## Constructors

- `protected UnlockableBase()`  

```csharp
protected UnlockableBase();
```


## Methods

- `public static DefaultLateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, System.Collections.Generic.List<Game.Prefabs.PrefabBase> dependencies) : System.Void`  

```csharp
public static void DefaultLateInitialize(EntityManager entityManager, Entity entity, List<PrefabBase> dependencies)
	{
		PrefabSystem existingSystemManaged = entityManager.World.GetExistingSystemManaged<PrefabSystem>();
		DynamicBuffer<UnlockRequirement> buffer = entityManager.GetBuffer<UnlockRequirement>(entity);
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
```

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
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
public virtual void LateInitialize(EntityManager entityManager, Entity entity, List<PrefabBase> dependencies)
	{
		LateInitialize(entityManager, entity);
	}
```


