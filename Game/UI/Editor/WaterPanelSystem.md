# Game.UI.Editor.WaterPanelSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Editor.EditorPanelSystemBase`  
**Implements:** `Game.UI.Editor.IEditorPanel`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WaterPanelSystem : Game.UI.Editor.EditorPanelSystemBase, Game.UI.Editor.IEditorPanel
{
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Tools.WaterToolSystem m_WaterToolSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Unity.Entities.EntityQuery m_WaterSourceQuery;
    private Unity.Entities.EntityQuery m_UpdatedSourceQuery;
    private Unity.Entities.EntityArchetype m_WaterSourceArchetype;
    private Game.UI.Editor.WaterPanelSystem+WaterConfig m_Config;
    private static readonly System.Int32[] kWaterSpeedValues;

    public WaterPanelSystem();

    private System.Void AddBorderSource(Unity.Entities.EntityCommandBuffer buffer, Unity.Entities.Entity entity, Game.UI.Editor.WaterPanelSystem+WaterConfig+BorderWaterSource source, System.Int32 constantDepth, Game.Simulation.TerrainHeightData& terrainHeightData);
    private System.Void AddSource(Unity.Entities.EntityCommandBuffer buffer, Unity.Entities.Entity entity, Game.UI.Editor.WaterPanelSystem+WaterConfig+WaterSource source, System.Int32 constantDepth, System.Single& amount, Game.Simulation.TerrainHeightData& terrainHeightData);
    private System.Void ApplyWaterSources();
    private Game.UI.Widgets.IWidget[] BuildWaterSpeedToggles();
    public System.Void FetchWaterSources();
    private Unity.Entities.Entity GetSource(Unity.Entities.EntityCommandBuffer buffer, Unity.Collections.NativeArray<Unity.Entities.Entity> sources, System.Int32& sourceCount);
    protected virtual System.Boolean OnCancel();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnStartRunning();
    protected virtual System.Void OnStopRunning();
    protected virtual System.Void OnUpdate();
    protected virtual System.Void OnValueChanged(Game.UI.Widgets.IWidget widget);
}
```


## Fields

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Tools.WaterToolSystem m_WaterToolSystem`  

```csharp
private Game.Tools.WaterToolSystem m_WaterToolSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Unity.Entities.EntityQuery m_WaterSourceQuery`  

```csharp
private Unity.Entities.EntityQuery m_WaterSourceQuery;
```

- `private Unity.Entities.EntityQuery m_UpdatedSourceQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedSourceQuery;
```

- `private Unity.Entities.EntityArchetype m_WaterSourceArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_WaterSourceArchetype;
```

- `private Game.UI.Editor.WaterPanelSystem+WaterConfig m_Config`  

```csharp
private Game.UI.Editor.WaterPanelSystem+WaterConfig m_Config;
```

- `private static readonly System.Int32[] kWaterSpeedValues`  

```csharp
private static readonly System.Int32[] kWaterSpeedValues;
```


## Constructors

- `public WaterPanelSystem()`  

```csharp
[Preserve]
	public WaterPanelSystem()
	{
	}
```


## Methods

- `private AddBorderSource(Unity.Entities.EntityCommandBuffer buffer, Unity.Entities.Entity entity, Game.UI.Editor.WaterPanelSystem+WaterConfig+BorderWaterSource source, System.Int32 constantDepth, Game.Simulation.TerrainHeightData& terrainHeightData) : System.Void`  

```csharp
private void AddBorderSource(EntityCommandBuffer buffer, Entity entity, WaterConfig.BorderWaterSource source, int constantDepth, ref TerrainHeightData terrainHeightData)
	{
		if (!source.m_Initialized)
		{
			CameraUpdateSystem existingSystemManaged = World.DefaultGameObjectInjectionWorld.GetExistingSystemManaged<CameraUpdateSystem>();
			float3 @float = existingSystemManaged.activeCameraController.pivot;
			source.m_Initialized = true;
			source.m_Position = @float.xz;
			Bounds3 bounds = TerrainUtils.GetBounds(ref terrainHeightData);
			Bounds3 bounds2 = MathUtils.Expand(bounds, 0f - source.m_Radius);
			if (!MathUtils.Intersect(MathUtils.Expand(bounds, source.m_Radius).xz, source.m_Position))
			{
				source.m_Position = MathUtils.Clamp(source.m_Position, bounds.xz);
				@float.xz = source.m_Position;
				existingSystemManaged.activeCameraController.pivot = @float;
			}
			else if (MathUtils.Intersect(bounds2.xz, source.m_Position))
			{
				float2 float2 = source.m_Position - bounds2.min.xz;
				float2 float3 = bounds2.max.xz - source.m_Position;
				float2 trueValue = math.select(bounds.min.xz, bounds.max.xz, float3 < float2);
				float2 = math.min(float2, float3);
				source.m_Position = math.select(source.m_Position, trueValue, float2.xy < float2.yx);
				@float.xz = source.m_Position;
				existingSystemManaged.activeCameraController.pivot = @float;
			}
			source.m_Height = TerrainUtils.SampleHeight(ref terrainHeightData, new float3(source.m_Position.x, 0f, source.m_Position.y));
			source.m_Height -= m_TerrainSystem.positionOffset.y;
			if (constantDepth == 2)
			{
				source.m_Radius = 50f;
				source.m_Height += 30f;
			}
			else
			{
				source.m_Radius = 5000f;
				source.m_Height += 100f;
			}
		}
		buffer.SetComponent(entity, new Game.Simulation.WaterSourceData
		{
			m_Amount = source.m_Height,
			m_ConstantDepth = constantDepth,
			m_Radius = source.m_Radius,
			m_Multiplier = source.m_FloodHeight,
			m_Polluted = source.m_Pollution
		});
		buffer.SetComponent(entity, new Game.Objects.Transform
		{
			m_Position = new float3(source.m_Position.x, 0f, source.m_Position.y),
			m_Rotation = quaternion.identity
		});
	}
```

- `private AddSource(Unity.Entities.EntityCommandBuffer buffer, Unity.Entities.Entity entity, Game.UI.Editor.WaterPanelSystem+WaterConfig+WaterSource source, System.Int32 constantDepth, System.Single& amount, Game.Simulation.TerrainHeightData& terrainHeightData) : System.Void`  

```csharp
private void AddSource(EntityCommandBuffer buffer, Entity entity, WaterConfig.WaterSource source, int constantDepth, ref float amount, ref TerrainHeightData terrainHeightData)
	{
		if (!source.m_Initialized)
		{
			CameraUpdateSystem existingSystemManaged = World.DefaultGameObjectInjectionWorld.GetExistingSystemManaged<CameraUpdateSystem>();
			float3 @float = existingSystemManaged.activeCameraController.pivot;
			source.m_Initialized = true;
			source.m_Position = @float.xz;
			Bounds3 bounds = MathUtils.Expand(TerrainUtils.GetBounds(ref terrainHeightData), 0f - source.m_Radius);
			if (!MathUtils.Intersect(bounds.xz, source.m_Position))
			{
				source.m_Position = MathUtils.Clamp(source.m_Position, bounds.xz);
				@float.xz = source.m_Position;
				existingSystemManaged.activeCameraController.pivot = @float;
			}
			if (constantDepth == 0)
			{
				source.m_Radius = 30f;
				amount = 20f;
			}
			else
			{
				source.m_Radius = 40f;
				amount = TerrainUtils.SampleHeight(ref terrainHeightData, new float3(source.m_Position.x, 0f, source.m_Position.y));
				amount += 25f - m_TerrainSystem.positionOffset.y;
			}
		}
		float3 float2 = new float3(source.m_Position.x, 0f, source.m_Position.y);
		Game.Simulation.WaterSourceData waterSourceData = new Game.Simulation.WaterSourceData
		{
			m_Amount = amount,
			m_ConstantDepth = constantDepth,
			m_Radius = source.m_Radius,
			m_Polluted = source.m_Pollution
		};
		waterSourceData.m_Multiplier = WaterSystem.CalculateSourceMultiplier(waterSourceData, float2);
		buffer.SetComponent(entity, waterSourceData);
		buffer.SetComponent(entity, new Game.Objects.Transform
		{
			m_Position = float2,
			m_Rotation = quaternion.identity
		});
	}
```

- `private ApplyWaterSources() : System.Void`  

```csharp
private void ApplyWaterSources()
	{
		EntityCommandBuffer buffer = m_EndFrameBarrier.CreateCommandBuffer();
		NativeArray<Entity> sources = m_WaterSourceQuery.ToEntityArray(Allocator.Temp);
		int sourceCount = 0;
		TerrainHeightData terrainHeightData = m_TerrainSystem.GetHeightData();
		foreach (WaterConfig.ConstantRateWaterSource item in m_Config.m_ConstantRateWaterSources)
		{
			AddSource(buffer, GetSource(buffer, sources, ref sourceCount), item, 0, ref item.m_Rate, ref terrainHeightData);
		}
		foreach (WaterConfig.ConstantLevelWaterSource item2 in m_Config.m_ConstantLevelWaterSources)
		{
			AddSource(buffer, GetSource(buffer, sources, ref sourceCount), item2, 1, ref item2.m_Height, ref terrainHeightData);
		}
		foreach (WaterConfig.BorderWaterSource item3 in m_Config.m_BorderRiverWaterSources)
		{
			AddBorderSource(buffer, GetSource(buffer, sources, ref sourceCount), item3, 2, ref terrainHeightData);
		}
		foreach (WaterConfig.BorderWaterSource item4 in m_Config.m_BorderSeaWaterSources)
		{
			AddBorderSource(buffer, GetSource(buffer, sources, ref sourceCount), item4, 3, ref terrainHeightData);
		}
		while (sourceCount < sources.Length)
		{
			buffer.AddComponent(sources[sourceCount++], default(Deleted));
		}
		sources.Dispose();
	}
```

- `private BuildWaterSpeedToggles() : Game.UI.Widgets.IWidget[]`  

```csharp
private IWidget[] BuildWaterSpeedToggles()
	{
		IWidget[] array = new IWidget[kWaterSpeedValues.Length];
		for (int i = 0; i < kWaterSpeedValues.Length; i++)
		{
			int speed = kWaterSpeedValues[i];
			array[i] = new ToggleField
			{
				displayName = $"{speed}x",
				accessor = new DelegateAccessor<bool>(() => m_WaterSystem.WaterSimSpeed == speed, delegate(bool val)
				{
					if (val)
					{
						m_WaterSystem.WaterSimSpeed = speed;
					}
				})
			};
		}
		return array;
	}
```

- `public FetchWaterSources() : System.Void`  

```csharp
public void FetchWaterSources()
	{
		m_Config.m_ConstantRateWaterSources.Clear();
		m_Config.m_ConstantLevelWaterSources.Clear();
		m_Config.m_BorderRiverWaterSources.Clear();
		m_Config.m_BorderSeaWaterSources.Clear();
		NativeArray<Game.Simulation.WaterSourceData> nativeArray = m_WaterSourceQuery.ToComponentDataArray<Game.Simulation.WaterSourceData>(Allocator.TempJob);
		NativeArray<Game.Objects.Transform> nativeArray2 = m_WaterSourceQuery.ToComponentDataArray<Game.Objects.Transform>(Allocator.TempJob);
		try
		{
			for (int i = 0; i < nativeArray.Length; i++)
			{
				switch (nativeArray[i].m_ConstantDepth)
				{
				case 0:
					m_Config.m_ConstantRateWaterSources.Add(new WaterConfig.ConstantRateWaterSource
					{
						m_Initialized = true,
						m_Rate = nativeArray[i].m_Amount,
						m_Position = nativeArray2[i].m_Position.xz,
						m_Radius = nativeArray[i].m_Radius,
						m_Pollution = nativeArray[i].m_Polluted
					});
					break;
				case 1:
					m_Config.m_ConstantLevelWaterSources.Add(new WaterConfig.ConstantLevelWaterSource
					{
						m_Initialized = true,
						m_Height = nativeArray[i].m_Amount,
						m_Position = nativeArray2[i].m_Position.xz,
						m_Radius = nativeArray[i].m_Radius,
						m_Pollution = nativeArray[i].m_Polluted
					});
					break;
				case 2:
					m_Config.m_BorderRiverWaterSources.Add(new WaterConfig.BorderWaterSource
					{
						m_Initialized = true,
						m_FloodHeight = nativeArray[i].m_Multiplier,
						m_Height = nativeArray[i].m_Amount,
						m_Position = nativeArray2[i].m_Position.xz,
						m_Radius = nativeArray[i].m_Radius,
						m_Pollution = nativeArray[i].m_Polluted
					});
					break;
				case 3:
					m_Config.m_BorderSeaWaterSources.Add(new WaterConfig.BorderWaterSource
					{
						m_Initialized = true,
						m_FloodHeight = nativeArray[i].m_Multiplier,
						m_Height = nativeArray[i].m_Amount,
						m_Position = nativeArray2[i].m_Position.xz,
						m_Radius = nativeArray[i].m_Radius,
						m_Pollution = nativeArray[i].m_Polluted
					});
					break;
				}
			}
		}
		finally
		{
			nativeArray.Dispose();
			nativeArray2.Dispose();
		}
	}
```

- `private GetSource(Unity.Entities.EntityCommandBuffer buffer, Unity.Collections.NativeArray<Unity.Entities.Entity> sources, System.Int32& sourceCount) : Unity.Entities.Entity`  

```csharp
private Entity GetSource(EntityCommandBuffer buffer, NativeArray<Entity> sources, ref int sourceCount)
	{
		if (sourceCount < sources.Length)
		{
			return sources[sourceCount++];
		}
		return buffer.CreateEntity(m_WaterSourceArchetype);
	}
```

- `protected virtual OnCancel() : System.Boolean`  

```csharp
protected override bool OnCancel()
	{
		if (m_ToolSystem.activeTool == m_WaterToolSystem)
		{
			m_ToolSystem.ActivatePrefabTool(null);
			return false;
		}
		return base.OnCancel();
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_WaterToolSystem = base.World.GetOrCreateSystemManaged<WaterToolSystem>();
		m_WaterSystem = base.World.GetOrCreateSystemManaged<WaterSystem>();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_WaterSourceQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Simulation.WaterSourceData>(), ComponentType.ReadOnly<Game.Objects.Transform>(), ComponentType.Exclude<PrefabRef>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_UpdatedSourceQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Game.Simulation.WaterSourceData>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Deleted>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<PrefabRef>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_WaterSourceArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Game.Simulation.WaterSourceData>(), ComponentType.ReadWrite<Game.Objects.Transform>());
		EditorGenerator editorGenerator = new EditorGenerator();
		title = "Editor.WATER";
		children = new IWidget[1] { Scrollable.WithChildren(new IWidget[2]
		{
			new EditorSection
			{
				displayName = "Editor.WATER_SETTINGS",
				tooltip = "Editor.WATER_SETTINGS_TOOLTIP",
				expanded = true,
				children = editorGenerator.BuildMembers(new ObjectAccessor<WaterConfig>(m_Config), 0, "WaterSettings").ToArray()
			},
			new EditorSection
			{
				displayName = "Editor.WATER_SIMULATION_SPEED",
				tooltip = "Editor.WATER_SIMULATION_SPEED_TOOLTIP",
				children = BuildWaterSpeedToggles()
			}
		}) };
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		base.OnGameLoaded(serializationContext);
		FetchWaterSources();
	}
```

- `protected virtual OnStartRunning() : System.Void`  

```csharp
[Preserve]
	protected override void OnStartRunning()
	{
		base.OnStartRunning();
		if (InputManager.instance.activeControlScheme == InputManager.ControlScheme.KeyboardAndMouse)
		{
			m_ToolSystem.activeTool = m_WaterToolSystem;
		}
	}
```

- `protected virtual OnStopRunning() : System.Void`  

```csharp
[Preserve]
	protected override void OnStopRunning()
	{
		if (m_ToolSystem.activeTool == m_WaterToolSystem)
		{
			m_ToolSystem.ActivatePrefabTool(null);
		}
		m_WaterSystem.WaterSimSpeed = 1;
		base.OnStopRunning();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (!m_UpdatedSourceQuery.IsEmptyIgnoreFilter)
		{
			FetchWaterSources();
		}
	}
```

- `protected virtual OnValueChanged(Game.UI.Widgets.IWidget widget) : System.Void`  

```csharp
protected override void OnValueChanged(IWidget widget)
	{
		ApplyWaterSources();
	}
```


## Nested types

- `Game.UI.Editor.WaterPanelSystem+WaterConfig`  
- `Game.UI.Editor.WaterPanelSystem+<>c__DisplayClass11_0`  

