# Game.Prefabs.Pollution

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `Game.Prefabs.IServiceUpgrade`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class Pollution : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, Game.Prefabs.IServiceUpgrade
{
    public System.Int32 m_GroundPollution;
    public System.Int32 m_AirPollution;
    public System.Int32 m_NoisePollution;
    public System.Boolean m_ScaleWithRenters;

    public Pollution();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    private Game.Prefabs.PollutionData GetPollutionData();
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public System.Void GetUpgradeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Int32 m_GroundPollution`  

```csharp
public System.Int32 m_GroundPollution;
```

- `public System.Int32 m_AirPollution`  

```csharp
public System.Int32 m_AirPollution;
```

- `public System.Int32 m_NoisePollution`  

```csharp
public System.Int32 m_NoisePollution;
```

- `public System.Boolean m_ScaleWithRenters`  

```csharp
public System.Boolean m_ScaleWithRenters;
```


## Constructors

- `public Pollution()`  

```csharp
public Pollution();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		if (!base.prefab.Has<ServiceUpgrade>() && !base.prefab.Has<PlaceholderBuilding>())
		{
			GetPollutionData().AddArchetypeComponents(components);
		}
	}
```

- `private GetPollutionData() : Game.Prefabs.PollutionData`  

```csharp
private PollutionData GetPollutionData()
	{
		return new PollutionData
		{
			m_GroundPollution = m_GroundPollution,
			m_AirPollution = m_AirPollution,
			m_NoisePollution = m_NoisePollution,
			m_ScaleWithRenters = m_ScaleWithRenters
		};
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<PollutionData>());
	}
```

- `public GetUpgradeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public void GetUpgradeComponents(HashSet<ComponentType> components)
	{
		GetPollutionData().AddArchetypeComponents(components);
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		entityManager.SetComponentData(entity, GetPollutionData());
	}
```


