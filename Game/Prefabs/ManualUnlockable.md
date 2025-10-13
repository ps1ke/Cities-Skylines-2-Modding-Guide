# Game.Prefabs.ManualUnlockable

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.UnlockableBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class ManualUnlockable : Game.Prefabs.UnlockableBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public ManualUnlockable();

    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, System.Collections.Generic.List<Game.Prefabs.PrefabBase> dependencies);
}
```


## Constructors

- `public ManualUnlockable()`  

```csharp
public ManualUnlockable();
```


## Methods

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, System.Collections.Generic.List<Game.Prefabs.PrefabBase> dependencies) : System.Void`  

```csharp
public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, System.Collections.Generic.List<Game.Prefabs.PrefabBase> dependencies);
```


