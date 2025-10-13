# Game.Prefabs.Effects.RandomTransform

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Effects`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class RandomTransform : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Unity.Mathematics.float3 m_MinAngle;
    public Unity.Mathematics.float3 m_MaxAngle;
    public Unity.Mathematics.float3 m_MinPosition;
    public Unity.Mathematics.float3 m_MaxPosition;

    public RandomTransform();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Unity.Mathematics.float3 m_MinAngle`  

```csharp
public Unity.Mathematics.float3 m_MinAngle;
```

- `public Unity.Mathematics.float3 m_MaxAngle`  

```csharp
public Unity.Mathematics.float3 m_MaxAngle;
```

- `public Unity.Mathematics.float3 m_MinPosition`  

```csharp
public Unity.Mathematics.float3 m_MinPosition;
```

- `public Unity.Mathematics.float3 m_MaxPosition`  

```csharp
public Unity.Mathematics.float3 m_MaxPosition;
```


## Constructors

- `public RandomTransform()`  

```csharp
public RandomTransform();
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


