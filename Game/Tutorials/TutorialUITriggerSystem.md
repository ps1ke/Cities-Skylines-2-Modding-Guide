# Game.Tutorials.TutorialUITriggerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.Tutorials.TutorialTriggerSystemBase`  
**Implements:** `Game.Tutorials.ITutorialUITriggerSystem`  

## Code

```csharp
public class TutorialUITriggerSystem : Game.Tutorials.TutorialTriggerSystemBase, Game.Tutorials.ITutorialUITriggerSystem
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
    private readonly System.Collections.Generic.HashSet<System.String> m_ActivatedTriggers;

    public TutorialUITriggerSystem();

    public System.Void ActivateTrigger(System.String trigger);
    public System.Void DisactivateTrigger(System.String trigger);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Unity.Entities.EntityArchetype m_UnlockEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
```

- `private readonly System.Collections.Generic.HashSet<System.String> m_ActivatedTriggers`  

```csharp
private readonly System.Collections.Generic.HashSet<System.String> m_ActivatedTriggers;
```


## Constructors

- `public TutorialUITriggerSystem()`  

```csharp
[Preserve]
	public TutorialUITriggerSystem()
	{
	}
```


## Methods

- `public ActivateTrigger(System.String trigger) : System.Void`  

```csharp
public void ActivateTrigger(string trigger)
	{
		m_ActivatedTriggers.Add(trigger);
	}
```

- `public DisactivateTrigger(System.String trigger) : System.Void`  

```csharp
public void DisactivateTrigger(string trigger)
	{
		m_ActivatedTriggers.Remove(trigger);
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_ActiveTriggerQuery = GetEntityQuery(ComponentType.ReadOnly<UITriggerData>(), ComponentType.ReadOnly<TriggerActive>(), ComponentType.Exclude<TriggerCompleted>());
		m_UnlockEventArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Event>(), ComponentType.ReadWrite<Unlock>());
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		base.OnUpdate();
		if (m_ActivatedTriggers.Count <= 0 || m_ActiveTriggerQuery.IsEmptyIgnoreFilter)
		{
			return;
		}
		NativeArray<Entity> nativeArray = m_ActiveTriggerQuery.ToEntityArray(Allocator.TempJob);
		EntityCommandBuffer commandBuffer = m_BarrierSystem.CreateCommandBuffer();
		for (int i = 0; i < nativeArray.Length; i++)
		{
			TutorialUITriggerPrefab.UITriggerInfo[] uITriggers = m_PrefabSystem.GetPrefab<TutorialUITriggerPrefab>(nativeArray[i]).m_UITriggers;
			foreach (TutorialUITriggerPrefab.UITriggerInfo uITriggerInfo in uITriggers)
			{
				string[] array = uITriggerInfo.m_UITagProvider.uiTag?.Split('|');
				if (array == null)
				{
					continue;
				}
				bool flag = false;
				for (int k = 0; k < array.Length; k++)
				{
					if (m_ActivatedTriggers.Contains(array[k]))
					{
						if (uITriggerInfo.m_GoToPhase != null)
						{
							Entity entity = m_PrefabSystem.GetEntity(uITriggerInfo.m_GoToPhase);
							commandBuffer.AddComponent(nativeArray[i], new TutorialNextPhase
							{
								m_NextPhase = entity
							});
							commandBuffer.AddComponent<TriggerPreCompleted>(nativeArray[i]);
						}
						else if (uITriggerInfo.m_CompleteManually)
						{
							commandBuffer.AddComponent<TriggerPreCompleted>(nativeArray[i]);
						}
						else
						{
							commandBuffer.AddComponent<TriggerCompleted>(nativeArray[i]);
						}
						TutorialSystem.ManualUnlock(nativeArray[i], m_UnlockEventArchetype, base.EntityManager, commandBuffer);
						DisactivateTrigger(array[k]);
						flag = true;
						break;
					}
				}
				if (flag)
				{
					break;
				}
			}
		}
		nativeArray.Dispose();
	}
```


