# Game.UpdateSystem

**Assembly:** `Game`  
**Namespace:** `Game`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class UpdateSystem : Game.GameSystemBase
{
    private System.Collections.Generic.List<Game.IGPUSystem> m_GPUSystems;
    private System.Collections.Generic.List<Game.UpdateSystem+SystemData> m_Systems;
    private System.Collections.Generic.List<Game.UpdateSystem+SystemData> m_Updates;
    private System.Collections.Generic.List<Unity.Mathematics.int2> m_UpdateRanges;
    private System.Collections.Generic.Dictionary<Unity.Entities.ComponentSystemBase, System.Collections.Generic.List<Game.UpdateSystem+SystemData>> m_RefMap;
    private System.Int32 m_AddIndex;
    private System.Boolean m_IsDirty;
    private Game.SystemUpdatePhase <currentPhase>k__BackingField;

    public Game.SystemUpdatePhase currentPhase { get; private set; }

    public UpdateSystem();

    private System.Void AddSystemUpdate(System.Collections.Generic.List<Game.UpdateSystem+IntervalData> intervalList, Game.UpdateSystem+SystemData systemData, System.Boolean inheritOffset, System.Int32 safety);
    public static System.Void GetInterval(Unity.Entities.ComponentSystemBase system, Game.SystemUpdatePhase phase, System.Int32& interval, System.Int32& offset);
    protected virtual System.Void OnBeginFrame(UnityEngine.Rendering.ScriptableRenderContext renderContext, UnityEngine.Camera[] cameras);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    private System.Void PatchSystemOffset(System.Int32& updateIndex, Game.UpdateSystem+SystemData systemData, System.Boolean inheritOffset, System.Int32 safety);
    private System.Void Refresh();
    private System.Void Register(System.Int32 addIndex, Unity.Entities.ComponentSystemBase system, Game.SystemUpdatePhase phase);
    private System.Void Register(System.Int32 addIndex, Unity.Entities.ComponentSystemBase system, Unity.Entities.ComponentSystemBase other, Game.SystemUpdatePhase phase);
    public System.Void RegisterGPUSystem<SystemType>();
    public System.Void RegisterGPUSystem(Game.IGPUSystem system);
    public System.Void Update(Game.SystemUpdatePhase phase);
    public System.Void Update(Game.SystemUpdatePhase phase, System.UInt32 updateIndex, System.Int32 iterationIndex);
    public System.Void UpdateAfter<SystemType>(Game.SystemUpdatePhase phase);
    public System.Void UpdateAfter<SystemType, OtherType>(Game.SystemUpdatePhase phase);
    public System.Void UpdateAt<SystemType>(Game.SystemUpdatePhase phase);
    public System.Void UpdateBefore<SystemType>(Game.SystemUpdatePhase phase);
    public System.Void UpdateBefore<SystemType, OtherType>(Game.SystemUpdatePhase phase);
}
```


## Fields

- `private System.Collections.Generic.List<Game.IGPUSystem> m_GPUSystems`  

```csharp
private System.Collections.Generic.List<Game.IGPUSystem> m_GPUSystems;
```

- `private System.Collections.Generic.List<Game.UpdateSystem+SystemData> m_Systems`  

```csharp
private System.Collections.Generic.List<Game.UpdateSystem+SystemData> m_Systems;
```

- `private System.Collections.Generic.List<Game.UpdateSystem+SystemData> m_Updates`  

```csharp
private System.Collections.Generic.List<Game.UpdateSystem+SystemData> m_Updates;
```

- `private System.Collections.Generic.List<Unity.Mathematics.int2> m_UpdateRanges`  

```csharp
private System.Collections.Generic.List<Unity.Mathematics.int2> m_UpdateRanges;
```

- `private System.Collections.Generic.Dictionary<Unity.Entities.ComponentSystemBase, System.Collections.Generic.List<Game.UpdateSystem+SystemData>> m_RefMap`  

```csharp
private System.Collections.Generic.Dictionary<Unity.Entities.ComponentSystemBase, System.Collections.Generic.List<Game.UpdateSystem+SystemData>> m_RefMap;
```

- `private System.Int32 m_AddIndex`  

```csharp
private System.Int32 m_AddIndex;
```

- `private System.Boolean m_IsDirty`  

```csharp
private System.Boolean m_IsDirty;
```

- `private Game.SystemUpdatePhase <currentPhase>k__BackingField`  

```csharp
private Game.SystemUpdatePhase <currentPhase>k__BackingField;
```


## Properties

- `public Game.SystemUpdatePhase currentPhase { get; private set }`  

```csharp
public Game.SystemUpdatePhase currentPhase { get; private set; }
```


## Constructors

- `public UpdateSystem()`  

```csharp
[Preserve]
	public UpdateSystem()
	{
	}
```


## Methods

- `private AddSystemUpdate(System.Collections.Generic.List<Game.UpdateSystem+IntervalData> intervalList, Game.UpdateSystem+SystemData systemData, System.Boolean inheritOffset, System.Int32 safety) : System.Void`  

```csharp
private void AddSystemUpdate(List<IntervalData> intervalList, SystemData systemData, bool inheritOffset, int safety)
	{
		if (++safety == 100)
		{
			throw new Exception("Too deep system order");
		}
		if (m_RefMap.TryGetValue(systemData.m_System, out var value))
		{
			if (value.Count >= 2)
			{
				value.Sort();
			}
			int count = m_Updates.Count;
			int num = 0;
			while (num < value.Count)
			{
				SystemData systemData2 = value[num++];
				if (systemData2.m_Phase == systemData.m_Phase)
				{
					if (systemData2.m_AddIndex >= 0)
					{
						num--;
						break;
					}
					bool flag = systemData2.m_Interval == systemData.m_Interval && systemData2.m_Offset < 0;
					if (flag)
					{
						systemData2.m_Offset = systemData.m_Offset;
					}
					AddSystemUpdate(intervalList, systemData2, flag, safety);
				}
			}
			if (systemData.m_Offset < 0)
			{
				if (systemData.m_Interval == 1)
				{
					systemData.m_Offset = 0;
				}
				else if (!inheritOffset)
				{
					intervalList.Add(new IntervalData(systemData.m_Interval, count, m_Updates.Count));
				}
			}
			m_Updates.Add(systemData);
			while (num < value.Count)
			{
				SystemData systemData3 = value[num++];
				if (systemData3.m_Phase == systemData.m_Phase)
				{
					bool flag2 = systemData3.m_Interval == systemData.m_Interval && systemData3.m_Offset < 0;
					if (flag2)
					{
						systemData3.m_Offset = systemData.m_Offset;
					}
					AddSystemUpdate(intervalList, systemData3, flag2, safety);
					continue;
				}
				break;
			}
			return;
		}
		if (systemData.m_Offset < 0)
		{
			if (systemData.m_Interval == 1)
			{
				systemData.m_Offset = 0;
			}
			else if (!inheritOffset)
			{
				intervalList.Add(new IntervalData(systemData.m_Interval, m_Updates.Count, m_Updates.Count));
			}
		}
		m_Updates.Add(systemData);
	}
```

- `public static GetInterval(Unity.Entities.ComponentSystemBase system, Game.SystemUpdatePhase phase, System.Int32& interval, System.Int32& offset) : System.Void`  

```csharp
public static void GetInterval(ComponentSystemBase system, SystemUpdatePhase phase, out int interval, out int offset)
	{
		interval = 1;
		offset = -1;
		if (system is GameSystemBase gameSystemBase)
		{
			interval = gameSystemBase.GetUpdateInterval(phase);
			offset = gameSystemBase.GetUpdateOffset(phase);
		}
		if (!math.ispow2(interval))
		{
			throw new Exception("System update interval not power of 2");
		}
	}
```

- `protected virtual OnBeginFrame(UnityEngine.Rendering.ScriptableRenderContext renderContext, UnityEngine.Camera[] cameras) : System.Void`  

```csharp
protected virtual void OnBeginFrame(ScriptableRenderContext renderContext, Camera[] cameras)
	{
		foreach (IGPUSystem gPUSystem in m_GPUSystems)
		{
			if (gPUSystem.Enabled)
			{
				CommandBuffer commandBuffer = CommandBufferPool.Get("");
				if (gPUSystem.IsAsync)
				{
					commandBuffer.SetExecutionFlags(CommandBufferExecutionFlags.AsyncCompute);
				}
				gPUSystem.OnSimulateGPU(commandBuffer);
				if (gPUSystem.IsAsync)
				{
					renderContext.ExecuteCommandBufferAsync(commandBuffer, ComputeQueueType.Default);
				}
				else
				{
					renderContext.ExecuteCommandBuffer(commandBuffer);
				}
				renderContext.Submit();
				commandBuffer.Clear();
				CommandBufferPool.Release(commandBuffer);
			}
		}
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		RenderPipelineManager.beginFrameRendering += OnBeginFrame;
		m_GPUSystems = new List<IGPUSystem>();
		m_Systems = new List<SystemData>(1000);
		m_Updates = new List<SystemData>(1000);
		m_UpdateRanges = new List<int2>(100);
		m_RefMap = new Dictionary<ComponentSystemBase, List<SystemData>>(100);
		currentPhase = SystemUpdatePhase.Invalid;
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		RenderPipelineManager.beginFrameRendering -= OnBeginFrame;
		m_GPUSystems.Clear();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
	}
```

- `private PatchSystemOffset(System.Int32& updateIndex, Game.UpdateSystem+SystemData systemData, System.Boolean inheritOffset, System.Int32 safety) : System.Void`  

```csharp
private void PatchSystemOffset(ref int updateIndex, SystemData systemData, bool inheritOffset, int safety)
	{
		if (++safety == 100)
		{
			throw new Exception("Too deep system order");
		}
		if (m_RefMap.TryGetValue(systemData.m_System, out var value))
		{
			int num = 0;
			while (num < value.Count)
			{
				SystemData systemData2 = value[num++];
				if (systemData2.m_Phase == systemData.m_Phase)
				{
					if (systemData2.m_AddIndex >= 0)
					{
						num--;
						break;
					}
					bool flag = systemData2.m_Interval == systemData.m_Interval && systemData2.m_Offset < 0;
					if (flag)
					{
						systemData2.m_Offset = systemData.m_Offset;
					}
					PatchSystemOffset(ref updateIndex, systemData2, flag, safety);
				}
			}
			if (inheritOffset)
			{
				SystemData value2 = m_Updates[updateIndex];
				value2.m_Offset = systemData.m_Offset;
				m_Updates[updateIndex] = value2;
			}
			updateIndex++;
			while (num < value.Count)
			{
				SystemData systemData3 = value[num++];
				if (systemData3.m_Phase == systemData.m_Phase)
				{
					bool flag2 = systemData3.m_Interval == systemData.m_Interval && systemData3.m_Offset < 0;
					if (flag2)
					{
						systemData3.m_Offset = systemData.m_Offset;
					}
					PatchSystemOffset(ref updateIndex, systemData3, flag2, safety);
					continue;
				}
				break;
			}
		}
		else
		{
			if (inheritOffset)
			{
				SystemData value3 = m_Updates[updateIndex];
				value3.m_Offset = systemData.m_Offset;
				m_Updates[updateIndex] = value3;
			}
			updateIndex++;
		}
	}
```

- `private Refresh() : System.Void`  

```csharp
private void Refresh()
	{
		m_IsDirty = false;
		m_Updates.Clear();
		m_UpdateRanges.Clear();
		if (m_Systems.Count >= 2)
		{
			m_Systems.Sort();
		}
		List<IntervalData> list = new List<IntervalData>(1000);
		int num = 0;
		while (num < m_Systems.Count)
		{
			int count = m_Updates.Count;
			list.Clear();
			SystemData systemData = m_Systems[num];
			SystemUpdatePhase phase = systemData.m_Phase;
			AddSystemUpdate(list, systemData, inheritOffset: false, 0);
			int i;
			for (i = num + 1; i < m_Systems.Count; i++)
			{
				SystemData systemData2 = m_Systems[i];
				if (systemData2.m_Phase != systemData.m_Phase)
				{
					break;
				}
				AddSystemUpdate(list, systemData2, inheritOffset: false, 0);
			}
			if (list.Count != 0)
			{
				if (list.Count >= 2)
				{
					list.Sort();
				}
				int num2 = 0;
				int num3 = 0;
				int num4 = 0;
				for (int j = 0; j < list.Count; j++)
				{
					IntervalData intervalData = list[j];
					if (intervalData.m_Interval != num2)
					{
						num2 = intervalData.m_Interval;
						num4 = 0;
					}
					systemData = m_Updates[intervalData.m_UpdateIndex];
					systemData.m_Offset = num3;
					PatchSystemOffset(ref intervalData.m_UpdateStart, systemData, inheritOffset: true, 0);
					num4++;
					int num5 = 0;
					while ((num4 & (1 << num5++)) == 0)
					{
					}
					num3 += num2 >> num5;
					num3 &= num2 - 1;
					if (num4 << 1 >= num2)
					{
						num4 = 0;
					}
				}
			}
			if (m_Updates.Count > count)
			{
				while (m_UpdateRanges.Count < (int)phase)
				{
					m_UpdateRanges.Add(count);
				}
				m_UpdateRanges.Add(new int2(count, m_Updates.Count));
			}
			num = i;
		}
	}
```

- `private Register(System.Int32 addIndex, Unity.Entities.ComponentSystemBase system, Game.SystemUpdatePhase phase) : System.Void`  

```csharp
private void Register(int addIndex, ComponentSystemBase system, ComponentSystemBase other, SystemUpdatePhase phase)
	{
		GetInterval(system, phase, out var interval, out var offset);
		if (m_RefMap.TryGetValue(other, out var value))
		{
			value.Add(new SystemData(phase, interval, offset, addIndex, system));
		}
		else
		{
			value = new List<SystemData>(10);
			value.Add(new SystemData(phase, interval, offset, addIndex, system));
			m_RefMap.Add(other, value);
		}
		m_IsDirty = true;
	}
```

- `private Register(System.Int32 addIndex, Unity.Entities.ComponentSystemBase system, Unity.Entities.ComponentSystemBase other, Game.SystemUpdatePhase phase) : System.Void`  

```csharp
private void Register(int addIndex, ComponentSystemBase system, ComponentSystemBase other, SystemUpdatePhase phase)
	{
		GetInterval(system, phase, out var interval, out var offset);
		if (m_RefMap.TryGetValue(other, out var value))
		{
			value.Add(new SystemData(phase, interval, offset, addIndex, system));
		}
		else
		{
			value = new List<SystemData>(10);
			value.Add(new SystemData(phase, interval, offset, addIndex, system));
			m_RefMap.Add(other, value);
		}
		m_IsDirty = true;
	}
```

- `public RegisterGPUSystem<SystemType>() : System.Void`  

```csharp
public System.Void RegisterGPUSystem<SystemType>();
```

- `public RegisterGPUSystem(Game.IGPUSystem system) : System.Void`  

```csharp
public void RegisterGPUSystem(IGPUSystem system)
	{
		if (!m_GPUSystems.Contains(system))
		{
			m_GPUSystems.Add(system);
		}
	}
```

- `public Update(Game.SystemUpdatePhase phase) : System.Void`  

```csharp
public void Update(SystemUpdatePhase phase, uint updateIndex, int iterationIndex)
	{
		if (m_IsDirty)
		{
			Refresh();
		}
		if (m_UpdateRanges.Count <= (int)phase)
		{
			return;
		}
		SystemUpdatePhase systemUpdatePhase = currentPhase;
		try
		{
			currentPhase = phase;
			int2 @int = m_UpdateRanges[(int)phase];
			for (int i = @int.x; i < @int.y; i++)
			{
				SystemData systemData = m_Updates[i];
				if ((updateIndex & (uint)(systemData.m_Interval - 1)) != (uint)systemData.m_Offset)
				{
					continue;
				}
				try
				{
					if (systemData.m_ResetInterval <= iterationIndex)
					{
						((GameSystemBase)systemData.m_System).ResetDependency();
					}
					systemData.m_System.Update();
				}
				catch (Exception exception)
				{
					COSystemBase.baseLog.CriticalFormat(exception, "System update error during {0}->{1}:", phase.ToString(), systemData.m_System.GetType().Name);
				}
			}
		}
		finally
		{
			currentPhase = systemUpdatePhase;
		}
	}
```

- `public Update(Game.SystemUpdatePhase phase, System.UInt32 updateIndex, System.Int32 iterationIndex) : System.Void`  

```csharp
public void Update(SystemUpdatePhase phase, uint updateIndex, int iterationIndex)
	{
		if (m_IsDirty)
		{
			Refresh();
		}
		if (m_UpdateRanges.Count <= (int)phase)
		{
			return;
		}
		SystemUpdatePhase systemUpdatePhase = currentPhase;
		try
		{
			currentPhase = phase;
			int2 @int = m_UpdateRanges[(int)phase];
			for (int i = @int.x; i < @int.y; i++)
			{
				SystemData systemData = m_Updates[i];
				if ((updateIndex & (uint)(systemData.m_Interval - 1)) != (uint)systemData.m_Offset)
				{
					continue;
				}
				try
				{
					if (systemData.m_ResetInterval <= iterationIndex)
					{
						((GameSystemBase)systemData.m_System).ResetDependency();
					}
					systemData.m_System.Update();
				}
				catch (Exception exception)
				{
					COSystemBase.baseLog.CriticalFormat(exception, "System update error during {0}->{1}:", phase.ToString(), systemData.m_System.GetType().Name);
				}
			}
		}
		finally
		{
			currentPhase = systemUpdatePhase;
		}
	}
```

- `public UpdateAfter<SystemType>(Game.SystemUpdatePhase phase) : System.Void`  

```csharp
public System.Void UpdateAfter<SystemType>(Game.SystemUpdatePhase phase);
```

- `public UpdateAfter<SystemType, OtherType>(Game.SystemUpdatePhase phase) : System.Void`  

```csharp
public System.Void UpdateAfter<SystemType, OtherType>(Game.SystemUpdatePhase phase);
```

- `public UpdateAt<SystemType>(Game.SystemUpdatePhase phase) : System.Void`  

```csharp
public System.Void UpdateAt<SystemType>(Game.SystemUpdatePhase phase);
```

- `public UpdateBefore<SystemType>(Game.SystemUpdatePhase phase) : System.Void`  

```csharp
public System.Void UpdateBefore<SystemType>(Game.SystemUpdatePhase phase);
```

- `public UpdateBefore<SystemType, OtherType>(Game.SystemUpdatePhase phase) : System.Void`  

```csharp
public System.Void UpdateBefore<SystemType, OtherType>(Game.SystemUpdatePhase phase);
```


## Nested types

- `Game.UpdateSystem+SystemData`  
- `Game.UpdateSystem+IntervalData`  

