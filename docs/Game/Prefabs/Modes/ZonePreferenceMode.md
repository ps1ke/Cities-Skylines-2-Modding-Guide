# Game.Prefabs.Modes.ZonePreferenceMode

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Modes`  

**Type:** class public  

**Base:** `Game.Prefabs.Modes.EntityQueryModePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ZonePreferenceMode : Game.Prefabs.Modes.EntityQueryModePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
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

    public ZonePreferenceMode();

    public virtual Unity.Jobs.JobHandle ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps);
    public virtual Unity.Entities.EntityQueryDesc GetEntityQueryDesc();
    protected virtual System.Void RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public virtual System.Void RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem);
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

- `public ZonePreferenceMode()`  

```csharp
public ZonePreferenceMode();
```


## Methods

- `public virtual ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps) : Unity.Jobs.JobHandle`  

```csharp
public virtual Unity.Jobs.JobHandle ApplyModeData(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery requestedQuery, Unity.Jobs.JobHandle deps);
```

- `public virtual GetEntityQueryDesc() : Unity.Entities.EntityQueryDesc`  

```csharp
public virtual Unity.Entities.EntityQueryDesc GetEntityQueryDesc();
```

- `protected virtual RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
protected virtual System.Void RecordChanges(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```

- `public virtual RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem) : System.Void`  

```csharp
public virtual System.Void RestoreDefaultData(Unity.Entities.EntityManager entityManager, Unity.Collections.NativeArray`1[[Unity.Entities.Entity, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entities, Game.Prefabs.PrefabSystem prefabSystem);
```


