# Game.Prefabs.PoliceConfigurationPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class PoliceConfigurationPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.PrefabBase m_PoliceServicePrefab;
    public Game.Prefabs.NotificationIconPrefab m_TrafficAccidentNotificationPrefab;
    public Game.Prefabs.NotificationIconPrefab m_CrimeSceneNotificationPrefab;
    public System.Single m_MaxCrimeAccumulation;
    public System.Single m_CrimeAccumulationTolerance;
    public System.Int32 m_HomeCrimeEffect;
    public System.Int32 m_WorkplaceCrimeEffect;
    public System.Single m_WelfareCrimeRecurrenceFactor;
    public System.Single m_CrimePoliceCoverageFactor;
    public System.Single m_CrimePopulationReduction;

    public System.Boolean ignoreUnlockDependencies { get; }

    public PoliceConfigurationPrefab();

    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.PrefabBase m_PoliceServicePrefab`  

```csharp
public Game.Prefabs.PrefabBase m_PoliceServicePrefab;
```

- `public Game.Prefabs.NotificationIconPrefab m_TrafficAccidentNotificationPrefab`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_TrafficAccidentNotificationPrefab;
```

- `public Game.Prefabs.NotificationIconPrefab m_CrimeSceneNotificationPrefab`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_CrimeSceneNotificationPrefab;
```

- `public System.Single m_MaxCrimeAccumulation`  

```csharp
public System.Single m_MaxCrimeAccumulation;
```

- `public System.Single m_CrimeAccumulationTolerance`  

```csharp
public System.Single m_CrimeAccumulationTolerance;
```

- `public System.Int32 m_HomeCrimeEffect`  

```csharp
public System.Int32 m_HomeCrimeEffect;
```

- `public System.Int32 m_WorkplaceCrimeEffect`  

```csharp
public System.Int32 m_WorkplaceCrimeEffect;
```

- `public System.Single m_WelfareCrimeRecurrenceFactor`  

```csharp
public System.Single m_WelfareCrimeRecurrenceFactor;
```

- `public System.Single m_CrimePoliceCoverageFactor`  

```csharp
public System.Single m_CrimePoliceCoverageFactor;
```

- `public System.Single m_CrimePopulationReduction`  

```csharp
public System.Single m_CrimePopulationReduction;
```


## Properties

- `public System.Boolean ignoreUnlockDependencies { get }`  

```csharp
public System.Boolean ignoreUnlockDependencies { get; }
```


## Constructors

- `public PoliceConfigurationPrefab()`  

```csharp
public PoliceConfigurationPrefab();
```


## Methods

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		base.GetDependencies(prefabs);
		prefabs.Add(m_PoliceServicePrefab);
		prefabs.Add(m_TrafficAccidentNotificationPrefab);
		prefabs.Add(m_CrimeSceneNotificationPrefab);
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<PoliceConfigurationData>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		PrefabSystem orCreateSystemManaged = entityManager.World.GetOrCreateSystemManaged<PrefabSystem>();
		PoliceConfigurationData componentData = default(PoliceConfigurationData);
		componentData.m_PoliceServicePrefab = orCreateSystemManaged.GetEntity(m_PoliceServicePrefab);
		componentData.m_TrafficAccidentNotificationPrefab = orCreateSystemManaged.GetEntity(m_TrafficAccidentNotificationPrefab);
		componentData.m_CrimeSceneNotificationPrefab = orCreateSystemManaged.GetEntity(m_CrimeSceneNotificationPrefab);
		componentData.m_MaxCrimeAccumulation = m_MaxCrimeAccumulation;
		componentData.m_CrimeAccumulationTolerance = m_CrimeAccumulationTolerance;
		componentData.m_HomeCrimeEffect = m_HomeCrimeEffect;
		componentData.m_WorkplaceCrimeEffect = m_WorkplaceCrimeEffect;
		componentData.m_WelfareCrimeRecurrenceFactor = m_WelfareCrimeRecurrenceFactor;
		componentData.m_CrimePoliceCoverageFactor = m_CrimePoliceCoverageFactor;
		componentData.m_CrimePopulationReduction = m_CrimePopulationReduction;
		entityManager.SetComponentData(entity, componentData);
	}
```


