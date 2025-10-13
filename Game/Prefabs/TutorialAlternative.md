# Game.Prefabs.TutorialAlternative

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class TutorialAlternative : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.TutorialPrefab[] m_Alternatives;

    public TutorialAlternative();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.TutorialPrefab[] m_Alternatives`  

```csharp
public Game.Prefabs.TutorialPrefab[] m_Alternatives;
```


## Constructors

- `public TutorialAlternative()`  

```csharp
public TutorialAlternative();
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
		TutorialPrefab[] alternatives = m_Alternatives;
		foreach (TutorialPrefab item in alternatives)
		{
			prefabs.Add(item);
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<Game.Tutorials.TutorialAlternative>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		PrefabSystem orCreateSystemManaged = entityManager.World.GetOrCreateSystemManaged<PrefabSystem>();
		DynamicBuffer<Game.Tutorials.TutorialAlternative> buffer = entityManager.GetBuffer<Game.Tutorials.TutorialAlternative>(entity);
		TutorialPrefab[] alternatives = m_Alternatives;
		foreach (TutorialPrefab tutorialPrefab in alternatives)
		{
			buffer.Add(new Game.Tutorials.TutorialAlternative
			{
				m_Alternative = orCreateSystemManaged.GetEntity(tutorialPrefab)
			});
		}
	}
```


