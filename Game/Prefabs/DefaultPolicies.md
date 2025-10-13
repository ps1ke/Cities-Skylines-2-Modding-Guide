# Game.Prefabs.DefaultPolicies

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class DefaultPolicies : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.DefaultPolicyInfo[] m_Policies;

    public DefaultPolicies();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.DefaultPolicyInfo[] m_Policies`  

```csharp
public Game.Prefabs.DefaultPolicyInfo[] m_Policies;
```


## Constructors

- `public DefaultPolicies()`  

```csharp
public DefaultPolicies();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		if (!components.Contains(ComponentType.ReadWrite<Waypoint>()) && !components.Contains(ComponentType.ReadWrite<Segment>()))
		{
			components.Add(ComponentType.ReadWrite<Policy>());
		}
	}
```

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		base.GetDependencies(prefabs);
		if (m_Policies != null)
		{
			for (int i = 0; i < m_Policies.Length; i++)
			{
				prefabs.Add(m_Policies[i].m_Policy);
			}
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<DefaultPolicyData>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		if (m_Policies != null)
		{
			PrefabSystem existingSystemManaged = entityManager.World.GetExistingSystemManaged<PrefabSystem>();
			DynamicBuffer<DefaultPolicyData> buffer = entityManager.GetBuffer<DefaultPolicyData>(entity);
			for (int i = 0; i < m_Policies.Length; i++)
			{
				DefaultPolicyInfo defaultPolicyInfo = m_Policies[i];
				buffer.Add(new DefaultPolicyData(existingSystemManaged.GetEntity(defaultPolicyInfo.m_Policy)));
			}
		}
	}
```


