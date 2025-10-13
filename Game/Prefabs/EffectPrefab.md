# Game.Prefabs.EffectPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.TransformPrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

## Code

```csharp
public class EffectPrefab : Game.Prefabs.TransformPrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.EffectCondition m_Conditions;
    public System.Boolean m_DisableDistanceCulling;

    public EffectPrefab();

    private Unity.Entities.EntityArchetype GetArchetype(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.EffectCondition m_Conditions`  

```csharp
public Game.Prefabs.EffectCondition m_Conditions;
```

- `public System.Boolean m_DisableDistanceCulling`  

```csharp
public System.Boolean m_DisableDistanceCulling;
```


## Constructors

- `public EffectPrefab()`  

```csharp
public EffectPrefab();
```


## Methods

- `private GetArchetype(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : Unity.Entities.EntityArchetype`  

```csharp
private EntityArchetype GetArchetype(EntityManager entityManager, Entity entity)
	{
		List<ComponentBase> list = new List<ComponentBase>();
		GetComponents(list);
		HashSet<ComponentType> hashSet = new HashSet<ComponentType>();
		for (int i = 0; i < list.Count; i++)
		{
			list[i].GetArchetypeComponents(hashSet);
		}
		hashSet.Add(ComponentType.ReadWrite<Created>());
		hashSet.Add(ComponentType.ReadWrite<Updated>());
		return entityManager.CreateArchetype(PrefabUtils.ToArray(hashSet));
	}
```

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		base.GetArchetypeComponents(components);
		components.Add(ComponentType.ReadWrite<EffectInstance>());
	}
```

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		base.GetDependencies(prefabs);
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<EffectData>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		entityManager.SetComponentData(entity, new EffectData
		{
			m_Archetype = GetArchetype(entityManager, entity),
			m_Flags = new EffectCondition
			{
				m_RequiredFlags = m_Conditions.m_RequiredFlags,
				m_ForbiddenFlags = m_Conditions.m_ForbiddenFlags,
				m_IntensityFlags = m_Conditions.m_IntensityFlags
			},
			m_OwnerCulling = !m_DisableDistanceCulling
		});
	}
```


