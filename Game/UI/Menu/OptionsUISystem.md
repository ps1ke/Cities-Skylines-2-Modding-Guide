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
[Preserve]
	public OptionsUISystem()
	{
	}
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
private static Label BuildGroupLabel(string pageId, string groupId)
	{
		string text = pageId + "." + groupId;
		return new Label
		{
			displayName = LocalizedString.Id("Options.GROUP[" + text + "]"),
			level = Label.Level.SubTitle,
			beta = BetaFilter.options.Contains(text)
		};
	}
```

- `private ConfirmDisplay() : System.Void`  

```csharp
private void ConfirmDisplay()
	{
		m_DisplayConfirmationTime = -1f;
	}
```

- `private FilterWidgets(System.Collections.Generic.List<System.Int32> ids, System.String query) : System.Void`  

```csharp
private void FilterWidgets()
	{
		List<IWidget> list = new List<IWidget>();
		int num = -1;
		int num2 = -1;
		int num3 = -1;
		List<Page> list2 = sortedPages;
		for (int i = 0; i < m_SearchIds.Count; i++)
		{
			WidgetInfo.GetIndices(m_SearchIds[i], out var page, out var section, out var widget);
			if (page >= list2.Count)
			{
				continue;
			}
			bool flag = page != num;
			if (flag)
			{
				num2 = -1;
			}
			Page page2 = list2[page];
			if (section >= page2.sections.Count)
			{
				continue;
			}
			bool flag2 = section != num2;
			if (flag2)
			{
				num3 = -1;
			}
			Section section2 = page2.sections[section];
			if (widget >= section2.options.Count)
			{
				continue;
			}
			Option option = section2.options[widget];
			if (option.searchHidden || !option.isVisible)
			{
				continue;
			}
			string text = section2.groupNames[option.advancedGroupIndex];
			bool flag3 = option.advancedGroupIndex != num3;
			if (flag || flag2 || flag3)
			{
				Breadcrumbs breadcrumbs = new Breadcrumbs();
				Label label = new Label
				{
					displayName = LocalizedString.Id("Options.SECTION[" + page2.id + "]"),
					level = Label.Level.Title,
					beta = BetaFilter.options.Contains(page2.id)
				};
				breadcrumbs.WithLabel(label);
				if (page2.sections.Count > 1)
				{
					Label label2 = new Label
					{
						displayName = LocalizedString.Id("Options.TAB[" + section2.id + "]"),
						level = Label.Level.SubTitle,
						beta = BetaFilter.options.Contains(section2.id)
					};
					breadcrumbs.WithLabel(label2);
				}
				if (section2.groupNames.Length > 1 && section2.groupToShowName.Contains(text))
				{
					Label label3 = BuildGroupLabel(page2.id, text);
					breadcrumbs.WithLabel(label3);
				}
				list.Add(breadcrumbs);
			}
			list.Add(option.widget);
			num = page;
			num2 = section;
			num3 = option.advancedGroupIndex;
		}
		m_WidgetBindings.children = list;
	}
```

- `private FilterWidgets() : System.Void`  

```csharp
private void FilterWidgets()
	{
		List<IWidget> list = new List<IWidget>();
		int num = -1;
		int num2 = -1;
		int num3 = -1;
		List<Page> list2 = sortedPages;
		for (int i = 0; i < m_SearchIds.Count; i++)
		{
			WidgetInfo.GetIndices(m_SearchIds[i], out var page, out var section, out var widget);
			if (page >= list2.Count)
			{
				continue;
			}
			bool flag = page != num;
			if (flag)
			{
				num2 = -1;
			}
			Page page2 = list2[page];
			if (section >= page2.sections.Count)
			{
				continue;
			}
			bool flag2 = section != num2;
			if (flag2)
			{
				num3 = -1;
			}
			Section section2 = page2.sections[section];
			if (widget >= section2.options.Count)
			{
				continue;
			}
			Option option = section2.options[widget];
			if (option.searchHidden || !option.isVisible)
			{
				continue;
			}
			string text = section2.groupNames[option.advancedGroupIndex];
			bool flag3 = option.advancedGroupIndex != num3;
			if (flag || flag2 || flag3)
			{
				Breadcrumbs breadcrumbs = new Breadcrumbs();
				Label label = new Label
				{
					displayName = LocalizedString.Id("Options.SECTION[" + page2.id + "]"),
					level = Label.Level.Title,
					beta = BetaFilter.options.Contains(page2.id)
				};
				breadcrumbs.WithLabel(label);
				if (page2.sections.Count > 1)
				{
					Label label2 = new Label
					{
						displayName = LocalizedString.Id("Options.TAB[" + section2.id + "]"),
						level = Label.Level.SubTitle,
						beta = BetaFilter.options.Contains(section2.id)
					};
					breadcrumbs.WithLabel(label2);
				}
				if (section2.groupNames.Length > 1 && section2.groupToShowName.Contains(text))
				{
					Label label3 = BuildGroupLabel(page2.id, text);
					breadcrumbs.WithLabel(label3);
				}
				list.Add(breadcrumbs);
			}
			list.Add(option.widget);
			num = page;
			num2 = section;
			num3 = option.advancedGroupIndex;
		}
		m_WidgetBindings.children = list;
	}
```

- `private OnCancelDirectory() : System.Void`  

```csharp
private void OnCancelDirectory()
	{
		if (m_DirectoryBrowser != null)
		{
			m_DirectoryBrowser = null;
		}
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		AddUpdateBinding(m_WidgetBindings = new WidgetBindings("options"));
		m_WidgetBindings.AddDefaultBindings();
		m_WidgetBindings.AddBindings<InputBindingField.Bindings>();
		AddBinding(m_ActivePageBinding = new ValueBinding<string>("options", "activePage", string.Empty));
		AddBinding(m_ActiveSectionBinding = new ValueBinding<string>("options", "activeSection", string.Empty));
		AddBinding(m_PagesBinding = new GetterValueBinding<List<Page>>("options", "pages", () => sortedPages, new ListWriter<Page>(new ValueWriter<Page>())));
		AddUpdateBinding(new GetterValueBinding<bool>("options", "displayConfirmationVisible", () => m_DisplayConfirmationTime > 0f));
		AddUpdateBinding(new GetterValueBinding<int>("options", "displayConfirmationTime", () => Mathf.Max(Mathf.CeilToInt(m_DisplayConfirmationTime), 0)));
		AddUpdateBinding(new GetterValueBinding<string>("options", "interfaceStyle", () => SharedSettings.instance.userInterface.interfaceStyle));
		AddUpdateBinding(new GetterValueBinding<float>("options", "interfaceTransparency", () => SharedSettings.instance.userInterface.interfaceTransparency));
		AddUpdateBinding(new GetterValueBinding<bool>("options", "interfaceScaling", () => SharedSettings.instance.userInterface.interfaceScaling));
		AddUpdateBinding(new GetterValueBinding<float>("options", "textScale", () => SharedSettings.instance.userInterface.textScale));
		AddUpdateBinding(new GetterValueBinding<string>("options", "interfaceStyle", () => SharedSettings.instance.userInterface.interfaceStyle));
		AddUpdateBinding(new GetterValueBinding<bool>("options", "unlockHighlightsEnabled", () => SharedSettings.instance.userInterface.unlockHighlightsEnabled));
		AddUpdateBinding(new GetterValueBinding<bool>("options", "chirperPopupsEnabled", () => SharedSettings.instance.userInterface.chirperPopupsEnabled));
		AddUpdateBinding(new GetterValueBinding<int>("options", "inputHintsType", () => (int)SharedSettings.instance.userInterface.GetFinalInputHintsType()));
		AddUpdateBinding(new GetterValueBinding<int>("options", "keyboardLayout", () => (int)SharedSettings.instance.userInterface.keyboardLayout));
		AddUpdateBinding(new GetterValueBinding<bool>("options", "shortcutHints", () => SharedSettings.instance.userInterface.shortcutHints));
		AddBinding(m_LayoutMapBinding = new ValueBinding<Dictionary<string, ControlPath>>("options", "layoutMap", new Dictionary<string, ControlPath>(), new DictionaryWriter<string, ControlPath>(null, new ValueWriter<ControlPath>())));
		AddUpdateBinding(new GetterValueBinding<UnitSettings>("options", "unitSettings", () => new UnitSettings(SharedSettings.instance.userInterface), new ValueWriter<UnitSettings>()));
		AddBinding(new TriggerBinding("options", "confirmDisplay", ConfirmDisplay));
		AddBinding(new TriggerBinding("options", "revertDisplay", RevertDisplay));
		AddBinding(new TriggerBinding<string>("options", "onOptionsPageClosed", OnPageClosed));
		AddBinding(new TriggerBinding<string, string, bool>("options", "selectPage", SelectSection));
		AddBinding(new TriggerBinding<List<int>, string>("options", "filteredWidgets", FilterWidgets, new ListReader<int>()));
		AddBinding(new TriggerBinding("options", "toolchain.dependency.action", ConfirmDisplay));
		AddUpdateBinding(m_DirectoryBrowserBinding = new WidgetBindings("options", "directoryBrowser"));
		m_DirectoryBrowserBinding.AddDefaultBindings();
		m_DirectoryBrowserBinding.AddBindings<IItemPicker.Bindings>();
		AddBinding(m_DirectoryBrowserActive = new ValueBinding<bool>("options", "directoryBrowserActive", initialValue: false));
		AddBinding(new TriggerBinding("options", "cancelDirectoryBrowser", OnCancelDirectory));
		SwitchBindings(browserActive: false);
		SelectDefaultPage();
		QueryToolchainState();
		ToolchainDeployment.dependencyManager.OnStateChanged += OnModdingToolchainStateChanged;
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		base.OnDestroy();
		ToolchainDeployment.dependencyManager.OnStateChanged -= OnModdingToolchainStateChanged;
	}
```

- `private OnModdingToolchainStateChanged(Game.Modding.Toolchain.ToolchainDependencyManager+State newState) : System.Void`  

```csharp
private void OnModdingToolchainStateChanged(ToolchainDependencyManager.State newState)
	{
		GameManager.instance.RunOnMainThread(delegate
		{
			UpdateNotificationState(newState.m_Status, newState.m_State);
		});
	}
```

- `private OnPageClosed(System.String pageId) : System.Void`  

```csharp
private void OnPageClosed(string pageId)
	{
		if (pageId == "Graphics")
		{
			Telemetry.GraphicsSettings();
		}
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		switch (GameManager.instance.gameMode)
		{
		case GameMode.MainMenu:
			if (m_MenuUISystem == null)
			{
				m_MenuUISystem = base.World.GetExistingSystemManaged<MenuUISystem>();
			}
			if (m_MenuUISystem != null && m_MenuUISystem.activeScreen != MenuUISystem.MenuScreen.Options)
			{
				return;
			}
			break;
		case GameMode.Game:
			if (m_GameScreenUISystem == null)
			{
				m_GameScreenUISystem = base.World.GetExistingSystemManaged<GameScreenUISystem>();
			}
			if (m_GameScreenUISystem != null && m_GameScreenUISystem.activeScreen != GameScreenUISystem.GameScreen.Options)
			{
				return;
			}
			break;
		case GameMode.Editor:
			if (m_EditorScreenUISystem == null)
			{
				m_EditorScreenUISystem = base.World.GetExistingSystemManaged<EditorScreenUISystem>();
			}
			if (m_EditorScreenUISystem != null && m_EditorScreenUISystem.activeScreen != EditorScreenUISystem.EditorScreen.Options)
			{
				return;
			}
			break;
		}
		bool flag = false;
		bool flag2 = false;
		foreach (Page value in pages.Values)
		{
			if (!string.IsNullOrEmpty(m_SearchQuery) || m_ActivePageBinding.value == value.id)
			{
				flag |= value.UpdateNameAndDescription(m_IsAdvanced);
				bool flag3 = value.UpdateVisibility(m_IsAdvanced);
				flag = flag || flag3;
				flag2 = flag2 || flag3;
			}
			if (string.IsNullOrEmpty(m_SearchQuery))
			{
				bool flag4 = value.UpdateWarning(m_IsAdvanced);
				flag = flag || flag4;
				if (m_ActivePageBinding.value == value.id)
				{
					flag2 = flag2 || flag4;
				}
			}
		}
		if (flag)
		{
			m_PagesBinding.Update();
		}
		if (flag2)
		{
			RefreshPage();
		}
		base.OnUpdate();
		if (m_DisplayConfirmationTime > 0f)
		{
			m_DisplayConfirmationTime -= UnityEngine.Time.deltaTime;
			if (m_DisplayConfirmationTime <= 0f)
			{
				RevertDisplay();
			}
		}
		if (m_DirectoryBrowser != null)
		{
			m_DirectoryBrowserActive.Update(newValue: true);
			m_DirectoryBrowserBinding.children = m_DirectoryBrowser.children;
		}
		else
		{
			m_DirectoryBrowserActive.Update(newValue: false);
			m_DirectoryBrowserBinding.children = Array.Empty<IWidget>();
		}
		if (m_LastDirectoryBrowser != m_DirectoryBrowser)
		{
			SwitchBindings(m_DirectoryBrowser != null);
			m_LastDirectoryBrowser = m_DirectoryBrowser;
		}
		string text = ((SharedSettings.instance.userInterface.keyboardLayout != InterfaceSettings.KeyboardLayout.AutoDetect) ? null : Keyboard.current?.keyboardLayout);
		if (!(text != m_LastLayout))
		{
			return;
		}
		m_LastLayout = text;
		Dictionary<string, ControlPath> dictionary = new Dictionary<string, ControlPath>();
		Keyboard current2 = Keyboard.current;
		if (m_LastLayout != null && current2 != null)
		{
			foreach (KeyControl key in current2.allKeys)
			{
				if (key != null && ControlPath.NeedLocalName(current2, key))
				{
					InputControl inputControl = current2.allControls.FirstOrDefault(delegate(InputControl c)
					{
						_ = c.displayName;
						return c.m_DisplayNameFromLayout == key.displayName;
					});
					if (inputControl == null)
					{
						dictionary[key.name] = new ControlPath
						{
							name = key.displayName,
							displayName = key.displayName
						};
					}
					else if (key.name != inputControl.name)
					{
						dictionary[key.name] = new ControlPath
						{
							name = inputControl.name,
							displayName = ((inputControl.name.Length == 1) ? inputControl.name.ToUpper() : inputControl.name)
						};
					}
				}
			}
		}
		m_LayoutMapBinding.Update(dictionary);
	}
```

- `public OpenDirectoryBrowser(System.String root, System.Action<System.String> onSelect) : System.Void`  

```csharp
public void OpenDirectoryBrowser(string root, Action<string> onSelect)
	{
		if (m_DirectoryBrowser == null)
		{
			m_DirectoryBrowser = new DirectoryBrowserPanel(root, null, delegate(string directory)
			{
				onSelect?.Invoke(directory);
				OnCancelDirectory();
			}, OnCancelDirectory);
		}
	}
```

- `public OpenPage(System.String pageID, System.String sectionID, System.Boolean isAdvanced) : System.Void`  

```csharp
public void OpenPage(string pageID, string sectionID, bool isAdvanced)
	{
		if (string.IsNullOrEmpty(pageID))
		{
			throw new ArgumentException("pageID can not be null or empty", "pageID");
		}
		switch (GameManager.instance.gameMode)
		{
		case GameMode.MainMenu:
			if (m_MenuUISystem == null)
			{
				m_MenuUISystem = base.World.GetExistingSystemManaged<MenuUISystem>();
			}
			if (m_MenuUISystem != null)
			{
				m_MenuUISystem.activeScreen = MenuUISystem.MenuScreen.Options;
				SelectSection(pageID, sectionID, isAdvanced);
			}
			break;
		case GameMode.Game:
			if (m_GameScreenUISystem == null)
			{
				m_GameScreenUISystem = base.World.GetExistingSystemManaged<GameScreenUISystem>();
			}
			if (m_GameScreenUISystem != null)
			{
				m_GameScreenUISystem.activeScreen = GameScreenUISystem.GameScreen.Options;
				SelectSection(pageID, sectionID, isAdvanced);
			}
			break;
		case GameMode.Editor:
			if (m_EditorScreenUISystem == null)
			{
				m_EditorScreenUISystem = base.World.GetExistingSystemManaged<EditorScreenUISystem>();
			}
			if (m_EditorScreenUISystem != null)
			{
				m_EditorScreenUISystem.activeScreen = EditorScreenUISystem.EditorScreen.Options;
				SelectSection(pageID, sectionID, isAdvanced);
			}
			break;
		}
	}
```

- `private QueryToolchainState() : System.Void`  

```csharp
private async void QueryToolchainState()
	{
		try
		{
			UpdateNotificationState(ModdingToolStatus.Idle, await ToolchainDeployment.dependencyManager.GetCurrentState());
		}
		catch (Exception exception)
		{
			UISystemBase.log.Error(exception, "Toolchain state query failed");
		}
	}
```

- `private RefreshPage() : System.Void`  

```csharp
private void RefreshPage()
	{
		SelectSection(m_ActivePageBinding.value, m_ActiveSectionBinding.value);
	}
```

- `public RegisterSetting(Game.Settings.Setting setting, System.String id, System.Boolean addPrefix = False) : System.Void`  

```csharp
public void RegisterSetting(Setting setting, string id, bool addPrefix = false)
	{
		bool flag = pages.Count == 0;
		Page page = setting.GetPageData(id, addPrefix).BuildPage();
		page.builtIn = setting.builtIn;
		if (pages.TryGetValue(page.id, out var value))
		{
			page.index = value.index;
		}
		else
		{
			page.index = pages.Count;
		}
		for (int i = 0; i < page.sections.Count; i++)
		{
			page.sections[i].index = i;
		}
		page.UpdateVisibility(m_IsAdvanced);
		page.UpdateNameAndDescription(m_IsAdvanced);
		page.UpdateWarning(m_IsAdvanced);
		pages[page.id] = page;
		if (flag && page.sections.Count != 0)
		{
			SelectVisibleSection(page);
		}
		m_PagesBinding.Update();
		RefreshPage();
	}
```

- `private RevertDisplay() : System.Void`  

```csharp
private void RevertDisplay()
	{
		m_DisplayConfirmationTime = -1f;
		SharedSettings.instance.graphics.resolution = m_LastResolution;
		SharedSettings.instance.graphics.displayMode = m_LastDisplayMode;
		SharedSettings.instance.graphics.displayIndex = m_LastDisplayIndex;
		SharedSettings.instance.graphics.ApplyAndSave();
	}
```

- `private SelectDefaultPage() : System.Void`  

```csharp
private void SelectDefaultPage()
	{
		foreach (Page value in pages.Values)
		{
			foreach (Section section in value.sections)
			{
				if (section.isVisible)
				{
					SelectSection(value, section);
					return;
				}
			}
		}
	}
```

- `private SelectSection(System.String pageID, System.String sectionID, System.Boolean isAdvanced) : System.Void`  

```csharp
private void SelectSection(Page page, Section section)
	{
		m_ActivePageBinding.Update(page?.id ?? string.Empty);
		m_ActiveSectionBinding.Update(section?.id ?? string.Empty);
		m_WidgetBindings.children = section.GetItems(m_IsAdvanced);
	}
```

- `private SelectSection(System.String pageID, System.String sectionID) : System.Void`  

```csharp
private void SelectSection(Page page, Section section)
	{
		m_ActivePageBinding.Update(page?.id ?? string.Empty);
		m_ActiveSectionBinding.Update(section?.id ?? string.Empty);
		m_WidgetBindings.children = section.GetItems(m_IsAdvanced);
	}
```

- `private SelectSection(Game.UI.Menu.OptionsUISystem+Page page, Game.UI.Menu.OptionsUISystem+Section section, System.Boolean isAdvanced) : System.Void`  

```csharp
private void SelectSection(Page page, Section section)
	{
		m_ActivePageBinding.Update(page?.id ?? string.Empty);
		m_ActiveSectionBinding.Update(section?.id ?? string.Empty);
		m_WidgetBindings.children = section.GetItems(m_IsAdvanced);
	}
```

- `private SelectSection(Game.UI.Menu.OptionsUISystem+Page page, Game.UI.Menu.OptionsUISystem+Section section) : System.Void`  

```csharp
private void SelectSection(Page page, Section section)
	{
		m_ActivePageBinding.Update(page?.id ?? string.Empty);
		m_ActiveSectionBinding.Update(section?.id ?? string.Empty);
		m_WidgetBindings.children = section.GetItems(m_IsAdvanced);
	}
```

- `private SelectVisibleSection(Game.UI.Menu.OptionsUISystem+Page page) : System.Void`  

```csharp
private void SelectVisibleSection(Page page)
	{
		SelectSection(page, page.visibleSections.FirstOrDefault());
	}
```

- `public ShowDisplayConfirmation() : System.Void`  

```csharp
public void ShowDisplayConfirmation()
	{
		m_DisplayConfirmationTime = 15f;
		m_LastResolution = SharedSettings.instance.graphics.resolution;
		m_LastDisplayMode = SharedSettings.instance.graphics.displayMode;
		m_LastDisplayIndex = SharedSettings.instance.graphics.displayIndex;
	}
```

- `private SwitchBindings(System.Boolean browserActive) : System.Void`  

```csharp
private void SwitchBindings(bool browserActive)
	{
		foreach (IBinding binding in m_WidgetBindings.bindings)
		{
			if (binding is RawTriggerBindingBase rawTriggerBindingBase)
			{
				rawTriggerBindingBase.active = !browserActive;
			}
		}
		foreach (IBinding binding2 in m_DirectoryBrowserBinding.bindings)
		{
			if (binding2 is RawTriggerBindingBase rawTriggerBindingBase2)
			{
				rawTriggerBindingBase2.active = browserActive;
			}
		}
	}
```

- `public UnregisterSettings(System.String id) : System.Void`  

```csharp
public void UnregisterSettings(string id)
	{
		pages.Remove(id);
		if (m_ActivePageBinding.value == id && pages.Count != 0)
		{
			SelectVisibleSection(pages.Values.First());
		}
		m_PagesBinding.Update();
		RefreshPage();
	}
```

- `public static UpdateNotificationState(Game.Modding.Toolchain.ModdingToolStatus toolStatus, Game.Modding.Toolchain.DeploymentState deploymentState) : System.Void`  

```csharp
public static void UpdateNotificationState(ModdingToolStatus toolStatus, DeploymentState deploymentState)
	{
		if (toolStatus != ModdingToolStatus.Idle)
		{
			NotificationSystem.Pop("ToolchainStatus");
		}
		else if (deploymentState == DeploymentState.Outdated || deploymentState == DeploymentState.Invalid)
		{
			string textId = "ToolchainStatus" + deploymentState;
			ProgressState? progressState = ProgressState.Warning;
			NotificationSystem.Push("ToolchainStatus", null, null, "ActionRequired", textId, null, progressState, null, delegate
			{
				ToolchainDeployment.RunWithUI(DeploymentAction.Install);
			});
		}
	}
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

