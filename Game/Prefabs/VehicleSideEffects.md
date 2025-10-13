# Game.Prefabs.VehicleSideEffects

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class VehicleSideEffects : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Unity.Mathematics.float2 m_RoadWear;
    public Unity.Mathematics.float2 m_NoisePollution;
    public Unity.Mathematics.float2 m_AirPollution;

    public VehicleSideEffects();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Unity.Mathematics.float2 m_RoadWear`  

```csharp
public Unity.Mathematics.float2 m_RoadWear;
```

- `public Unity.Mathematics.float2 m_NoisePollution`  

```csharp
public Unity.Mathematics.float2 m_NoisePollution;
```

- `public Unity.Mathematics.float2 m_AirPollution`  

```csharp
public Unity.Mathematics.float2 m_AirPollution;
```


## Constructors

- `public VehicleSideEffects()`  

```csharp
public VehicleSideEffects();
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


