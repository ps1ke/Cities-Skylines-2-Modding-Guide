# Game.Debug.WaterCullingDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

## Code

```csharp
public class WaterCullingDebugSystem : Game.Debug.BaseDebugSystem
{
    private Colossal.GizmosSystem m_GizmosSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Debug.BaseDebugSystem+Option m_ActiveWaterCellOption;
    private Game.Debug.BaseDebugSystem+Option m_FixedHeight;

    public WaterCullingDebugSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Debug.BaseDebugSystem+Option m_ActiveWaterCellOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_ActiveWaterCellOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_FixedHeight`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_FixedHeight;
```


## Constructors

- `public WaterCullingDebugSystem()`  

```csharp
[Preserve]
	public WaterCullingDebugSystem()
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
		m_GizmosSystem = base.World.GetOrCreateSystemManaged<GizmosSystem>();
		m_WaterSystem = base.World.GetOrCreateSystemManaged<WaterSystem>();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_ActiveWaterCellOption = AddOption("Show active water cell", defaultEnabled: false);
		m_FixedHeight = AddOption("Fixed Height", defaultEnabled: false);
		base.Enabled = false;
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		int num = 25;
		int num2 = 49;
		if (!(RenderPipelineManager.currentPipeline is HDRenderPipeline hDRenderPipeline))
		{
			return;
		}
		JobHandle dependencies;
		GizmoBatcher gizmosBatcher = m_GizmosSystem.GetGizmosBatcher(out dependencies);
		dependencies.Complete();
		if (!m_ActiveWaterCellOption.enabled)
		{
			float3[] waterPatchesPositions = hDRenderPipeline.GetWaterPatchesPositions();
			for (int i = 0; i < num; i++)
			{
				float3 center = waterPatchesPositions[i];
				float3 @float = waterPatchesPositions[i + num2];
				float2 size = new float2(@float.x, @float.y);
				Color color = ((@float.z > 0f) ? Color.blue : Color.red);
				if (m_FixedHeight.enabled)
				{
					center.y = 400f;
				}
				gizmosBatcher.DrawWireNode(center, 1f, color);
				gizmosBatcher.DrawWireRect(center, size, color);
				if (@float.z > 0f)
				{
					gizmosBatcher.DrawWireCapsule(center, 64f, @float.z, Color.blue);
				}
			}
			return;
		}
		float num3 = (float)m_WaterSystem.GridSize * m_WaterSystem.CellSize;
		float3 float2 = m_TerrainSystem.positionOffset + new float3(num3 * 0.5f, 0f, num3 * 0.5f);
		NativeArray<int> active = m_WaterSystem.GetActive();
		int2 activeGridSize = m_WaterSystem.m_ActiveGridSize;
		float2 float3 = new float2(num3, num3);
		for (int j = 0; j < activeGridSize.x; j++)
		{
			for (int k = 0; k < activeGridSize.y; k++)
			{
				float2 float4 = new float2((float)j * num3, (float)k * num3);
				float3 center2 = float2 + new float3(float4.x, 400f, float4.y);
				Color color2 = ((active[j + k * activeGridSize.x] > 0) ? Color.green : Color.red);
				gizmosBatcher.DrawWireRect(center2, float3 * 0.49f, color2);
			}
		}
	}
```


