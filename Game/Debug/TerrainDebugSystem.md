# Game.Debug.TerrainDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `FormerlySerializedAs`  

## Code

```csharp
public class TerrainDebugSystem : Game.GameSystemBase
{
    private Game.Debug.TerrainDebugSystem+DebugMode m_Mode;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Rendering.TerrainRenderSystem m_TerrainRenderSystem;

    public TerrainDebugSystem();

    private System.Void DrawCascades();
    private System.Void DrawDebug();
    private System.Void DrawRoads();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void RenderDebugUI();
}
```


## Fields

- `private Game.Debug.TerrainDebugSystem+DebugMode m_Mode`  

```csharp
private Game.Debug.TerrainDebugSystem+DebugMode m_Mode;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Rendering.TerrainRenderSystem m_TerrainRenderSystem`  

```csharp
private Game.Rendering.TerrainRenderSystem m_TerrainRenderSystem;
```


## Constructors

- `public TerrainDebugSystem()`  

```csharp
[Preserve]
	public TerrainDebugSystem()
	{
	}
```


## Methods

- `private DrawCascades() : System.Void`  

```csharp
private void DrawCascades()
	{
		for (int i = 0; i < 4; i++)
		{
			Colossal.Gizmos.batcher.DrawWireBounds(m_TerrainRenderSystem.GetCascadeRegion(i), new Color(0.1f, 0.28f, 0.89f, 0.9f));
			if (m_TerrainSystem.heightMapSliceUpdatedLast[i])
			{
				Colossal.Gizmos.batcher.DrawWireBounds(m_TerrainRenderSystem.GetCascadeViewport(i), new Color(0.1f, 0.89f, 0.28f, 0.9f));
				Colossal.Gizmos.batcher.DrawWireBounds(m_TerrainRenderSystem.GetCascadeCullArea(i), new Color(1f, 0.85f, 0.2f, 0.9f));
			}
		}
		Colossal.Gizmos.batcher.DrawWireBounds(m_TerrainRenderSystem.GetLastCullArea(), new Color(0.9f, 0.9f, 0.2f, 0.9f));
	}
```

- `private DrawDebug() : System.Void`  

```csharp
private void DrawDebug()
	{
		if (m_Mode == DebugMode.Cascade)
		{
			DrawRoads();
			DrawCascades();
		}
	}
```

- `private DrawRoads() : System.Void`  

```csharp
private void DrawRoads()
	{
		NativeList<TerrainSystem.LaneSection> roads = m_TerrainSystem.GetRoads();
		Bounds bounds = default(Bounds);
		Bounds lastCullArea = m_TerrainRenderSystem.GetLastCullArea();
		Bounds cascadeRegion = m_TerrainRenderSystem.GetCascadeRegion(3);
		for (int i = 0; i < roads.Length; i++)
		{
			TerrainSystem.LaneSection laneSection = roads[i];
			float4 @float = math.min(laneSection.m_Left.c1, laneSection.m_Right.c1);
			float y = math.min(math.min(@float.x, @float.y), math.min(@float.z, @float.w)) - 1f;
			@float = math.max(laneSection.m_Left.c1, laneSection.m_Right.c1);
			float y2 = math.max(math.max(@float.x, @float.y), math.max(@float.z, @float.w)) + 1f;
			bounds.SetMinMax(new float3(laneSection.m_Bounds.min.x, y, laneSection.m_Bounds.min.y), new float3(laneSection.m_Bounds.max.x, y2, laneSection.m_Bounds.max.y));
			if ((laneSection.m_Flags & TerrainSystem.LaneFlags.ShiftTerrain) == 0)
			{
				Colossal.Gizmos.batcher.DrawWireBounds(bounds, new Color(0.84f, 0.84f, 0.84f, 0.9f));
			}
			else if (bounds.Intersects(lastCullArea))
			{
				if (bounds.Intersects(cascadeRegion))
				{
					Colossal.Gizmos.batcher.DrawWireBounds(bounds, new Color(0.37f, 0.84f, 0.42f, 0.9f));
				}
				else
				{
					Colossal.Gizmos.batcher.DrawWireBounds(bounds, new Color(0.59f, 0.59f, 0.21f, 0.9f));
				}
			}
			else
			{
				Colossal.Gizmos.batcher.DrawWireBounds(bounds, new Color(0.59f, 0.21f, 0.18f, 0.9f));
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
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_TerrainRenderSystem = base.World.GetOrCreateSystemManaged<TerrainRenderSystem>();
		base.Enabled = false;
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		DrawDebug();
	}
```

- `public RenderDebugUI() : System.Void`  

```csharp
public void RenderDebugUI()
	{
		GUILayout.BeginHorizontal();
		GUILayout.Label("Debug Mode");
		if (GUILayout.Button("Cascades"))
		{
			m_Mode = DebugMode.Cascade;
		}
		if (GUILayout.Button("World"))
		{
			m_Mode = DebugMode.World;
		}
		GUILayout.EndHorizontal();
		if (m_Mode == DebugMode.Cascade)
		{
			GUIStyle gUIStyle = new GUIStyle();
			GUIStyle gUIStyle2 = new GUIStyle();
			gUIStyle.fontSize = 16;
			gUIStyle2.fontSize = 16;
			gUIStyle2.normal.textColor = new Color(1f, 1f, 1f);
			gUIStyle.normal.textColor = new Color(0.4f, 1f, 0.4f);
			GUILayout.Label("Last Cull Area " + m_TerrainSystem.lastCullArea.ToString(), gUIStyle);
			for (int i = 0; i < 4; i++)
			{
				float4 @float = m_TerrainSystem.heightMapSliceArea[i];
				float4 float2 = m_TerrainSystem.heightMapViewportUpdated[i];
				GUILayout.Label($"Cascade[{i}] Size min:{@float.x},{@float.y} max:{@float.z},{@float.w} Viewport[{float2.x},{float2.y},{float2.z},{float2.w}]", m_TerrainSystem.heightMapSliceUpdatedLast[i] ? gUIStyle : gUIStyle2);
			}
			m_TerrainSystem.freezeCascadeUpdates = GUILayout.Toggle(m_TerrainSystem.freezeCascadeUpdates, "Freeze Cascade Updates");
		}
		else if (m_Mode == DebugMode.World)
		{
			GUILayout.Label($"World Size {m_TerrainSystem.worldSize.x}, {m_TerrainSystem.worldSize.y}");
			GUILayout.Label($"World Offset {m_TerrainSystem.worldOffset.x}, {m_TerrainSystem.worldOffset.y}");
			GUILayout.Label($"Playable Size {m_TerrainSystem.playableArea.x}, {m_TerrainSystem.playableArea.y}");
			GUILayout.Label($"Playable Offset {m_TerrainSystem.playableOffset.x}, {m_TerrainSystem.playableOffset.y}");
		}
	}
```


## Nested types

- `Game.Debug.TerrainDebugSystem+DebugViewMode`  
- `Game.Debug.TerrainDebugSystem+DebugMode`  

