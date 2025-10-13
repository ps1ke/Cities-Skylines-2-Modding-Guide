# Game.Settings.ModdingSettings

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.Setting`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

**Attributes:** `FileLocation`, `SettingsUIShowGroupName`, `SettingsUIGroupOrder`, `SettingsUIPageWarning`  

## Code

```csharp
public class ModdingSettings : Game.Settings.Setting, System.IEquatable<Game.Settings.Setting>
{
    private System.Boolean <isInstalled>k__BackingField;
    private System.String <downloadDirectory>k__BackingField;
    public static const System.String kName;
    public static const System.String kDisclaimer;
    public static const System.String kMain;
    public static const System.String kDependencies;

    public System.Boolean isInstalled { get; set; }
    public System.Boolean installModdingToolchain { set; }
    public System.Boolean uninstallModdingToolchain { set; }
    public System.Boolean repairModdingToolchain { set; }
    public System.Boolean updateModdingToolchain { set; }
    public System.Boolean showEnvVars { set; }
    public System.Boolean showCurrentValues { set; }
    public System.Boolean updateEnvVars { set; }
    public System.Boolean removeEnvVars { set; }
    private System.Boolean disableEnvVarUpdate { private get; }
    public System.String downloadDirectory { get; set; }
    public System.Boolean isActionDisabled { get; }
    public System.Boolean canNotBeInstalled { get; }
    public System.Boolean canNotBeUninstalled { get; }
    public System.Boolean canNotBeRepaired { get; }
    public System.Boolean canNotBeUpdated { get; }
    public System.Boolean noNeedDownloadPath { get; }
    public System.Boolean showWarning { get; }

    public ModdingSettings();

    private System.Void <set_installModdingToolchain>b__9_0(System.Boolean success);
    private System.Void <set_repairModdingToolchain>b__13_0(System.Boolean success);
    private System.Void <set_uninstallModdingToolchain>b__11_0(System.Boolean success);
    private System.Void <set_updateModdingToolchain>b__15_0(System.Boolean success);
    private Game.UI.Menu.ModdingToolchainSettingItem GetItem(Game.Modding.Toolchain.IToolchainDependency dependency, Game.UI.Menu.AutomaticSettings+SettingPageData pageData);
    public virtual Game.UI.Menu.AutomaticSettings+SettingPageData GetPageData(System.String id, System.Boolean addPrefix);
    public virtual System.Void SetDefaults();
}
```


## Fields

- `private System.Boolean <isInstalled>k__BackingField`  

```csharp
private System.Boolean <isInstalled>k__BackingField;
```

- `private System.String <downloadDirectory>k__BackingField`  

```csharp
private System.String <downloadDirectory>k__BackingField;
```

- `public static const System.String kName`  

```csharp
public static const System.String kName;
```

- `public static const System.String kDisclaimer`  

```csharp
public static const System.String kDisclaimer;
```

- `public static const System.String kMain`  

```csharp
public static const System.String kMain;
```

- `public static const System.String kDependencies`  

```csharp
public static const System.String kDependencies;
```


## Properties

- `public System.Boolean isInstalled { get; set }`  

```csharp
public System.Boolean isInstalled { get; set; }
```

- `public System.Boolean installModdingToolchain { set }`  

```csharp
public System.Boolean installModdingToolchain { set; }
```

- `public System.Boolean uninstallModdingToolchain { set }`  

```csharp
public System.Boolean uninstallModdingToolchain { set; }
```

- `public System.Boolean repairModdingToolchain { set }`  

```csharp
public System.Boolean repairModdingToolchain { set; }
```

- `public System.Boolean updateModdingToolchain { set }`  

```csharp
public System.Boolean updateModdingToolchain { set; }
```

- `public System.Boolean showEnvVars { set }`  

```csharp
public System.Boolean showEnvVars { set; }
```

- `public System.Boolean showCurrentValues { set }`  

```csharp
public System.Boolean showCurrentValues { set; }
```

- `public System.Boolean updateEnvVars { set }`  

```csharp
public System.Boolean updateEnvVars { set; }
```

- `public System.Boolean removeEnvVars { set }`  

```csharp
public System.Boolean removeEnvVars { set; }
```

- `private System.Boolean disableEnvVarUpdate { private get }`  

```csharp
private System.Boolean disableEnvVarUpdate { private get; }
```

- `public System.String downloadDirectory { get; set }`  

```csharp
public System.String downloadDirectory { get; set; }
```

- `public System.Boolean isActionDisabled { get }`  

```csharp
public System.Boolean isActionDisabled { get; }
```

- `public System.Boolean canNotBeInstalled { get }`  

```csharp
public System.Boolean canNotBeInstalled { get; }
```

- `public System.Boolean canNotBeUninstalled { get }`  

```csharp
public System.Boolean canNotBeUninstalled { get; }
```

- `public System.Boolean canNotBeRepaired { get }`  

```csharp
public System.Boolean canNotBeRepaired { get; }
```

- `public System.Boolean canNotBeUpdated { get }`  

```csharp
public System.Boolean canNotBeUpdated { get; }
```

- `public System.Boolean noNeedDownloadPath { get }`  

```csharp
public System.Boolean noNeedDownloadPath { get; }
```

- `public System.Boolean showWarning { get }`  

```csharp
public System.Boolean showWarning { get; }
```


## Constructors

- `public ModdingSettings()`  

```csharp
public ModdingSettings();
```


## Methods

- `private <set_installModdingToolchain>b__9_0(System.Boolean success) : System.Void`  

```csharp
private System.Void <set_installModdingToolchain>b__9_0(System.Boolean success);
```

- `private <set_repairModdingToolchain>b__13_0(System.Boolean success) : System.Void`  

```csharp
private System.Void <set_repairModdingToolchain>b__13_0(System.Boolean success);
```

- `private <set_uninstallModdingToolchain>b__11_0(System.Boolean success) : System.Void`  

```csharp
private System.Void <set_uninstallModdingToolchain>b__11_0(System.Boolean success);
```

- `private <set_updateModdingToolchain>b__15_0(System.Boolean success) : System.Void`  

```csharp
private System.Void <set_updateModdingToolchain>b__15_0(System.Boolean success);
```

- `private GetItem(Game.Modding.Toolchain.IToolchainDependency dependency, Game.UI.Menu.AutomaticSettings+SettingPageData pageData) : Game.UI.Menu.ModdingToolchainSettingItem`  

```csharp
private ModdingToolchainSettingItem GetItem(IToolchainDependency dependency, AutomaticSettings.SettingPageData pageData)
	{
		AutomaticSettings.ManualProperty property = new AutomaticSettings.ManualProperty(typeof(ModdingSettings), typeof(IToolchainDependency), dependency.GetType().Name)
		{
			canRead = true,
			canWrite = false,
			getter = (object obj) => dependency
		};
		ModdingToolchainSettingItem moddingToolchainSettingItem = new ModdingToolchainSettingItem(this, property, pageData.prefix)
		{
			simpleGroup = "Dependencies",
			valueVersionAction = dependency.GetHashCode,
			description = dependency.description
		};
		if (dependency.canBeInstalled)
		{
			foreach (DeploymentAction action in Enum.GetValues(typeof(DeploymentAction)))
			{
				if (action != DeploymentAction.None)
				{
					AutomaticSettings.ManualProperty property2 = new AutomaticSettings.ManualProperty(typeof(ModdingSettings), typeof(bool), action.ToString().ToLower() + "ModdingToolchain")
					{
						canRead = false,
						canWrite = true,
						setter = delegate
						{
							ToolchainDeployment.RunWithUI(action, new List<IToolchainDependency> { dependency });
						},
						attributes = { (Attribute)new SettingsUIButtonGroupAttribute(dependency.name + "toolchainAction") }
					};
					AutomaticSettings.SettingItemData item = new AutomaticSettings.SettingItemData(AutomaticSettings.WidgetType.BoolButton, this, property2, pageData.prefix)
					{
						hideAction = () => (dependency.availableActions & action) == 0,
						disableAction = () => isActionDisabled
					};
					moddingToolchainSettingItem.children.Add(item);
				}
			}
		}
		if (dependency.canBeInstalled && dependency.canChangeInstallationDirectory)
		{
			AutomaticSettings.ManualProperty property3 = new AutomaticSettings.ManualProperty(typeof(ModdingSettings), typeof(string), dependency.GetType().Name + ".InstallationDirectory")
			{
				canRead = true,
				canWrite = true,
				getter = (object obj) => dependency.installationDirectory,
				setter = delegate(object obj, object value)
				{
					dependency.installationDirectory = (string)value;
				},
				attributes = { (Attribute)new SettingsUIDisplayNameAttribute(typeof(ModdingSettings).Name + ".installationDirectory") }
			};
			AutomaticSettings.SettingItemData item2 = new AutomaticSettings.SettingItemData(AutomaticSettings.WidgetType.DirectoryPicker, this, property3, pageData.prefix)
			{
				hideAction = () => isActionDisabled || dependency.state.m_State == DependencyState.Installed
			};
			moddingToolchainSettingItem.children.Add(item2);
		}
		if (dependency is CombinedDependency combinedDependency)
		{
			moddingToolchainSettingItem.children.AddRange(combinedDependency.dependencies.Select((IToolchainDependency d) => GetItem(d, pageData)));
		}
		return moddingToolchainSettingItem;
	}
```

- `public virtual GetPageData(System.String id, System.Boolean addPrefix) : Game.UI.Menu.AutomaticSettings+SettingPageData`  

```csharp
public override AutomaticSettings.SettingPageData GetPageData(string id, bool addPrefix)
	{
		AutomaticSettings.SettingPageData pageData = base.GetPageData(id, addPrefix);
		pageData.AddGroup("Disclaimer");
		AutomaticSettings.ManualProperty property = new AutomaticSettings.ManualProperty(typeof(ModdingSettings), typeof(string), "disclaimer")
		{
			canRead = true,
			canWrite = false,
			attributes = 
			{
				(Attribute)new SettingsUIMultilineTextAttribute("Media/Misc/Warning.svg"),
				(Attribute)new SettingsUISearchHiddenAttribute()
			}
		};
		MultilineTextSettingItemData item = new MultilineTextSettingItemData(this, property, pageData.prefix)
		{
			simpleGroup = "Disclaimer"
		};
		pageData["General"].AddItem(item);
		AutomaticSettings.ManualProperty property2 = new AutomaticSettings.ManualProperty(typeof(ModdingSettings), typeof(IToolchainDependency), "ToolchainDeployment")
		{
			canRead = true,
			canWrite = false,
			getter = (object _) => ToolchainDependencyManager.m_MainDependency
		};
		ModdingToolchainSettingItem item2 = new ModdingToolchainSettingItem(this, property2, pageData.prefix)
		{
			simpleGroup = "Main",
			valueVersionAction = ToolchainDependencyManager.m_MainDependency.GetHashCode
		};
		pageData["General"].InsertItem(item2, 0);
		pageData.AddGroup("Dependencies");
		foreach (IToolchainDependency item3 in ToolchainDeployment.dependencyManager)
		{
			pageData["General"].AddItem(GetItem(item3, pageData));
		}
		return pageData;
	}
```

- `public virtual SetDefaults() : System.Void`  

```csharp
public override void SetDefaults()
	{
	}
```


## Nested types

- `Game.Settings.ModdingSettings+<>c`  
- `Game.Settings.ModdingSettings+<>c__DisplayClass46_0`  
- `Game.Settings.ModdingSettings+<>c__DisplayClass46_1`  

