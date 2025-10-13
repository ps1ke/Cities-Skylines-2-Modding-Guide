# Game.UI.InGame.ProgressionUtils

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class ProgressionUtils
{
    public static System.Boolean CollectSubRequirements(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity prefab, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Prefabs.UnlockFlags> requiredPrefabs, Game.Prefabs.UnlockFlags flags);
    public static System.Int32 GetRequiredMilestone(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Methods

- `public static CollectSubRequirements(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity prefab, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Prefabs.UnlockFlags> requiredPrefabs, Game.Prefabs.UnlockFlags flags = RequireAll, RequireAny) : System.Boolean`  

```csharp
public static System.Boolean CollectSubRequirements(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity prefab, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Prefabs.UnlockFlags> requiredPrefabs, Game.Prefabs.UnlockFlags flags);
```

- `public static GetRequiredMilestone(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Int32`  

```csharp
public static System.Int32 GetRequiredMilestone(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


