# Game.Prefabs.SpawnableBuilding

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class SpawnableBuilding : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.ZonePrefab m_ZoneType;
    public System.Byte m_Level;

    public System.Boolean ignoreUnlockDependencies { get; }
    public System.Collections.Generic.IEnumerable<System.String> modTags { get; }

    public SpawnableBuilding();

    private System.Collections.Generic.IEnumerable<System.String> <>n__0();
    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.ZonePrefab m_ZoneType`  

```csharp
public Game.Prefabs.ZonePrefab m_ZoneType;
```

- `public System.Byte m_Level`  

```csharp
public System.Byte m_Level;
```


## Properties

- `public System.Boolean ignoreUnlockDependencies { get }`  

```csharp
public System.Boolean ignoreUnlockDependencies { get; }
```

- `public System.Collections.Generic.IEnumerable<System.String> modTags { get }`  

```csharp
public System.Collections.Generic.IEnumerable<System.String> modTags { get; }
```


## Constructors

- `public SpawnableBuilding()`  

```csharp
public SpawnableBuilding();
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

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


## Nested types

- `Game.Prefabs.SpawnableBuilding+<get_modTags>d__10`  

