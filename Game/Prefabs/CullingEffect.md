# Game.Prefabs.CullingEffect

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class CullingEffect : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.CullingEffect+AudioCullingGroup m_AudioCullGroup;

    public CullingEffect();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.CullingEffect+AudioCullingGroup m_AudioCullGroup`  

```csharp
public Game.Prefabs.CullingEffect+AudioCullingGroup m_AudioCullGroup;
```


## Constructors

- `public CullingEffect()`  

```csharp
public CullingEffect();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		if (m_AudioCullGroup != AudioCullingGroup.None)
		{
			components.Add(ComponentType.ReadWrite<CullingGroupData>());
		}
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		if (m_AudioCullGroup != AudioCullingGroup.None)
		{
			CullingGroupData componentData = new CullingGroupData
			{
				m_GroupIndex = (int)m_AudioCullGroup
			};
			entityManager.SetComponentData(entity, componentData);
		}
	}
```


## Nested types

- `Game.Prefabs.CullingEffect+AudioCullingGroup`  

