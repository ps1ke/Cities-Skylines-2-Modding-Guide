# Game.Prefabs.TutorialBalloonPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.TutorialPhasePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class TutorialBalloonPrefab : Game.Prefabs.TutorialPhasePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.TutorialBalloonPrefab+BalloonUITarget[] m_UITargets;

    public TutorialBalloonPrefab();

    public virtual System.Void GenerateTutorialLinks(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> linkedPrefabs);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.TutorialBalloonPrefab+BalloonUITarget[] m_UITargets`  

```csharp
public Game.Prefabs.TutorialBalloonPrefab+BalloonUITarget[] m_UITargets;
```


## Constructors

- `public TutorialBalloonPrefab()`  

```csharp
public TutorialBalloonPrefab();
```


## Methods

- `public virtual GenerateTutorialLinks(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> linkedPrefabs) : System.Void`  

```csharp
public override void GenerateTutorialLinks(EntityManager entityManager, NativeParallelHashSet<Entity> linkedPrefabs)
	{
		base.GenerateTutorialLinks(entityManager, linkedPrefabs);
		PrefabSystem existingSystemManaged = entityManager.World.GetExistingSystemManaged<PrefabSystem>();
		for (int i = 0; i < m_UITargets.Length; i++)
		{
			if (m_UITargets[i].m_UITagProvider != null)
			{
				linkedPrefabs.Add(existingSystemManaged.GetEntity(m_UITargets[i].m_UITagProvider));
			}
		}
	}
```

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		base.GetDependencies(prefabs);
		for (int i = 0; i < m_UITargets.Length; i++)
		{
			if (m_UITargets[i].m_UITagProvider != null)
			{
				prefabs.Add(m_UITargets[i].m_UITagProvider);
			}
		}
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		entityManager.SetComponentData(entity, new TutorialPhaseData
		{
			m_Type = TutorialPhaseType.Balloon,
			m_OverrideCompletionDelay = m_OverrideCompletionDelay
		});
	}
```


## Nested types

- `Game.Prefabs.TutorialBalloonPrefab+BalloonUITarget`  
- `Game.Prefabs.TutorialBalloonPrefab+BalloonDirection`  
- `Game.Prefabs.TutorialBalloonPrefab+BalloonAlignment`  

