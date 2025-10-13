# Game.Prefabs.Hospital

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `Game.Prefabs.IServiceUpgrade`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class Hospital : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, Game.Prefabs.IServiceUpgrade
{
    public System.Int32 m_AmbulanceCapacity;
    public System.Int32 m_MedicalHelicopterCapacity;
    public System.Int32 m_PatientCapacity;
    public System.Int32 m_TreatmentBonus;
    public Unity.Mathematics.int2 m_HealthRange;
    public System.Boolean m_TreatDiseases;
    public System.Boolean m_TreatInjuries;

    public Hospital();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public System.Void GetUpgradeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Int32 m_AmbulanceCapacity`  

```csharp
public System.Int32 m_AmbulanceCapacity;
```

- `public System.Int32 m_MedicalHelicopterCapacity`  

```csharp
public System.Int32 m_MedicalHelicopterCapacity;
```

- `public System.Int32 m_PatientCapacity`  

```csharp
public System.Int32 m_PatientCapacity;
```

- `public System.Int32 m_TreatmentBonus`  

```csharp
public System.Int32 m_TreatmentBonus;
```

- `public Unity.Mathematics.int2 m_HealthRange`  

```csharp
public Unity.Mathematics.int2 m_HealthRange;
```

- `public System.Boolean m_TreatDiseases`  

```csharp
public System.Boolean m_TreatDiseases;
```

- `public System.Boolean m_TreatInjuries`  

```csharp
public System.Boolean m_TreatInjuries;
```


## Constructors

- `public Hospital()`  

```csharp
public Hospital();
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

- `public GetUpgradeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public System.Void GetUpgradeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


