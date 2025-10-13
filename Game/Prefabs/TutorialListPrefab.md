# Game.Prefabs.TutorialListPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class TutorialListPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.Int32 m_Priority;
    public Game.Prefabs.TutorialPrefab[] m_Tutorials;

    public TutorialListPrefab();

    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Int32 m_Priority`  

```csharp
public System.Int32 m_Priority;
```

- `public Game.Prefabs.TutorialPrefab[] m_Tutorials`  

```csharp
public Game.Prefabs.TutorialPrefab[] m_Tutorials;
```


## Constructors

- `public TutorialListPrefab()`  

```csharp
public TutorialListPrefab();
```


## Methods

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		base.GetDependencies(prefabs);
		TutorialPrefab[] tutorials = m_Tutorials;
		foreach (TutorialPrefab item in tutorials)
		{
			prefabs.Add(item);
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<TutorialListData>());
		components.Add(ComponentType.ReadWrite<TutorialRef>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		entityManager.SetComponentData(entity, new TutorialListData(m_Priority));
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		PrefabSystem existingSystemManaged = World.DefaultGameObjectInjectionWorld.GetExistingSystemManaged<PrefabSystem>();
		DynamicBuffer<TutorialRef> buffer = entityManager.GetBuffer<TutorialRef>(entity);
		TutorialPrefab[] tutorials = m_Tutorials;
		foreach (TutorialPrefab tutorialPrefab in tutorials)
		{
			Entity entity2 = existingSystemManaged.GetEntity(tutorialPrefab);
			TutorialRef elem = new TutorialRef
			{
				m_Tutorial = entity2
			};
			buffer.Add(elem);
		}
	}
```


