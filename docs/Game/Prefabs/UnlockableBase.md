# Game.Prefabs.UnlockableBase

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class abstract public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

## Code

```csharp
public abstract class UnlockableBase : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    protected UnlockableBase();

    public static System.Void DefaultLateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, System.Collections.Generic.List<Game.Prefabs.PrefabBase> dependencies);
    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, System.Collections.Generic.List<Game.Prefabs.PrefabBase> dependencies);
}
```


## Constructors

- `protected UnlockableBase()`  

```csharp
protected UnlockableBase();
```


## Methods

- `public static DefaultLateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, System.Collections.Generic.List<Game.Prefabs.PrefabBase> dependencies) : System.Void`  

```csharp
public static System.Void DefaultLateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, System.Collections.Generic.List<Game.Prefabs.PrefabBase> dependencies);
```

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, System.Collections.Generic.List<Game.Prefabs.PrefabBase> dependencies) : System.Void`  

```csharp
public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, System.Collections.Generic.List<Game.Prefabs.PrefabBase> dependencies);
```


