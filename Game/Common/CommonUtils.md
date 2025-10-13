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
public static bool ExclusiveGroundCollision(CollisionMask mask1, CollisionMask mask2)
	{
		if ((mask1 & mask2 & CollisionMask.OnGround) != 0)
		{
			return ((mask1 | mask2) & CollisionMask.ExclusiveGround) != 0;
		}
		return false;
	}
```

- `public static GetBoundsMask(Game.Prefabs.MeshLayer meshLayers) : Game.Common.BoundsMask`  

```csharp
public static BoundsMask GetBoundsMask(MeshLayer meshLayers)
	{
		BoundsMask boundsMask = (BoundsMask)0;
		if ((meshLayers & (MeshLayer.Default | MeshLayer.Moving | MeshLayer.Tunnel | MeshLayer.Marker)) != 0)
		{
			boundsMask |= BoundsMask.NormalLayers;
		}
		if ((meshLayers & MeshLayer.Pipeline) != 0)
		{
			boundsMask |= BoundsMask.PipelineLayer;
		}
		if ((meshLayers & MeshLayer.SubPipeline) != 0)
		{
			boundsMask |= BoundsMask.SubPipelineLayer;
		}
		if ((meshLayers & MeshLayer.Waterway) != 0)
		{
			boundsMask |= BoundsMask.WaterwayLayer;
		}
		return boundsMask;
	}
```

- `public static GetRandomEntity(Unity.Mathematics.Random& random, Unity.Collections.NativeArray<Unity.Entities.ArchetypeChunk> chunks, Unity.Entities.EntityTypeHandle entityType) : Unity.Entities.Entity`  

```csharp
public static Entity GetRandomEntity(ref Random random, NativeArray<ArchetypeChunk> chunks, EntityTypeHandle entityType)
	{
		int num = 0;
		for (int i = 0; i < chunks.Length; i++)
		{
			num += chunks[i].Count;
		}
		if (num == 0)
		{
			return Entity.Null;
		}
		num = random.NextInt(num);
		for (int j = 0; j < chunks.Length; j++)
		{
			ArchetypeChunk archetypeChunk = chunks[j];
			if (num < archetypeChunk.Count)
			{
				return archetypeChunk.GetNativeArray(entityType)[num];
			}
			num -= archetypeChunk.Count;
		}
		return Entity.Null;
	}
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
public static void SwapBits(ref uint bitMask, uint a, uint b)
	{
		uint2 @uint = math.select(0u, new uint2(b, a), (bitMask & new uint2(a, b)) != 0u);
		bitMask = (bitMask & ~(a | b)) | @uint.x | @uint.y;
	}
```


