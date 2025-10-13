# Game.UI.Editor.ClimatePanelSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Editor.EditorPanelSystemBase`  
**Implements:** `Game.UI.Editor.IEditorPanel`, `Game.UI.Editor.SeasonsField+IAdapter`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ClimatePanelSystem : Game.UI.Editor.EditorPanelSystemBase, Game.UI.Editor.IEditorPanel, Game.UI.Editor.SeasonsField+IAdapter
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Simulation.ClimateSystem m_ClimateSystem;
    private Game.Simulation.WindSimulationSystem m_WindSimulationSystem;
    private Game.Simulation.PlanetarySystem m_PlanetarySystem;
    private Unity.Entities.EntityQuery m_ClimateQuery;
    private Unity.Entities.EntityQuery m_ClimateSeasonQuery;
    private Unity.Entities.EntityQuery m_UpdatedQuery;
    private Game.UI.Editor.SeasonsField+SeasonCurves m_SeasonsCurves;
    private Unity.Entities.EntityQuery m_RenderQuery;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Prefabs.InfoviewPrefab m_WindInfoview;
    private System.Double m_LastWindDirection;
    private System.Int32 m_LastClimateHash;
    private System.Int32 m_InfoviewCooldown;
    private Game.UI.Editor.EditorSection m_InspectorSection;
    private Game.UI.Widgets.EditorGenerator m_Generator;
    private UnityEngine.Coroutine m_DelayedInfomodeReset;
    private Game.Prefabs.InfoviewPrefab m_PreviousInfoview;
    private Unity.Entities.EntityQuery m_AllInfoviewQuery;
    private Unity.Entities.Entity <selectedSeason>k__BackingField;
    private Game.UI.Editor.ClimatePanelSystem+TypeHandle __TypeHandle;

    private Game.Prefabs.Climate.ClimatePrefab currentClimate { private get; private set; }
    private System.Double windDirection { private get; private set; }
    private System.Collections.Generic.IEnumerable<Game.Simulation.ClimateSystem+SeasonInfo> Game.UI.Editor.SeasonsField.IAdapter.seasons { private get; private set; }
    private Game.UI.Editor.SeasonsField+SeasonCurves Game.UI.Editor.SeasonsField.IAdapter.curves { private get; private set; }
    public Unity.Entities.Entity selectedSeason { get; set; }

    public ClimatePanelSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private Game.Prefabs.PrefabBase <RebuildInspector>b__28_0();
    private System.Void <RebuildInspector>b__28_1(Game.Prefabs.PrefabBase prefab);
    private System.Collections.IEnumerator DisableInfomode();
    private System.Void Duplicate();
    private System.Void GetWindInfoView();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnValueChanged(Game.UI.Widgets.IWidget widget);
    public System.Void RebuildCurves();
    private System.Void RebuildInspector();
}
```


## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Simulation.ClimateSystem m_ClimateSystem`  

```csharp
private Game.Simulation.ClimateSystem m_ClimateSystem;
```

- `private Game.Simulation.WindSimulationSystem m_WindSimulationSystem`  

```csharp
private Game.Simulation.WindSimulationSystem m_WindSimulationSystem;
```

- `private Game.Simulation.PlanetarySystem m_PlanetarySystem`  

```csharp
private Game.Simulation.PlanetarySystem m_PlanetarySystem;
```

- `private Unity.Entities.EntityQuery m_ClimateQuery`  

```csharp
private Unity.Entities.EntityQuery m_ClimateQuery;
```

- `private Unity.Entities.EntityQuery m_ClimateSeasonQuery`  

```csharp
private Unity.Entities.EntityQuery m_ClimateSeasonQuery;
```

- `private Unity.Entities.EntityQuery m_UpdatedQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedQuery;
```

- `private Game.UI.Editor.SeasonsField+SeasonCurves m_SeasonsCurves`  

```csharp
private Game.UI.Editor.SeasonsField+SeasonCurves m_SeasonsCurves;
```

- `private Unity.Entities.EntityQuery m_RenderQuery`  

```csharp
private Unity.Entities.EntityQuery m_RenderQuery;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Prefabs.InfoviewPrefab m_WindInfoview`  

```csharp
private Game.Prefabs.InfoviewPrefab m_WindInfoview;
```

- `private System.Double m_LastWindDirection`  

```csharp
private System.Double m_LastWindDirection;
```

- `private System.Int32 m_LastClimateHash`  

```csharp
private System.Int32 m_LastClimateHash;
```

- `private System.Int32 m_InfoviewCooldown`  

```csharp
private System.Int32 m_InfoviewCooldown;
```

- `private Game.UI.Editor.EditorSection m_InspectorSection`  

```csharp
private Game.UI.Editor.EditorSection m_InspectorSection;
```

- `private Game.UI.Widgets.EditorGenerator m_Generator`  

```csharp
private Game.UI.Widgets.EditorGenerator m_Generator;
```

- `private UnityEngine.Coroutine m_DelayedInfomodeReset`  

```csharp
private UnityEngine.Coroutine m_DelayedInfomodeReset;
```

- `private Game.Prefabs.InfoviewPrefab m_PreviousInfoview`  

```csharp
private Game.Prefabs.InfoviewPrefab m_PreviousInfoview;
```

- `private Unity.Entities.EntityQuery m_AllInfoviewQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllInfoviewQuery;
```

- `private Unity.Entities.Entity <selectedSeason>k__BackingField`  

```csharp
private Unity.Entities.Entity <selectedSeason>k__BackingField;
```

- `private Game.UI.Editor.ClimatePanelSystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.Editor.ClimatePanelSystem+TypeHandle __TypeHandle;
```


## Properties

- `private Game.Prefabs.Climate.ClimatePrefab currentClimate { private get; private set }`  

```csharp
private Game.Prefabs.Climate.ClimatePrefab currentClimate { private get; private set; }
```

- `private System.Double windDirection { private get; private set }`  

```csharp
private System.Double windDirection { private get; private set; }
```

- `private System.Collections.Generic.IEnumerable<Game.Simulation.ClimateSystem+SeasonInfo> Game.UI.Editor.SeasonsField.IAdapter.seasons { private get; private set }`  

```csharp
private System.Collections.Generic.IEnumerable<Game.Simulation.ClimateSystem+SeasonInfo> Game.UI.Editor.SeasonsField.IAdapter.seasons { private get; private set; }
```

- `private Game.UI.Editor.SeasonsField+SeasonCurves Game.UI.Editor.SeasonsField.IAdapter.curves { private get; private set }`  

```csharp
private Game.UI.Editor.SeasonsField+SeasonCurves Game.UI.Editor.SeasonsField.IAdapter.curves { private get; private set; }
```

- `public Unity.Entities.Entity selectedSeason { get; set }`  

```csharp
public Unity.Entities.Entity selectedSeason { get; set; }
```


## Constructors

- `public ClimatePanelSystem()`  

```csharp
[Preserve]
	public ClimatePanelSystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		new EntityQueryBuilder(Allocator.Temp).Dispose();
	}
```

- `private <RebuildInspector>b__28_0() : Game.Prefabs.PrefabBase`  

```csharp
private Game.Prefabs.PrefabBase <RebuildInspector>b__28_0();
```

- `private <RebuildInspector>b__28_1(Game.Prefabs.PrefabBase prefab) : System.Void`  

```csharp
private System.Void <RebuildInspector>b__28_1(Game.Prefabs.PrefabBase prefab);
```

- `private DisableInfomode() : System.Collections.IEnumerator`  

```csharp
private IEnumerator DisableInfomode()
	{
		yield return new WaitForSeconds(1f);
		m_ToolSystem.infoview = m_PreviousInfoview;
		m_DelayedInfomodeReset = null;
	}
```

- `private Duplicate() : System.Void`  

```csharp
private void Duplicate()
	{
		PrefabBase prefabBase = currentClimate.Clone();
		m_PrefabSystem.AddPrefab(prefabBase);
		currentClimate = (ClimatePrefab)prefabBase;
	}
```

- `private GetWindInfoView() : System.Void`  

```csharp
private void GetWindInfoView()
	{
		ComponentTypeHandle<PrefabData> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
		NativeArray<ArchetypeChunk> nativeArray = m_AllInfoviewQuery.ToArchetypeChunkArray(Allocator.TempJob);
		for (int i = 0; i < nativeArray.Length; i++)
		{
			NativeArray<PrefabData> nativeArray2 = nativeArray[i].GetNativeArray(ref typeHandle);
			for (int j = 0; j < nativeArray2.Length; j++)
			{
				InfoviewPrefab prefab = m_PrefabSystem.GetPrefab<InfoviewPrefab>(nativeArray2[j]);
				if (prefab.name == "AirPollution")
				{
					m_WindInfoview = prefab;
				}
			}
		}
		nativeArray.Dispose();
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_ClimateSystem = base.World.GetOrCreateSystemManaged<ClimateSystem>();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_WindSimulationSystem = base.World.GetOrCreateSystemManaged<WindSimulationSystem>();
		m_PlanetarySystem = base.World.GetOrCreateSystemManaged<PlanetarySystem>();
		m_AllInfoviewQuery = GetEntityQuery(ComponentType.ReadOnly<PrefabData>(), ComponentType.ReadOnly<InfoviewData>());
		GetWindInfoView();
		title = "Editor.CLIMATE_SETTINGS";
		m_Generator = new EditorGenerator();
		IWidget[] array = new IWidget[1];
		IWidget[] array2 = new IWidget[1];
		EditorSection obj = new EditorSection
		{
			displayName = "Editor.CLIMATE_SETTINGS",
			tooltip = "Editor.CLIMATE_SETTINGS_TOOLTIP",
			expanded = true
		};
		EditorSection editorSection = obj;
		m_InspectorSection = obj;
		array2[0] = editorSection;
		array[0] = Scrollable.WithChildren(array2);
		children = array;
	}
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected override void OnCreateForCompiler()
	{
		base.OnCreateForCompiler();
		__AssignQueries(ref base.CheckedStateRef);
		__TypeHandle.__AssignHandles(ref base.CheckedStateRef);
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		base.OnGameLoaded(serializationContext);
		if (serializationContext.purpose == Purpose.LoadMap || serializationContext.purpose == Purpose.NewMap)
		{
			RebuildInspector();
		}
	}
```

- `protected virtual OnValueChanged(Game.UI.Widgets.IWidget widget) : System.Void`  

```csharp
protected override void OnValueChanged(IWidget widget)
	{
		base.OnValueChanged(widget);
		ClimatePrefab climatePrefab = currentClimate;
		if (!climatePrefab.builtin)
		{
			climatePrefab.RebuildCurves();
		}
		m_PlanetarySystem.latitude = climatePrefab.m_Latitude;
		m_PlanetarySystem.longitude = climatePrefab.m_Longitude;
	}
```

- `public RebuildCurves() : System.Void`  

```csharp
public void RebuildCurves()
	{
		ClimatePrefab climatePrefab = currentClimate;
		climatePrefab.RebuildCurves();
		m_SeasonsCurves = default(SeasonsField.SeasonCurves);
		m_SeasonsCurves.m_Temperature = climatePrefab.m_Temperature;
		m_SeasonsCurves.m_Precipitation = climatePrefab.m_Precipitation;
		m_SeasonsCurves.m_Cloudiness = climatePrefab.m_Cloudiness;
		m_SeasonsCurves.m_Aurora = climatePrefab.m_Aurora;
		m_SeasonsCurves.m_Fog = climatePrefab.m_Fog;
	}
```

- `private RebuildInspector() : System.Void`  

```csharp
private void RebuildInspector()
	{
		List<IWidget> list = new List<IWidget>
		{
			new PopupValueField<PrefabBase>
			{
				displayName = "Editor.CLIMATE_LOAD_PREFAB",
				tooltip = "Editor.CLIMATE_LOAD_PREFAB_TOOLTIP",
				accessor = new DelegateAccessor<PrefabBase>(() => currentClimate, delegate(PrefabBase prefab)
				{
					currentClimate = (ClimatePrefab)prefab;
				}),
				popup = new PrefabPickerPopup(typeof(ClimatePrefab))
			}
		};
		ClimatePrefab climatePrefab = currentClimate;
		bool builtin = climatePrefab.builtin;
		if (builtin)
		{
			list.Add(new Label
			{
				displayName = "Editor.CREATE_CUSTOM_CLIMATE_PROMPT"
			});
			list.Add(new Button
			{
				displayName = "Editor.CREATE_CUSTOM_CLIMATE",
				action = Duplicate
			});
		}
		IWidget[] array = m_Generator.BuildMembers(new ObjectAccessor<PrefabBase>(climatePrefab), 0, "Climate Settings").ToArray();
		if (builtin)
		{
			IWidget[] array2 = array;
			for (int num = 0; num < array2.Length; num++)
			{
				InspectorPanelSystem.DisableAllFields(array2[num]);
			}
		}
		list.AddRange(array);
		m_InspectorSection.children = list;
	}
```


## Nested types

- `Game.UI.Editor.ClimatePanelSystem+TypeHandle`  
- `Game.UI.Editor.ClimatePanelSystem+<DisableInfomode>d__30`  

