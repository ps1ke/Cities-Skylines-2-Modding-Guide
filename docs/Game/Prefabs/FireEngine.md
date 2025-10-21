# Game.Prefabs.FireEngine

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ExcludeGeneratedModTag`, `ComponentMenu`  

## Code

```csharp
public class FireEngine : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public System.Single m_ExtinguishingRate;
    public System.Single m_ExtinguishingSpread;
    public System.Single m_ExtinguishingCapacity;
    public System.Single m_DestroyedClearDuration;

    public System.Collections.Generic.IEnumerable<System.String> modTags { get; }

    public FireEngine();

    private System.Collections.Generic.IEnumerable<System.String> <>n__0();
    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Single m_ExtinguishingRate`  

```csharp
public System.Single m_ExtinguishingRate;
```

- `public System.Single m_ExtinguishingSpread`  

```csharp
public System.Single m_ExtinguishingSpread;
```

- `public System.Single m_ExtinguishingCapacity`  

```csharp
public System.Single m_ExtinguishingCapacity;
```

- `public System.Single m_DestroyedClearDuration`  

```csharp
public System.Single m_DestroyedClearDuration;
```


## Properties

- `public System.Collections.Generic.IEnumerable<System.String> modTags { get }`  

```csharp
public System.Collections.Generic.IEnumerable<System.String> modTags { get; }
```


## Constructors

- `public FireEngine()`  

```csharp
public FireEngine();
```


## Methods

- `private <>n__0() : System.Collections.Generic.IEnumerable<System.String>`  

```csharp
private System.Collections.Generic.IEnumerable<System.String> <>n__0();
```

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


## Nested types

- `Game.Prefabs.FireEngine+<get_modTags>d__8`  

