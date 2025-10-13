# Game.Debug.PathfindDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

## Code

```csharp
public class PathfindDebugSystem : Game.Debug.BaseDebugSystem
{
    private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem;
    private Colossal.GizmosSystem m_GizmosSystem;
    private Game.Rendering.RenderingSystem m_RenderingSystem;
    private Unity.Collections.NativeList<Game.Debug.PathfindDebugSystem+PathfindLine> m_PathfindLines;
    private Game.Debug.BaseDebugSystem+Option m_GraphOption;
    private Game.Debug.BaseDebugSystem+Option m_RestrictedOption;
    private Game.Debug.BaseDebugSystem+Option m_TimeCostOption;
    private Game.Debug.BaseDebugSystem+Option m_BehaviorCostOption;
    private Game.Debug.BaseDebugSystem+Option m_MoneyCostOption;
    private Game.Debug.BaseDebugSystem+Option m_ComfortCostOption;
    private Game.Debug.BaseDebugSystem+Option m_PathfindOption;

    public PathfindDebugSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem`  

```csharp
private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  

```csharp
private Game.Rendering.RenderingSystem m_RenderingSystem;
```

- `private Unity.Collections.NativeList<Game.Debug.PathfindDebugSystem+PathfindLine> m_PathfindLines`  

```csharp
private Unity.Collections.NativeList<Game.Debug.PathfindDebugSystem+PathfindLine> m_PathfindLines;
```

- `private Game.Debug.BaseDebugSystem+Option m_GraphOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_GraphOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_RestrictedOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_RestrictedOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_TimeCostOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_TimeCostOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_BehaviorCostOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_BehaviorCostOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_MoneyCostOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_MoneyCostOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_ComfortCostOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_ComfortCostOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_PathfindOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_PathfindOption;
```


## Constructors

- `public PathfindDebugSystem()`  

```csharp
[Preserve]
	public PathfindDebugSystem()
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
		m_PathfindQueueSystem = base.World.GetOrCreateSystemManaged<PathfindQueueSystem>();
		m_GizmosSystem = base.World.GetOrCreateSystemManaged<GizmosSystem>();
		m_RenderingSystem = base.World.GetOrCreateSystemManaged<RenderingSystem>();
		m_PathfindLines = new NativeList<PathfindLine>(Allocator.Persistent);
		m_GraphOption = AddOption("Draw Graph", defaultEnabled: true);
		m_RestrictedOption = AddOption("Show Restrictions", defaultEnabled: false);
		m_TimeCostOption = AddOption("Show time cost", defaultEnabled: false);
		m_BehaviorCostOption = AddOption("Show behavior cost", defaultEnabled: false);
		m_MoneyCostOption = AddOption("Show money cost", defaultEnabled: false);
		m_ComfortCostOption = AddOption("Show comfort cost", defaultEnabled: false);
		m_PathfindOption = AddOption("Visualize Queries", defaultEnabled: true);
		base.Enabled = false;
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		m_PathfindLines.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
[Preserve]
	protected unsafe override JobHandle OnUpdate(JobHandle inputDeps)
	{
		if (!m_GraphOption.enabled && !m_PathfindOption.enabled)
		{
			return inputDeps;
		}
		JobHandle jobHandle = inputDeps;
		JobHandle dependencies;
		NativePathfindData dataContainer = m_PathfindQueueSystem.GetDataContainer(out dependencies);
		inputDeps = JobHandle.CombineDependencies(inputDeps, dependencies);
		if (m_GraphOption.enabled)
		{
			NativeReference<int> nativeReference = new NativeReference<int>(Allocator.TempJob);
			EdgeCountJob jobData = new EdgeCountJob
			{
				m_PathfindData = dataContainer,
				m_EdgeCount = nativeReference
			};
			JobHandle dependencies2;
			JobHandle jobHandle2 = new PathfindEdgeGizmoJob
			{
				m_RestrictedOption = m_RestrictedOption.enabled,
				m_CostOptions = new bool4(m_TimeCostOption.enabled, m_BehaviorCostOption.enabled, m_MoneyCostOption.enabled, m_ComfortCostOption.enabled),
				m_PathfindData = dataContainer,
				m_GizmoBatcher = m_GizmosSystem.GetGizmosBatcher(out dependencies2)
			}.Schedule(dependsOn: JobHandle.CombineDependencies(IJobExtensions.Schedule(jobData, inputDeps), dependencies2), forEachCount: nativeReference.GetUnsafePtrWithoutChecks(), innerloopBatchCount: 64);
			nativeReference.Dispose(jobHandle2);
			m_GizmosSystem.AddGizmosBatcherWriter(jobHandle2);
			m_PathfindQueueSystem.AddDataReader(jobHandle2);
			jobHandle = JobHandle.CombineDependencies(jobHandle, jobHandle2);
		}
		if (m_PathfindOption.enabled)
		{
			m_PathfindQueueSystem.RequireDebug();
			PathfindQueueSystem.ActionList<PathfindAction> pathfindActions = m_PathfindQueueSystem.GetPathfindActions();
			JobHandle jobHandle3 = inputDeps;
			for (int i = 0; i < pathfindActions.m_Items.Count; i++)
			{
				PathfindQueueSystem.ActionListItem<PathfindAction> value = pathfindActions.m_Items[i];
				if ((value.m_Flags & PathFlags.Debug) == 0)
				{
					JobHandle jobHandle4 = IJobExtensions.Schedule(new FillPathfindGizmoLinesJob
					{
						m_Action = value.m_Action,
						m_Owner = value.m_Owner,
						m_Flags = PathFlags.Pending,
						m_PathfindLines = m_PathfindLines,
						m_PathfindData = dataContainer
					}, JobHandle.CombineDependencies(jobHandle3, value.m_Dependencies));
					m_PathfindQueueSystem.AddDataReader(jobHandle4);
					jobHandle3 = jobHandle4;
					value.m_Dependencies = jobHandle4;
					value.m_Flags |= PathFlags.Debug;
					pathfindActions.m_Items[i] = value;
				}
				if ((value.m_Flags & (PathFlags.Pending | PathFlags.Scheduled)) == 0)
				{
					PathFlags pathFlags = (PathFlags)0;
					bool tooLong = false;
					if (value.m_Action.readOnlyData.m_Result[0].m_Distance < 0f)
					{
						pathFlags |= PathFlags.Failed;
						tooLong = value.m_Action.readOnlyData.m_Result[0].m_TotalCost > 0f;
					}
					jobHandle3 = IJobExtensions.Schedule(new SetPathfindGizmoLineFlagsJob
					{
						m_Owner = value.m_Owner,
						m_Flags = pathFlags,
						m_TooLong = tooLong,
						m_PathfindLines = m_PathfindLines
					}, jobHandle3);
				}
			}
			JobHandle dependencies3;
			JobHandle jobHandle5 = IJobExtensions.Schedule(new PathfindLineGizmoJob
			{
				m_DeltaTime = m_RenderingSystem.frameDelta / 60f,
				m_PathfindLines = m_PathfindLines,
				m_GizmoBatcher = m_GizmosSystem.GetGizmosBatcher(out dependencies3)
			}, JobHandle.CombineDependencies(jobHandle3, dependencies3));
			m_GizmosSystem.AddGizmosBatcherWriter(jobHandle5);
			jobHandle = JobHandle.CombineDependencies(jobHandle, jobHandle5);
		}
		return jobHandle;
	}
```


## Nested types

- `Game.Debug.PathfindDebugSystem+PathfindLine`  
- `Game.Debug.PathfindDebugSystem+EdgeCountJob`  
- `Game.Debug.PathfindDebugSystem+PathfindEdgeGizmoJob`  
- `Game.Debug.PathfindDebugSystem+FillPathfindGizmoLinesJob`  
- `Game.Debug.PathfindDebugSystem+SetPathfindGizmoLineFlagsJob`  
- `Game.Debug.PathfindDebugSystem+PathfindLineGizmoJob`  

