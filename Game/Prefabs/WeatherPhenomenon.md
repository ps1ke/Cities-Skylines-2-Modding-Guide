# Game.Prefabs.WeatherPhenomenon

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class WeatherPhenomenon : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public System.Single m_OccurrenceProbability;
    public Colossal.Mathematics.Bounds1 m_OccurenceTemperature;
    public Colossal.Mathematics.Bounds1 m_OccurenceRain;
    public Colossal.Mathematics.Bounds1 m_Duration;
    public Colossal.Mathematics.Bounds1 m_PhenomenonRadius;
    public Colossal.Mathematics.Bounds1 m_HotspotRadius;
    public Colossal.Mathematics.Bounds1 m_LightningInterval;
    public System.Single m_HotspotInstability;
    public System.Single m_DamageSeverity;
    public System.Single m_DangerLevel;
    public System.Boolean m_Evacuate;
    public System.Boolean m_StayIndoors;

    public WeatherPhenomenon();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Single m_OccurrenceProbability`  

```csharp
public System.Single m_OccurrenceProbability;
```

- `public Colossal.Mathematics.Bounds1 m_OccurenceTemperature`  

```csharp
public Colossal.Mathematics.Bounds1 m_OccurenceTemperature;
```

- `public Colossal.Mathematics.Bounds1 m_OccurenceRain`  

```csharp
public Colossal.Mathematics.Bounds1 m_OccurenceRain;
```

- `public Colossal.Mathematics.Bounds1 m_Duration`  

```csharp
public Colossal.Mathematics.Bounds1 m_Duration;
```

- `public Colossal.Mathematics.Bounds1 m_PhenomenonRadius`  

```csharp
public Colossal.Mathematics.Bounds1 m_PhenomenonRadius;
```

- `public Colossal.Mathematics.Bounds1 m_HotspotRadius`  

```csharp
public Colossal.Mathematics.Bounds1 m_HotspotRadius;
```

- `public Colossal.Mathematics.Bounds1 m_LightningInterval`  

```csharp
public Colossal.Mathematics.Bounds1 m_LightningInterval;
```

- `public System.Single m_HotspotInstability`  

```csharp
public System.Single m_HotspotInstability;
```

- `public System.Single m_DamageSeverity`  

```csharp
public System.Single m_DamageSeverity;
```

- `public System.Single m_DangerLevel`  

```csharp
public System.Single m_DangerLevel;
```

- `public System.Boolean m_Evacuate`  

```csharp
public System.Boolean m_Evacuate;
```

- `public System.Boolean m_StayIndoors`  

```csharp
public System.Boolean m_StayIndoors;
```


## Constructors

- `public WeatherPhenomenon()`  

```csharp
public WeatherPhenomenon();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<Game.Events.WeatherPhenomenon>());
		components.Add(ComponentType.ReadWrite<HotspotFrame>());
		components.Add(ComponentType.ReadWrite<Duration>());
		components.Add(ComponentType.ReadWrite<DangerLevel>());
		components.Add(ComponentType.ReadWrite<TargetElement>());
		components.Add(ComponentType.ReadWrite<InterpolatedTransform>());
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<WeatherPhenomenonData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		WeatherPhenomenonData componentData = default(WeatherPhenomenonData);
		componentData.m_OccurenceProbability = m_OccurrenceProbability;
		componentData.m_HotspotInstability = m_HotspotInstability;
		componentData.m_DamageSeverity = m_DamageSeverity;
		componentData.m_DangerLevel = m_DangerLevel;
		componentData.m_PhenomenonRadius = m_PhenomenonRadius;
		componentData.m_HotspotRadius = m_HotspotRadius;
		componentData.m_LightningInterval = m_LightningInterval;
		componentData.m_Duration = m_Duration;
		componentData.m_OccurenceTemperature = m_OccurenceTemperature;
		componentData.m_OccurenceRain = m_OccurenceRain;
		componentData.m_DangerFlags = (DangerFlags)0u;
		if (m_Evacuate)
		{
			componentData.m_DangerFlags = DangerFlags.Evacuate;
		}
		if (m_StayIndoors)
		{
			componentData.m_DangerFlags = DangerFlags.StayIndoors;
		}
		entityManager.SetComponentData(entity, componentData);
	}
```


