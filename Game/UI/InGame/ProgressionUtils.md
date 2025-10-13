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
public static bool CollectSubRequirements(EntityManager entityManager, Entity prefab, NativeParallelHashMap<Entity, UnlockFlags> requiredPrefabs, UnlockFlags flags = UnlockFlags.RequireAll | UnlockFlags.RequireAny)
	{
		if (prefab == Entity.Null || (requiredPrefabs.ContainsKey(prefab) && (requiredPrefabs[prefab] & flags) != 0))
		{
			return false;
		}
		if (entityManager.TryGetBuffer(prefab, isReadOnly: true, out DynamicBuffer<UnlockRequirement> buffer))
		{
			for (int i = 0; i < buffer.Length; i++)
			{
				UnlockRequirement unlockRequirement = buffer[i];
				if (unlockRequirement.m_Prefab == prefab && (unlockRequirement.m_Flags & UnlockFlags.RequireAll) != 0)
				{
					return true;
				}
			}
			for (int j = 0; j < buffer.Length; j++)
			{
				UnlockRequirement unlockRequirement2 = buffer[j];
				if (unlockRequirement2.m_Prefab == prefab)
				{
					continue;
				}
				requiredPrefabs.Add(prefab, UnlockFlags.RequireAll | UnlockFlags.RequireAny);
				if (CollectSubRequirements(entityManager, unlockRequirement2.m_Prefab, requiredPrefabs, unlockRequirement2.m_Flags))
				{
					if (requiredPrefabs.ContainsKey(unlockRequirement2.m_Prefab))
					{
						requiredPrefabs[unlockRequirement2.m_Prefab] |= unlockRequirement2.m_Flags;
					}
					else
					{
						requiredPrefabs.Add(unlockRequirement2.m_Prefab, unlockRequirement2.m_Flags);
					}
				}
				requiredPrefabs.Remove(prefab);
			}
		}
		return false;
	}
```

- `public static GetRequiredMilestone(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Int32`  

```csharp
public static int GetRequiredMilestone(EntityManager entityManager, Entity entity)
	{
		int num = 0;
		if (entityManager.HasComponent<UnlockRequirement>(entity))
		{
			NativeParallelHashMap<Entity, UnlockFlags> requiredPrefabs = new NativeParallelHashMap<Entity, UnlockFlags>(10, Allocator.TempJob);
			CollectSubRequirements(entityManager, entity, requiredPrefabs);
			foreach (KeyValue<Entity, UnlockFlags> item in requiredPrefabs)
			{
				if ((item.Value & UnlockFlags.RequireAll) != 0 && entityManager.TryGetComponent<MilestoneData>(item.Key, out var component) && component.m_Index > num)
				{
					num = component.m_Index;
				}
			}
			requiredPrefabs.Dispose();
		}
		return num;
	}
```


