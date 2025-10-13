# Game.UI.InGame.ToolUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

## Code

```csharp
public class ToolUISystem : Game.UI.UISystemBase
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Tools.NetToolSystem m_NetToolSystem;
    private Game.Tools.AreaToolSystem m_AreaToolSystem;
    private Game.Tools.ZoneToolSystem m_ZoneToolSystem;
    private Game.Tools.RouteToolSystem m_RouteToolSystem;
    private Game.Tools.ObjectToolSystem m_ObjectToolSystem;
    private Game.Tools.TerrainToolSystem m_TerrainToolSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Tools.DefaultToolSystem m_DefaultToolSystem;
    private Game.Tools.UpgradeToolSystem m_UpgradeToolSystem;
    private Game.Tools.BulldozeToolSystem m_BulldozeToolSystem;
    private Game.Tools.SelectionToolSystem m_SelectionToolSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Unity.Entities.EntityQuery m_BulldozeQuery;
    private Unity.Entities.EntityQuery m_BrushQuery;
    private Colossal.UI.Binding.RawValueBinding m_ActiveToolBinding;
    private System.Collections.Generic.List<Game.Tools.ToolMode> m_ToolModes;
    public static const System.String kGroup;

    public ToolUISystem();

    private System.UInt32 <OnCreate>b__18_0();
    private System.UInt32 <OnCreate>b__18_1();
    private System.Boolean <OnCreate>b__18_10();
    private System.Single <OnCreate>b__18_11();
    private System.Single <OnCreate>b__18_12();
    private Unity.Entities.Entity <OnCreate>b__18_13();
    private System.Single <OnCreate>b__18_14();
    private System.Nullable<System.Single> <OnCreate>b__18_15();
    private System.Single <OnCreate>b__18_16();
    private System.Single <OnCreate>b__18_17();
    private System.Single <OnCreate>b__18_19();
    private System.UInt32 <OnCreate>b__18_2();
    private System.Single <OnCreate>b__18_20();
    private System.Single <OnCreate>b__18_21();
    private UnityEngine.Color32 <OnCreate>b__18_3();
    private System.Single <OnCreate>b__18_4();
    private System.Single <OnCreate>b__18_5();
    private System.Boolean <OnCreate>b__18_6();
    private System.Single <OnCreate>b__18_7();
    private System.Boolean <OnCreate>b__18_8();
    private System.Boolean <OnCreate>b__18_9();
    private System.Boolean AllowBrush();
    private System.Void BindActiveTool(Colossal.UI.Binding.IJsonWriter binder);
    private Game.UI.InGame.ToolUISystem+Brush[] BindBrushTypes();
    private System.Void BindToolModes(Colossal.UI.Binding.IJsonWriter binder);
    private System.Boolean GetColorSupported();
    private System.Boolean GetElevationDownDisabled();
    private Colossal.Mathematics.Bounds1 GetElevationRange();
    private System.Boolean GetElevationUpDisabled();
    private System.Boolean GetParallelModeSupported();
    private Game.Tools.ToolBaseSystem GetToolSystem(System.String tool);
    private System.String[] InitSnapOptionNames();
    private System.Boolean IsEditor();
    private System.Void OnBulldozeConfirmationRequested();
    private System.Void OnConfirmBulldoze(System.Int32 msg);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    private System.Void OnElevationDown();
    private System.Void OnElevationScroll();
    private System.Void OnElevationUp();
    private System.Void OnPrefabChanged(Game.Prefabs.PrefabBase prefab);
    private System.Void OnToolChanged(Game.Tools.ToolBaseSystem tool);
    private System.Void SelectBrush(Unity.Entities.Entity entity);
    private System.Void SelectTool(System.String tool);
    public System.Void SelectTool(Game.Tools.ToolBaseSystem tool);
    private System.Void SelectToolMode(System.Int32 modeIndex);
    private System.Void SetBrushAngle(System.Single angle);
    private System.Void SetBrushHeight(System.Single height);
    private System.Void SetBrushSize(System.Single size);
    private System.Void SetBrushStrength(System.Single strength);
    private System.Void SetColor(UnityEngine.Color32 color);
    private System.Void SetDistance(System.Single distance);
    private System.Void SetElevationStep(System.Single step);
    private System.Void SetParallelOffset(System.Single offset);
    private System.Void SetSelectedSnapMask(System.UInt32 mask);
    private System.Void SetUndergroundMode(System.Boolean enabled);
    private System.Void ToggleParallelMode();
}
```


## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Tools.NetToolSystem m_NetToolSystem`  

```csharp
private Game.Tools.NetToolSystem m_NetToolSystem;
```

- `private Game.Tools.AreaToolSystem m_AreaToolSystem`  

```csharp
private Game.Tools.AreaToolSystem m_AreaToolSystem;
```

- `private Game.Tools.ZoneToolSystem m_ZoneToolSystem`  

```csharp
private Game.Tools.ZoneToolSystem m_ZoneToolSystem;
```

- `private Game.Tools.RouteToolSystem m_RouteToolSystem`  

```csharp
private Game.Tools.RouteToolSystem m_RouteToolSystem;
```

- `private Game.Tools.ObjectToolSystem m_ObjectToolSystem`  

```csharp
private Game.Tools.ObjectToolSystem m_ObjectToolSystem;
```

- `private Game.Tools.TerrainToolSystem m_TerrainToolSystem`  

```csharp
private Game.Tools.TerrainToolSystem m_TerrainToolSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Tools.DefaultToolSystem m_DefaultToolSystem`  

```csharp
private Game.Tools.DefaultToolSystem m_DefaultToolSystem;
```

- `private Game.Tools.UpgradeToolSystem m_UpgradeToolSystem`  

```csharp
private Game.Tools.UpgradeToolSystem m_UpgradeToolSystem;
```

- `private Game.Tools.BulldozeToolSystem m_BulldozeToolSystem`  

```csharp
private Game.Tools.BulldozeToolSystem m_BulldozeToolSystem;
```

- `private Game.Tools.SelectionToolSystem m_SelectionToolSystem`  

```csharp
private Game.Tools.SelectionToolSystem m_SelectionToolSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Unity.Entities.EntityQuery m_BulldozeQuery`  

```csharp
private Unity.Entities.EntityQuery m_BulldozeQuery;
```

- `private Unity.Entities.EntityQuery m_BrushQuery`  

```csharp
private Unity.Entities.EntityQuery m_BrushQuery;
```

- `private Colossal.UI.Binding.RawValueBinding m_ActiveToolBinding`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_ActiveToolBinding;
```

- `private System.Collections.Generic.List<Game.Tools.ToolMode> m_ToolModes`  

```csharp
private System.Collections.Generic.List<Game.Tools.ToolMode> m_ToolModes;
```

- `public static const System.String kGroup`  

```csharp
public static const System.String kGroup;
```


## Constructors

- `public ToolUISystem()`  

```csharp
[Preserve]
	public ToolUISystem()
	{
	}
```


## Methods

- `private <OnCreate>b__18_0() : System.UInt32`  

```csharp
private System.UInt32 <OnCreate>b__18_0();
```

- `private <OnCreate>b__18_1() : System.UInt32`  

```csharp
private System.UInt32 <OnCreate>b__18_1();
```

- `private <OnCreate>b__18_10() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__18_10();
```

- `private <OnCreate>b__18_11() : System.Single`  

```csharp
private System.Single <OnCreate>b__18_11();
```

- `private <OnCreate>b__18_12() : System.Single`  

```csharp
private System.Single <OnCreate>b__18_12();
```

- `private <OnCreate>b__18_13() : Unity.Entities.Entity`  

```csharp
private Unity.Entities.Entity <OnCreate>b__18_13();
```

- `private <OnCreate>b__18_14() : System.Single`  

```csharp
private System.Single <OnCreate>b__18_14();
```

- `private <OnCreate>b__18_15() : System.Nullable<System.Single>`  

```csharp
private System.Nullable<System.Single> <OnCreate>b__18_15();
```

- `private <OnCreate>b__18_16() : System.Single`  

```csharp
private System.Single <OnCreate>b__18_16();
```

- `private <OnCreate>b__18_17() : System.Single`  

```csharp
private System.Single <OnCreate>b__18_17();
```

- `private <OnCreate>b__18_19() : System.Single`  

```csharp
private System.Single <OnCreate>b__18_19();
```

- `private <OnCreate>b__18_2() : System.UInt32`  

```csharp
private System.UInt32 <OnCreate>b__18_2();
```

- `private <OnCreate>b__18_20() : System.Single`  

```csharp
private System.Single <OnCreate>b__18_20();
```

- `private <OnCreate>b__18_21() : System.Single`  

```csharp
private System.Single <OnCreate>b__18_21();
```

- `private <OnCreate>b__18_3() : UnityEngine.Color32`  

```csharp
private UnityEngine.Color32 <OnCreate>b__18_3();
```

- `private <OnCreate>b__18_4() : System.Single`  

```csharp
private System.Single <OnCreate>b__18_4();
```

- `private <OnCreate>b__18_5() : System.Single`  

```csharp
private System.Single <OnCreate>b__18_5();
```

- `private <OnCreate>b__18_6() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__18_6();
```

- `private <OnCreate>b__18_7() : System.Single`  

```csharp
private System.Single <OnCreate>b__18_7();
```

- `private <OnCreate>b__18_8() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__18_8();
```

- `private <OnCreate>b__18_9() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__18_9();
```

- `private AllowBrush() : System.Boolean`  

```csharp
private bool AllowBrush()
	{
		if (m_ToolSystem.activeTool == m_ObjectToolSystem)
		{
			return m_ObjectToolSystem.allowBrush;
		}
		if (m_ToolSystem.activeTool == m_TerrainToolSystem)
		{
			return true;
		}
		return false;
	}
```

- `private BindActiveTool(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
private void BindActiveTool(IJsonWriter binder)
	{
		binder.TypeBegin("tool.UITool");
		binder.PropertyName("id");
		binder.Write(m_ToolSystem.activeTool.toolID);
		binder.PropertyName("modeIndex");
		binder.Write(m_ToolSystem.activeTool.uiModeIndex);
		binder.PropertyName("modes");
		BindToolModes(binder);
		binder.TypeEnd();
	}
```

- `private BindBrushTypes() : Game.UI.InGame.ToolUISystem+Brush[]`  

```csharp
private Brush[] BindBrushTypes()
	{
		PrefabSystem orCreateSystemManaged = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		NativeArray<Entity> nativeArray = m_BrushQuery.ToEntityArray(Allocator.TempJob);
		Brush[] array = new Brush[nativeArray.Length];
		for (int i = 0; i < nativeArray.Length; i++)
		{
			BrushPrefab prefab = orCreateSystemManaged.GetPrefab<BrushPrefab>(nativeArray[i]);
			array[i] = new Brush
			{
				m_Entity = nativeArray[i],
				m_Name = prefab.name,
				m_Icon = string.Empty,
				m_Priority = prefab.m_Priority
			};
		}
		nativeArray.Dispose();
		return array;
	}
```

- `private BindToolModes(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
private void BindToolModes(IJsonWriter binder)
	{
		m_ToolModes.Clear();
		m_ToolSystem.activeTool.GetUIModes(m_ToolModes);
		binder.ArrayBegin(m_ToolModes.Count);
		for (int i = 0; i < m_ToolModes.Count; i++)
		{
			ToolMode toolMode = m_ToolModes[i];
			binder.TypeBegin("tool.ToolMode");
			binder.PropertyName("id");
			binder.Write(toolMode.name);
			binder.PropertyName("index");
			binder.Write(toolMode.index);
			binder.PropertyName("icon");
			binder.Write("Media/Tools/" + m_ToolSystem.activeTool.toolID + "/" + toolMode.name + ".svg");
			binder.TypeEnd();
		}
		binder.ArrayEnd();
	}
```

- `private GetColorSupported() : System.Boolean`  

```csharp
private bool GetColorSupported()
	{
		return m_ToolSystem.activePrefab is IColored;
	}
```

- `private GetElevationDownDisabled() : System.Boolean`  

```csharp
private bool GetElevationDownDisabled()
	{
		if (m_ToolSystem.activeTool == m_NetToolSystem)
		{
			Bounds1 elevationRange = GetElevationRange();
			if (elevationRange != default(Bounds1))
			{
				return elevationRange.min >= m_NetToolSystem.elevation;
			}
		}
		if (!m_ToolSystem.activeTool.requireUnderground)
		{
			return !m_ToolSystem.activeTool.allowUnderground;
		}
		return true;
	}
```

- `private GetElevationRange() : Colossal.Mathematics.Bounds1`  

```csharp
private Bounds1 GetElevationRange()
	{
		if (m_ToolSystem.activeTool == m_NetToolSystem && m_NetToolSystem.mode != NetToolSystem.Mode.Replace && m_NetToolSystem.prefab != null && m_NetToolSystem.prefab.TryGet<PlaceableNet>(out var component))
		{
			if (component.m_UndergroundPrefab != null && component.m_UndergroundPrefab.TryGet<PlaceableNet>(out var component2))
			{
				return component.m_ElevationRange | component2.m_ElevationRange;
			}
			return component.m_ElevationRange;
		}
		return default(Bounds1);
	}
```

- `private GetElevationUpDisabled() : System.Boolean`  

```csharp
private bool GetElevationUpDisabled()
	{
		if (m_ToolSystem.activeTool == m_NetToolSystem)
		{
			Bounds1 elevationRange = GetElevationRange();
			if (elevationRange != default(Bounds1))
			{
				return elevationRange.max <= m_NetToolSystem.elevation;
			}
		}
		return !m_ToolSystem.activeTool.requireUnderground;
	}
```

- `private GetParallelModeSupported() : System.Boolean`  

```csharp
private bool GetParallelModeSupported()
	{
		if (m_ToolSystem.activeTool == m_NetToolSystem && m_NetToolSystem.mode != NetToolSystem.Mode.Grid && m_NetToolSystem.mode != NetToolSystem.Mode.Replace)
		{
			if (m_NetToolSystem.prefab != null && m_NetToolSystem.prefab.TryGet<PlaceableNet>(out var component) && component.m_AllowParallelMode)
			{
				return true;
			}
			if (m_NetToolSystem.lane != null)
			{
				return true;
			}
		}
		return false;
	}
```

- `private GetToolSystem(System.String tool) : Game.Tools.ToolBaseSystem`  

```csharp
private ToolBaseSystem GetToolSystem(string tool)
	{
		return tool switch
		{
			"Net Tool" => m_NetToolSystem, 
			"Area Tool" => m_AreaToolSystem, 
			"Zone Tool" => m_ZoneToolSystem, 
			"Route Tool" => m_RouteToolSystem, 
			"Object Tool" => m_ObjectToolSystem, 
			"Terrain Tool" => m_TerrainToolSystem, 
			"Upgrade Tool" => m_UpgradeToolSystem, 
			"Bulldoze Tool" => m_BulldozeToolSystem, 
			"Selection Tool" => m_SelectionToolSystem, 
			_ => m_DefaultToolSystem, 
		};
	}
```

- `private InitSnapOptionNames() : System.String[]`  

```csharp
private string[] InitSnapOptionNames()
	{
		uint[] obj = (uint[])Enum.GetValues(typeof(Snap));
		List<string> list = new List<string>();
		uint[] array = obj;
		foreach (uint num in array)
		{
			if (num != uint.MaxValue && num != 0)
			{
				list.Add(Enum.GetName(typeof(Snap), num));
			}
		}
		return list.ToArray();
	}
```

- `private IsEditor() : System.Boolean`  

```csharp
private bool IsEditor()
	{
		return GameManager.instance.gameMode.IsEditor();
	}
```

- `private OnBulldozeConfirmationRequested() : System.Void`  

```csharp
private void OnBulldozeConfirmationRequested()
	{
		GameManager.instance.userInterface.appBindings.ShowConfirmationDialog(new ConfirmationDialog(null, "Common.DIALOG_MESSAGE[Bulldozer]", "Common.DIALOG_ACTION[Yes]", "Common.DIALOG_ACTION[No]"), OnConfirmBulldoze);
	}
```

- `private OnConfirmBulldoze(System.Int32 msg) : System.Void`  

```csharp
private void OnConfirmBulldoze(int msg)
	{
		m_BulldozeToolSystem.ConfirmAction(msg == 0);
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_NetToolSystem = base.World.GetOrCreateSystemManaged<NetToolSystem>();
		m_AreaToolSystem = base.World.GetOrCreateSystemManaged<AreaToolSystem>();
		m_ZoneToolSystem = base.World.GetOrCreateSystemManaged<ZoneToolSystem>();
		m_RouteToolSystem = base.World.GetOrCreateSystemManaged<RouteToolSystem>();
		m_ObjectToolSystem = base.World.GetOrCreateSystemManaged<ObjectToolSystem>();
		m_TerrainToolSystem = base.World.GetOrCreateSystemManaged<TerrainToolSystem>();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_DefaultToolSystem = base.World.GetOrCreateSystemManaged<DefaultToolSystem>();
		m_UpgradeToolSystem = base.World.GetOrCreateSystemManaged<UpgradeToolSystem>();
		m_BulldozeToolSystem = base.World.GetOrCreateSystemManaged<BulldozeToolSystem>();
		m_SelectionToolSystem = base.World.GetOrCreateSystemManaged<SelectionToolSystem>();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_BulldozeQuery = GetEntityQuery(ComponentType.ReadOnly<BulldozeData>(), ComponentType.ReadOnly<PrefabData>());
		m_BrushQuery = GetEntityQuery(ComponentType.ReadOnly<BrushData>(), ComponentType.ReadOnly<PrefabData>());
		ToolSystem toolSystem = m_ToolSystem;
		toolSystem.EventToolChanged = (Action<ToolBaseSystem>)Delegate.Combine(toolSystem.EventToolChanged, new Action<ToolBaseSystem>(OnToolChanged));
		ToolSystem toolSystem2 = m_ToolSystem;
		toolSystem2.EventPrefabChanged = (Action<PrefabBase>)Delegate.Combine(toolSystem2.EventPrefabChanged, new Action<PrefabBase>(OnPrefabChanged));
		BulldozeToolSystem bulldozeToolSystem = m_BulldozeToolSystem;
		bulldozeToolSystem.EventConfirmationRequested = (Action)Delegate.Combine(bulldozeToolSystem.EventConfirmationRequested, new Action(OnBulldozeConfirmationRequested));
		AddBinding(m_ActiveToolBinding = new RawValueBinding("tool", "activeTool", BindActiveTool));
		AddUpdateBinding(new GetterValueBinding<uint>("tool", "availableSnapMask", delegate
		{
			if (m_ToolSystem.activeTool == null)
			{
				return 0u;
			}
			m_ToolSystem.activeTool.GetAvailableSnapMask(out var onMask, out var offMask);
			return (uint)(onMask & offMask);
		}));
		AddUpdateBinding(new GetterValueBinding<uint>("tool", "allSnapMask", delegate
		{
			if (m_ToolSystem.activeTool == null)
			{
				return 0u;
			}
			m_ToolSystem.activeTool.GetAvailableSnapMask(out var onMask, out var offMask);
			return (uint)(onMask & offMask) & 0xFFF8FFFFu;
		}));
		AddUpdateBinding(new GetterValueBinding<uint>("tool", "selectedSnapMask", () => (uint)((m_ToolSystem.activeTool != null) ? m_ToolSystem.activeTool.selectedSnap : Snap.None)));
		AddBinding(new ValueBinding<string[]>("tool", "snapOptionNames", InitSnapOptionNames(), new ArrayWriter<string>(new StringWriter())));
		AddUpdateBinding(new GetterValueBinding<bool>("tool", "colorSupported", GetColorSupported));
		AddUpdateBinding(new GetterValueBinding<Color32>("tool", "color", () => m_ToolSystem.activeTool?.color ?? default(Color32)));
		AddUpdateBinding(new GetterValueBinding<Bounds1>("tool", "elevationRange", GetElevationRange));
		AddUpdateBinding(new GetterValueBinding<float>("tool", "elevation", () => m_NetToolSystem.elevation));
		AddUpdateBinding(new GetterValueBinding<float>("tool", "elevationStep", () => m_NetToolSystem.elevationStep));
		AddUpdateBinding(new GetterValueBinding<bool>("tool", "parallelModeSupported", GetParallelModeSupported));
		AddUpdateBinding(new GetterValueBinding<bool>("tool", "parallelMode", () => GetParallelModeSupported() && m_NetToolSystem.parallelCount != 0));
		AddUpdateBinding(new GetterValueBinding<float>("tool", "parallelOffset", () => m_NetToolSystem.parallelOffset));
		AddUpdateBinding(new GetterValueBinding<bool>("tool", "undergroundModeSupported", () => m_ToolSystem.activeTool != null && m_ToolSystem.activeTool.allowUnderground));
		AddUpdateBinding(new GetterValueBinding<bool>("tool", "undergroundMode", () => m_ToolSystem.activeTool != null && m_ToolSystem.activeTool.requireUnderground));
		AddUpdateBinding(new GetterValueBinding<bool>("tool", "elevationDownDisabled", GetElevationDownDisabled));
		AddUpdateBinding(new GetterValueBinding<bool>("tool", "elevationUpDisabled", GetElevationUpDisabled));
		AddUpdateBinding(new GetterValueBinding<bool>("tool", "replacingTrees", () => !m_ObjectToolSystem.GetNetUpgradeStates(out var _).IsEmpty));
		AddUpdateBinding(new GetterValueBinding<float>("tool", "distance", () => m_ObjectToolSystem.distance));
		AddUpdateBinding(new GetterValueBinding<float>("tool", "distanceScale", () => m_ObjectToolSystem.distanceScale));
		AddBinding(new TriggerBinding<string>("tool", "selectTool", SelectTool));
		AddBinding(new TriggerBinding<int>("tool", "selectToolMode", SelectToolMode));
		AddBinding(new TriggerBinding<uint>("tool", "setSelectedSnapMask", SetSelectedSnapMask));
		AddBinding(new TriggerBinding("tool", "elevationUp", OnElevationUp));
		AddBinding(new TriggerBinding("tool", "elevationDown", OnElevationDown));
		AddBinding(new TriggerBinding("tool", "elevationScroll", OnElevationScroll));
		AddBinding(new TriggerBinding<float>("tool", "setElevationStep", SetElevationStep));
		AddBinding(new TriggerBinding("tool", "toggleParallelMode", ToggleParallelMode));
		AddBinding(new TriggerBinding<float>("tool", "setParallelOffset", SetParallelOffset));
		AddBinding(new TriggerBinding<bool>("tool", "setUndergroundMode", SetUndergroundMode));
		AddBinding(new TriggerBinding<float>("tool", "setDistance", SetDistance));
		AddUpdateBinding(new GetterValueBinding<bool>("tool", "allowBrush", AllowBrush));
		AddUpdateBinding(new GetterValueBinding<Entity>("tool", "selectedBrush", () => (!AllowBrush() || !m_ToolSystem.activeTool.brushing) ? Entity.Null : m_PrefabSystem.GetEntity(m_ToolSystem.activeTool.brushType)));
		AddBinding(new GetterValueBinding<Brush[]>("tool", "brushes", BindBrushTypes, new ArrayWriter<Brush>(new ValueWriter<Brush>())));
		AddUpdateBinding(new GetterValueBinding<float>("tool", "brushSize", () => (!AllowBrush()) ? 0f : m_ToolSystem.activeTool.brushSize));
		AddUpdateBinding(new GetterValueBinding<float?>("tool", "brushHeight", () => (m_ToolSystem.activeTool != m_TerrainToolSystem || m_TerrainToolSystem.prefab.m_Type != TerraformingType.Level) ? ((float?)null) : new float?(m_TerrainToolSystem.brushHeight - WaterSystem.SeaLevel), ValueWritersStruct.Nullable(ValueWriters.Create<float>())));
		AddUpdateBinding(new GetterValueBinding<float>("tool", "brushStrength", () => (!AllowBrush()) ? 0f : m_ToolSystem.activeTool.brushStrength));
		AddUpdateBinding(new GetterValueBinding<float>("tool", "brushAngle", () => (!AllowBrush()) ? 0f : m_ToolSystem.activeTool.brushAngle));
		AddUpdateBinding(new GetterValueBinding<float>("tool", "brushSizeMin", () => 10f));
		AddUpdateBinding(new GetterValueBinding<float>("tool", "brushSizeMax", () => (!m_ToolSystem.actionMode.IsEditor()) ? 1000f : 5000f));
		AddUpdateBinding(new GetterValueBinding<float>("tool", "brushHeightMin", () => 0f - m_TerrainSystem.heightScaleOffset.y - WaterSystem.SeaLevel));
		AddUpdateBinding(new GetterValueBinding<float>("tool", "brushHeightMax", () => m_TerrainSystem.heightScaleOffset.x - m_TerrainSystem.heightScaleOffset.y - WaterSystem.SeaLevel));
		AddBinding(new TriggerBinding<Entity>("tool", "selectBrush", SelectBrush));
		AddBinding(new TriggerBinding<float>("tool", "setBrushHeight", SetBrushHeight));
		AddBinding(new TriggerBinding<float>("tool", "setBrushSize", SetBrushSize));
		AddBinding(new TriggerBinding<float>("tool", "setBrushStrength", SetBrushStrength));
		AddBinding(new TriggerBinding<float>("tool", "setBrushAngle", SetBrushAngle));
		AddBinding(new TriggerBinding<Color32>("tool", "setColor", SetColor));
		AddUpdateBinding(new GetterValueBinding<bool>("tool", "isEditor", IsEditor));
		m_ToolModes = new List<ToolMode>();
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		ToolSystem toolSystem = m_ToolSystem;
		toolSystem.EventToolChanged = (Action<ToolBaseSystem>)Delegate.Remove(toolSystem.EventToolChanged, new Action<ToolBaseSystem>(OnToolChanged));
		ToolSystem toolSystem2 = m_ToolSystem;
		toolSystem2.EventPrefabChanged = (Action<PrefabBase>)Delegate.Remove(toolSystem2.EventPrefabChanged, new Action<PrefabBase>(OnPrefabChanged));
		BulldozeToolSystem bulldozeToolSystem = m_BulldozeToolSystem;
		bulldozeToolSystem.EventConfirmationRequested = (Action)Delegate.Remove(bulldozeToolSystem.EventConfirmationRequested, new Action(OnBulldozeConfirmationRequested));
		base.OnDestroy();
	}
```

- `private OnElevationDown() : System.Void`  

```csharp
private void OnElevationDown()
	{
		if (m_ToolSystem.activeTool != null)
		{
			m_ToolSystem.activeTool.ElevationDown();
		}
	}
```

- `private OnElevationScroll() : System.Void`  

```csharp
private void OnElevationScroll()
	{
		if (m_ToolSystem.activeTool != null)
		{
			m_ToolSystem.activeTool.ElevationScroll();
		}
	}
```

- `private OnElevationUp() : System.Void`  

```csharp
private void OnElevationUp()
	{
		if (m_ToolSystem.activeTool != null)
		{
			m_ToolSystem.activeTool.ElevationUp();
		}
	}
```

- `private OnPrefabChanged(Game.Prefabs.PrefabBase prefab) : System.Void`  

```csharp
private void OnPrefabChanged(PrefabBase prefab)
	{
		m_ActiveToolBinding.Update();
	}
```

- `private OnToolChanged(Game.Tools.ToolBaseSystem tool) : System.Void`  

```csharp
private void OnToolChanged(ToolBaseSystem tool)
	{
		if (tool != m_TerrainToolSystem)
		{
			m_TerrainToolSystem.SetDisableFX();
		}
		m_ActiveToolBinding.Update();
	}
```

- `private SelectBrush(Unity.Entities.Entity entity) : System.Void`  

```csharp
private void SelectBrush(Entity entity)
	{
		if (!AllowBrush())
		{
			return;
		}
		if (entity != Entity.Null)
		{
			BrushPrefab prefab = m_PrefabSystem.GetPrefab<BrushPrefab>(entity);
			m_ToolSystem.activeTool.brushType = prefab;
			if (m_ToolSystem.activeTool == m_ObjectToolSystem)
			{
				m_ObjectToolSystem.mode = ObjectToolSystem.Mode.Brush;
			}
		}
		else if (m_ToolSystem.activeTool == m_ObjectToolSystem && m_ObjectToolSystem.mode == ObjectToolSystem.Mode.Brush)
		{
			m_ObjectToolSystem.mode = ObjectToolSystem.Mode.Create;
		}
	}
```

- `private SelectTool(System.String tool) : System.Void`  

```csharp
public void SelectTool(ToolBaseSystem tool)
	{
		if (m_ToolSystem.activeTool == tool)
		{
			return;
		}
		m_ToolSystem.activeTool = tool;
		if (tool == m_BulldozeToolSystem && !m_BulldozeQuery.IsEmptyIgnoreFilter)
		{
			NativeArray<PrefabData> nativeArray = m_BulldozeQuery.ToComponentDataArray<PrefabData>(Allocator.TempJob);
			try
			{
				m_BulldozeToolSystem.prefab = m_PrefabSystem.GetPrefab<BulldozePrefab>(nativeArray[0]);
			}
			finally
			{
				nativeArray.Dispose();
			}
		}
	}
```

- `public SelectTool(Game.Tools.ToolBaseSystem tool) : System.Void`  

```csharp
public void SelectTool(ToolBaseSystem tool)
	{
		if (m_ToolSystem.activeTool == tool)
		{
			return;
		}
		m_ToolSystem.activeTool = tool;
		if (tool == m_BulldozeToolSystem && !m_BulldozeQuery.IsEmptyIgnoreFilter)
		{
			NativeArray<PrefabData> nativeArray = m_BulldozeQuery.ToComponentDataArray<PrefabData>(Allocator.TempJob);
			try
			{
				m_BulldozeToolSystem.prefab = m_PrefabSystem.GetPrefab<BulldozePrefab>(nativeArray[0]);
			}
			finally
			{
				nativeArray.Dispose();
			}
		}
	}
```

- `private SelectToolMode(System.Int32 modeIndex) : System.Void`  

```csharp
private void SelectToolMode(int modeIndex)
	{
		ToolBaseSystem activeTool = m_ToolSystem.activeTool;
		if (!(activeTool is NetToolSystem netToolSystem))
		{
			if (!(activeTool is ZoneToolSystem zoneToolSystem))
			{
				if (!(activeTool is BulldozeToolSystem bulldozeToolSystem))
				{
					if (!(activeTool is AreaToolSystem areaToolSystem))
					{
						if (activeTool is ObjectToolSystem objectToolSystem)
						{
							objectToolSystem.mode = (ObjectToolSystem.Mode)modeIndex;
						}
					}
					else
					{
						areaToolSystem.mode = (AreaToolSystem.Mode)modeIndex;
					}
				}
				else
				{
					bulldozeToolSystem.mode = (BulldozeToolSystem.Mode)modeIndex;
				}
			}
			else
			{
				zoneToolSystem.mode = (ZoneToolSystem.Mode)modeIndex;
			}
		}
		else
		{
			netToolSystem.mode = (NetToolSystem.Mode)modeIndex;
		}
		m_ActiveToolBinding.Update();
	}
```

- `private SetBrushAngle(System.Single angle) : System.Void`  

```csharp
private void SetBrushAngle(float angle)
	{
		m_ToolSystem.activeTool.brushAngle = angle;
	}
```

- `private SetBrushHeight(System.Single height) : System.Void`  

```csharp
private void SetBrushHeight(float height)
	{
		m_TerrainToolSystem.brushHeight = height + WaterSystem.SeaLevel;
	}
```

- `private SetBrushSize(System.Single size) : System.Void`  

```csharp
private void SetBrushSize(float size)
	{
		m_ToolSystem.activeTool.brushSize = size;
	}
```

- `private SetBrushStrength(System.Single strength) : System.Void`  

```csharp
private void SetBrushStrength(float strength)
	{
		m_ToolSystem.activeTool.brushStrength = strength;
	}
```

- `private SetColor(UnityEngine.Color32 color) : System.Void`  

```csharp
private void SetColor(Color32 color)
	{
		m_ToolSystem.activeTool.color = color;
	}
```

- `private SetDistance(System.Single distance) : System.Void`  

```csharp
private void SetDistance(float distance)
	{
		m_ObjectToolSystem.distance = distance;
	}
```

- `private SetElevationStep(System.Single step) : System.Void`  

```csharp
private void SetElevationStep(float step)
	{
		m_NetToolSystem.elevationStep = step;
	}
```

- `private SetParallelOffset(System.Single offset) : System.Void`  

```csharp
private void SetParallelOffset(float offset)
	{
		m_NetToolSystem.parallelOffset = offset;
	}
```

- `private SetSelectedSnapMask(System.UInt32 mask) : System.Void`  

```csharp
private void SetSelectedSnapMask(uint mask)
	{
		m_ToolSystem.activeTool.selectedSnap = (Snap)mask;
	}
```

- `private SetUndergroundMode(System.Boolean enabled) : System.Void`  

```csharp
private void SetUndergroundMode(bool enabled)
	{
		if (m_ToolSystem.activeTool != null)
		{
			m_ToolSystem.activeTool.SetUnderground(enabled);
		}
	}
```

- `private ToggleParallelMode() : System.Void`  

```csharp
private void ToggleParallelMode()
	{
		m_NetToolSystem.parallelCount = ((m_NetToolSystem.parallelCount == 0) ? 1 : 0);
	}
```


## Nested types

- `Game.UI.InGame.ToolUISystem+Brush`  
- `Game.UI.InGame.ToolUISystem+<>c`  

