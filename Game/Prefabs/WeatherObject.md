# Game.Prefabs.WeatherObject

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class WeatherObject : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public System.Boolean m_RequireSnow;
    public System.Boolean m_ForbidSnow;

    public WeatherObject();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Boolean m_RequireSnow`  

```csharp
public System.Boolean m_RequireSnow;
```

- `public System.Boolean m_ForbidSnow`  

```csharp
public System.Boolean m_ForbidSnow;
```


## Constructors

- `public WeatherObject()`  

```csharp
public WeatherObject();
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
		if (m_RequireSnow)
		{
			objectRequirementFlags |= ObjectRequirementFlags.Snow;
		}
		if (m_ForbidSnow)
		{
			objectRequirementFlags2 |= ObjectRequirementFlags.Snow;
		}
		buffer.Add(new ObjectRequirementElement(objectRequirementFlags, objectRequirementFlags2, length));
	}
```


