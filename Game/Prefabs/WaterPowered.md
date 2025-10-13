# Game.Prefabs.WaterPowered

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `Game.Prefabs.IServiceUpgrade`  

**Attributes:** `RequireComponent`, `ComponentMenu`  

## Code

```csharp
public class WaterPowered : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, Game.Prefabs.IServiceUpgrade
{
    public System.Single m_ProductionFactor;
    public System.Single m_CapacityFactor;

    public WaterPowered();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public System.Void GetUpgradeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Single m_ProductionFactor`  

```csharp
public System.Single m_ProductionFactor;
```

- `public System.Single m_CapacityFactor`  

```csharp
public System.Single m_CapacityFactor;
```


## Constructors

- `public WaterPowered()`  

```csharp
public WaterPowered();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		if (GetComponent<ServiceUpgrade>() == null)
		{
			components.Add(ComponentType.ReadWrite<Game.Buildings.WaterPowered>());
			components.Add(ComponentType.ReadWrite<Efficiency>());
			components.Add(ComponentType.ReadWrite<RenewableElectricityProduction>());
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<WaterPoweredData>());
	}
```

- `public GetUpgradeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public void GetUpgradeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<Game.Buildings.WaterPowered>());
		components.Add(ComponentType.ReadWrite<Efficiency>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		if (base.prefab.TryGet<PowerPlant>(out var component) && component.m_ElectricityProduction != 0)
		{
			UnityEngine.Debug.LogErrorFormat(base.prefab, "WaterPowered has non-zero electricity production: {0}", base.prefab.name);
		}
		entityManager.SetComponentData(entity, new WaterPoweredData
		{
			m_ProductionFactor = m_ProductionFactor,
			m_CapacityFactor = m_CapacityFactor
		});
	}
```


