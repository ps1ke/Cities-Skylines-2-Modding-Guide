# Game.Prefabs.RandomLikeCount

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class RandomLikeCount : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public System.Single m_EducatedPercentage;
    public System.Single m_UneducatedPercentage;
    public Unity.Mathematics.float2 m_ActiveDays;
    public Unity.Mathematics.int2 m_GoViralFactor;
    public Unity.Mathematics.float2 m_RandomAmountFactor;
    public System.Single m_ContinuousFactor;

    public RandomLikeCount();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Single m_EducatedPercentage`  

```csharp
public System.Single m_EducatedPercentage;
```

- `public System.Single m_UneducatedPercentage`  

```csharp
public System.Single m_UneducatedPercentage;
```

- `public Unity.Mathematics.float2 m_ActiveDays`  

```csharp
public Unity.Mathematics.float2 m_ActiveDays;
```

- `public Unity.Mathematics.int2 m_GoViralFactor`  

```csharp
public Unity.Mathematics.int2 m_GoViralFactor;
```

- `public Unity.Mathematics.float2 m_RandomAmountFactor`  

```csharp
public Unity.Mathematics.float2 m_RandomAmountFactor;
```

- `public System.Single m_ContinuousFactor`  

```csharp
public System.Single m_ContinuousFactor;
```


## Constructors

- `public RandomLikeCount()`  

```csharp
public RandomLikeCount();
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


