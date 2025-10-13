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
public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


