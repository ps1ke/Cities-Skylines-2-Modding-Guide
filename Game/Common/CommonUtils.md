# Game.Common.CommonUtils

**Assembly:** `Game`  
**Namespace:** `Game.Common`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class CommonUtils
{
    public static System.Boolean ExclusiveGroundCollision(Game.Common.CollisionMask mask1, Game.Common.CollisionMask mask2);
    public static Game.Common.BoundsMask GetBoundsMask(Game.Prefabs.MeshLayer meshLayers);
    public static Unity.Entities.Entity GetRandomEntity(Unity.Mathematics.Random& random, Unity.Collections.NativeArray<Unity.Entities.ArchetypeChunk> chunks, Unity.Entities.EntityTypeHandle entityType);
    public static Unity.Entities.Entity GetRandomEntity<T>(Unity.Mathematics.Random& random, Unity.Collections.NativeArray<Unity.Entities.ArchetypeChunk> chunks, Unity.Entities.EntityTypeHandle entityType, Unity.Entities.ComponentTypeHandle<T> componentType, T& componentData);
    public static Unity.Entities.Entity GetRandomEntity<T1, T2>(Unity.Mathematics.Random& random, Unity.Collections.NativeArray<Unity.Entities.ArchetypeChunk> chunks, Unity.Entities.EntityTypeHandle entityType, Unity.Entities.ComponentTypeHandle<T1> componentType1, Unity.Entities.ComponentTypeHandle<T2> componentType2, T1& componentData1, T2& componentData2);
    public static System.Void Swap<T>(T& a, T& b);
    public static System.Void SwapBits(System.UInt32& bitMask, System.UInt32 a, System.UInt32 b);
}
```


## Methods

- `public static ExclusiveGroundCollision(Game.Common.CollisionMask mask1, Game.Common.CollisionMask mask2) : System.Boolean`  

```csharp
public static System.Boolean ExclusiveGroundCollision(Game.Common.CollisionMask mask1, Game.Common.CollisionMask mask2);
```

- `public static GetBoundsMask(Game.Prefabs.MeshLayer meshLayers) : Game.Common.BoundsMask`  

```csharp
public static Game.Common.BoundsMask GetBoundsMask(Game.Prefabs.MeshLayer meshLayers);
```

- `public static GetRandomEntity(Unity.Mathematics.Random& random, Unity.Collections.NativeArray<Unity.Entities.ArchetypeChunk> chunks, Unity.Entities.EntityTypeHandle entityType) : Unity.Entities.Entity`  

```csharp
public static Unity.Entities.Entity GetRandomEntity(Unity.Mathematics.Random& random, Unity.Collections.NativeArray<Unity.Entities.ArchetypeChunk> chunks, Unity.Entities.EntityTypeHandle entityType);
```

- `public static GetRandomEntity<T>(Unity.Mathematics.Random& random, Unity.Collections.NativeArray<Unity.Entities.ArchetypeChunk> chunks, Unity.Entities.EntityTypeHandle entityType, Unity.Entities.ComponentTypeHandle<T> componentType, T& componentData) : Unity.Entities.Entity`  

```csharp
public static Unity.Entities.Entity GetRandomEntity<T>(Unity.Mathematics.Random& random, Unity.Collections.NativeArray<Unity.Entities.ArchetypeChunk> chunks, Unity.Entities.EntityTypeHandle entityType, Unity.Entities.ComponentTypeHandle<T> componentType, T& componentData);
```

- `public static GetRandomEntity<T1, T2>(Unity.Mathematics.Random& random, Unity.Collections.NativeArray<Unity.Entities.ArchetypeChunk> chunks, Unity.Entities.EntityTypeHandle entityType, Unity.Entities.ComponentTypeHandle<T1> componentType1, Unity.Entities.ComponentTypeHandle<T2> componentType2, T1& componentData1, T2& componentData2) : Unity.Entities.Entity`  

```csharp
public static Unity.Entities.Entity GetRandomEntity<T1, T2>(Unity.Mathematics.Random& random, Unity.Collections.NativeArray<Unity.Entities.ArchetypeChunk> chunks, Unity.Entities.EntityTypeHandle entityType, Unity.Entities.ComponentTypeHandle<T1> componentType1, Unity.Entities.ComponentTypeHandle<T2> componentType2, T1& componentData1, T2& componentData2);
```

- `public static Swap<T>(T& a, T& b) : System.Void`  

```csharp
public static System.Void Swap<T>(T& a, T& b);
```

- `public static SwapBits(System.UInt32& bitMask, System.UInt32 a, System.UInt32 b) : System.Void`  

```csharp
public static System.Void SwapBits(System.UInt32& bitMask, System.UInt32 a, System.UInt32 b);
```


