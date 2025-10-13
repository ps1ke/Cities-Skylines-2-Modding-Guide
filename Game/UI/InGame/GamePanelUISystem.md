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
public GamePanelUISystem();
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
private System.Void CloseActivePanel();
```

- `public ClosePanel(System.String panelType) : System.Void`  

```csharp
public System.Void ClosePanel(System.String panelType);
```

- `private InitializeDefaults() : System.Void`  

```csharp
private System.Void InitializeDefaults();
```

- `private IsPanelAllowed(Game.UI.InGame.GamePanel panel) : System.Boolean`  

```csharp
private System.Boolean IsPanelAllowed(Game.UI.InGame.GamePanel panel);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `private OnPanelChanged(Game.UI.InGame.GamePanel previous, Game.UI.InGame.GamePanel next) : System.Void`  

```csharp
private System.Void OnPanelChanged(Game.UI.InGame.GamePanel previous, Game.UI.InGame.GamePanel next);
```

- `private OnPanelClosed(Game.UI.InGame.GamePanel panel) : System.Void`  

```csharp
private System.Void OnPanelClosed(Game.UI.InGame.GamePanel panel);
```

- `private OnPanelOpened(Game.UI.InGame.GamePanel panel) : System.Void`  

```csharp
private System.Void OnPanelOpened(Game.UI.InGame.GamePanel panel);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
```

- `public SetDefaultArgs(Game.UI.InGame.GamePanel defaultArgs) : System.Void`  

```csharp
public System.Void SetDefaultArgs(Game.UI.InGame.GamePanel defaultArgs);
```

- `public ShowPanel(System.String panelType) : System.Void`  

```csharp
public System.Void ShowPanel(System.String panelType);
```

- `public ShowPanel(Game.UI.InGame.GamePanel panel) : System.Void`  

```csharp
public System.Void ShowPanel(Game.UI.InGame.GamePanel panel);
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
public System.Void TogglePanel(System.String panelType);
```

- `private TryGetTransportConfig(Game.Prefabs.UITransportConfigurationPrefab& config) : System.Boolean`  

```csharp
private System.Boolean TryGetTransportConfig(Game.Prefabs.UITransportConfigurationPrefab& config);
```


