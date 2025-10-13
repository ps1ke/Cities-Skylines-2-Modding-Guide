# Game.Prefabs.TrafficLightObject

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class TrafficLightObject : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public System.Boolean m_VehicleLeft;
    public System.Boolean m_VehicleRight;
    public System.Boolean m_CrossingLeft;
    public System.Boolean m_CrossingRight;
    public System.Boolean m_AllowFlipped;
    public Colossal.Mathematics.Bounds1 m_ReachOffset;

    public TrafficLightObject();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Boolean m_VehicleLeft`  

```csharp
public System.Boolean m_VehicleLeft;
```

- `public System.Boolean m_VehicleRight`  

```csharp
public System.Boolean m_VehicleRight;
```

- `public System.Boolean m_CrossingLeft`  

```csharp
public System.Boolean m_CrossingLeft;
```

- `public System.Boolean m_CrossingRight`  

```csharp
public System.Boolean m_CrossingRight;
```

- `public System.Boolean m_AllowFlipped`  

```csharp
public System.Boolean m_AllowFlipped;
```

- `public Colossal.Mathematics.Bounds1 m_ReachOffset`  

```csharp
public Colossal.Mathematics.Bounds1 m_ReachOffset;
```


## Constructors

- `public TrafficLightObject()`  

```csharp
public TrafficLightObject();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<TrafficLight>());
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<TrafficLightData>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		TrafficLightData componentData = default(TrafficLightData);
		componentData.m_Type = (TrafficLightType)0;
		componentData.m_ReachOffset = m_ReachOffset;
		if (m_VehicleLeft)
		{
			componentData.m_Type |= TrafficLightType.VehicleLeft;
		}
		if (m_VehicleRight)
		{
			componentData.m_Type |= TrafficLightType.VehicleRight;
		}
		if (m_CrossingLeft)
		{
			componentData.m_Type |= TrafficLightType.CrossingLeft;
		}
		if (m_CrossingRight)
		{
			componentData.m_Type |= TrafficLightType.CrossingRight;
		}
		if (m_AllowFlipped)
		{
			componentData.m_Type |= TrafficLightType.AllowFlipped;
		}
		entityManager.SetComponentData(entity, componentData);
	}
```


