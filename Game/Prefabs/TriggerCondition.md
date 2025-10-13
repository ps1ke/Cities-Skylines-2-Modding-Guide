# Game.Prefabs.TriggerCondition

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class TriggerCondition : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.TriggerConditionData[] m_Conditions;

    public TriggerCondition();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.TriggerConditionData[] m_Conditions`  

```csharp
public Game.Prefabs.TriggerConditionData[] m_Conditions;
```


## Constructors

- `public TriggerCondition()`  

```csharp
public TriggerCondition();
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
		if (m_Conditions != null && m_Conditions.Length != 0)
		{
			components.Add(ComponentType.ReadWrite<TriggerConditionData>());
		}
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		if (m_Conditions != null && m_Conditions.Length != 0)
		{
			DynamicBuffer<TriggerConditionData> buffer = entityManager.GetBuffer<TriggerConditionData>(entity);
			for (int i = 0; i < m_Conditions.Length; i++)
			{
				buffer.Add(m_Conditions[i]);
			}
		}
	}
```


