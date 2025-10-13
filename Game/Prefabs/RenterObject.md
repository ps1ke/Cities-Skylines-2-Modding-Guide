# Game.Prefabs.RenterObject

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class RenterObject : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public System.Boolean m_RequireEmpty;
    public System.Boolean m_RequireRenter;
    public System.Boolean m_RequireGoodWealth;
    public System.Boolean m_RequireDogs;
    public System.Boolean m_RequireHomeless;
    public System.Boolean m_RequireChildren;
    public System.Boolean m_RequireTeens;

    public RenterObject();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Boolean m_RequireEmpty`  

```csharp
public System.Boolean m_RequireEmpty;
```

- `public System.Boolean m_RequireRenter`  

```csharp
public System.Boolean m_RequireRenter;
```

- `public System.Boolean m_RequireGoodWealth`  

```csharp
public System.Boolean m_RequireGoodWealth;
```

- `public System.Boolean m_RequireDogs`  

```csharp
public System.Boolean m_RequireDogs;
```

- `public System.Boolean m_RequireHomeless`  

```csharp
public System.Boolean m_RequireHomeless;
```

- `public System.Boolean m_RequireChildren`  

```csharp
public System.Boolean m_RequireChildren;
```

- `public System.Boolean m_RequireTeens`  

```csharp
public System.Boolean m_RequireTeens;
```


## Constructors

- `public RenterObject()`  

```csharp
public RenterObject();
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
		components.Add(ComponentType.ReadWrite<ObjectRequirementElement>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		DynamicBuffer<ObjectRequirementElement> buffer = entityManager.GetBuffer<ObjectRequirementElement>(entity);
		int length = buffer.Length;
		ObjectRequirementFlags objectRequirementFlags = (ObjectRequirementFlags)0;
		ObjectRequirementFlags objectRequirementFlags2 = (ObjectRequirementFlags)0;
		if (m_RequireEmpty)
		{
			objectRequirementFlags2 |= ObjectRequirementFlags.Renter;
		}
		if (m_RequireRenter)
		{
			objectRequirementFlags |= ObjectRequirementFlags.Renter;
		}
		if (m_RequireGoodWealth)
		{
			objectRequirementFlags |= ObjectRequirementFlags.GoodWealth;
		}
		if (m_RequireDogs)
		{
			objectRequirementFlags |= ObjectRequirementFlags.Dogs;
		}
		if (m_RequireHomeless)
		{
			objectRequirementFlags |= ObjectRequirementFlags.Homeless;
		}
		if (!m_RequireChildren && !m_RequireTeens)
		{
			buffer.Add(new ObjectRequirementElement(objectRequirementFlags, objectRequirementFlags2, length));
		}
		if (m_RequireChildren)
		{
			buffer.Add(new ObjectRequirementElement(objectRequirementFlags | ObjectRequirementFlags.Children, objectRequirementFlags2, length));
		}
		if (m_RequireTeens)
		{
			buffer.Add(new ObjectRequirementElement(objectRequirementFlags | ObjectRequirementFlags.Teens, objectRequirementFlags2, length));
		}
	}
```


