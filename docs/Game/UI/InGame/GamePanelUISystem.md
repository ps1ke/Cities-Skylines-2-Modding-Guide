# Game.UI.InGame.GamePanelUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Tools.DefaultToolSystem m_DefaultTool`  
- `private Game.UI.InGame.SelectedInfoUISystem m_SelectedInfoUISystem`  
- `private Game.UI.InGame.ToolbarUISystem m_ToolbarUISystem`  
- `private Game.UI.InGame.PhotoModeUISystem m_PhotoModeUISystem`  
- `private Unity.Entities.EntityQuery m_TransportConfigQuery`  
- `private Game.Input.InputBarrier m_ToolBarrier`  
- `private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.GamePanel> m_ActivePanelBinding`  
- `private System.Collections.Generic.Dictionary<System.String, Game.UI.InGame.GamePanel> m_defaultArgs`  
- `public System.Action<Game.UI.InGame.GamePanel> eventPanelOpened`  
- `public System.Action<Game.UI.InGame.GamePanel> eventPanelClosed`  
- `private Unity.Entities.Entity m_PreviousSelectedEntity`  
- `private Game.Prefabs.InfoviewPrefab m_PreviousInfoview`  
- `private static const System.String kGroup`  

## Properties

- `public Game.UI.InGame.GamePanel activePanel { get }`  
- `private System.Boolean NeedsClear { private get }`  

## Constructors

- `public GamePanelUISystem()`  

## Methods

- `private <OnCreate>b__15_0() : System.Boolean`  
- `private <OnCreate>b__15_1() : System.Int32`  
- `private CloseActivePanel() : System.Void`  
- `public ClosePanel(System.String panelType) : System.Void`  
- `private InitializeDefaults() : System.Void`  
- `private IsPanelAllowed(Game.UI.InGame.GamePanel panel) : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `private OnPanelChanged(Game.UI.InGame.GamePanel previous, Game.UI.InGame.GamePanel next) : System.Void`  
- `private OnPanelClosed(Game.UI.InGame.GamePanel panel) : System.Void`  
- `private OnPanelOpened(Game.UI.InGame.GamePanel panel) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  
- `public SetDefaultArgs(Game.UI.InGame.GamePanel defaultArgs) : System.Void`  
- `public ShowPanel(System.String panelType) : System.Void`  
- `public ShowPanel(Game.UI.InGame.GamePanel panel) : System.Void`  
- `public ShowPanel<T>(System.Int32 tab) : System.Void`  
- `public ShowPanel<T>(Unity.Entities.Entity selectedEntity) : System.Void`  
- `public TogglePanel(System.String panelType) : System.Void`  
- `private TryGetTransportConfig(Game.Prefabs.UITransportConfigurationPrefab& config) : System.Boolean`  

