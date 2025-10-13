# Game.Prefabs.TaxParameterPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class TaxParameterPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Unity.Mathematics.int2 m_TotalTaxLimits;
    public Unity.Mathematics.int2 m_ResidentialTaxLimits;
    public Unity.Mathematics.int2 m_CommercialTaxLimits;
    public Unity.Mathematics.int2 m_IndustrialTaxLimits;
    public Unity.Mathematics.int2 m_OfficeTaxLimits;
    public Unity.Mathematics.int2 m_JobLevelTaxLimits;
    public Unity.Mathematics.int2 m_ResourceTaxLimits;

    public TaxParameterPrefab();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Unity.Mathematics.int2 m_TotalTaxLimits`  

```csharp
public Unity.Mathematics.int2 m_TotalTaxLimits;
```

- `public Unity.Mathematics.int2 m_ResidentialTaxLimits`  

```csharp
public Unity.Mathematics.int2 m_ResidentialTaxLimits;
```

- `public Unity.Mathematics.int2 m_CommercialTaxLimits`  

```csharp
public Unity.Mathematics.int2 m_CommercialTaxLimits;
```

- `public Unity.Mathematics.int2 m_IndustrialTaxLimits`  

```csharp
public Unity.Mathematics.int2 m_IndustrialTaxLimits;
```

- `public Unity.Mathematics.int2 m_OfficeTaxLimits`  

```csharp
public Unity.Mathematics.int2 m_OfficeTaxLimits;
```

- `public Unity.Mathematics.int2 m_JobLevelTaxLimits`  

```csharp
public Unity.Mathematics.int2 m_JobLevelTaxLimits;
```

- `public Unity.Mathematics.int2 m_ResourceTaxLimits`  

```csharp
public Unity.Mathematics.int2 m_ResourceTaxLimits;
```


## Constructors

- `public TaxParameterPrefab()`  

```csharp
public TaxParameterPrefab();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		base.GetArchetypeComponents(components);
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<TaxParameterData>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		entityManager.World.GetOrCreateSystemManaged<PrefabSystem>();
		entityManager.SetComponentData(entity, new TaxParameterData
		{
			m_TotalTaxLimits = m_TotalTaxLimits,
			m_ResidentialTaxLimits = m_ResidentialTaxLimits,
			m_CommercialTaxLimits = m_CommercialTaxLimits,
			m_IndustrialTaxLimits = m_IndustrialTaxLimits,
			m_OfficeTaxLimits = m_OfficeTaxLimits,
			m_JobLevelTaxLimits = m_JobLevelTaxLimits,
			m_ResourceTaxLimits = m_ResourceTaxLimits
		});
	}
```


