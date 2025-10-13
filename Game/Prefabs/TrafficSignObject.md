# Game.Prefabs.TrafficSignObject

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class TrafficSignObject : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.TrafficSignType[] m_SignTypes;
    public System.Int32 m_SpeedLimit;

    public TrafficSignObject();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.TrafficSignType[] m_SignTypes`  

```csharp
public Game.Prefabs.TrafficSignType[] m_SignTypes;
```

- `public System.Int32 m_SpeedLimit`  

```csharp
public System.Int32 m_SpeedLimit;
```


## Constructors

- `public TrafficSignObject()`  

```csharp
public TrafficSignObject();
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
		components.Add(ComponentType.ReadWrite<TrafficSignData>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		TrafficSignData componentData = default(TrafficSignData);
		componentData.m_TypeMask = 0u;
		componentData.m_SpeedLimit = m_SpeedLimit;
		if (m_SignTypes != null)
		{
			for (int i = 0; i < m_SignTypes.Length; i++)
			{
				componentData.m_TypeMask |= TrafficSignData.GetTypeMask(m_SignTypes[i]);
			}
		}
		entityManager.SetComponentData(entity, componentData);
	}
```


