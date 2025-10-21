# Game.Prefabs.RandomLocalization

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.Localization`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class RandomLocalization : Game.Prefabs.Localization, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public RandomLocalization();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    protected virtual System.Int32 GetLocalizationCount();
    public static System.Int32 GetLocalizationIndexCount(Game.Prefabs.PrefabBase prefab, System.String id);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Constructors

- `public RandomLocalization()`  

```csharp
public RandomLocalization();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `protected virtual GetLocalizationCount() : System.Int32`  

```csharp
protected virtual System.Int32 GetLocalizationCount();
```

- `public static GetLocalizationIndexCount(Game.Prefabs.PrefabBase prefab, System.String id) : System.Int32`  

```csharp
public static System.Int32 GetLocalizationIndexCount(Game.Prefabs.PrefabBase prefab, System.String id);
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


