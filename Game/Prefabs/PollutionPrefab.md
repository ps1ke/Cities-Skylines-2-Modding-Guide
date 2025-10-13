# Game.Prefabs.PollutionPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class PollutionPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.Single m_GroundMultiplier;
    public System.Single m_AirMultiplier;
    public System.Single m_NoiseMultiplier;
    public System.Single m_NetAirMultiplier;
    public System.Single m_NetNoiseMultiplier;
    public System.Single m_GroundRadius;
    public System.Single m_AirRadius;
    public System.Single m_NoiseRadius;
    public System.Single m_NetNoiseRadius;
    public System.Single m_WindAdvectionSpeed;
    public System.Int16 m_AirFade;
    public System.Int16 m_GroundFade;
    public System.Single m_PlantAirMultiplier;
    public System.Single m_PlantGroundMultiplier;
    public System.Single m_PlantFade;
    public System.Single m_FertilityGroundMultiplier;
    public System.Single m_DistanceExponent;
    public Game.Prefabs.NotificationIconPrefab m_AirPollutionNotification;
    public Game.Prefabs.NotificationIconPrefab m_NoisePollutionNotification;
    public Game.Prefabs.NotificationIconPrefab m_GroundPollutionNotification;
    public System.Int32 m_AirPollutionNotificationLimit;
    public System.Int32 m_NoisePollutionNotificationLimit;
    public System.Int32 m_GroundPollutionNotificationLimit;
    public System.Single m_AbandonedNoisePollutionMultiplier;
    public System.Int32 m_HomelessNoisePollution;
    public System.Int32 m_GroundPollutionLandValueDivisor;

    public PollutionPrefab();

    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Single m_GroundMultiplier`  

```csharp
public System.Single m_GroundMultiplier;
```

- `public System.Single m_AirMultiplier`  

```csharp
public System.Single m_AirMultiplier;
```

- `public System.Single m_NoiseMultiplier`  

```csharp
public System.Single m_NoiseMultiplier;
```

- `public System.Single m_NetAirMultiplier`  

```csharp
public System.Single m_NetAirMultiplier;
```

- `public System.Single m_NetNoiseMultiplier`  

```csharp
public System.Single m_NetNoiseMultiplier;
```

- `public System.Single m_GroundRadius`  

```csharp
public System.Single m_GroundRadius;
```

- `public System.Single m_AirRadius`  

```csharp
public System.Single m_AirRadius;
```

- `public System.Single m_NoiseRadius`  

```csharp
public System.Single m_NoiseRadius;
```

- `public System.Single m_NetNoiseRadius`  

```csharp
public System.Single m_NetNoiseRadius;
```

- `public System.Single m_WindAdvectionSpeed`  

```csharp
public System.Single m_WindAdvectionSpeed;
```

- `public System.Int16 m_AirFade`  

```csharp
public System.Int16 m_AirFade;
```

- `public System.Int16 m_GroundFade`  

```csharp
public System.Int16 m_GroundFade;
```

- `public System.Single m_PlantAirMultiplier`  

```csharp
public System.Single m_PlantAirMultiplier;
```

- `public System.Single m_PlantGroundMultiplier`  

```csharp
public System.Single m_PlantGroundMultiplier;
```

- `public System.Single m_PlantFade`  

```csharp
public System.Single m_PlantFade;
```

- `public System.Single m_FertilityGroundMultiplier`  

```csharp
public System.Single m_FertilityGroundMultiplier;
```

- `public System.Single m_DistanceExponent`  

```csharp
public System.Single m_DistanceExponent;
```

- `public Game.Prefabs.NotificationIconPrefab m_AirPollutionNotification`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_AirPollutionNotification;
```

- `public Game.Prefabs.NotificationIconPrefab m_NoisePollutionNotification`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_NoisePollutionNotification;
```

- `public Game.Prefabs.NotificationIconPrefab m_GroundPollutionNotification`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_GroundPollutionNotification;
```

- `public System.Int32 m_AirPollutionNotificationLimit`  

```csharp
public System.Int32 m_AirPollutionNotificationLimit;
```

- `public System.Int32 m_NoisePollutionNotificationLimit`  

```csharp
public System.Int32 m_NoisePollutionNotificationLimit;
```

- `public System.Int32 m_GroundPollutionNotificationLimit`  

```csharp
public System.Int32 m_GroundPollutionNotificationLimit;
```

- `public System.Single m_AbandonedNoisePollutionMultiplier`  

```csharp
public System.Single m_AbandonedNoisePollutionMultiplier;
```

- `public System.Int32 m_HomelessNoisePollution`  

```csharp
public System.Int32 m_HomelessNoisePollution;
```

- `public System.Int32 m_GroundPollutionLandValueDivisor`  

```csharp
public System.Int32 m_GroundPollutionLandValueDivisor;
```


## Constructors

- `public PollutionPrefab()`  

```csharp
public PollutionPrefab();
```


## Methods

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<PollutionParameterData>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		PrefabSystem orCreateSystemManaged = World.DefaultGameObjectInjectionWorld.GetOrCreateSystemManaged<PrefabSystem>();
		entityManager.SetComponentData(entity, new PollutionParameterData
		{
			m_GroundMultiplier = m_GroundMultiplier,
			m_AirMultiplier = m_AirMultiplier,
			m_NoiseMultiplier = m_NoiseMultiplier,
			m_NetAirMultiplier = m_NetAirMultiplier,
			m_NetNoiseMultiplier = m_NetNoiseMultiplier,
			m_GroundRadius = m_GroundRadius,
			m_AirRadius = m_AirRadius,
			m_NoiseRadius = m_NoiseRadius,
			m_NetNoiseRadius = m_NetNoiseRadius,
			m_WindAdvectionSpeed = m_WindAdvectionSpeed,
			m_AirFade = m_AirFade,
			m_GroundFade = m_GroundFade,
			m_PlantAirMultiplier = m_PlantAirMultiplier,
			m_PlantGroundMultiplier = m_PlantGroundMultiplier,
			m_PlantFade = m_PlantFade,
			m_FertilityGroundMultiplier = m_FertilityGroundMultiplier,
			m_DistanceExponent = m_DistanceExponent,
			m_AirPollutionNotification = orCreateSystemManaged.GetEntity(m_AirPollutionNotification),
			m_NoisePollutionNotification = orCreateSystemManaged.GetEntity(m_NoisePollutionNotification),
			m_GroundPollutionNotification = orCreateSystemManaged.GetEntity(m_GroundPollutionNotification),
			m_AirPollutionNotificationLimit = m_AirPollutionNotificationLimit,
			m_NoisePollutionNotificationLimit = m_NoisePollutionNotificationLimit,
			m_GroundPollutionNotificationLimit = m_GroundPollutionNotificationLimit,
			m_AbandonedNoisePollutionMultiplier = m_AbandonedNoisePollutionMultiplier,
			m_HomelessNoisePollution = m_HomelessNoisePollution,
			m_GroundPollutionLandValueDivisor = m_GroundPollutionLandValueDivisor
		});
	}
```


