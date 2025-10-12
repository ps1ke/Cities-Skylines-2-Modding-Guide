# Game.UI.Menu.AutomaticSettings+SettingItemData

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `private readonly Game.UI.Menu.AutomaticSettings+WidgetType <widgetType>k__BackingField`  
- `private readonly Game.Settings.Setting <setting>k__BackingField`  
- `private readonly Game.UI.Menu.AutomaticSettings+IProxyProperty <property>k__BackingField`  
- `private readonly System.String <prefix>k__BackingField`  
- `private readonly System.String <path>k__BackingField`  
- `private Game.UI.Localization.LocalizedString <displayName>k__BackingField`  
- `private Game.UI.Localization.LocalizedString <description>k__BackingField`  
- `private System.Boolean <isAdvanced>k__BackingField`  
- `private System.String <simpleGroup>k__BackingField`  
- `private System.String <advancedGroup>k__BackingField`  
- `private System.Boolean <isSearchHidden>k__BackingField`  
- `private System.Delegate <setterAction>k__BackingField`  
- `private System.Func<System.Boolean> <disableAction>k__BackingField`  
- `private System.Func<System.Boolean> <hideAction>k__BackingField`  
- `private System.Func<System.Int32> <valueVersionAction>k__BackingField`  
- `private System.Func<Game.UI.Localization.LocalizedString> <dispayNameAction>k__BackingField`  
- `private System.Func<Game.UI.Localization.LocalizedString> <descriptionAction>k__BackingField`  
- `private System.Func<System.Boolean> <warningAction>k__BackingField`  
- `private Game.UI.Widgets.IWidget m_Widget`  

## Properties

- `public Game.UI.Menu.AutomaticSettings+WidgetType widgetType { get }`  
- `public Game.Settings.Setting setting { get }`  
- `public Game.UI.Menu.AutomaticSettings+IProxyProperty property { get }`  
- `public System.String prefix { get }`  
- `public System.String path { get }`  
- `public Game.UI.Localization.LocalizedString displayName { get; set }`  
- `public Game.UI.Localization.LocalizedString description { get; set }`  
- `public System.Boolean isAdvanced { get; set }`  
- `public System.String simpleGroup { get; set }`  
- `public System.String advancedGroup { get; set }`  
- `public System.Boolean isSearchHidden { get; set }`  
- `public System.Delegate setterAction { get; set }`  
- `public System.Func<System.Boolean> disableAction { get; set }`  
- `public System.Func<System.Boolean> hideAction { get; set }`  
- `public System.Func<System.Int32> valueVersionAction { get; set }`  
- `public System.Func<Game.UI.Localization.LocalizedString> dispayNameAction { get; set }`  
- `public System.Func<Game.UI.Localization.LocalizedString> descriptionAction { get; set }`  
- `public System.Func<System.Boolean> warningAction { get; set }`  
- `public Game.UI.Widgets.IWidget widget { get }`  

## Constructors

- `public SettingItemData(Game.UI.Menu.AutomaticSettings+WidgetType widgetType, Game.Settings.Setting setting, Game.UI.Menu.AutomaticSettings+IProxyProperty property, System.String prefix)`  

## Methods

- `private GetDescription(Game.UI.Menu.AutomaticSettings+IProxyProperty property, System.String path) : Game.UI.Localization.LocalizedString`  
- `private GetDescriptionAction(Game.UI.Menu.AutomaticSettings+IProxyProperty property, Game.Settings.Setting setting) : System.Func<Game.UI.Localization.LocalizedString>`  
- `private GetDisableAction(Game.UI.Menu.AutomaticSettings+IProxyProperty property, Game.Settings.Setting setting) : System.Func<System.Boolean>`  
- `private GetDisplayName(Game.UI.Menu.AutomaticSettings+IProxyProperty property, System.String path) : Game.UI.Localization.LocalizedString`  
- `private GetDisplayNameAction(Game.UI.Menu.AutomaticSettings+IProxyProperty property, Game.Settings.Setting setting) : System.Func<Game.UI.Localization.LocalizedString>`  
- `private GetHideAction(Game.UI.Menu.AutomaticSettings+IProxyProperty property, Game.Settings.Setting setting) : System.Func<System.Boolean>`  
- `private GetPath(Game.UI.Menu.AutomaticSettings+IProxyProperty property, System.String prefix) : System.String`  
- `private GetSetterAction(Game.UI.Menu.AutomaticSettings+IProxyProperty property, Game.Settings.Setting setting) : System.Delegate`  
- `private GetValueVersionAction(Game.UI.Menu.AutomaticSettings+IProxyProperty property, Game.Settings.Setting setting) : System.Func<System.Int32>`  
- `private GetWarningAction(Game.UI.Menu.AutomaticSettings+IProxyProperty property, Game.Settings.Setting setting) : System.Func<System.Boolean>`  
- `protected virtual GetWidget() : Game.UI.Widgets.IWidget`  
- `private IsAdvanced(Game.UI.Menu.AutomaticSettings+IProxyProperty property) : System.Boolean`  
- `private IsSearchHidden(Game.UI.Menu.AutomaticSettings+IProxyProperty property) : System.Boolean`  

## Nested types

- `Game.UI.Menu.AutomaticSettings+SettingItemData+<>c__DisplayClass81_0`  
- `Game.UI.Menu.AutomaticSettings+SettingItemData+<>c__DisplayClass82_0`  

