# Game.UI.InGame.GamePanelUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class GamePanelUISystem : Game.UI.UISystemBase, Game.Serialization.IPreDeserialize
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Tools.DefaultToolSystem m_DefaultTool;
    private Game.UI.InGame.SelectedInfoUISystem m_SelectedInfoUISystem;
    private Game.UI.InGame.ToolbarUISystem m_ToolbarUISystem;
    private Game.UI.InGame.PhotoModeUISystem m_PhotoModeUISystem;
    private Unity.Entities.EntityQuery m_TransportConfigQuery;
    private Game.Input.InputBarrier m_ToolBarrier;
    private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.GamePanel> m_ActivePanelBinding;
    private System.Collections.Generic.Dictionary<System.String, Game.UI.InGame.GamePanel> m_defaultArgs;
    public System.Action<Game.UI.InGame.GamePanel> eventPanelOpened;
    public System.Action<Game.UI.InGame.GamePanel> eventPanelClosed;
    private Unity.Entities.Entity m_PreviousSelectedEntity;
    private Game.Prefabs.InfoviewPrefab m_PreviousInfoview;
    private static const System.String kGroup;

    public Game.UI.InGame.GamePanel activePanel { get; }
    private System.Boolean NeedsClear { private get; }

    public GamePanelUISystem();

    private System.Boolean <OnCreate>b__15_0();
    private System.Int32 <OnCreate>b__15_1();
    private System.Void CloseActivePanel();
    public System.Void ClosePanel(System.String panelType);
    private System.Void InitializeDefaults();
    private System.Boolean IsPanelAllowed(Game.UI.InGame.GamePanel panel);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    private System.Void OnPanelChanged(Game.UI.InGame.GamePanel previous, Game.UI.InGame.GamePanel next);
    private System.Void OnPanelClosed(Game.UI.InGame.GamePanel panel);
    private System.Void OnPanelOpened(Game.UI.InGame.GamePanel panel);
    protected virtual System.Void OnUpdate();
    public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
    public System.Void SetDefaultArgs(Game.UI.InGame.GamePanel defaultArgs);
    public System.Void ShowPanel(System.String panelType);
    public System.Void ShowPanel(Game.UI.InGame.GamePanel panel);
    public System.Void ShowPanel<T>(System.Int32 tab);
    public System.Void ShowPanel<T>(Unity.Entities.Entity selectedEntity);
    public System.Void TogglePanel(System.String panelType);
    private System.Boolean TryGetTransportConfig(Game.Prefabs.UITransportConfigurationPrefab& config);
}
```


## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Tools.DefaultToolSystem m_DefaultTool`  

```csharp
private Game.Tools.DefaultToolSystem m_DefaultTool;
```

- `private Game.UI.InGame.SelectedInfoUISystem m_SelectedInfoUISystem`  

```csharp
private Game.UI.InGame.SelectedInfoUISystem m_SelectedInfoUISystem;
```

- `private Game.UI.InGame.ToolbarUISystem m_ToolbarUISystem`  

```csharp
private Game.UI.InGame.ToolbarUISystem m_ToolbarUISystem;
```

- `private Game.UI.InGame.PhotoModeUISystem m_PhotoModeUISystem`  

```csharp
private Game.UI.InGame.PhotoModeUISystem m_PhotoModeUISystem;
```

- `private Unity.Entities.EntityQuery m_TransportConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_TransportConfigQuery;
```

- `private Game.Input.InputBarrier m_ToolBarrier`  

```csharp
private Game.Input.InputBarrier m_ToolBarrier;
```

- `private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.GamePanel> m_ActivePanelBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.GamePanel> m_ActivePanelBinding;
```

- `private System.Collections.Generic.Dictionary<System.String, Game.UI.InGame.GamePanel> m_defaultArgs`  

```csharp
private System.Collections.Generic.Dictionary<System.String, Game.UI.InGame.GamePanel> m_defaultArgs;
```

- `public System.Action<Game.UI.InGame.GamePanel> eventPanelOpened`  

```csharp
public System.Action<Game.UI.InGame.GamePanel> eventPanelOpened;
```

- `public System.Action<Game.UI.InGame.GamePanel> eventPanelClosed`  

```csharp
public System.Action<Game.UI.InGame.GamePanel> eventPanelClosed;
```

- `private Unity.Entities.Entity m_PreviousSelectedEntity`  

```csharp
private Unity.Entities.Entity m_PreviousSelectedEntity;
```

- `private Game.Prefabs.InfoviewPrefab m_PreviousInfoview`  

```csharp
private Game.Prefabs.InfoviewPrefab m_PreviousInfoview;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Properties

- `public Game.UI.InGame.GamePanel activePanel { get }`  

```csharp
public Game.UI.InGame.GamePanel activePanel { get; }
```

- `private System.Boolean NeedsClear { private get }`  

```csharp
private System.Boolean NeedsClear { private get; }
```


## Constructors

- `public GamePanelUISystem()`  

```csharp
[Preserve]
	public GamePanelUISystem()
	{
	}
```


## Methods

- `private <OnCreate>b__15_0() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__15_0();
```

- `private <OnCreate>b__15_1() : System.Int32`  

```csharp
private System.Int32 <OnCreate>b__15_1();
```

- `private CloseActivePanel() : System.Void`  

```csharp
private void CloseActivePanel()
	{
		GamePanel value = m_ActivePanelBinding.value;
		if (value != null)
		{
			m_ActivePanelBinding.Update(null);
			OnPanelChanged(value, null);
		}
	}
```

- `public ClosePanel(System.String panelType) : System.Void`  

```csharp
public void ClosePanel(string panelType)
	{
		GamePanel value = m_ActivePanelBinding.value;
		if (value != null && value.GetType().FullName == panelType)
		{
			m_ActivePanelBinding.Update(null);
			OnPanelChanged(value, null);
		}
	}
```

- `private InitializeDefaults() : System.Void`  

```csharp
private void InitializeDefaults()
	{
		SetDefaultArgs(new InfoviewMenu());
		SetDefaultArgs(new ProgressionPanel());
		AddBinding(new TriggerBinding<int>("game", "showProgressionPanel", ShowPanel<ProgressionPanel>));
		SetDefaultArgs(new EconomyPanel());
		AddBinding(new TriggerBinding<int>("game", "showEconomyPanel", ShowPanel<EconomyPanel>));
		SetDefaultArgs(new CityInfoPanel());
		AddBinding(new TriggerBinding<int>("game", "showCityInfoPanel", ShowPanel<CityInfoPanel>));
		SetDefaultArgs(new StatisticsPanel());
		SetDefaultArgs(new TransportationOverviewPanel());
		AddBinding(new TriggerBinding<int>("game", "showTransportationOverviewPanel", ShowPanel<TransportationOverviewPanel>));
		SetDefaultArgs(new ChirperPanel());
		SetDefaultArgs(new LifePathPanel());
		AddBinding(new TriggerBinding<Entity>("game", "showLifePathDetail", ShowPanel<LifePathPanel>));
		SetDefaultArgs(new JournalPanel());
		SetDefaultArgs(new RadioPanel());
		SetDefaultArgs(new PhotoModePanel());
		SetDefaultArgs(new CinematicCameraPanel());
		SetDefaultArgs(new NotificationsPanel());
	}
```

- `private IsPanelAllowed(Game.UI.InGame.GamePanel panel) : System.Boolean`  

```csharp
private bool IsPanelAllowed(GamePanel panel)
	{
		if (panel is RadioPanel)
		{
			return SharedSettings.instance.audio.radioActive;
		}
		if (panel is LifePathPanel lifePathPanel && lifePathPanel.selectedEntity != Entity.Null)
		{
			return base.EntityManager.HasComponent<Followed>(lifePathPanel.selectedEntity);
		}
		return true;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_DefaultTool = base.World.GetOrCreateSystemManaged<DefaultToolSystem>();
		m_SelectedInfoUISystem = base.World.GetOrCreateSystemManaged<SelectedInfoUISystem>();
		m_ToolbarUISystem = base.World.GetOrCreateSystemManaged<ToolbarUISystem>();
		m_PhotoModeUISystem = base.World.GetOrCreateSystemManaged<PhotoModeUISystem>();
		m_TransportConfigQuery = GetEntityQuery(ComponentType.ReadOnly<UITransportConfigurationData>());
		m_ToolBarrier = InputManager.instance.CreateMapBarrier("Tool", "GamePanelUISystem");
		AddBinding(m_ActivePanelBinding = new ValueBinding<GamePanel>("game", "activePanel", null, ValueWriters.Nullable(new ValueWriter<GamePanel>())));
		AddUpdateBinding(new GetterValueBinding<bool>("game", "blockingPanelActive", () => activePanel?.blocking ?? false));
		AddUpdateBinding(new GetterValueBinding<int>("game", "activePanelPosition", () => (int)((activePanel != null) ? activePanel.position : GamePanel.LayoutPosition.Undefined)));
		AddBinding(new TriggerBinding<string>("game", "togglePanel", TogglePanel));
		AddBinding(new TriggerBinding<string>("game", "showPanel", ShowPanel));
		AddBinding(new TriggerBinding<string>("game", "closePanel", ClosePanel));
		AddBinding(new TriggerBinding("game", "closeActivePanel", CloseActivePanel));
		m_defaultArgs = new Dictionary<string, GamePanel>();
		InitializeDefaults();
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		base.OnGameLoaded(serializationContext);
		InitializeDefaults();
	}
```

- `private OnPanelChanged(Game.UI.InGame.GamePanel previous, Game.UI.InGame.GamePanel next) : System.Void`  

```csharp
private void OnPanelChanged([CanBeNull] GamePanel previous, [CanBeNull] GamePanel next)
	{
		if (previous != null && (next == null || next.GetType() != previous.GetType()))
		{
			eventPanelClosed?.Invoke(previous);
			OnPanelClosed(previous);
			if (next == null)
			{
				if (!(previous is InfoviewMenu))
				{
					m_ToolSystem.infoview = ((m_PreviousInfoview != null) ? m_PreviousInfoview : m_ToolSystem.infoview);
					m_PreviousInfoview = null;
				}
				if (m_SelectedInfoUISystem.selectedEntity == Entity.Null)
				{
					m_SelectedInfoUISystem.SetSelection(m_PreviousSelectedEntity);
					m_PreviousSelectedEntity = Entity.Null;
				}
			}
		}
		if (next != null && (previous == null || next.GetType() != previous.GetType()))
		{
			OnPanelOpened(next);
			eventPanelOpened?.Invoke(next);
		}
	}
```

- `private OnPanelClosed(Game.UI.InGame.GamePanel panel) : System.Void`  

```csharp
private void OnPanelClosed(GamePanel panel)
	{
		if (panel is PhotoModePanel)
		{
			m_PhotoModeUISystem.Activate(enabled: false);
		}
		Telemetry.PanelClosed(panel);
		if (panel.retainProperties)
		{
			SetDefaultArgs(panel);
		}
	}
```

- `private OnPanelOpened(Game.UI.InGame.GamePanel panel) : System.Void`  

```csharp
private void OnPanelOpened(GamePanel panel)
	{
		m_PreviousInfoview = m_ToolSystem.activeInfoview;
		if (panel is PhotoModePanel)
		{
			m_PhotoModeUISystem.Activate(enabled: true);
		}
		if (!(panel is InfoviewMenu))
		{
			m_ToolSystem.activeTool = m_DefaultTool;
			m_ToolbarUISystem.ClearAssetSelection();
		}
		if (panel is TransportationOverviewPanel && TryGetTransportConfig(out var config))
		{
			m_ToolSystem.infoview = config.m_TransportInfoview;
		}
		Telemetry.PanelOpened(panel);
		if (panel.retainSelection)
		{
			m_PreviousSelectedEntity = m_SelectedInfoUISystem.selectedEntity;
		}
		m_SelectedInfoUISystem.SetSelection(Entity.Null);
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		base.OnUpdate();
		if (activePanel != null && (NeedsClear || !IsPanelAllowed(activePanel)))
		{
			CloseActivePanel();
		}
		m_ToolBarrier.blocked = activePanel?.blocking ?? false;
	}
```

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PreDeserialize(Context context)
	{
		if (m_ActivePanelBinding.value is PhotoModePanel)
		{
			m_PhotoModeUISystem.Activate(enabled: false);
		}
		m_ActivePanelBinding.Update(null);
	}
```

- `public SetDefaultArgs(Game.UI.InGame.GamePanel defaultArgs) : System.Void`  

```csharp
public void SetDefaultArgs(GamePanel defaultArgs)
	{
		m_defaultArgs[defaultArgs.GetType().FullName] = defaultArgs;
	}
```

- `public ShowPanel(System.String panelType) : System.Void`  

```csharp
public void ShowPanel(GamePanel panel)
	{
		if (IsPanelAllowed(panel))
		{
			GamePanel value = m_ActivePanelBinding.value;
			m_ActivePanelBinding.Update(panel);
			OnPanelChanged(value, panel);
		}
	}
```

- `public ShowPanel(Game.UI.InGame.GamePanel panel) : System.Void`  

```csharp
public void ShowPanel(GamePanel panel)
	{
		if (IsPanelAllowed(panel))
		{
			GamePanel value = m_ActivePanelBinding.value;
			m_ActivePanelBinding.Update(panel);
			OnPanelChanged(value, panel);
		}
	}
```

- `public ShowPanel<T>(System.Int32 tab) : System.Void`  

```csharp
public System.Void ShowPanel<T>(System.Int32 tab);
```

- `public ShowPanel<T>(Unity.Entities.Entity selectedEntity) : System.Void`  

```csharp
public System.Void ShowPanel<T>(Unity.Entities.Entity selectedEntity);
```

- `public TogglePanel(System.String panelType) : System.Void`  

```csharp
public void TogglePanel([CanBeNull] string panelType)
	{
		GamePanel value = m_ActivePanelBinding.value;
		if (value != null && value.GetType().FullName == panelType)
		{
			m_ActivePanelBinding.Update(null);
			OnPanelChanged(value, null);
		}
		else
		{
			ShowPanel(panelType);
		}
	}
```

- `private TryGetTransportConfig(Game.Prefabs.UITransportConfigurationPrefab& config) : System.Boolean`  

```csharp
private bool TryGetTransportConfig(out UITransportConfigurationPrefab config)
	{
		return m_PrefabSystem.TryGetSingletonPrefab<UITransportConfigurationPrefab>(m_TransportConfigQuery, out config);
	}
```


