# Game.Prefabs.CitizenParametersPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class CitizenParametersPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public System.Single m_DivorceRate;
    public System.Single m_LookForPartnerRate;
    public Unity.Mathematics.float2 m_LookForPartnerTypeRate;
    public System.Single m_BaseBirthRate;
    public System.Single m_AdultFemaleBirthRateBonus;
    public System.Single m_StudentBirthRateAdjust;
    public System.Single m_SwitchJobRate;
    public System.Single m_LookForNewJobEmployableRate;

    public CitizenParametersPrefab();

    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Single m_DivorceRate`  

```csharp
public System.Single m_DivorceRate;
```

- `public System.Single m_LookForPartnerRate`  

```csharp
public System.Single m_LookForPartnerRate;
```

- `public Unity.Mathematics.float2 m_LookForPartnerTypeRate`  

```csharp
public Unity.Mathematics.float2 m_LookForPartnerTypeRate;
```

- `public System.Single m_BaseBirthRate`  

```csharp
public System.Single m_BaseBirthRate;
```

- `public System.Single m_AdultFemaleBirthRateBonus`  

```csharp
public System.Single m_AdultFemaleBirthRateBonus;
```

- `public System.Single m_StudentBirthRateAdjust`  

```csharp
public System.Single m_StudentBirthRateAdjust;
```

- `public System.Single m_SwitchJobRate`  

```csharp
public System.Single m_SwitchJobRate;
```

- `public System.Single m_LookForNewJobEmployableRate`  

```csharp
public System.Single m_LookForNewJobEmployableRate;
```


## Constructors

- `public CitizenParametersPrefab()`  

```csharp
public CitizenParametersPrefab();
```


## Methods

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


