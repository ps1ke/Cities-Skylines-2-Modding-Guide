# Game.Prefabs.TutorialAreaTriggerPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.TutorialTriggerPrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class TutorialAreaTriggerPrefab : Game.Prefabs.TutorialTriggerPrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.AreaPrefab[] m_Targets;
    public Game.Tutorials.AreaTriggerFlags m_Flags;

    public TutorialAreaTriggerPrefab();

    protected virtual System.Void GenerateBlinkTags();
    public virtual System.Void GenerateTutorialLinks(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> linkedPrefabs);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.AreaPrefab[] m_Targets`  

```csharp
public Game.Prefabs.AreaPrefab[] m_Targets;
```

- `public Game.Tutorials.AreaTriggerFlags m_Flags`  

```csharp
public Game.Tutorials.AreaTriggerFlags m_Flags;
```


## Constructors

- `public TutorialAreaTriggerPrefab()`  

```csharp
public TutorialAreaTriggerPrefab();
```


## Methods

- `protected virtual GenerateBlinkTags() : System.Void`  

```csharp
protected override void GenerateBlinkTags()
	{
		base.GenerateBlinkTags();
		AreaPrefab[] targets = m_Targets;
		foreach (AreaPrefab areaPrefab in targets)
		{
			if (areaPrefab.TryGet<UIObject>(out var component) && component.m_Group is UIAssetCategoryPrefab uIAssetCategoryPrefab && uIAssetCategoryPrefab.m_Menu != null)
			{
				AddBlinkTagAtPosition(areaPrefab.uiTag, 0);
				AddBlinkTagAtPosition(uIAssetCategoryPrefab.uiTag, 1);
				AddBlinkTagAtPosition(uIAssetCategoryPrefab.m_Menu.uiTag, 2);
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
		AreaPrefab[] targets = m_Targets;
		foreach (AreaPrefab areaPrefab in targets)
		{
			linkedPrefabs.Add(existingSystemManaged.GetEntity(areaPrefab));
		}
	}
```

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		base.GetDependencies(prefabs);
		AreaPrefab[] targets = m_Targets;
		foreach (AreaPrefab item in targets)
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
		components.Add(ComponentType.ReadWrite<AreaTriggerData>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		DynamicBuffer<AreaTriggerData> buffer = entityManager.GetBuffer<AreaTriggerData>(entity);
		PrefabSystem existingSystemManaged = entityManager.World.GetExistingSystemManaged<PrefabSystem>();
		AreaPrefab[] targets = m_Targets;
		foreach (AreaPrefab areaPrefab in targets)
		{
			if (existingSystemManaged.TryGetEntity(areaPrefab, out var entity2))
			{
				buffer.Add(new AreaTriggerData(entity2, m_Flags));
			}
		}
	}
```


