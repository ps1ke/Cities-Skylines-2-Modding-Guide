# Game.Prefabs.PoliceCar

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ExcludeGeneratedModTag`, `ComponentMenu`  

## Code

```csharp
public class PoliceCar : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public System.Int32 m_CriminalCapacity;
    public System.Single m_CrimeReductionRate;
    public System.Single m_ShiftDuration;
    public Game.Prefabs.PolicePurpose m_Purposes;

    public System.Collections.Generic.IEnumerable<System.String> modTags { get; }

    public PoliceCar();

    private System.Collections.Generic.IEnumerable<System.String> <>n__0();
    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Int32 m_CriminalCapacity`  

```csharp
public System.Int32 m_CriminalCapacity;
```

- `public System.Single m_CrimeReductionRate`  

```csharp
public System.Single m_CrimeReductionRate;
```

- `public System.Single m_ShiftDuration`  

```csharp
public System.Single m_ShiftDuration;
```

- `public Game.Prefabs.PolicePurpose m_Purposes`  

```csharp
public Game.Prefabs.PolicePurpose m_Purposes;
```


## Properties

- `public System.Collections.Generic.IEnumerable<System.String> modTags { get }`  

```csharp
public System.Collections.Generic.IEnumerable<System.String> modTags { get; }
```


## Constructors

- `public PoliceCar()`  

```csharp
public PoliceCar();
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

- `Game.Prefabs.PoliceCar+<get_modTags>d__8`  

