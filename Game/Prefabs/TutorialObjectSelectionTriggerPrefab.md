# Game.Prefabs.TutorialObjectSelectionTriggerPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.TutorialTriggerPrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class TutorialObjectSelectionTriggerPrefab : Game.Prefabs.TutorialTriggerPrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.TutorialObjectSelectionTriggerPrefab+ObjectSelectionTriggerInfo[] m_Triggers;

    public System.Boolean phaseBranching { get; }

    public TutorialObjectSelectionTriggerPrefab();

    public virtual System.Void GenerateTutorialLinks(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> linkedPrefabs);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.TutorialObjectSelectionTriggerPrefab+ObjectSelectionTriggerInfo[] m_Triggers`  

```csharp
public Game.Prefabs.TutorialObjectSelectionTriggerPrefab+ObjectSelectionTriggerInfo[] m_Triggers;
```


## Properties

- `public System.Boolean phaseBranching { get }`  

```csharp
public System.Boolean phaseBranching { get; }
```


## Constructors

- `public TutorialObjectSelectionTriggerPrefab()`  

```csharp
public TutorialObjectSelectionTriggerPrefab();
```


## Methods

- `public virtual GenerateTutorialLinks(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> linkedPrefabs) : System.Void`  

```csharp
public override void GenerateTutorialLinks(EntityManager entityManager, NativeParallelHashSet<Entity> linkedPrefabs)
	{
		base.GenerateTutorialLinks(entityManager, linkedPrefabs);
		PrefabSystem existingSystemManaged = entityManager.World.GetExistingSystemManaged<PrefabSystem>();
		for (int i = 0; i < m_Triggers.Length; i++)
		{
			ObjectSelectionTriggerInfo objectSelectionTriggerInfo = m_Triggers[i];
			linkedPrefabs.Add(existingSystemManaged.GetEntity(objectSelectionTriggerInfo.m_Trigger));
		}
	}
```

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		base.GetDependencies(prefabs);
		for (int i = 0; i < m_Triggers.Length; i++)
		{
			prefabs.Add(m_Triggers[i].m_Trigger);
			if (m_Triggers[i].m_GoToPhase != null)
			{
				prefabs.Add(m_Triggers[i].m_GoToPhase);
			}
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<ObjectSelectionTriggerData>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		DynamicBuffer<ObjectSelectionTriggerData> buffer = entityManager.GetBuffer<ObjectSelectionTriggerData>(entity);
		PrefabSystem existingSystemManaged = entityManager.World.GetExistingSystemManaged<PrefabSystem>();
		for (int i = 0; i < m_Triggers.Length; i++)
		{
			ObjectSelectionTriggerInfo objectSelectionTriggerInfo = m_Triggers[i];
			Entity entity2 = existingSystemManaged.GetEntity(objectSelectionTriggerInfo.m_Trigger);
			Entity goToPhase = ((objectSelectionTriggerInfo.m_GoToPhase == null) ? Entity.Null : existingSystemManaged.GetEntity(objectSelectionTriggerInfo.m_GoToPhase));
			buffer.Add(new ObjectSelectionTriggerData
			{
				m_Prefab = entity2,
				m_GoToPhase = goToPhase
			});
		}
		if (m_Triggers.Length <= 1)
		{
			return;
		}
		for (int j = 0; j < m_Triggers.Length; j++)
		{
			TutorialPhasePrefab goToPhase2 = m_Triggers[j].m_GoToPhase;
			if (goToPhase2 != null)
			{
				entityManager.AddComponent<TutorialPhaseBranch>(existingSystemManaged.GetEntity(goToPhase2));
			}
		}
	}
```


## Nested types

- `Game.Prefabs.TutorialObjectSelectionTriggerPrefab+ObjectSelectionTriggerInfo`  
- `Game.Prefabs.TutorialObjectSelectionTriggerPrefab+<>c`  

