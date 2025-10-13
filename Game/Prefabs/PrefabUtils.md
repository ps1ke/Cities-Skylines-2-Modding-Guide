# Game.Prefabs.PrefabUtils

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class PrefabUtils
{
    public static System.String GetContentPrerequisite(Game.Prefabs.PrefabBase prefab);
    public static System.Boolean HasUnlockedPrefab<T>(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery unlockQuery);
    public static System.Boolean HasUnlockedPrefabAll<T1, T2>(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery unlockQuery);
    public static System.Boolean HasUnlockedPrefabAny<T1, T2, T3, T4>(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery unlockQuery);
    public static T[] ToArray<T>(System.Collections.Generic.HashSet<T> hashSet);
}
```


## Methods

- `public static GetContentPrerequisite(Game.Prefabs.PrefabBase prefab) : System.String`  

```csharp
public static System.String GetContentPrerequisite(Game.Prefabs.PrefabBase prefab);
```

- `public static HasUnlockedPrefab<T>(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery unlockQuery) : System.Boolean`  

```csharp
public static System.Boolean HasUnlockedPrefab<T>(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery unlockQuery);
```

- `public static HasUnlockedPrefabAll<T1, T2>(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery unlockQuery) : System.Boolean`  

```csharp
public static System.Boolean HasUnlockedPrefabAll<T1, T2>(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery unlockQuery);
```

- `public static HasUnlockedPrefabAny<T1, T2, T3, T4>(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery unlockQuery) : System.Boolean`  

```csharp
public static System.Boolean HasUnlockedPrefabAny<T1, T2, T3, T4>(Unity.Entities.EntityManager entityManager, Unity.Entities.EntityQuery unlockQuery);
```

- `public static ToArray<T>(System.Collections.Generic.HashSet<T> hashSet) : T[]`  

```csharp
public static T[] ToArray<T>(System.Collections.Generic.HashSet<T> hashSet);
```


