# Game.Prefabs.TutorialUITriggerPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.TutorialTriggerPrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class TutorialUITriggerPrefab : Game.Prefabs.TutorialTriggerPrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.TutorialUITriggerPrefab+UITriggerInfo[] m_UITriggers;

    public System.Boolean phaseBranching { get; }

    public TutorialUITriggerPrefab();

    protected virtual System.Void GenerateBlinkTags();
    public virtual System.Void GenerateTutorialLinks(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> linkedPrefabs);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.TutorialUITriggerPrefab+UITriggerInfo[] m_UITriggers`  

```csharp
public Game.Prefabs.TutorialUITriggerPrefab+UITriggerInfo[] m_UITriggers;
```


## Properties

- `public System.Boolean phaseBranching { get }`  

```csharp
public System.Boolean phaseBranching { get; }
```


## Constructors

- `public TutorialUITriggerPrefab()`  

```csharp
public TutorialUITriggerPrefab();
```


## Methods

- `protected virtual GenerateBlinkTags() : System.Void`  

```csharp
protected override void GenerateBlinkTags()
	{
		base.GenerateBlinkTags();
		for (int i = 0; i < m_UITriggers.Length; i++)
		{
			if (!m_UITriggers[i].m_DisableBlinking)
			{
				string[] array = m_UITriggers[i].m_UITagProvider.uiTag.Split('|');
				foreach (string text in array)
				{
					AddBlinkTag(text.Trim());
				}
			}
		}
	}
```

- `public virtual GenerateTutorialLinks(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> linkedPrefabs) : System.Void`  

```csharp
public override void GenerateTutorialLinks(EntityManager entityManager, NativeParallelHashSet<Entity> linkedPrefabs)
	{
		base.GenerateTutorialLinks(entityManager, linkedPrefabs);
		PrefabSystem existingSystemManaged = entityManager.World.GetExistingSystemManaged<PrefabSystem>();
		for (int i = 0; i < m_UITriggers.Length; i++)
		{
			linkedPrefabs.Add(existingSystemManaged.GetEntity(m_UITriggers[i].m_UITagProvider));
		}
	}
```

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		base.GetDependencies(prefabs);
		for (int i = 0; i < m_UITriggers.Length; i++)
		{
			prefabs.Add(m_UITriggers[i].m_UITagProvider);
			if (m_UITriggers[i].m_GoToPhase != null)
			{
				prefabs.Add(m_UITriggers[i].m_GoToPhase);
			}
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<UITriggerData>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		if (m_UITriggers.Length <= 1)
		{
			return;
		}
		PrefabSystem existingSystemManaged = World.DefaultGameObjectInjectionWorld.GetExistingSystemManaged<PrefabSystem>();
		for (int i = 0; i < m_UITriggers.Length; i++)
		{
			TutorialPhasePrefab goToPhase = m_UITriggers[i].m_GoToPhase;
			if (goToPhase != null)
			{
				entityManager.AddComponent<TutorialPhaseBranch>(existingSystemManaged.GetEntity(goToPhase));
			}
		}
	}
```


## Nested types

- `Game.Prefabs.TutorialUITriggerPrefab+UITriggerInfo`  
- `Game.Prefabs.TutorialUITriggerPrefab+<>c`  

