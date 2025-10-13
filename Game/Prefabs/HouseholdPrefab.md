# Game.Prefabs.HouseholdPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ArchetypePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class HouseholdPrefab : Game.Prefabs.ArchetypePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.Int32 m_ResourceConsumption;
    public System.Int32 m_InitialWealthRange;
    public System.Int32 m_InitialWealthOffset;
    public System.Int32 m_InitialCarProbability;
    public System.Int32 m_ChildCount;
    public System.Int32 m_AdultCount;
    public System.Int32 m_ElderlyCount;
    public System.Int32 m_StudentCount;
    public System.Int32 m_FirstPetProbability;
    public System.Int32 m_NextPetProbability;
    public System.Boolean m_DynamicHousehold;
    public System.Int32 m_Weight;

    public HouseholdPrefab();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Int32 m_ResourceConsumption`  

```csharp
public System.Int32 m_ResourceConsumption;
```

- `public System.Int32 m_InitialWealthRange`  

```csharp
public System.Int32 m_InitialWealthRange;
```

- `public System.Int32 m_InitialWealthOffset`  

```csharp
public System.Int32 m_InitialWealthOffset;
```

- `public System.Int32 m_InitialCarProbability`  

```csharp
public System.Int32 m_InitialCarProbability;
```

- `public System.Int32 m_ChildCount`  

```csharp
public System.Int32 m_ChildCount;
```

- `public System.Int32 m_AdultCount`  

```csharp
public System.Int32 m_AdultCount;
```

- `public System.Int32 m_ElderlyCount`  

```csharp
public System.Int32 m_ElderlyCount;
```

- `public System.Int32 m_StudentCount`  

```csharp
public System.Int32 m_StudentCount;
```

- `public System.Int32 m_FirstPetProbability`  

```csharp
public System.Int32 m_FirstPetProbability;
```

- `public System.Int32 m_NextPetProbability`  

```csharp
public System.Int32 m_NextPetProbability;
```

- `public System.Boolean m_DynamicHousehold`  

```csharp
public System.Boolean m_DynamicHousehold;
```

- `public System.Int32 m_Weight`  

```csharp
public System.Int32 m_Weight;
```


## Constructors

- `public HouseholdPrefab()`  

```csharp
public HouseholdPrefab();
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

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


