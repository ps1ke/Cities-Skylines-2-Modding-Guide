# Game.Prefabs.ZonePreferencePrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ZonePreferencePrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.Single m_ResidentialSignificanceServices;
    public System.Single m_ResidentialSignificanceWorkplaces;
    public System.Single m_ResidentialSignificanceLandValue;
    public System.Single m_ResidentialSignificancePollution;
    public System.Single m_ResidentialNeutralLandValue;
    public System.Single m_CommercialSignificanceConsumers;
    public System.Single m_CommercialSignificanceCompetitors;
    public System.Single m_CommercialSignificanceWorkplaces;
    public System.Single m_CommercialSignificanceLandValue;
    public System.Single m_CommercialNeutralLandValue;
    public System.Single m_IndustrialSignificanceInput;
    public System.Single m_IndustrialSignificanceOutside;
    public System.Single m_IndustrialSignificanceLandValue;
    public System.Single m_IndustrialNeutralLandValue;
    public System.Single m_OfficeSignificanceEmployees;
    public System.Single m_OfficeSignificanceServices;

    public ZonePreferencePrefab();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Single m_ResidentialSignificanceServices`  

```csharp
public System.Single m_ResidentialSignificanceServices;
```

- `public System.Single m_ResidentialSignificanceWorkplaces`  

```csharp
public System.Single m_ResidentialSignificanceWorkplaces;
```

- `public System.Single m_ResidentialSignificanceLandValue`  

```csharp
public System.Single m_ResidentialSignificanceLandValue;
```

- `public System.Single m_ResidentialSignificancePollution`  

```csharp
public System.Single m_ResidentialSignificancePollution;
```

- `public System.Single m_ResidentialNeutralLandValue`  

```csharp
public System.Single m_ResidentialNeutralLandValue;
```

- `public System.Single m_CommercialSignificanceConsumers`  

```csharp
public System.Single m_CommercialSignificanceConsumers;
```

- `public System.Single m_CommercialSignificanceCompetitors`  

```csharp
public System.Single m_CommercialSignificanceCompetitors;
```

- `public System.Single m_CommercialSignificanceWorkplaces`  

```csharp
public System.Single m_CommercialSignificanceWorkplaces;
```

- `public System.Single m_CommercialSignificanceLandValue`  

```csharp
public System.Single m_CommercialSignificanceLandValue;
```

- `public System.Single m_CommercialNeutralLandValue`  

```csharp
public System.Single m_CommercialNeutralLandValue;
```

- `public System.Single m_IndustrialSignificanceInput`  

```csharp
public System.Single m_IndustrialSignificanceInput;
```

- `public System.Single m_IndustrialSignificanceOutside`  

```csharp
public System.Single m_IndustrialSignificanceOutside;
```

- `public System.Single m_IndustrialSignificanceLandValue`  

```csharp
public System.Single m_IndustrialSignificanceLandValue;
```

- `public System.Single m_IndustrialNeutralLandValue`  

```csharp
public System.Single m_IndustrialNeutralLandValue;
```

- `public System.Single m_OfficeSignificanceEmployees`  

```csharp
public System.Single m_OfficeSignificanceEmployees;
```

- `public System.Single m_OfficeSignificanceServices`  

```csharp
public System.Single m_OfficeSignificanceServices;
```


## Constructors

- `public ZonePreferencePrefab()`  

```csharp
public ZonePreferencePrefab();
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


