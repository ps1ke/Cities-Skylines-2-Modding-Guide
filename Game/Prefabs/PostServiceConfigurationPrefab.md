# Game.Prefabs.PostServiceConfigurationPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class PostServiceConfigurationPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.ServicePrefab m_PostServicePrefab;
    public System.Int32 m_MaxMailAccumulation;
    public System.Int32 m_MailAccumulationTolerance;
    public System.Int32 m_OutgoingMailPercentage;

    public System.Boolean ignoreUnlockDependencies { get; }

    public PostServiceConfigurationPrefab();

    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.ServicePrefab m_PostServicePrefab`  

```csharp
public Game.Prefabs.ServicePrefab m_PostServicePrefab;
```

- `public System.Int32 m_MaxMailAccumulation`  

```csharp
public System.Int32 m_MaxMailAccumulation;
```

- `public System.Int32 m_MailAccumulationTolerance`  

```csharp
public System.Int32 m_MailAccumulationTolerance;
```

- `public System.Int32 m_OutgoingMailPercentage`  

```csharp
public System.Int32 m_OutgoingMailPercentage;
```


## Properties

- `public System.Boolean ignoreUnlockDependencies { get }`  

```csharp
public System.Boolean ignoreUnlockDependencies { get; }
```


## Constructors

- `public PostServiceConfigurationPrefab()`  

```csharp
public PostServiceConfigurationPrefab();
```


## Methods

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		base.GetDependencies(prefabs);
		prefabs.Add(m_PostServicePrefab);
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<PostConfigurationData>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		PrefabSystem orCreateSystemManaged = entityManager.World.GetOrCreateSystemManaged<PrefabSystem>();
		entityManager.SetComponentData(entity, new PostConfigurationData
		{
			m_PostServicePrefab = orCreateSystemManaged.GetEntity(m_PostServicePrefab),
			m_MaxMailAccumulation = m_MaxMailAccumulation,
			m_MailAccumulationTolerance = m_MailAccumulationTolerance,
			m_OutgoingMailPercentage = m_OutgoingMailPercentage
		});
	}
```


