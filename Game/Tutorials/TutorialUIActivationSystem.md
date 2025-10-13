# Game.Tutorials.TutorialUIActivationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Tutorials.ITutorialUIActivationSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TutorialUIActivationSystem : Game.GameSystemBase, Game.Tutorials.ITutorialUIActivationSystem
{
    protected Unity.Entities.EntityCommandBufferSystem m_BarrierSystem;
    private readonly System.Collections.Generic.Dictionary<System.String, System.Collections.Generic.List<Unity.Entities.Entity>> m_TutorialMap;
    private readonly System.Collections.Generic.List<System.String> m_ActiveTags;
    private Unity.Entities.EntityQuery m_TutorialQuery;

    public TutorialUIActivationSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
    private System.Void RebuildTutorialMap();
    public System.Void SetTag(System.String tag, System.Boolean active);
}
```


## Fields

- `protected Unity.Entities.EntityCommandBufferSystem m_BarrierSystem`  

```csharp
protected Unity.Entities.EntityCommandBufferSystem m_BarrierSystem;
```

- `private readonly System.Collections.Generic.Dictionary<System.String, System.Collections.Generic.List<Unity.Entities.Entity>> m_TutorialMap`  

```csharp
private readonly System.Collections.Generic.Dictionary<System.String, System.Collections.Generic.List<Unity.Entities.Entity>> m_TutorialMap;
```

- `private readonly System.Collections.Generic.List<System.String> m_ActiveTags`  

```csharp
private readonly System.Collections.Generic.List<System.String> m_ActiveTags;
```

- `private Unity.Entities.EntityQuery m_TutorialQuery`  

```csharp
private Unity.Entities.EntityQuery m_TutorialQuery;
```


## Constructors

- `public TutorialUIActivationSystem()`  

```csharp
[Preserve]
	public TutorialUIActivationSystem()
	{
	}
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_BarrierSystem = base.World.GetOrCreateSystemManaged<ModificationBarrier4>();
		m_TutorialQuery = GetEntityQuery(ComponentType.ReadOnly<UIActivationData>(), ComponentType.ReadOnly<PrefabData>());
		RebuildTutorialMap();
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		RebuildTutorialMap();
		m_ActiveTags.Clear();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (m_ActiveTags.Count <= 0)
		{
			return;
		}
		EntityCommandBuffer entityCommandBuffer = m_BarrierSystem.CreateCommandBuffer();
		foreach (string item in m_ActiveTags)
		{
			if (!m_TutorialMap.TryGetValue(item, out var value))
			{
				continue;
			}
			foreach (Entity item2 in value)
			{
				if (!base.EntityManager.HasComponent<TutorialCompleted>(item2))
				{
					base.EntityManager.AddComponent<TutorialActivated>(item2);
					if (!base.EntityManager.GetComponentData<UIActivationData>(item2).m_CanDeactivate)
					{
						entityCommandBuffer.AddComponent<ForceActivation>(item2);
					}
				}
			}
		}
	}
```

- `private RebuildTutorialMap() : System.Void`  

```csharp
private void RebuildTutorialMap()
	{
		m_TutorialMap.Clear();
		if (m_TutorialQuery.IsEmptyIgnoreFilter)
		{
			return;
		}
		NativeArray<Entity> nativeArray = m_TutorialQuery.ToEntityArray(Allocator.TempJob);
		PrefabSystem orCreateSystemManaged = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		for (int i = 0; i < nativeArray.Length; i++)
		{
			Entity item = nativeArray[i];
			string[] array = orCreateSystemManaged.GetPrefab<TutorialPrefab>(nativeArray[i]).GetComponent<TutorialUIActivation>().m_UITagProvider?.uiTag?.Split('|');
			if (array == null)
			{
				continue;
			}
			for (int j = 0; j < array.Length; j++)
			{
				string key = array[j].Trim();
				if (!m_TutorialMap.ContainsKey(key))
				{
					m_TutorialMap[key] = new List<Entity>();
				}
				if (!m_TutorialMap[key].Contains(item))
				{
					m_TutorialMap[key].Add(item);
				}
			}
		}
		nativeArray.Dispose();
	}
```

- `public SetTag(System.String tag, System.Boolean active) : System.Void`  

```csharp
public void SetTag(string tag, bool active)
	{
		if (m_TutorialMap.ContainsKey(tag))
		{
			m_ActiveTags.Remove(tag);
			if (active)
			{
				m_ActiveTags.Add(tag);
			}
		}
	}
```


