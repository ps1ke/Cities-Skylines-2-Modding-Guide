# Game.Prefabs.TutorialPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class TutorialPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.TutorialPhasePrefab[] m_Phases;
    public System.Int32 m_Priority;
    public System.Boolean m_ReplaceActive;
    public System.Boolean m_Mandatory;
    public System.Boolean m_EditorTutorial;
    public System.Boolean m_FireTelemetry;

    public System.Boolean ignoreUnlockDependencies { get; }

    public TutorialPrefab();

    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.TutorialPhasePrefab[] m_Phases`  

```csharp
public Game.Prefabs.TutorialPhasePrefab[] m_Phases;
```

- `public System.Int32 m_Priority`  

```csharp
public System.Int32 m_Priority;
```

- `public System.Boolean m_ReplaceActive`  

```csharp
public System.Boolean m_ReplaceActive;
```

- `public System.Boolean m_Mandatory`  

```csharp
public System.Boolean m_Mandatory;
```

- `public System.Boolean m_EditorTutorial`  

```csharp
public System.Boolean m_EditorTutorial;
```

- `public System.Boolean m_FireTelemetry`  

```csharp
public System.Boolean m_FireTelemetry;
```


## Properties

- `public System.Boolean ignoreUnlockDependencies { get }`  

```csharp
public System.Boolean ignoreUnlockDependencies { get; }
```


## Constructors

- `public TutorialPrefab()`  

```csharp
public TutorialPrefab();
```


## Methods

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		base.GetDependencies(prefabs);
		TutorialPhasePrefab[] phases = m_Phases;
		foreach (TutorialPhasePrefab item in phases)
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
		components.Add(ComponentType.ReadWrite<TutorialData>());
		components.Add(ComponentType.ReadWrite<TutorialPhaseRef>());
		if (m_ReplaceActive)
		{
			components.Add(ComponentType.ReadWrite<ReplaceActiveData>());
		}
		if (m_FireTelemetry)
		{
			components.Add(ComponentType.ReadOnly<TutorialFireTelemetry>());
		}
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		entityManager.SetComponentData(entity, new TutorialData(m_Priority));
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		PrefabSystem existingSystemManaged = World.DefaultGameObjectInjectionWorld.GetExistingSystemManaged<PrefabSystem>();
		DynamicBuffer<TutorialPhaseRef> buffer = entityManager.GetBuffer<TutorialPhaseRef>(entity);
		NativeParallelHashSet<Entity> linkedPrefabs = new NativeParallelHashSet<Entity>(5, Allocator.TempJob);
		TutorialPhasePrefab[] phases = m_Phases;
		foreach (TutorialPhasePrefab tutorialPhasePrefab in phases)
		{
			Entity entity2 = existingSystemManaged.GetEntity(tutorialPhasePrefab);
			TutorialPhaseRef elem = new TutorialPhaseRef
			{
				m_Phase = entity2
			};
			buffer.Add(elem);
			tutorialPhasePrefab.GenerateTutorialLinks(entityManager, linkedPrefabs);
		}
		foreach (Entity item in linkedPrefabs)
		{
			if (!entityManager.TryGetBuffer(item, isReadOnly: false, out DynamicBuffer<TutorialLinkData> buffer2))
			{
				buffer2 = entityManager.AddBuffer<TutorialLinkData>(item);
			}
			buffer2.Add(new TutorialLinkData
			{
				m_Tutorial = entity
			});
		}
		if (m_EditorTutorial)
		{
			entityManager.AddComponent<EditorTutorial>(entity);
		}
		linkedPrefabs.Dispose();
	}
```


