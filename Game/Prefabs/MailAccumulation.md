# Game.Prefabs.MailAccumulation

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class MailAccumulation : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public System.Boolean m_RequireCollect;
    public System.Single m_SendingRate;
    public System.Single m_ReceivingRate;

    public MailAccumulation();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Boolean m_RequireCollect`  

```csharp
public System.Boolean m_RequireCollect;
```

- `public System.Single m_SendingRate`  

```csharp
public System.Single m_SendingRate;
```

- `public System.Single m_ReceivingRate`  

```csharp
public System.Single m_ReceivingRate;
```


## Constructors

- `public MailAccumulation()`  

```csharp
public MailAccumulation();
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
		components.Add(ComponentType.ReadWrite<MailAccumulationData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		MailAccumulationData componentData = default(MailAccumulationData);
		componentData.m_RequireCollect = m_RequireCollect;
		componentData.m_AccumulationRate.x = m_SendingRate;
		componentData.m_AccumulationRate.y = m_ReceivingRate;
		entityManager.SetComponentData(entity, componentData);
	}
```


