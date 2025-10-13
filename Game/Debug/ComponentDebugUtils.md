# Game.Debug.ComponentDebugUtils

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class ComponentDebugUtils
{
    public static System.Collections.Generic.List<Game.Debug.ComponentDebugUtils+ComponentInfo> GetCommonComponents(Unity.Entities.EntityManager entityManager, System.String filter, System.Boolean unusedOnly, System.Int32& archetypeCount, System.Int32& filteredArchetypeCount, System.Int32& chunkCount, System.Int32& chunkCapacity, System.Int32& entityCount);
    private static System.Boolean IsMatching(Unity.Entities.ComponentType type, System.String filter);
}
```


## Methods

- `public static GetCommonComponents(Unity.Entities.EntityManager entityManager, System.String filter, System.Boolean unusedOnly, System.Int32& archetypeCount, System.Int32& filteredArchetypeCount, System.Int32& chunkCount, System.Int32& chunkCapacity, System.Int32& entityCount) : System.Collections.Generic.List<Game.Debug.ComponentDebugUtils+ComponentInfo>`  

```csharp
public static List<ComponentInfo> GetCommonComponents(EntityManager entityManager, string filter, bool unusedOnly, out int archetypeCount, out int filteredArchetypeCount, out int chunkCount, out int chunkCapacity, out int entityCount)
	{
		Dictionary<ComponentType, ComponentInfo> dictionary = new Dictionary<ComponentType, ComponentInfo>();
		NativeList<EntityArchetype> allArchetypes = new NativeList<EntityArchetype>(Allocator.Temp);
		entityManager.GetAllArchetypes(allArchetypes);
		archetypeCount = allArchetypes.Length;
		filteredArchetypeCount = 0;
		foreach (EntityArchetype item in allArchetypes)
		{
			NativeArray<ComponentType> componentTypes = item.GetComponentTypes();
			bool flag = false;
			if (!string.IsNullOrEmpty(filter))
			{
				flag = true;
				foreach (ComponentType item2 in componentTypes)
				{
					if (dictionary.TryGetValue(item2, out var value))
					{
						if (value.m_Matching)
						{
							flag = false;
							break;
						}
					}
					else if (IsMatching(item2, filter))
					{
						flag = false;
						break;
					}
				}
			}
			if (!flag && (!unusedOnly || item.ChunkCount == 0))
			{
				filteredArchetypeCount++;
				foreach (ComponentType item3 in componentTypes)
				{
					if (dictionary.TryGetValue(item3, out var value2))
					{
						value2.m_ArchetypeCount++;
						value2.m_ChunkCount++;
						continue;
					}
					dictionary[item3] = new ComponentInfo
					{
						m_Type = item3.GetManagedType(),
						m_ArchetypeCount = 1,
						m_Matching = IsMatching(item3, filter),
						m_ChunkCount = item.ChunkCount
					};
				}
			}
			componentTypes.Dispose();
		}
		allArchetypes.Dispose();
		entityCount = 0;
		chunkCount = 0;
		chunkCapacity = 0;
		NativeArray<ArchetypeChunk> allChunks = entityManager.GetAllChunks(Allocator.Temp);
		foreach (ArchetypeChunk item4 in allChunks)
		{
			entityCount += item4.Count;
			chunkCount++;
			chunkCapacity += item4.Capacity;
			NativeArray<ComponentType> componentTypes2 = item4.Archetype.GetComponentTypes();
			foreach (ComponentType item5 in componentTypes2)
			{
				if (dictionary.TryGetValue(item5, out var value3))
				{
					value3.m_EntityCount += item4.Count;
					value3.m_ChunkCapacity += item4.Capacity;
				}
			}
			componentTypes2.Dispose();
		}
		allChunks.Dispose();
		return (from pair in dictionary
			select pair.Value into pair
			orderby pair.m_ArchetypeCount descending
			select pair).Take(100).ToList();
	}
```

- `private static IsMatching(Unity.Entities.ComponentType type, System.String filter) : System.Boolean`  

```csharp
private static bool IsMatching(ComponentType type, string filter)
	{
		return type.GetManagedType().FullName.ToLower().Contains(filter.ToLower());
	}
```


## Nested types

- `Game.Debug.ComponentDebugUtils+ComponentInfo`  
- `Game.Debug.ComponentDebugUtils+<>c`  

