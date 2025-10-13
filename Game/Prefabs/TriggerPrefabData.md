# Game.Prefabs.TriggerPrefabData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public sealed struct TriggerPrefabData : System.IDisposable
{
    private Unity.Collections.NativeParallelMultiHashMap<Game.Prefabs.TriggerPrefabData+PrefabKey, Game.Prefabs.TriggerPrefabData+PrefabValue> m_PrefabMap;

    public TriggerPrefabData(Unity.Collections.Allocator allocator);

    public System.Void AddPrefab(Unity.Entities.Entity prefab, Game.Prefabs.TriggerData triggerData);
    public System.Void Dispose();
    public System.Boolean HasAnyPrefabs(Game.Triggers.TriggerType triggerType, Unity.Entities.Entity triggerPrefab);
    public System.Void RemovePrefab(Unity.Entities.Entity prefab, Game.Prefabs.TriggerData triggerData);
    public System.Boolean TryGetFirstPrefab(Game.Triggers.TriggerType triggerType, Game.Triggers.TargetType targetType, Unity.Entities.Entity triggerPrefab, Unity.Entities.Entity& prefab, Game.Prefabs.TriggerPrefabData+Iterator& iterator);
    public System.Boolean TryGetNextPrefab(Game.Triggers.TriggerType triggerType, Game.Triggers.TargetType targetType, Unity.Entities.Entity triggerPrefab, Unity.Entities.Entity& prefab, Game.Prefabs.TriggerPrefabData+Iterator& iterator);
}
```


## Fields

- `private Unity.Collections.NativeParallelMultiHashMap<Game.Prefabs.TriggerPrefabData+PrefabKey, Game.Prefabs.TriggerPrefabData+PrefabValue> m_PrefabMap`  

```csharp
private Unity.Collections.NativeParallelMultiHashMap<Game.Prefabs.TriggerPrefabData+PrefabKey, Game.Prefabs.TriggerPrefabData+PrefabValue> m_PrefabMap;
```


## Constructors

- `public TriggerPrefabData(Unity.Collections.Allocator allocator)`  

```csharp
public TriggerPrefabData(Allocator allocator)
	{
		m_PrefabMap = new NativeParallelMultiHashMap<PrefabKey, PrefabValue>(100, allocator);
	}
```


## Methods

- `public AddPrefab(Unity.Entities.Entity prefab, Game.Prefabs.TriggerData triggerData) : System.Void`  

```csharp
public void AddPrefab(Entity prefab, TriggerData triggerData)
	{
		PrefabKey key = new PrefabKey
		{
			m_TriggerType = triggerData.m_TriggerType,
			m_TriggerEntity = triggerData.m_TriggerPrefab
		};
		PrefabValue item = new PrefabValue
		{
			m_TargetTypes = triggerData.m_TargetTypes,
			m_Prefab = prefab
		};
		m_PrefabMap.Add(key, item);
	}
```

- `public Dispose() : System.Void`  

```csharp
public void Dispose()
	{
		m_PrefabMap.Dispose();
	}
```

- `public HasAnyPrefabs(Game.Triggers.TriggerType triggerType, Unity.Entities.Entity triggerPrefab) : System.Boolean`  

```csharp
public bool HasAnyPrefabs(TriggerType triggerType, Entity triggerPrefab)
	{
		PrefabKey key = new PrefabKey
		{
			m_TriggerType = triggerType,
			m_TriggerEntity = triggerPrefab
		};
		PrefabValue item;
		NativeParallelMultiHashMapIterator<PrefabKey> it;
		return m_PrefabMap.TryGetFirstValue(key, out item, out it);
	}
```

- `public RemovePrefab(Unity.Entities.Entity prefab, Game.Prefabs.TriggerData triggerData) : System.Void`  

```csharp
public void RemovePrefab(Entity prefab, TriggerData triggerData)
	{
		PrefabKey key = new PrefabKey
		{
			m_TriggerType = triggerData.m_TriggerType,
			m_TriggerEntity = triggerData.m_TriggerPrefab
		};
		if (!m_PrefabMap.TryGetFirstValue(key, out var item, out var it))
		{
			return;
		}
		do
		{
			if (item.m_TargetTypes == triggerData.m_TargetTypes && item.m_Prefab == prefab)
			{
				m_PrefabMap.Remove(it);
				break;
			}
		}
		while (m_PrefabMap.TryGetNextValue(out item, ref it));
	}
```

- `public TryGetFirstPrefab(Game.Triggers.TriggerType triggerType, Game.Triggers.TargetType targetType, Unity.Entities.Entity triggerPrefab, Unity.Entities.Entity& prefab, Game.Prefabs.TriggerPrefabData+Iterator& iterator) : System.Boolean`  

```csharp
public bool TryGetFirstPrefab(TriggerType triggerType, TargetType targetType, Entity triggerPrefab, out Entity prefab, out Iterator iterator)
	{
		PrefabKey key = new PrefabKey
		{
			m_TriggerType = triggerType,
			m_TriggerEntity = triggerPrefab
		};
		if (m_PrefabMap.TryGetFirstValue(key, out var item, out iterator.m_Iterator))
		{
			do
			{
				if (targetType == TargetType.Nothing || (item.m_TargetTypes & targetType) != TargetType.Nothing)
				{
					prefab = item.m_Prefab;
					return true;
				}
			}
			while (m_PrefabMap.TryGetNextValue(out item, ref iterator.m_Iterator));
		}
		prefab = Entity.Null;
		return false;
	}
```

- `public TryGetNextPrefab(Game.Triggers.TriggerType triggerType, Game.Triggers.TargetType targetType, Unity.Entities.Entity triggerPrefab, Unity.Entities.Entity& prefab, Game.Prefabs.TriggerPrefabData+Iterator& iterator) : System.Boolean`  

```csharp
public bool TryGetNextPrefab(TriggerType triggerType, TargetType targetType, Entity triggerPrefab, out Entity prefab, ref Iterator iterator)
	{
		PrefabKey prefabKey = new PrefabKey
		{
			m_TriggerType = triggerType,
			m_TriggerEntity = triggerPrefab
		};
		PrefabValue item;
		while (m_PrefabMap.TryGetNextValue(out item, ref iterator.m_Iterator))
		{
			if (targetType == TargetType.Nothing || (item.m_TargetTypes & targetType) != TargetType.Nothing)
			{
				prefab = item.m_Prefab;
				return true;
			}
		}
		prefab = Entity.Null;
		return false;
	}
```


## Nested types

- `Game.Prefabs.TriggerPrefabData+PrefabKey`  
- `Game.Prefabs.TriggerPrefabData+PrefabValue`  
- `Game.Prefabs.TriggerPrefabData+Iterator`  

