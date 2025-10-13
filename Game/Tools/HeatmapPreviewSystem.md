# Game.Tools.HeatmapPreviewSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class HeatmapPreviewSystem : Game.GameSystemBase
{
    private Game.Tools.TelecomPreviewSystem m_TelecomPreviewSystem;
    private Unity.Entities.EntityQuery m_InfomodeQuery;
    private Unity.Entities.ComponentSystemBase m_LastPreviewSystem;

    public HeatmapPreviewSystem();

    private Unity.Entities.ComponentSystemBase GetPreviewSystem();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnStopRunning();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Tools.TelecomPreviewSystem m_TelecomPreviewSystem`  

```csharp
private Game.Tools.TelecomPreviewSystem m_TelecomPreviewSystem;
```

- `private Unity.Entities.EntityQuery m_InfomodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_InfomodeQuery;
```

- `private Unity.Entities.ComponentSystemBase m_LastPreviewSystem`  

```csharp
private Unity.Entities.ComponentSystemBase m_LastPreviewSystem;
```


## Constructors

- `public HeatmapPreviewSystem()`  

```csharp
[Preserve]
	public HeatmapPreviewSystem()
	{
	}
```


## Methods

- `private GetPreviewSystem() : Unity.Entities.ComponentSystemBase`  

```csharp
private ComponentSystemBase GetPreviewSystem()
	{
		if (m_InfomodeQuery.IsEmptyIgnoreFilter)
		{
			return null;
		}
		NativeArray<InfoviewHeatmapData> nativeArray = m_InfomodeQuery.ToComponentDataArray<InfoviewHeatmapData>(Allocator.TempJob);
		try
		{
			for (int i = 0; i < nativeArray.Length; i++)
			{
				if (nativeArray[i].m_Type == HeatmapData.TelecomCoverage)
				{
					return m_TelecomPreviewSystem;
				}
			}
		}
		finally
		{
			nativeArray.Dispose();
		}
		return null;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_TelecomPreviewSystem = base.World.GetOrCreateSystemManaged<TelecomPreviewSystem>();
		m_InfomodeQuery = GetEntityQuery(ComponentType.ReadOnly<InfomodeActive>(), ComponentType.ReadOnly<InfoviewHeatmapData>());
		RequireForUpdate(m_InfomodeQuery);
	}
```

- `protected virtual OnStopRunning() : System.Void`  

```csharp
[Preserve]
	protected override void OnStopRunning()
	{
		if (m_LastPreviewSystem != null)
		{
			m_LastPreviewSystem.Enabled = false;
			m_LastPreviewSystem.Update();
			m_LastPreviewSystem = null;
		}
		base.OnStopRunning();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		ComponentSystemBase previewSystem = GetPreviewSystem();
		if (previewSystem != m_LastPreviewSystem)
		{
			if (m_LastPreviewSystem != null)
			{
				m_LastPreviewSystem.Enabled = false;
				m_LastPreviewSystem.Update();
			}
			m_LastPreviewSystem = previewSystem;
			if (m_LastPreviewSystem != null)
			{
				m_LastPreviewSystem.Enabled = true;
			}
		}
		previewSystem?.Update();
	}
```


