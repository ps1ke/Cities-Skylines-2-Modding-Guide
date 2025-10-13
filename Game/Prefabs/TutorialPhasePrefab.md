# Game.Prefabs.TutorialPhasePrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class abstract public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

## Code

```csharp
public abstract class TutorialPhasePrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.String m_Image;
    public System.String m_OverrideImagePS;
    public System.String m_OverrideImageXBox;
    public System.String m_Icon;
    public System.Boolean m_TitleVisible;
    public System.Boolean m_DescriptionVisible;
    public System.Boolean m_CanDeactivate;
    public Game.Prefabs.TutorialPhasePrefab+ControlScheme m_ControlScheme;
    public Game.Prefabs.TutorialTriggerPrefabBase m_Trigger;
    public System.Single m_OverrideCompletionDelay;

    public System.Boolean ignoreUnlockDependencies { get; }

    protected TutorialPhasePrefab();

    public virtual System.Void GenerateTutorialLinks(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> linkedPrefabs);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.String m_Image`  

```csharp
public System.String m_Image;
```

- `public System.String m_OverrideImagePS`  

```csharp
public System.String m_OverrideImagePS;
```

- `public System.String m_OverrideImageXBox`  

```csharp
public System.String m_OverrideImageXBox;
```

- `public System.String m_Icon`  

```csharp
public System.String m_Icon;
```

- `public System.Boolean m_TitleVisible`  

```csharp
public System.Boolean m_TitleVisible;
```

- `public System.Boolean m_DescriptionVisible`  

```csharp
public System.Boolean m_DescriptionVisible;
```

- `public System.Boolean m_CanDeactivate`  

```csharp
public System.Boolean m_CanDeactivate;
```

- `public Game.Prefabs.TutorialPhasePrefab+ControlScheme m_ControlScheme`  

```csharp
public Game.Prefabs.TutorialPhasePrefab+ControlScheme m_ControlScheme;
```

- `public Game.Prefabs.TutorialTriggerPrefabBase m_Trigger`  

```csharp
public Game.Prefabs.TutorialTriggerPrefabBase m_Trigger;
```

- `public System.Single m_OverrideCompletionDelay`  

```csharp
public System.Single m_OverrideCompletionDelay;
```


## Properties

- `public System.Boolean ignoreUnlockDependencies { get }`  

```csharp
public System.Boolean ignoreUnlockDependencies { get; }
```


## Constructors

- `protected TutorialPhasePrefab()`  

```csharp
protected TutorialPhasePrefab();
```


## Methods

- `public virtual GenerateTutorialLinks(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> linkedPrefabs) : System.Void`  

```csharp
public virtual void GenerateTutorialLinks(EntityManager entityManager, NativeParallelHashSet<Entity> linkedPrefabs)
	{
		if (m_Trigger != null)
		{
			m_Trigger.GenerateTutorialLinks(entityManager, linkedPrefabs);
		}
	}
```

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		base.GetDependencies(prefabs);
		if (m_Trigger != null)
		{
			prefabs.Add(m_Trigger);
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<TutorialPhaseData>());
		if (m_Trigger != null)
		{
			components.Add(ComponentType.ReadWrite<TutorialTrigger>());
		}
		if (m_CanDeactivate)
		{
			components.Add(ComponentType.ReadWrite<TutorialPhaseCanDeactivate>());
		}
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		PrefabSystem existingSystemManaged = entityManager.World.GetExistingSystemManaged<PrefabSystem>();
		if (entityManager.HasComponent<TutorialTrigger>(entity))
		{
			entityManager.SetComponentData(entity, new TutorialTrigger
			{
				m_Trigger = existingSystemManaged.GetEntity(m_Trigger)
			});
		}
	}
```


## Nested types

- `Game.Prefabs.TutorialPhasePrefab+ControlScheme`  

