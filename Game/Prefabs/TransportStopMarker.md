# Game.Prefabs.TransportStopMarker

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class TransportStopMarker : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.TransportType m_TransportType;
    public System.Boolean m_PassengerTransport;
    public System.Boolean m_CargoTransport;
    public System.Boolean m_WorkStop;
    public System.Boolean m_WorkLocation;

    public TransportStopMarker();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.TransportType m_TransportType`  

```csharp
public Game.Prefabs.TransportType m_TransportType;
```

- `public System.Boolean m_PassengerTransport`  

```csharp
public System.Boolean m_PassengerTransport;
```

- `public System.Boolean m_CargoTransport`  

```csharp
public System.Boolean m_CargoTransport;
```

- `public System.Boolean m_WorkStop`  

```csharp
public System.Boolean m_WorkStop;
```

- `public System.Boolean m_WorkLocation`  

```csharp
public System.Boolean m_WorkLocation;
```


## Constructors

- `public TransportStopMarker()`  

```csharp
public TransportStopMarker();
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
		components.Add(ComponentType.ReadWrite<TransportStopMarkerData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		TransportStopMarkerData componentData = default(TransportStopMarkerData);
		componentData.m_TransportType = m_TransportType;
		if (m_TransportType == TransportType.Work)
		{
			componentData.m_StopTypeA = m_WorkStop;
			componentData.m_StopTypeB = m_WorkLocation;
		}
		else
		{
			componentData.m_StopTypeA = m_PassengerTransport;
			componentData.m_StopTypeB = m_CargoTransport;
		}
		entityManager.SetComponentData(entity, componentData);
	}
```


