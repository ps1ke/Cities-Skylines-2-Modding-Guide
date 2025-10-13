# Game.Prefabs.FireConfigurationPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class FireConfigurationPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.NotificationIconPrefab m_FireNotificationPrefab;
    public Game.Prefabs.NotificationIconPrefab m_BurnedDownNotificationPrefab;
    public System.Single m_DefaultStructuralIntegrity;
    public System.Single m_BuildingStructuralIntegrity;
    public System.Single m_StructuralIntegrityLevel1;
    public System.Single m_StructuralIntegrityLevel2;
    public System.Single m_StructuralIntegrityLevel3;
    public System.Single m_StructuralIntegrityLevel4;
    public System.Single m_StructuralIntegrityLevel5;
    public Colossal.Mathematics.Bounds1 m_ResponseTimeRange;
    public System.Single m_TelecomResponseTimeModifier;
    public System.Single m_DarknessResponseTimeModifier;
    public UnityEngine.AnimationCurve m_TemperatureForestFireHazard;
    public UnityEngine.AnimationCurve m_NoRainForestFireHazard;
    public System.Single m_DeathRateOfFireAccident;

    public FireConfigurationPrefab();

    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.NotificationIconPrefab m_FireNotificationPrefab`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_FireNotificationPrefab;
```

- `public Game.Prefabs.NotificationIconPrefab m_BurnedDownNotificationPrefab`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_BurnedDownNotificationPrefab;
```

- `public System.Single m_DefaultStructuralIntegrity`  

```csharp
public System.Single m_DefaultStructuralIntegrity;
```

- `public System.Single m_BuildingStructuralIntegrity`  

```csharp
public System.Single m_BuildingStructuralIntegrity;
```

- `public System.Single m_StructuralIntegrityLevel1`  

```csharp
public System.Single m_StructuralIntegrityLevel1;
```

- `public System.Single m_StructuralIntegrityLevel2`  

```csharp
public System.Single m_StructuralIntegrityLevel2;
```

- `public System.Single m_StructuralIntegrityLevel3`  

```csharp
public System.Single m_StructuralIntegrityLevel3;
```

- `public System.Single m_StructuralIntegrityLevel4`  

```csharp
public System.Single m_StructuralIntegrityLevel4;
```

- `public System.Single m_StructuralIntegrityLevel5`  

```csharp
public System.Single m_StructuralIntegrityLevel5;
```

- `public Colossal.Mathematics.Bounds1 m_ResponseTimeRange`  

```csharp
public Colossal.Mathematics.Bounds1 m_ResponseTimeRange;
```

- `public System.Single m_TelecomResponseTimeModifier`  

```csharp
public System.Single m_TelecomResponseTimeModifier;
```

- `public System.Single m_DarknessResponseTimeModifier`  

```csharp
public System.Single m_DarknessResponseTimeModifier;
```

- `public UnityEngine.AnimationCurve m_TemperatureForestFireHazard`  

```csharp
public UnityEngine.AnimationCurve m_TemperatureForestFireHazard;
```

- `public UnityEngine.AnimationCurve m_NoRainForestFireHazard`  

```csharp
public UnityEngine.AnimationCurve m_NoRainForestFireHazard;
```

- `public System.Single m_DeathRateOfFireAccident`  

```csharp
public System.Single m_DeathRateOfFireAccident;
```


## Constructors

- `public FireConfigurationPrefab()`  

```csharp
public FireConfigurationPrefab();
```


## Methods

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		base.GetDependencies(prefabs);
		prefabs.Add(m_FireNotificationPrefab);
		prefabs.Add(m_BurnedDownNotificationPrefab);
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<FireConfigurationData>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		PrefabSystem existingSystemManaged = entityManager.World.GetExistingSystemManaged<PrefabSystem>();
		FireConfigurationData componentData = default(FireConfigurationData);
		componentData.m_FireNotificationPrefab = existingSystemManaged.GetEntity(m_FireNotificationPrefab);
		componentData.m_BurnedDownNotificationPrefab = existingSystemManaged.GetEntity(m_BurnedDownNotificationPrefab);
		componentData.m_DefaultStructuralIntegrity = m_DefaultStructuralIntegrity;
		componentData.m_BuildingStructuralIntegrity = m_BuildingStructuralIntegrity;
		componentData.m_StructuralIntegrityLevel1 = m_StructuralIntegrityLevel1;
		componentData.m_StructuralIntegrityLevel2 = m_StructuralIntegrityLevel2;
		componentData.m_StructuralIntegrityLevel3 = m_StructuralIntegrityLevel3;
		componentData.m_StructuralIntegrityLevel4 = m_StructuralIntegrityLevel4;
		componentData.m_StructuralIntegrityLevel5 = m_StructuralIntegrityLevel5;
		componentData.m_ResponseTimeRange = m_ResponseTimeRange;
		componentData.m_TelecomResponseTimeModifier = m_TelecomResponseTimeModifier;
		componentData.m_DarknessResponseTimeModifier = m_DarknessResponseTimeModifier;
		componentData.m_DeathRateOfFireAccident = m_DeathRateOfFireAccident;
		entityManager.SetComponentData(entity, componentData);
	}
```


