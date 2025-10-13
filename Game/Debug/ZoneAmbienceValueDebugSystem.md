# Game.Debug.ZoneAmbienceValueDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

## Code

```csharp
public class ZoneAmbienceValueDebugSystem : Game.Debug.BaseDebugSystem
{
    private Game.Simulation.ZoneAmbienceSystem m_ZoneAmbienceSystem;
    private Colossal.GizmosSystem m_GizmosSystem;
    private System.Collections.Generic.Dictionary<Game.Simulation.GroupAmbienceType, Game.Debug.BaseDebugSystem+Option> m_CoverageOptions;
    private Unity.Collections.NativeArray<UnityEngine.Color> m_DistinctColors;

    public ZoneAmbienceValueDebugSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Game.Simulation.ZoneAmbienceSystem m_ZoneAmbienceSystem`  

```csharp
private Game.Simulation.ZoneAmbienceSystem m_ZoneAmbienceSystem;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private System.Collections.Generic.Dictionary<Game.Simulation.GroupAmbienceType, Game.Debug.BaseDebugSystem+Option> m_CoverageOptions`  

```csharp
private System.Collections.Generic.Dictionary<Game.Simulation.GroupAmbienceType, Game.Debug.BaseDebugSystem+Option> m_CoverageOptions;
```

- `private Unity.Collections.NativeArray<UnityEngine.Color> m_DistinctColors`  

```csharp
private Unity.Collections.NativeArray<UnityEngine.Color> m_DistinctColors;
```


## Constructors

- `public ZoneAmbienceValueDebugSystem()`  

```csharp
[Preserve]
	public ZoneAmbienceValueDebugSystem()
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
		m_ZoneAmbienceSystem = base.World.GetOrCreateSystemManaged<ZoneAmbienceSystem>();
		m_GizmosSystem = base.World.GetOrCreateSystemManaged<GizmosSystem>();
		m_CoverageOptions = new Dictionary<GroupAmbienceType, Option>();
		string[] names = Enum.GetNames(typeof(GroupAmbienceType));
		Array values = Enum.GetValues(typeof(GroupAmbienceType));
		for (int i = 0; i < names.Length; i++)
		{
			GroupAmbienceType groupAmbienceType = (GroupAmbienceType)values.GetValue(i);
			if (groupAmbienceType != GroupAmbienceType.Count)
			{
				m_CoverageOptions.Add(groupAmbienceType, AddOption(names[i], i == 0));
			}
		}
		m_DistinctColors = new NativeArray<Color>(22, Allocator.Persistent);
		for (int j = 0; j < 22; j++)
		{
			float h = (float)j / 22f % 1f;
			m_DistinctColors[j] = Color.HSVToRGB(h, 1f, 1f);
		}
		base.Enabled = false;
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		base.OnDestroy();
		m_DistinctColors.Dispose();
	}
```

- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
[Preserve]
	protected override JobHandle OnUpdate(JobHandle inputDeps)
	{
		JobHandle jobHandle = inputDeps;
		foreach (KeyValuePair<GroupAmbienceType, Option> coverageOption in m_CoverageOptions)
		{
			if (coverageOption.Value.enabled)
			{
				JobHandle dependencies;
				JobHandle dependencies2;
				JobHandle jobHandle2 = new ZoneAmbienceValueGizmoJob
				{
					m_Type = coverageOption.Key,
					m_AmbienceMap = m_ZoneAmbienceSystem.GetMap(readOnly: true, out dependencies),
					m_DistinctColors = m_DistinctColors,
					m_GizmoBatcher = m_GizmosSystem.GetGizmosBatcher(out dependencies2)
				}.Schedule(JobHandle.CombineDependencies(dependencies, dependencies2, base.Dependency));
				m_GizmosSystem.AddGizmosBatcherWriter(jobHandle2);
				jobHandle = JobHandle.CombineDependencies(jobHandle, jobHandle2);
			}
		}
		return jobHandle;
	}
```


## Nested types

- `Game.Debug.ZoneAmbienceValueDebugSystem+ZoneAmbienceValueGizmoJob`  

