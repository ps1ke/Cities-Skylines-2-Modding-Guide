# Game.Prefabs.CompanyPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ArchetypePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class CompanyPrefab : Game.Prefabs.ArchetypePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Zones.AreaType zone;
    public System.Single profitability;

    public CompanyPrefab();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
}
```


## Fields

- `public Game.Zones.AreaType zone`  

```csharp
public Game.Zones.AreaType zone;
```

- `public System.Single profitability`  

```csharp
public System.Single profitability;
```


## Constructors

- `public CompanyPrefab()`  

```csharp
public CompanyPrefab();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		base.GetArchetypeComponents(components);
		components.Add(ComponentType.ReadWrite<CompanyData>());
		components.Add(ComponentType.ReadWrite<UpdateFrame>());
		components.Add(ComponentType.ReadWrite<Resources>());
		components.Add(ComponentType.ReadWrite<PropertySeeker>());
		components.Add(ComponentType.ReadWrite<TripNeeded>());
		components.Add(ComponentType.ReadWrite<CompanyNotifications>());
		components.Add(ComponentType.ReadWrite<GuestVehicle>());
		if (zone == AreaType.Commercial)
		{
			components.Add(ComponentType.ReadWrite<CommercialCompany>());
		}
		else if (zone == AreaType.Industrial)
		{
			components.Add(ComponentType.ReadWrite<IndustrialCompany>());
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		if (zone == AreaType.Commercial)
		{
			components.Add(ComponentType.ReadWrite<CommercialCompanyData>());
		}
		else if (zone == AreaType.Industrial)
		{
			components.Add(ComponentType.ReadWrite<IndustrialCompanyData>());
		}
		components.Add(ComponentType.ReadWrite<CompanyBrandElement>());
		components.Add(ComponentType.ReadWrite<AffiliatedBrandElement>());
	}
```


