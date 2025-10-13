# Game.Tutorials.TutorialInputTriggerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.Tutorials.TutorialTriggerSystemBase`  

## Code

```csharp
public class TutorialInputTriggerSystem : Game.Tutorials.TutorialTriggerSystemBase
{
    private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;

    public TutorialInputTriggerSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
    private System.Boolean Performed(Game.Prefabs.TutorialInputTriggerPrefab prefab);
}
```


## Fields

- `private Unity.Entities.EntityArchetype m_UnlockEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```


## Constructors

- `public TutorialInputTriggerSystem()`  

```csharp
[Preserve]
	public TutorialInputTriggerSystem()
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
		m_ActiveTriggerQuery = GetEntityQuery(ComponentType.ReadOnly<InputTriggerData>(), ComponentType.ReadOnly<TriggerActive>(), ComponentType.Exclude<TriggerCompleted>());
		m_UnlockEventArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Event>(), ComponentType.ReadWrite<Unlock>());
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		RequireForUpdate(m_ActiveTriggerQuery);
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		base.OnUpdate();
		NativeArray<InputTriggerData> nativeArray = m_ActiveTriggerQuery.ToComponentDataArray<InputTriggerData>(Allocator.TempJob);
		NativeArray<Entity> nativeArray2 = m_ActiveTriggerQuery.ToEntityArray(Allocator.TempJob);
		EntityCommandBuffer commandBuffer = m_BarrierSystem.CreateCommandBuffer();
		for (int i = 0; i < nativeArray.Length; i++)
		{
			TutorialInputTriggerPrefab prefab = m_PrefabSystem.GetPrefab<TutorialInputTriggerPrefab>(nativeArray2[i]);
			if (Performed(prefab))
			{
				commandBuffer.AddComponent<TriggerCompleted>(nativeArray2[i]);
				TutorialSystem.ManualUnlock(nativeArray2[i], m_UnlockEventArchetype, base.EntityManager, commandBuffer);
			}
		}
		nativeArray.Dispose();
		nativeArray2.Dispose();
	}
```

- `private Performed(Game.Prefabs.TutorialInputTriggerPrefab prefab) : System.Boolean`  

```csharp
private bool Performed(TutorialInputTriggerPrefab prefab)
	{
		for (int i = 0; i < prefab.m_Actions.Length; i++)
		{
			if (InputManager.instance.TryFindAction(prefab.m_Actions[i].m_Map, prefab.m_Actions[i].m_Action, out var action) && action.WasPerformedThisFrame())
			{
				return true;
			}
		}
		return false;
	}
```


