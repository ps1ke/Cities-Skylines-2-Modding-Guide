# Game.Prefabs.TutorialObjectPlacementTriggerPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.TutorialTriggerPrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class TutorialObjectPlacementTriggerPrefab : Game.Prefabs.TutorialTriggerPrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.TutorialObjectPlacementTriggerPrefab+ObjectPlacementTarget[] m_Targets;
    public System.Int32 m_RequiredCount;

    public TutorialObjectPlacementTriggerPrefab();

    protected virtual System.Void GenerateBlinkTags();
    public virtual System.Void GenerateTutorialLinks(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> linkedPrefabs);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.TutorialObjectPlacementTriggerPrefab+ObjectPlacementTarget[] m_Targets`  

```csharp
public Game.Prefabs.TutorialObjectPlacementTriggerPrefab+ObjectPlacementTarget[] m_Targets;
```

- `public System.Int32 m_RequiredCount`  

```csharp
public System.Int32 m_RequiredCount;
```


## Constructors

- `public TutorialObjectPlacementTriggerPrefab()`  

```csharp
public TutorialObjectPlacementTriggerPrefab();
```


## Methods

- `protected virtual GenerateBlinkTags() : System.Void`  

```csharp
protected override void GenerateBlinkTags()
	{
		base.GenerateBlinkTags();
		ObjectPlacementTarget[] targets = m_Targets;
		foreach (ObjectPlacementTarget objectPlacementTarget in targets)
		{
			if (objectPlacementTarget.m_Target.TryGet<UIObject>(out var component) && component.m_Group is UIAssetCategoryPrefab uIAssetCategoryPrefab && uIAssetCategoryPrefab.m_Menu != null)
			{
				AddBlinkTagAtPosition(objectPlacementTarget.m_Target.uiTag, 0);
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
		for (int i = 0; i < m_Targets.Length; i++)
		{
			linkedPrefabs.Add(existingSystemManaged.GetEntity(m_Targets[i].m_Target));
		}
	}
```

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		base.GetDependencies(prefabs);
		ObjectPlacementTarget[] targets = m_Targets;
		foreach (ObjectPlacementTarget objectPlacementTarget in targets)
		{
			prefabs.Add(objectPlacementTarget.m_Target);
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<ObjectPlacementTriggerData>());
		components.Add(ComponentType.ReadWrite<ObjectPlacementTriggerCountData>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		DynamicBuffer<ObjectPlacementTriggerData> buffer = entityManager.GetBuffer<ObjectPlacementTriggerData>(entity);
		PrefabSystem existingSystemManaged = entityManager.World.GetExistingSystemManaged<PrefabSystem>();
		ObjectPlacementTarget[] targets = m_Targets;
		foreach (ObjectPlacementTarget objectPlacementTarget in targets)
		{
			if (existingSystemManaged.TryGetEntity(objectPlacementTarget.m_Target, out var entity2))
			{
				buffer.Add(new ObjectPlacementTriggerData(entity2, objectPlacementTarget.m_Flags));
			}
		}
		entityManager.SetComponentData(entity, new ObjectPlacementTriggerCountData(math.max(m_RequiredCount, 1)));
	}
```


## Nested types

- `Game.Prefabs.TutorialObjectPlacementTriggerPrefab+ObjectPlacementTarget`  

