# Game.Prefabs.PollutionModifier

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class PollutionModifier : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public System.Single m_GroundPollutionMultiplier;
    public System.Single m_AirPollutionMultiplier;
    public System.Single m_NoisePollutionMultiplier;

    public PollutionModifier();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Single m_GroundPollutionMultiplier`  

```csharp
public System.Single m_GroundPollutionMultiplier;
```

- `public System.Single m_AirPollutionMultiplier`  

```csharp
public System.Single m_AirPollutionMultiplier;
```

- `public System.Single m_NoisePollutionMultiplier`  

```csharp
public System.Single m_NoisePollutionMultiplier;
```


## Constructors

- `public PollutionModifier()`  

```csharp
public PollutionModifier();
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
		components.Add(ComponentType.ReadWrite<PollutionModifierData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		if (!base.prefab.Has<ServiceUpgrade>())
		{
			ComponentBase.baseLog.ErrorFormat(base.prefab, "PollutionModifier should only be added to service upgrades: {0}", base.prefab.name);
		}
		entityManager.SetComponentData(entity, new PollutionModifierData
		{
			m_GroundPollutionMultiplier = m_GroundPollutionMultiplier,
			m_AirPollutionMultiplier = m_AirPollutionMultiplier,
			m_NoisePollutionMultiplier = m_NoisePollutionMultiplier
		});
	}
```


