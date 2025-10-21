# Game.UI.Menu.OptionsUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class OptionsUISystem : Game.UI.UISystemBase
{
    private Game.UI.InGame.GameScreenUISystem m_GameScreenUISystem;
    private Game.UI.Editor.EditorScreenUISystem m_EditorScreenUISystem;
    private Game.UI.Menu.MenuUISystem m_MenuUISystem;
    private System.Boolean m_IsAdvanced;
    private System.String m_SearchQuery;
    private System.Collections.Generic.List<System.Int32> m_SearchIds;
    private System.String m_LastLayout;
    private Colossal.UI.Binding.ValueBinding<System.String> m_ActivePageBinding;
    private Colossal.UI.Binding.ValueBinding<System.String> m_ActiveSectionBinding;
    private Colossal.UI.Binding.GetterValueBinding<System.Collections.Generic.List<Game.UI.Menu.OptionsUISystem+Page>> m_PagesBinding;
    private Game.UI.Widgets.WidgetBindings m_WidgetBindings;
    private Colossal.UI.Binding.ValueBinding<System.Collections.Generic.Dictionary<System.String, Game.Input.ControlPath>> m_LayoutMapBinding;
    private Colossal.UI.Binding.ValueBinding<System.Boolean> m_DirectoryBrowserActive;
    private Game.UI.Widgets.WidgetBindings m_DirectoryBrowserBinding;
    private Game.UI.Editor.DirectoryBrowserPanel m_DirectoryBrowser;
    private Game.UI.Editor.DirectoryBrowserPanel m_LastDirectoryBrowser;
    private System.Single m_DisplayConfirmationTime;
    private Game.Settings.DisplayMode m_LastDisplayMode;
    private Game.Settings.ScreenResolution m_LastResolution;
    private System.Int32 m_LastDisplayIndex;
    private readonly System.Collections.Generic.Dictionary<System.String, Game.UI.Menu.OptionsUISystem+Page> <pages>k__BackingField;
    private static const System.String kGroup;

    private System.Collections.Generic.Dictionary<System.String, Game.UI.Menu.OptionsUISystem+Page> pages { private get; }
    private System.Collections.Generic.List<Game.UI.Menu.OptionsUISystem+Page> sortedPages { private get; }

    public OptionsUISystem();

    private System.Collections.Generic.List<Game.UI.Menu.OptionsUISystem+Page> <OnCreate>b__32_0();
    private System.Boolean <OnCreate>b__32_1();
    private System.Int32 <OnCreate>b__32_2();
    private static Game.UI.Widgets.Label BuildGroupLabel(System.String pageId, System.String groupId);
    private System.Void ConfirmDisplay();
    private System.Void FilterWidgets(System.Collections.Generic.List<System.Int32> ids, System.String query);
    private System.Void FilterWidgets();
    private System.Void OnCancelDirectory();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    private System.Void OnModdingToolchainStateChanged(Game.Modding.Toolchain.ToolchainDependencyManager+State newState);
    private System.Void OnPageClosed(System.String pageId);
    protected virtual System.Void OnUpdate();
    public System.Void OpenDirectoryBrowser(System.String root, System.Action<System.String> onSelect);
    public System.Void OpenPage(System.String pageID, System.String sectionID, System.Boolean isAdvanced);
    private System.Void QueryToolchainState();
    private System.Void RefreshPage();
    public System.Void RegisterSetting(Game.Settings.Setting setting, System.String id, System.Boolean addPrefix);
    private System.Void RevertDisplay();
    private System.Void SelectDefaultPage();
    private System.Void SelectSection(System.String pageID, System.String sectionID, System.Boolean isAdvanced);
    private System.Void SelectSection(System.String pageID, System.String sectionID);
    private System.Void SelectSection(Game.UI.Menu.OptionsUISystem+Page page, Game.UI.Menu.OptionsUISystem+Section section, System.Boolean isAdvanced);
    private System.Void SelectSection(Game.UI.Menu.OptionsUISystem+Page page, Game.UI.Menu.OptionsUISystem+Section section);
    private System.Void SelectVisibleSection(Game.UI.Menu.OptionsUISystem+Page page);
    public System.Void ShowDisplayConfirmation();
    private System.Void SwitchBindings(System.Boolean browserActive);
    public System.Void UnregisterSettings(System.String id);
    public static System.Void UpdateNotificationState(Game.Modding.Toolchain.ModdingToolStatus toolStatus, Game.Modding.Toolchain.DeploymentState deploymentState);
}
```


## Fields

- `private Game.UI.InGame.GameScreenUISystem m_GameScreenUISystem`  

```csharp
private Game.UI.InGame.GameScreenUISystem m_GameScreenUISystem;
```

- `private Game.UI.Editor.EditorScreenUISystem m_EditorScreenUISystem`  

```csharp
private Game.UI.Editor.EditorScreenUISystem m_EditorScreenUISystem;
```

- `private Game.UI.Menu.MenuUISystem m_MenuUISystem`  

```csharp
private Game.UI.Menu.MenuUISystem m_MenuUISystem;
```

- `private System.Boolean m_IsAdvanced`  

```csharp
private System.Boolean m_IsAdvanced;
```

- `private System.String m_SearchQuery`  

```csharp
private System.String m_SearchQuery;
```

- `private System.Collections.Generic.List<System.Int32> m_SearchIds`  

```csharp
private System.Collections.Generic.List<System.Int32> m_SearchIds;
```

- `private System.String m_LastLayout`  

```csharp
private System.String m_LastLayout;
```

- `private Colossal.UI.Binding.ValueBinding<System.String> m_ActivePageBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.String> m_ActivePageBinding;
```

- `private Colossal.UI.Binding.ValueBinding<System.String> m_ActiveSectionBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.String> m_ActiveSectionBinding;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Collections.Generic.List<Game.UI.Menu.OptionsUISystem+Page>> m_PagesBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Collections.Generic.List<Game.UI.Menu.OptionsUISystem+Page>> m_PagesBinding;
```

- `private Game.UI.Widgets.WidgetBindings m_WidgetBindings`  

```csharp
private Game.UI.Widgets.WidgetBindings m_WidgetBindings;
```

- `private Colossal.UI.Binding.ValueBinding<System.Collections.Generic.Dictionary<System.String, Game.Input.ControlPath>> m_LayoutMapBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Collections.Generic.Dictionary<System.String, Game.Input.ControlPath>> m_LayoutMapBinding;
```

- `private Colossal.UI.Binding.ValueBinding<System.Boolean> m_DirectoryBrowserActive`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Boolean> m_DirectoryBrowserActive;
```

- `private Game.UI.Widgets.WidgetBindings m_DirectoryBrowserBinding`  

```csharp
private Game.UI.Widgets.WidgetBindings m_DirectoryBrowserBinding;
```

- `private Game.UI.Editor.DirectoryBrowserPanel m_DirectoryBrowser`  

```csharp
private Game.UI.Editor.DirectoryBrowserPanel m_DirectoryBrowser;
```

- `private Game.UI.Editor.DirectoryBrowserPanel m_LastDirectoryBrowser`  

```csharp
private Game.UI.Editor.DirectoryBrowserPanel m_LastDirectoryBrowser;
```

- `private System.Single m_DisplayConfirmationTime`  

```csharp
private System.Single m_DisplayConfirmationTime;
```

- `private Game.Settings.DisplayMode m_LastDisplayMode`  

```csharp
private Game.Settings.DisplayMode m_LastDisplayMode;
```

- `private Game.Settings.ScreenResolution m_LastResolution`  

```csharp
private Game.Settings.ScreenResolution m_LastResolution;
```

- `private System.Int32 m_LastDisplayIndex`  

```csharp
private System.Int32 m_LastDisplayIndex;
```

- `private readonly System.Collections.Generic.Dictionary<System.String, Game.UI.Menu.OptionsUISystem+Page> <pages>k__BackingField`  

```csharp
private readonly System.Collections.Generic.Dictionary<System.String, Game.UI.Menu.OptionsUISystem+Page> <pages>k__BackingField;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Properties

- `private System.Collections.Generic.Dictionary<System.String, Game.UI.Menu.OptionsUISystem+Page> pages { private get }`  

```csharp
private System.Collections.Generic.Dictionary<System.String, Game.UI.Menu.OptionsUISystem+Page> pages { private get; }
```

- `private System.Collections.Generic.List<Game.UI.Menu.OptionsUISystem+Page> sortedPages { private get }`  

```csharp
private System.Collections.Generic.List<Game.UI.Menu.OptionsUISystem+Page> sortedPages { private get; }
```


## Constructors

- `public OptionsUISystem()`  

```csharp
public OptionsUISystem();
```


## Methods

- `private <OnCreate>b__32_0() : System.Collections.Generic.List<Game.UI.Menu.OptionsUISystem+Page>`  

```csharp
private System.Collections.Generic.List<Game.UI.Menu.OptionsUISystem+Page> <OnCreate>b__32_0();
```

- `private <OnCreate>b__32_1() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__32_1();
```

- `private <OnCreate>b__32_2() : System.Int32`  

```csharp
private System.Int32 <OnCreate>b__32_2();
```

- `private static BuildGroupLabel(System.String pageId, System.String groupId) : Game.UI.Widgets.Label`  

```csharp
private static Game.UI.Widgets.Label BuildGroupLabel(System.String pageId, System.String groupId);
```

- `private ConfirmDisplay() : System.Void`  

```csharp
private System.Void ConfirmDisplay();
```

- `private FilterWidgets(System.Collections.Generic.List<System.Int32> ids, System.String query) : System.Void`  

```csharp
private System.Void FilterWidgets(System.Collections.Generic.List<System.Int32> ids, System.String query);
```

- `private FilterWidgets() : System.Void`  

```csharp
private System.Void FilterWidgets();
```

- `private OnCancelDirectory() : System.Void`  

```csharp
private System.Void OnCancelDirectory();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `private OnModdingToolchainStateChanged(Game.Modding.Toolchain.ToolchainDependencyManager+State newState) : System.Void`  

```csharp
private System.Void OnModdingToolchainStateChanged(Game.Modding.Toolchain.ToolchainDependencyManager+State newState);
```

- `private OnPageClosed(System.String pageId) : System.Void`  

```csharp
private System.Void OnPageClosed(System.String pageId);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public OpenDirectoryBrowser(System.String root, System.Action<System.String> onSelect) : System.Void`  

```csharp
public System.Void OpenDirectoryBrowser(System.String root, System.Action<System.String> onSelect);
```

- `public OpenPage(System.String pageID, System.String sectionID, System.Boolean isAdvanced) : System.Void`  

```csharp
public System.Void OpenPage(System.String pageID, System.String sectionID, System.Boolean isAdvanced);
```

- `private QueryToolchainState() : System.Void`  

```csharp
private System.Void QueryToolchainState();
```

- `private RefreshPage() : System.Void`  

```csharp
private System.Void RefreshPage();
```

- `public RegisterSetting(Game.Settings.Setting setting, System.String id, System.Boolean addPrefix = False) : System.Void`  

```csharp
public System.Void RegisterSetting(Game.Settings.Setting setting, System.String id, System.Boolean addPrefix);
```

- `private RevertDisplay() : System.Void`  

```csharp
private System.Void RevertDisplay();
```

- `private SelectDefaultPage() : System.Void`  

```csharp
private System.Void SelectDefaultPage();
```

- `private SelectSection(System.String pageID, System.String sectionID, System.Boolean isAdvanced) : System.Void`  

```csharp
private System.Void SelectSection(System.String pageID, System.String sectionID, System.Boolean isAdvanced);
```

- `private SelectSection(System.String pageID, System.String sectionID) : System.Void`  

```csharp
private System.Void SelectSection(System.String pageID, System.String sectionID);
```

- `private SelectSection(Game.UI.Menu.OptionsUISystem+Page page, Game.UI.Menu.OptionsUISystem+Section section, System.Boolean isAdvanced) : System.Void`  

```csharp
private System.Void SelectSection(Game.UI.Menu.OptionsUISystem+Page page, Game.UI.Menu.OptionsUISystem+Section section, System.Boolean isAdvanced);
```

- `private SelectSection(Game.UI.Menu.OptionsUISystem+Page page, Game.UI.Menu.OptionsUISystem+Section section) : System.Void`  

```csharp
private System.Void SelectSection(Game.UI.Menu.OptionsUISystem+Page page, Game.UI.Menu.OptionsUISystem+Section section);
```

- `private SelectVisibleSection(Game.UI.Menu.OptionsUISystem+Page page) : System.Void`  

```csharp
private System.Void SelectVisibleSection(Game.UI.Menu.OptionsUISystem+Page page);
```

- `public ShowDisplayConfirmation() : System.Void`  

```csharp
public System.Void ShowDisplayConfirmation();
```

- `private SwitchBindings(System.Boolean browserActive) : System.Void`  

```csharp
private System.Void SwitchBindings(System.Boolean browserActive);
```

- `public UnregisterSettings(System.String id) : System.Void`  

```csharp
public System.Void UnregisterSettings(System.String id);
```

- `public static UpdateNotificationState(Game.Modding.Toolchain.ModdingToolStatus toolStatus, Game.Modding.Toolchain.DeploymentState deploymentState) : System.Void`  

```csharp
public static System.Void UpdateNotificationState(Game.Modding.Toolchain.ModdingToolStatus toolStatus, Game.Modding.Toolchain.DeploymentState deploymentState);
```


## Nested types

- `Game.UI.Menu.OptionsUISystem+Page`  
- `Game.UI.Menu.OptionsUISystem+Section`  
- `Game.UI.Menu.OptionsUISystem+Option`  
- `Game.UI.Menu.OptionsUISystem+WidgetInfo`  
- `Game.UI.Menu.OptionsUISystem+UnitSettings`  
- `Game.UI.Menu.OptionsUISystem+<>c`  
- `Game.UI.Menu.OptionsUISystem+<>c__DisplayClass19_0`  
- `Game.UI.Menu.OptionsUISystem+<>c__DisplayClass20_0`  
- `Game.UI.Menu.OptionsUISystem+<>c__DisplayClass37_0`  
- `Game.UI.Menu.OptionsUISystem+<>c__DisplayClass46_0`  
- `Game.UI.Menu.OptionsUISystem+<QueryToolchainState>d__18`  

