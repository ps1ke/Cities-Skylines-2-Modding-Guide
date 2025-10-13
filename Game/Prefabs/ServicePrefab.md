# Game.Prefabs.ServicePrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ServicePrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    private Game.City.PlayerResource[] m_CityResources;
    private Game.City.CityService m_Service;
    private System.Boolean m_BudgetAdjustable;

    public ServicePrefab();

    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `private Game.City.PlayerResource[] m_CityResources`  

```csharp
private Game.City.PlayerResource[] m_CityResources;
```

- `private Game.City.CityService m_Service`  

```csharp
private Game.City.CityService m_Service;
```

- `private System.Boolean m_BudgetAdjustable`  

```csharp
private System.Boolean m_BudgetAdjustable;
```


## Constructors

- `public ServicePrefab()`  

```csharp
public ServicePrefab();
```


## Methods

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<ServiceData>());
		components.Add(ComponentType.ReadWrite<CollectedCityServiceBudgetData>());
		components.Add(ComponentType.ReadWrite<CollectedCityServiceUpkeepData>());
		if (m_CityResources != null && m_CityResources.Length != 0)
		{
			components.Add(ComponentType.ReadWrite<CollectedCityServiceFeeData>());
		}
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		if (m_CityResources != null && m_CityResources.Length != 0)
		{
			DynamicBuffer<CollectedCityServiceFeeData> buffer = entityManager.GetBuffer<CollectedCityServiceFeeData>(entity);
			for (int i = 0; i < m_CityResources.Length; i++)
			{
				buffer.Add(new CollectedCityServiceFeeData
				{
					m_PlayerResource = (int)m_CityResources[i]
				});
			}
		}
		entityManager.SetComponentData(entity, new ServiceData
		{
			m_Service = m_Service,
			m_BudgetAdjustable = m_BudgetAdjustable
		});
	}
```


