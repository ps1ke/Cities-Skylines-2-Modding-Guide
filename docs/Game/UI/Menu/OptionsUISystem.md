# Game.UI.Menu.OptionsUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.UI.InGame.GameScreenUISystem m_GameScreenUISystem`  
- `private Game.UI.Editor.EditorScreenUISystem m_EditorScreenUISystem`  
- `private Game.UI.Menu.MenuUISystem m_MenuUISystem`  
- `private System.Boolean m_IsAdvanced`  
- `private System.String m_SearchQuery`  
- `private System.Collections.Generic.List<System.Int32> m_SearchIds`  
- `private System.String m_LastLayout`  
- `private Colossal.UI.Binding.ValueBinding<System.String> m_ActivePageBinding`  
- `private Colossal.UI.Binding.ValueBinding<System.String> m_ActiveSectionBinding`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Collections.Generic.List<Game.UI.Menu.OptionsUISystem+Page>> m_PagesBinding`  
- `private Game.UI.Widgets.WidgetBindings m_WidgetBindings`  
- `private Colossal.UI.Binding.ValueBinding<System.Collections.Generic.Dictionary<System.String, Game.Input.ControlPath>> m_LayoutMapBinding`  
- `private Colossal.UI.Binding.ValueBinding<System.Boolean> m_DirectoryBrowserActive`  
- `private Game.UI.Widgets.WidgetBindings m_DirectoryBrowserBinding`  
- `private Game.UI.Editor.DirectoryBrowserPanel m_DirectoryBrowser`  
- `private Game.UI.Editor.DirectoryBrowserPanel m_LastDirectoryBrowser`  
- `private System.Single m_DisplayConfirmationTime`  
- `private Game.Settings.DisplayMode m_LastDisplayMode`  
- `private Game.Settings.ScreenResolution m_LastResolution`  
- `private System.Int32 m_LastDisplayIndex`  
- `private readonly System.Collections.Generic.Dictionary<System.String, Game.UI.Menu.OptionsUISystem+Page> <pages>k__BackingField`  
- `private static const System.String kGroup`  

## Properties

- `private System.Collections.Generic.Dictionary<System.String, Game.UI.Menu.OptionsUISystem+Page> pages { private get }`  
- `private System.Collections.Generic.List<Game.UI.Menu.OptionsUISystem+Page> sortedPages { private get }`  

## Constructors

- `public OptionsUISystem()`  

## Methods

- `private <OnCreate>b__32_0() : System.Collections.Generic.List<Game.UI.Menu.OptionsUISystem+Page>`  
- `private <OnCreate>b__32_1() : System.Boolean`  
- `private <OnCreate>b__32_2() : System.Int32`  
- `private static BuildGroupLabel(System.String pageId, System.String groupId) : Game.UI.Widgets.Label`  
- `private ConfirmDisplay() : System.Void`  
- `private FilterWidgets(System.Collections.Generic.List<System.Int32> ids, System.String query) : System.Void`  
- `private FilterWidgets() : System.Void`  
- `private OnCancelDirectory() : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `private OnModdingToolchainStateChanged(Game.Modding.Toolchain.ToolchainDependencyManager+State newState) : System.Void`  
- `private OnPageClosed(System.String pageId) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public OpenDirectoryBrowser(System.String root, System.Action<System.String> onSelect) : System.Void`  
- `public OpenPage(System.String pageID, System.String sectionID, System.Boolean isAdvanced) : System.Void`  
- `private QueryToolchainState() : System.Void`  
- `private RefreshPage() : System.Void`  
- `public RegisterSetting(Game.Settings.Setting setting, System.String id, System.Boolean addPrefix = False) : System.Void`  
- `private RevertDisplay() : System.Void`  
- `private SelectDefaultPage() : System.Void`  
- `private SelectSection(System.String pageID, System.String sectionID, System.Boolean isAdvanced) : System.Void`  
- `private SelectSection(System.String pageID, System.String sectionID) : System.Void`  
- `private SelectSection(Game.UI.Menu.OptionsUISystem+Page page, Game.UI.Menu.OptionsUISystem+Section section, System.Boolean isAdvanced) : System.Void`  
- `private SelectSection(Game.UI.Menu.OptionsUISystem+Page page, Game.UI.Menu.OptionsUISystem+Section section) : System.Void`  
- `private SelectVisibleSection(Game.UI.Menu.OptionsUISystem+Page page) : System.Void`  
- `public ShowDisplayConfirmation() : System.Void`  
- `private SwitchBindings(System.Boolean browserActive) : System.Void`  
- `public UnregisterSettings(System.String id) : System.Void`  
- `public static UpdateNotificationState(Game.Modding.Toolchain.ModdingToolStatus toolStatus, Game.Modding.Toolchain.DeploymentState deploymentState) : System.Void`  

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

