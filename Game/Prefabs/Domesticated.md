# Game.Prefabs.Domesticated

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class Domesticated : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Colossal.Mathematics.Bounds1 m_IdleTime;
    public System.Int32 m_MinGroupMemberCount;
    public System.Int32 m_MaxGroupMemberCount;

    public Domesticated();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Colossal.Mathematics.Bounds1 m_IdleTime`  

```csharp
public Colossal.Mathematics.Bounds1 m_IdleTime;
```

- `public System.Int32 m_MinGroupMemberCount`  

```csharp
public System.Int32 m_MinGroupMemberCount;
```

- `public System.Int32 m_MaxGroupMemberCount`  

```csharp
public System.Int32 m_MaxGroupMemberCount;
```


## Constructors

- `public Domesticated()`  

```csharp
public Domesticated();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<Game.Creatures.Domesticated>());
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<DomesticatedData>());
		components.Add(ComponentType.ReadWrite<UpdateFrameData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		DomesticatedData componentData = default(DomesticatedData);
		componentData.m_IdleTime = m_IdleTime;
		componentData.m_GroupMemberCount.x = m_MinGroupMemberCount;
		componentData.m_GroupMemberCount.y = m_MaxGroupMemberCount;
		entityManager.SetComponentData(entity, componentData);
		entityManager.SetComponentData(entity, new UpdateFrameData(9));
	}
```


