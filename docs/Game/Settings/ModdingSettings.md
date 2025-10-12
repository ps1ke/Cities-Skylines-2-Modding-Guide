# Game.Settings.ModdingSettings

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.Setting`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

**Attributes:** `FileLocation`, `SettingsUIShowGroupName`, `SettingsUIGroupOrder`, `SettingsUIPageWarning`  

## Fields

- `private System.Boolean <isInstalled>k__BackingField`  
- `private System.String <downloadDirectory>k__BackingField`  
- `public static const System.String kName`  
- `public static const System.String kDisclaimer`  
- `public static const System.String kMain`  
- `public static const System.String kDependencies`  

## Properties

- `public System.Boolean isInstalled { get; set }`  
- `public System.Boolean installModdingToolchain { set }`  
- `public System.Boolean uninstallModdingToolchain { set }`  
- `public System.Boolean repairModdingToolchain { set }`  
- `public System.Boolean updateModdingToolchain { set }`  
- `public System.Boolean showEnvVars { set }`  
- `public System.Boolean showCurrentValues { set }`  
- `public System.Boolean updateEnvVars { set }`  
- `public System.Boolean removeEnvVars { set }`  
- `private System.Boolean disableEnvVarUpdate { private get }`  
- `public System.String downloadDirectory { get; set }`  
- `public System.Boolean isActionDisabled { get }`  
- `public System.Boolean canNotBeInstalled { get }`  
- `public System.Boolean canNotBeUninstalled { get }`  
- `public System.Boolean canNotBeRepaired { get }`  
- `public System.Boolean canNotBeUpdated { get }`  
- `public System.Boolean noNeedDownloadPath { get }`  
- `public System.Boolean showWarning { get }`  

## Constructors

- `public ModdingSettings()`  

## Methods

- `private <set_installModdingToolchain>b__9_0(System.Boolean success) : System.Void`  
- `private <set_repairModdingToolchain>b__13_0(System.Boolean success) : System.Void`  
- `private <set_uninstallModdingToolchain>b__11_0(System.Boolean success) : System.Void`  
- `private <set_updateModdingToolchain>b__15_0(System.Boolean success) : System.Void`  
- `private GetItem(Game.Modding.Toolchain.IToolchainDependency dependency, Game.UI.Menu.AutomaticSettings+SettingPageData pageData) : Game.UI.Menu.ModdingToolchainSettingItem`  
- `public virtual GetPageData(System.String id, System.Boolean addPrefix) : Game.UI.Menu.AutomaticSettings+SettingPageData`  
- `public virtual SetDefaults() : System.Void`  

## Nested types

- `Game.Settings.ModdingSettings+<>c`  
- `Game.Settings.ModdingSettings+<>c__DisplayClass46_0`  
- `Game.Settings.ModdingSettings+<>c__DisplayClass46_1`  

