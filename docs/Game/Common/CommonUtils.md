# Game.Common.CommonUtils

**Assembly:** `Game`  
**Namespace:** `Game.Common`  

**Type:** class static public  

**Base:** `System.Object`  

## Methods

- `public static ExclusiveGroundCollision(Game.Common.CollisionMask mask1, Game.Common.CollisionMask mask2) : System.Boolean`  
- `public static GetBoundsMask(Game.Prefabs.MeshLayer meshLayers) : Game.Common.BoundsMask`  
- `public static GetRandomEntity(Unity.Mathematics.Random& random, Unity.Collections.NativeArray<Unity.Entities.ArchetypeChunk> chunks, Unity.Entities.EntityTypeHandle entityType) : Unity.Entities.Entity`  
- `public static GetRandomEntity<T>(Unity.Mathematics.Random& random, Unity.Collections.NativeArray<Unity.Entities.ArchetypeChunk> chunks, Unity.Entities.EntityTypeHandle entityType, Unity.Entities.ComponentTypeHandle<T> componentType, T& componentData) : Unity.Entities.Entity`  
- `public static GetRandomEntity<T1, T2>(Unity.Mathematics.Random& random, Unity.Collections.NativeArray<Unity.Entities.ArchetypeChunk> chunks, Unity.Entities.EntityTypeHandle entityType, Unity.Entities.ComponentTypeHandle<T1> componentType1, Unity.Entities.ComponentTypeHandle<T2> componentType2, T1& componentData1, T2& componentData2) : Unity.Entities.Entity`  
- `public static Swap<T>(T& a, T& b) : System.Void`  
- `public static SwapBits(System.UInt32& bitMask, System.UInt32 a, System.UInt32 b) : System.Void`  

