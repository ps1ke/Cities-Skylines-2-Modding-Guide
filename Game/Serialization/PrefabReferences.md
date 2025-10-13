# Game.Serialization.PrefabReferences

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct PrefabReferences
{
    private Unity.Entities.ComponentLookup<Game.Prefabs.PrefabData> m_PrefabData;
    private Unity.Collections.NativeArray<Unity.Entities.Entity> m_PrefabArray;
    private Unity.Collections.LowLevel.Unsafe.UnsafeList<System.Boolean> m_ReferencedPrefabs;
    private Unity.Entities.Entity m_LastPrefabIn;
    private Unity.Entities.Entity m_LastPrefabOut;
    private System.Boolean m_IsLoading;

    public PrefabReferences(Unity.Collections.NativeArray<Unity.Entities.Entity> prefabArray, Unity.Collections.LowLevel.Unsafe.UnsafeList<System.Boolean> referencedPrefabs, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabData> prefabData, System.Boolean isLoading);

    public System.Void Check(Unity.Entities.Entity& prefab);
    public Unity.Entities.Entity Check(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity prefab);
    public System.Void SetDirty(Unity.Entities.Entity prefab);
}
```


## Fields

- `private Unity.Entities.ComponentLookup<Game.Prefabs.PrefabData> m_PrefabData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Prefabs.PrefabData> m_PrefabData;
```

- `private Unity.Collections.NativeArray<Unity.Entities.Entity> m_PrefabArray`  

```csharp
private Unity.Collections.NativeArray<Unity.Entities.Entity> m_PrefabArray;
```

- `private Unity.Collections.LowLevel.Unsafe.UnsafeList<System.Boolean> m_ReferencedPrefabs`  

```csharp
private Unity.Collections.LowLevel.Unsafe.UnsafeList<System.Boolean> m_ReferencedPrefabs;
```

- `private Unity.Entities.Entity m_LastPrefabIn`  

```csharp
private Unity.Entities.Entity m_LastPrefabIn;
```

- `private Unity.Entities.Entity m_LastPrefabOut`  

```csharp
private Unity.Entities.Entity m_LastPrefabOut;
```

- `private System.Boolean m_IsLoading`  

```csharp
private System.Boolean m_IsLoading;
```


## Constructors

- `public PrefabReferences(Unity.Collections.NativeArray<Unity.Entities.Entity> prefabArray, Unity.Collections.LowLevel.Unsafe.UnsafeList<System.Boolean> referencedPrefabs, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabData> prefabData, System.Boolean isLoading)`  

```csharp
public PrefabReferences(NativeArray<Entity> prefabArray, UnsafeList<bool> referencedPrefabs, ComponentLookup<PrefabData> prefabData, bool isLoading)
	{
		m_PrefabArray = prefabArray;
		m_ReferencedPrefabs = referencedPrefabs;
		m_PrefabData = prefabData;
		m_LastPrefabIn = Entity.Null;
		m_LastPrefabOut = Entity.Null;
		m_IsLoading = isLoading;
	}
```


## Methods

- `public Check(Unity.Entities.Entity& prefab) : System.Void`  

```csharp
public Entity Check(EntityManager entityManager, Entity prefab)
	{
		if (prefab == Entity.Null)
		{
			return Entity.Null;
		}
		if (m_IsLoading && entityManager.HasComponent<LoadedIndex>(prefab))
		{
			return prefab;
		}
		if (prefab != m_LastPrefabIn)
		{
			PrefabData componentData = entityManager.GetComponentData<PrefabData>(prefab);
			componentData.m_Index = math.select(componentData.m_Index, m_ReferencedPrefabs.Length + componentData.m_Index, componentData.m_Index < 0);
			m_LastPrefabIn = prefab;
			if (m_IsLoading)
			{
				m_LastPrefabOut = m_PrefabArray[componentData.m_Index];
				if (m_LastPrefabOut == m_LastPrefabIn)
				{
					m_ReferencedPrefabs[componentData.m_Index] = true;
				}
			}
			else
			{
				m_LastPrefabOut = prefab;
				m_ReferencedPrefabs[componentData.m_Index] = true;
			}
		}
		return m_LastPrefabOut;
	}
```

- `public Check(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity prefab) : Unity.Entities.Entity`  

```csharp
public Entity Check(EntityManager entityManager, Entity prefab)
	{
		if (prefab == Entity.Null)
		{
			return Entity.Null;
		}
		if (m_IsLoading && entityManager.HasComponent<LoadedIndex>(prefab))
		{
			return prefab;
		}
		if (prefab != m_LastPrefabIn)
		{
			PrefabData componentData = entityManager.GetComponentData<PrefabData>(prefab);
			componentData.m_Index = math.select(componentData.m_Index, m_ReferencedPrefabs.Length + componentData.m_Index, componentData.m_Index < 0);
			m_LastPrefabIn = prefab;
			if (m_IsLoading)
			{
				m_LastPrefabOut = m_PrefabArray[componentData.m_Index];
				if (m_LastPrefabOut == m_LastPrefabIn)
				{
					m_ReferencedPrefabs[componentData.m_Index] = true;
				}
			}
			else
			{
				m_LastPrefabOut = prefab;
				m_ReferencedPrefabs[componentData.m_Index] = true;
			}
		}
		return m_LastPrefabOut;
	}
```

- `public SetDirty(Unity.Entities.Entity prefab) : System.Void`  

```csharp
public void SetDirty(Entity prefab)
	{
		if (!m_IsLoading)
		{
			PrefabData prefabData = m_PrefabData[prefab];
			if (prefabData.m_Index >= 0)
			{
				m_ReferencedPrefabs[prefabData.m_Index] = true;
			}
		}
	}
```


