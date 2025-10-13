# Game.Tutorials.TutorialUIDeactivationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.Tutorials.TutorialDeactivationSystemBase`  
**Implements:** `Game.Tutorials.ITutorialUIDeactivationSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TutorialUIDeactivationSystem : Game.Tutorials.TutorialDeactivationSystemBase, Game.Tutorials.ITutorialUIDeactivationSystem
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private readonly System.Collections.Generic.HashSet<System.String> m_Deactivate;
    private Unity.Entities.EntityQuery m_PendingTutorialQuery;
    private Unity.Entities.EntityQuery m_ActiveTutorialQuery;

    public TutorialUIDeactivationSystem();

    private System.Void CheckDeactivate(Unity.Entities.EntityQuery query);
    public System.Void DeactivateTag(System.String tag);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private readonly System.Collections.Generic.HashSet<System.String> m_Deactivate`  

```csharp
private readonly System.Collections.Generic.HashSet<System.String> m_Deactivate;
```

- `private Unity.Entities.EntityQuery m_PendingTutorialQuery`  

```csharp
private Unity.Entities.EntityQuery m_PendingTutorialQuery;
```

- `private Unity.Entities.EntityQuery m_ActiveTutorialQuery`  

```csharp
private Unity.Entities.EntityQuery m_ActiveTutorialQuery;
```


## Constructors

- `public TutorialUIDeactivationSystem()`  

```csharp
[Preserve]
	public TutorialUIDeactivationSystem()
	{
	}
```


## Methods

- `private CheckDeactivate(Unity.Entities.EntityQuery query) : System.Void`  

```csharp
private void CheckDeactivate(EntityQuery query)
	{
		NativeArray<PrefabData> nativeArray = query.ToComponentDataArray<PrefabData>(Allocator.TempJob);
		NativeArray<Entity> nativeArray2 = query.ToEntityArray(Allocator.TempJob);
		EntityCommandBuffer entityCommandBuffer = m_BarrierSystem.CreateCommandBuffer();
		for (int i = 0; i < nativeArray2.Length; i++)
		{
			string[] array = m_PrefabSystem.GetPrefab<TutorialPrefab>(nativeArray[i]).GetComponent<TutorialUIActivation>().m_UITagProvider.uiTag?.Split('|');
			if (array == null)
			{
				continue;
			}
			for (int j = 0; j < array.Length; j++)
			{
				if (m_Deactivate.Contains(array[j].Trim()))
				{
					entityCommandBuffer.RemoveComponent<TutorialActivated>(nativeArray2[i]);
				}
			}
		}
		nativeArray.Dispose();
		nativeArray2.Dispose();
	}
```

- `public DeactivateTag(System.String tag) : System.Void`  

```csharp
public void DeactivateTag(string tag)
	{
		m_Deactivate.Add(tag);
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_PendingTutorialQuery = GetEntityQuery(ComponentType.ReadOnly<UIActivationData>(), ComponentType.ReadOnly<TutorialData>(), ComponentType.ReadOnly<TutorialActivated>(), ComponentType.ReadOnly<PrefabData>(), ComponentType.Exclude<TutorialActive>(), ComponentType.Exclude<TutorialCompleted>(), ComponentType.Exclude<ForceActivation>());
		m_ActiveTutorialQuery = GetEntityQuery(ComponentType.ReadOnly<UIActivationData>(), ComponentType.ReadOnly<TutorialData>(), ComponentType.ReadOnly<TutorialActivated>(), ComponentType.ReadOnly<PrefabData>(), ComponentType.ReadOnly<TutorialActive>(), ComponentType.Exclude<TutorialCompleted>(), ComponentType.Exclude<ForceActivation>());
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (m_Deactivate.Count > 0)
		{
			if (!m_PendingTutorialQuery.IsEmptyIgnoreFilter)
			{
				CheckDeactivate(m_PendingTutorialQuery);
			}
			if (!m_ActiveTutorialQuery.IsEmptyIgnoreFilter && base.phaseCanDeactivate)
			{
				CheckDeactivate(m_ActiveTutorialQuery);
			}
		}
		m_Deactivate.Clear();
	}
```


