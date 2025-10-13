# Game.Prefabs.PostFacility

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `Game.Prefabs.IServiceUpgrade`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class PostFacility : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, Game.Prefabs.IServiceUpgrade
{
    public System.Int32 m_PostVanCapacity;
    public System.Int32 m_PostTruckCapacity;
    public System.Int32 m_MailStorageCapacity;
    public System.Int32 m_MailBoxCapacity;
    public System.Int32 m_SortingRate;

    public PostFacility();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public System.Void GetUpgradeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Int32 m_PostVanCapacity`  

```csharp
public System.Int32 m_PostVanCapacity;
```

- `public System.Int32 m_PostTruckCapacity`  

```csharp
public System.Int32 m_PostTruckCapacity;
```

- `public System.Int32 m_MailStorageCapacity`  

```csharp
public System.Int32 m_MailStorageCapacity;
```

- `public System.Int32 m_MailBoxCapacity`  

```csharp
public System.Int32 m_MailBoxCapacity;
```

- `public System.Int32 m_SortingRate`  

```csharp
public System.Int32 m_SortingRate;
```


## Constructors

- `public PostFacility()`  

```csharp
public PostFacility();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<Game.Buildings.PostFacility>());
		if (GetComponent<ServiceUpgrade>() == null)
		{
			components.Add(ComponentType.ReadWrite<Resources>());
			if (GetComponent<CityServiceBuilding>() != null)
			{
				components.Add(ComponentType.ReadWrite<GuestVehicle>());
				components.Add(ComponentType.ReadWrite<Efficiency>());
			}
			if (m_PostTruckCapacity > 0)
			{
				components.Add(ComponentType.ReadWrite<ServiceDispatch>());
				components.Add(ComponentType.ReadWrite<OwnedVehicle>());
			}
			if (m_PostVanCapacity > 0)
			{
				components.Add(ComponentType.ReadWrite<ServiceDispatch>());
				components.Add(ComponentType.ReadWrite<ServiceDistrict>());
				components.Add(ComponentType.ReadWrite<OwnedVehicle>());
			}
			if (m_MailBoxCapacity > 0)
			{
				components.Add(ComponentType.ReadWrite<Game.Routes.MailBox>());
			}
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<PostFacilityData>());
		components.Add(ComponentType.ReadWrite<UpdateFrameData>());
		if (m_MailBoxCapacity > 0)
		{
			components.Add(ComponentType.ReadWrite<MailBoxData>());
		}
	}
```

- `public GetUpgradeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public void GetUpgradeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<Game.Buildings.PostFacility>());
		components.Add(ComponentType.ReadWrite<Resources>());
		if (m_PostTruckCapacity > 0)
		{
			components.Add(ComponentType.ReadWrite<ServiceDispatch>());
			components.Add(ComponentType.ReadWrite<OwnedVehicle>());
		}
		if (m_PostVanCapacity > 0)
		{
			components.Add(ComponentType.ReadWrite<ServiceDispatch>());
			components.Add(ComponentType.ReadWrite<OwnedVehicle>());
		}
		if (m_MailBoxCapacity > 0)
		{
			components.Add(ComponentType.ReadWrite<Game.Routes.MailBox>());
		}
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		PostFacilityData componentData = default(PostFacilityData);
		componentData.m_PostVanCapacity = m_PostVanCapacity;
		componentData.m_PostTruckCapacity = m_PostTruckCapacity;
		componentData.m_MailCapacity = m_MailStorageCapacity;
		componentData.m_SortingRate = m_SortingRate;
		entityManager.SetComponentData(entity, componentData);
		if (m_MailBoxCapacity > 0)
		{
			MailBoxData componentData2 = default(MailBoxData);
			componentData2.m_MailCapacity = m_MailBoxCapacity;
			entityManager.SetComponentData(entity, componentData2);
		}
		entityManager.SetComponentData(entity, new UpdateFrameData(11));
	}
```


