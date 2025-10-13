# Game.Tutorials.TutorialFireActivationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class TutorialFireActivationSystem : Game.GameSystemBase
{
    protected Unity.Entities.EntityCommandBufferSystem m_BarrierSystem;
    private Unity.Entities.EntityQuery m_BuildingFireQuery;
    private Unity.Entities.EntityQuery m_ForestFireQuery;
    private Unity.Entities.EntityQuery m_BuildingFireTutorialQuery;
    private Unity.Entities.EntityQuery m_ForestFireTutorialQuery;

    public TutorialFireActivationSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `protected Unity.Entities.EntityCommandBufferSystem m_BarrierSystem`  

```csharp
protected Unity.Entities.EntityCommandBufferSystem m_BarrierSystem;
```

- `private Unity.Entities.EntityQuery m_BuildingFireQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingFireQuery;
```

- `private Unity.Entities.EntityQuery m_ForestFireQuery`  

```csharp
private Unity.Entities.EntityQuery m_ForestFireQuery;
```

- `private Unity.Entities.EntityQuery m_BuildingFireTutorialQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingFireTutorialQuery;
```

- `private Unity.Entities.EntityQuery m_ForestFireTutorialQuery`  

```csharp
private Unity.Entities.EntityQuery m_ForestFireTutorialQuery;
```


## Constructors

- `public TutorialFireActivationSystem()`  

```csharp
[Preserve]
	public TutorialFireActivationSystem()
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
		m_BuildingFireQuery = GetEntityQuery(ComponentType.ReadOnly<OnFire>(), ComponentType.ReadOnly<Building>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_ForestFireQuery = GetEntityQuery(ComponentType.ReadOnly<OnFire>(), ComponentType.ReadOnly<Tree>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_BuildingFireTutorialQuery = GetEntityQuery(ComponentType.ReadOnly<BuildingFireActivationData>(), ComponentType.Exclude<TutorialActivated>(), ComponentType.Exclude<TutorialCompleted>());
		m_ForestFireTutorialQuery = GetEntityQuery(ComponentType.ReadOnly<ForestFireActivationData>(), ComponentType.Exclude<TutorialActivated>(), ComponentType.Exclude<TutorialCompleted>());
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		bool flag = !m_ForestFireQuery.IsEmptyIgnoreFilter && !m_ForestFireTutorialQuery.IsEmptyIgnoreFilter;
		bool flag2 = !m_BuildingFireQuery.IsEmptyIgnoreFilter && !m_BuildingFireTutorialQuery.IsEmptyIgnoreFilter;
		if (flag || flag2)
		{
			EntityCommandBuffer entityCommandBuffer = m_BarrierSystem.CreateCommandBuffer();
			if (flag)
			{
				entityCommandBuffer.AddComponent<TutorialActivated>(m_ForestFireTutorialQuery, EntityQueryCaptureMode.AtPlayback);
			}
			if (flag2)
			{
				entityCommandBuffer.AddComponent<TutorialActivated>(m_BuildingFireTutorialQuery, EntityQueryCaptureMode.AtPlayback);
			}
		}
	}
```


