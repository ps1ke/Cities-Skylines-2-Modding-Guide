# Game.Prefabs.Unlockable

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.UnlockableBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class Unlockable : Game.Prefabs.UnlockableBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.PrefabBase[] m_RequireAll;
    public Game.Prefabs.PrefabBase[] m_RequireAny;
    public System.Boolean m_IgnoreDependencies;

    public Unlockable();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, System.Collections.Generic.List<Game.Prefabs.PrefabBase> dependencies);
}
```


## Fields

- `public Game.Prefabs.PrefabBase[] m_RequireAll`  

```csharp
public Game.Prefabs.PrefabBase[] m_RequireAll;
```

- `public Game.Prefabs.PrefabBase[] m_RequireAny`  

```csharp
public Game.Prefabs.PrefabBase[] m_RequireAny;
```

- `public System.Boolean m_IgnoreDependencies`  

```csharp
public System.Boolean m_IgnoreDependencies;
```


## Constructors

- `public Unlockable()`  

```csharp
public Unlockable();
```


## Methods

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

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, System.Collections.Generic.List<Game.Prefabs.PrefabBase> dependencies) : System.Void`  

```csharp
public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, System.Collections.Generic.List<Game.Prefabs.PrefabBase> dependencies);
```


