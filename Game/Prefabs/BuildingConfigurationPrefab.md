# Game.Prefabs.BuildingConfigurationPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class BuildingConfigurationPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.Int32 m_BuildingConditionIncrement;
    public System.Int32 m_BuildingConditionDecrement;
    public Game.Prefabs.NotificationIconPrefab m_AbandonedCollapsedNotification;
    public Game.Prefabs.NotificationIconPrefab m_AbandonedNotification;
    public Game.Prefabs.NotificationIconPrefab m_CondemnedNotification;
    public Game.Prefabs.NotificationIconPrefab m_LevelUpNotification;
    public Game.Prefabs.NotificationIconPrefab m_TurnedOffNotification;
    public Game.Prefabs.NetLanePrefab m_ElectricityConnectionLane;
    public Game.Prefabs.NetLanePrefab m_SewageConnectionLane;
    public Game.Prefabs.NetLanePrefab m_WaterConnectionLane;
    public System.UInt32 m_AbandonedDestroyDelay;
    public Game.Prefabs.NotificationIconPrefab m_HighRentNotification;
    public Game.Prefabs.BrandPrefab m_DefaultRenterBrand;
    public Game.Prefabs.AreaPrefab m_ConstructionSurface;
    public Game.Prefabs.NetLanePrefab m_ConstructionBorder;
    public Game.Prefabs.ObjectPrefab m_ConstructionObject;
    public Game.Prefabs.ObjectPrefab m_CollapsedObject;
    public Game.Prefabs.EffectPrefab m_CollapseVFX;
    public Game.Prefabs.EffectPrefab m_CollapseSFX;
    public System.Single m_CollapseSFXDensity;
    public Game.Prefabs.AreaPrefab m_CollapsedSurface;
    public Game.Prefabs.EffectPrefab m_FireLoopSFX;
    public Game.Prefabs.EffectPrefab m_FireSpotSFX;

    public BuildingConfigurationPrefab();

    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Int32 m_BuildingConditionIncrement`  

```csharp
public System.Int32 m_BuildingConditionIncrement;
```

- `public System.Int32 m_BuildingConditionDecrement`  

```csharp
public System.Int32 m_BuildingConditionDecrement;
```

- `public Game.Prefabs.NotificationIconPrefab m_AbandonedCollapsedNotification`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_AbandonedCollapsedNotification;
```

- `public Game.Prefabs.NotificationIconPrefab m_AbandonedNotification`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_AbandonedNotification;
```

- `public Game.Prefabs.NotificationIconPrefab m_CondemnedNotification`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_CondemnedNotification;
```

- `public Game.Prefabs.NotificationIconPrefab m_LevelUpNotification`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_LevelUpNotification;
```

- `public Game.Prefabs.NotificationIconPrefab m_TurnedOffNotification`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_TurnedOffNotification;
```

- `public Game.Prefabs.NetLanePrefab m_ElectricityConnectionLane`  

```csharp
public Game.Prefabs.NetLanePrefab m_ElectricityConnectionLane;
```

- `public Game.Prefabs.NetLanePrefab m_SewageConnectionLane`  

```csharp
public Game.Prefabs.NetLanePrefab m_SewageConnectionLane;
```

- `public Game.Prefabs.NetLanePrefab m_WaterConnectionLane`  

```csharp
public Game.Prefabs.NetLanePrefab m_WaterConnectionLane;
```

- `public System.UInt32 m_AbandonedDestroyDelay`  

```csharp
public System.UInt32 m_AbandonedDestroyDelay;
```

- `public Game.Prefabs.NotificationIconPrefab m_HighRentNotification`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_HighRentNotification;
```

- `public Game.Prefabs.BrandPrefab m_DefaultRenterBrand`  

```csharp
public Game.Prefabs.BrandPrefab m_DefaultRenterBrand;
```

- `public Game.Prefabs.AreaPrefab m_ConstructionSurface`  

```csharp
public Game.Prefabs.AreaPrefab m_ConstructionSurface;
```

- `public Game.Prefabs.NetLanePrefab m_ConstructionBorder`  

```csharp
public Game.Prefabs.NetLanePrefab m_ConstructionBorder;
```

- `public Game.Prefabs.ObjectPrefab m_ConstructionObject`  

```csharp
public Game.Prefabs.ObjectPrefab m_ConstructionObject;
```

- `public Game.Prefabs.ObjectPrefab m_CollapsedObject`  

```csharp
public Game.Prefabs.ObjectPrefab m_CollapsedObject;
```

- `public Game.Prefabs.EffectPrefab m_CollapseVFX`  

```csharp
public Game.Prefabs.EffectPrefab m_CollapseVFX;
```

- `public Game.Prefabs.EffectPrefab m_CollapseSFX`  

```csharp
public Game.Prefabs.EffectPrefab m_CollapseSFX;
```

- `public System.Single m_CollapseSFXDensity`  

```csharp
public System.Single m_CollapseSFXDensity;
```

- `public Game.Prefabs.AreaPrefab m_CollapsedSurface`  

```csharp
public Game.Prefabs.AreaPrefab m_CollapsedSurface;
```

- `public Game.Prefabs.EffectPrefab m_FireLoopSFX`  

```csharp
public Game.Prefabs.EffectPrefab m_FireLoopSFX;
```

- `public Game.Prefabs.EffectPrefab m_FireSpotSFX`  

```csharp
public Game.Prefabs.EffectPrefab m_FireSpotSFX;
```


## Constructors

- `public BuildingConfigurationPrefab()`  

```csharp
public BuildingConfigurationPrefab();
```


## Methods

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		base.GetDependencies(prefabs);
		prefabs.Add(m_AbandonedCollapsedNotification);
		prefabs.Add(m_AbandonedNotification);
		prefabs.Add(m_CondemnedNotification);
		prefabs.Add(m_LevelUpNotification);
		prefabs.Add(m_TurnedOffNotification);
		prefabs.Add(m_ElectricityConnectionLane);
		prefabs.Add(m_SewageConnectionLane);
		prefabs.Add(m_WaterConnectionLane);
		prefabs.Add(m_HighRentNotification);
		prefabs.Add(m_DefaultRenterBrand);
		prefabs.Add(m_ConstructionSurface);
		prefabs.Add(m_ConstructionBorder);
		prefabs.Add(m_ConstructionObject);
		prefabs.Add(m_CollapsedObject);
		prefabs.Add(m_CollapseVFX);
		prefabs.Add(m_CollapseSFX);
		prefabs.Add(m_CollapsedSurface);
		prefabs.Add(m_FireLoopSFX);
		prefabs.Add(m_FireSpotSFX);
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<BuildingConfigurationData>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		PrefabSystem orCreateSystemManaged = entityManager.World.GetOrCreateSystemManaged<PrefabSystem>();
		entityManager.SetComponentData(entity, new BuildingConfigurationData
		{
			m_BuildingConditionIncrement = m_BuildingConditionIncrement,
			m_BuildingConditionDecrement = m_BuildingConditionDecrement,
			m_AbandonedCollapsedNotification = orCreateSystemManaged.GetEntity(m_AbandonedCollapsedNotification),
			m_AbandonedNotification = orCreateSystemManaged.GetEntity(m_AbandonedNotification),
			m_CondemnedNotification = orCreateSystemManaged.GetEntity(m_CondemnedNotification),
			m_LevelUpNotification = orCreateSystemManaged.GetEntity(m_LevelUpNotification),
			m_TurnedOffNotification = orCreateSystemManaged.GetEntity(m_TurnedOffNotification),
			m_ElectricityConnectionLane = orCreateSystemManaged.GetEntity(m_ElectricityConnectionLane),
			m_SewageConnectionLane = orCreateSystemManaged.GetEntity(m_SewageConnectionLane),
			m_WaterConnectionLane = orCreateSystemManaged.GetEntity(m_WaterConnectionLane),
			m_AbandonedDestroyDelay = m_AbandonedDestroyDelay,
			m_HighRentNotification = orCreateSystemManaged.GetEntity(m_HighRentNotification),
			m_DefaultRenterBrand = orCreateSystemManaged.GetEntity(m_DefaultRenterBrand),
			m_ConstructionSurface = orCreateSystemManaged.GetEntity(m_ConstructionSurface),
			m_ConstructionBorder = orCreateSystemManaged.GetEntity(m_ConstructionBorder),
			m_ConstructionObject = orCreateSystemManaged.GetEntity(m_ConstructionObject),
			m_CollapsedObject = orCreateSystemManaged.GetEntity(m_CollapsedObject),
			m_CollapseVFX = orCreateSystemManaged.GetEntity(m_CollapseVFX),
			m_CollapseSFX = orCreateSystemManaged.GetEntity(m_CollapseSFX),
			m_CollapseSFXDensity = m_CollapseSFXDensity,
			m_CollapsedSurface = orCreateSystemManaged.GetEntity(m_CollapsedSurface),
			m_FireLoopSFX = orCreateSystemManaged.GetEntity(m_FireLoopSFX),
			m_FireSpotSFX = orCreateSystemManaged.GetEntity(m_FireSpotSFX)
		});
	}
```


