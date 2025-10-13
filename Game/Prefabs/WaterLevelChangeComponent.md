# Game.Prefabs.WaterLevelChangeComponent

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class WaterLevelChangeComponent : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.WaterLevelTargetType m_TargetType;
    public Game.Prefabs.WaterLevelChangeType m_ChangeType;
    public System.Single m_EscalationDelay;
    public System.Boolean m_Evacuate;
    public System.Boolean m_StayIndoors;
    public System.Single m_DangerLevel;

    public WaterLevelChangeComponent();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.WaterLevelTargetType m_TargetType`  

```csharp
public Game.Prefabs.WaterLevelTargetType m_TargetType;
```

- `public Game.Prefabs.WaterLevelChangeType m_ChangeType`  

```csharp
public Game.Prefabs.WaterLevelChangeType m_ChangeType;
```

- `public System.Single m_EscalationDelay`  

```csharp
public System.Single m_EscalationDelay;
```

- `public System.Boolean m_Evacuate`  

```csharp
public System.Boolean m_Evacuate;
```

- `public System.Boolean m_StayIndoors`  

```csharp
public System.Boolean m_StayIndoors;
```

- `public System.Single m_DangerLevel`  

```csharp
public System.Single m_DangerLevel;
```


## Constructors

- `public WaterLevelChangeComponent()`  

```csharp
public WaterLevelChangeComponent();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<WaterLevelChange>());
		components.Add(ComponentType.ReadWrite<Duration>());
		components.Add(ComponentType.ReadWrite<DangerLevel>());
		components.Add(ComponentType.ReadWrite<TargetElement>());
		if (m_ChangeType == WaterLevelChangeType.RainControlled)
		{
			components.Add(ComponentType.ReadWrite<Flood>());
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<WaterLevelChangeData>());
		if (m_ChangeType == WaterLevelChangeType.RainControlled)
		{
			components.Add(ComponentType.ReadWrite<FloodData>());
		}
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		WaterLevelChangeData componentData = default(WaterLevelChangeData);
		componentData.m_TargetType = m_TargetType;
		componentData.m_ChangeType = m_ChangeType;
		componentData.m_EscalationDelay = m_EscalationDelay;
		componentData.m_DangerFlags = (DangerFlags)0u;
		if (m_Evacuate)
		{
			componentData.m_DangerFlags = DangerFlags.Evacuate;
		}
		if (m_StayIndoors)
		{
			componentData.m_DangerFlags = DangerFlags.StayIndoors;
		}
		componentData.m_DangerLevel = m_DangerLevel;
		entityManager.SetComponentData(entity, componentData);
	}
```


