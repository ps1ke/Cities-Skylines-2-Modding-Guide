# Game.Prefabs.WaterPipeParametersPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class WaterPipeParametersPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.PrefabBase m_WaterService;
    public Game.Prefabs.NotificationIconPrefab m_WaterNotification;
    public Game.Prefabs.NotificationIconPrefab m_DirtyWaterNotification;
    public Game.Prefabs.NotificationIconPrefab m_SewageNotification;
    public Game.Prefabs.NotificationIconPrefab m_WaterPipeNotConnectedNotification;
    public Game.Prefabs.NotificationIconPrefab m_SewagePipeNotConnectedNotification;
    public Game.Prefabs.NotificationIconPrefab m_NotEnoughWaterCapacityNotification;
    public Game.Prefabs.NotificationIconPrefab m_NotEnoughSewageCapacityNotification;
    public Game.Prefabs.NotificationIconPrefab m_NotEnoughGroundwaterNotification;
    public Game.Prefabs.NotificationIconPrefab m_NotEnoughSurfaceWaterNotification;
    public Game.Prefabs.NotificationIconPrefab m_DirtyWaterPumpNotification;
    public System.Single m_GroundwaterReplenish;
    public System.Int32 m_GroundwaterPurification;
    public System.Single m_GroundwaterUsageMultiplier;
    public System.Single m_GroundwaterPumpEffectiveAmount;
    public System.Single m_SurfaceWaterUsageMultiplier;
    public System.Single m_SurfaceWaterPumpEffectiveDepth;
    public System.Single m_MaxToleratedPollution;
    public System.Int32 m_WaterPipePollutionSpreadInterval;
    public System.Single m_StaleWaterPipePurification;

    public WaterPipeParametersPrefab();

    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.PrefabBase m_WaterService`  

```csharp
public Game.Prefabs.PrefabBase m_WaterService;
```

- `public Game.Prefabs.NotificationIconPrefab m_WaterNotification`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_WaterNotification;
```

- `public Game.Prefabs.NotificationIconPrefab m_DirtyWaterNotification`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_DirtyWaterNotification;
```

- `public Game.Prefabs.NotificationIconPrefab m_SewageNotification`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_SewageNotification;
```

- `public Game.Prefabs.NotificationIconPrefab m_WaterPipeNotConnectedNotification`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_WaterPipeNotConnectedNotification;
```

- `public Game.Prefabs.NotificationIconPrefab m_SewagePipeNotConnectedNotification`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_SewagePipeNotConnectedNotification;
```

- `public Game.Prefabs.NotificationIconPrefab m_NotEnoughWaterCapacityNotification`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_NotEnoughWaterCapacityNotification;
```

- `public Game.Prefabs.NotificationIconPrefab m_NotEnoughSewageCapacityNotification`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_NotEnoughSewageCapacityNotification;
```

- `public Game.Prefabs.NotificationIconPrefab m_NotEnoughGroundwaterNotification`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_NotEnoughGroundwaterNotification;
```

- `public Game.Prefabs.NotificationIconPrefab m_NotEnoughSurfaceWaterNotification`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_NotEnoughSurfaceWaterNotification;
```

- `public Game.Prefabs.NotificationIconPrefab m_DirtyWaterPumpNotification`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_DirtyWaterPumpNotification;
```

- `public System.Single m_GroundwaterReplenish`  

```csharp
public System.Single m_GroundwaterReplenish;
```

- `public System.Int32 m_GroundwaterPurification`  

```csharp
public System.Int32 m_GroundwaterPurification;
```

- `public System.Single m_GroundwaterUsageMultiplier`  

```csharp
public System.Single m_GroundwaterUsageMultiplier;
```

- `public System.Single m_GroundwaterPumpEffectiveAmount`  

```csharp
public System.Single m_GroundwaterPumpEffectiveAmount;
```

- `public System.Single m_SurfaceWaterUsageMultiplier`  

```csharp
public System.Single m_SurfaceWaterUsageMultiplier;
```

- `public System.Single m_SurfaceWaterPumpEffectiveDepth`  

```csharp
public System.Single m_SurfaceWaterPumpEffectiveDepth;
```

- `public System.Single m_MaxToleratedPollution`  

```csharp
public System.Single m_MaxToleratedPollution;
```

- `public System.Int32 m_WaterPipePollutionSpreadInterval`  

```csharp
public System.Int32 m_WaterPipePollutionSpreadInterval;
```

- `public System.Single m_StaleWaterPipePurification`  

```csharp
public System.Single m_StaleWaterPipePurification;
```


## Constructors

- `public WaterPipeParametersPrefab()`  

```csharp
public WaterPipeParametersPrefab();
```


## Methods

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		base.GetDependencies(prefabs);
		prefabs.Add(m_WaterService);
		prefabs.Add(m_WaterNotification);
		prefabs.Add(m_DirtyWaterNotification);
		prefabs.Add(m_SewageNotification);
		prefabs.Add(m_WaterPipeNotConnectedNotification);
		prefabs.Add(m_SewagePipeNotConnectedNotification);
		prefabs.Add(m_NotEnoughWaterCapacityNotification);
		prefabs.Add(m_NotEnoughSewageCapacityNotification);
		prefabs.Add(m_NotEnoughGroundwaterNotification);
		prefabs.Add(m_NotEnoughSurfaceWaterNotification);
		prefabs.Add(m_DirtyWaterPumpNotification);
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<WaterPipeParameterData>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		PrefabSystem orCreateSystemManaged = entityManager.World.GetOrCreateSystemManaged<PrefabSystem>();
		entityManager.SetComponentData(entity, new WaterPipeParameterData
		{
			m_WaterService = orCreateSystemManaged.GetEntity(m_WaterService),
			m_WaterNotification = orCreateSystemManaged.GetEntity(m_WaterNotification),
			m_DirtyWaterNotification = orCreateSystemManaged.GetEntity(m_DirtyWaterNotification),
			m_SewageNotification = orCreateSystemManaged.GetEntity(m_SewageNotification),
			m_WaterPipeNotConnectedNotification = orCreateSystemManaged.GetEntity(m_WaterPipeNotConnectedNotification),
			m_SewagePipeNotConnectedNotification = orCreateSystemManaged.GetEntity(m_SewagePipeNotConnectedNotification),
			m_NotEnoughWaterCapacityNotification = orCreateSystemManaged.GetEntity(m_NotEnoughWaterCapacityNotification),
			m_NotEnoughSewageCapacityNotification = orCreateSystemManaged.GetEntity(m_NotEnoughSewageCapacityNotification),
			m_NotEnoughGroundwaterNotification = orCreateSystemManaged.GetEntity(m_NotEnoughGroundwaterNotification),
			m_NotEnoughSurfaceWaterNotification = orCreateSystemManaged.GetEntity(m_NotEnoughSurfaceWaterNotification),
			m_DirtyWaterPumpNotification = orCreateSystemManaged.GetEntity(m_DirtyWaterPumpNotification),
			m_GroundwaterReplenish = m_GroundwaterReplenish,
			m_GroundwaterPurification = m_GroundwaterPurification,
			m_GroundwaterUsageMultiplier = m_GroundwaterUsageMultiplier,
			m_GroundwaterPumpEffectiveAmount = m_GroundwaterPumpEffectiveAmount,
			m_SurfaceWaterUsageMultiplier = m_SurfaceWaterUsageMultiplier,
			m_SurfaceWaterPumpEffectiveDepth = m_SurfaceWaterPumpEffectiveDepth,
			m_MaxToleratedPollution = m_MaxToleratedPollution,
			m_WaterPipePollutionSpreadInterval = m_WaterPipePollutionSpreadInterval,
			m_StaleWaterPipePurification = m_StaleWaterPipePurification
		});
	}
```


