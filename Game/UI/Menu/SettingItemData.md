# Game.UI.Menu.AutomaticSettings+SettingItemData

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class SettingItemData
{
    private readonly Game.UI.Menu.AutomaticSettings+WidgetType <widgetType>k__BackingField;
    private readonly Game.Settings.Setting <setting>k__BackingField;
    private readonly Game.UI.Menu.AutomaticSettings+IProxyProperty <property>k__BackingField;
    private readonly System.String <prefix>k__BackingField;
    private readonly System.String <path>k__BackingField;
    private Game.UI.Localization.LocalizedString <displayName>k__BackingField;
    private Game.UI.Localization.LocalizedString <description>k__BackingField;
    private System.Boolean <isAdvanced>k__BackingField;
    private System.String <simpleGroup>k__BackingField;
    private System.String <advancedGroup>k__BackingField;
    private System.Boolean <isSearchHidden>k__BackingField;
    private System.Delegate <setterAction>k__BackingField;
    private System.Func<System.Boolean> <disableAction>k__BackingField;
    private System.Func<System.Boolean> <hideAction>k__BackingField;
    private System.Func<System.Int32> <valueVersionAction>k__BackingField;
    private System.Func<Game.UI.Localization.LocalizedString> <dispayNameAction>k__BackingField;
    private System.Func<Game.UI.Localization.LocalizedString> <descriptionAction>k__BackingField;
    private System.Func<System.Boolean> <warningAction>k__BackingField;
    private Game.UI.Widgets.IWidget m_Widget;

    public Game.UI.Menu.AutomaticSettings+WidgetType widgetType { get; }
    public Game.Settings.Setting setting { get; }
    public Game.UI.Menu.AutomaticSettings+IProxyProperty property { get; }
    public System.String prefix { get; }
    public System.String path { get; }
    public Game.UI.Localization.LocalizedString displayName { get; set; }
    public Game.UI.Localization.LocalizedString description { get; set; }
    public System.Boolean isAdvanced { get; set; }
    public System.String simpleGroup { get; set; }
    public System.String advancedGroup { get; set; }
    public System.Boolean isSearchHidden { get; set; }
    public System.Delegate setterAction { get; set; }
    public System.Func<System.Boolean> disableAction { get; set; }
    public System.Func<System.Boolean> hideAction { get; set; }
    public System.Func<System.Int32> valueVersionAction { get; set; }
    public System.Func<Game.UI.Localization.LocalizedString> dispayNameAction { get; set; }
    public System.Func<Game.UI.Localization.LocalizedString> descriptionAction { get; set; }
    public System.Func<System.Boolean> warningAction { get; set; }
    public Game.UI.Widgets.IWidget widget { get; }

    public SettingItemData(Game.UI.Menu.AutomaticSettings+WidgetType widgetType, Game.Settings.Setting setting, Game.UI.Menu.AutomaticSettings+IProxyProperty property, System.String prefix);

    private Game.UI.Localization.LocalizedString GetDescription(Game.UI.Menu.AutomaticSettings+IProxyProperty property, System.String path);
    private System.Func<Game.UI.Localization.LocalizedString> GetDescriptionAction(Game.UI.Menu.AutomaticSettings+IProxyProperty property, Game.Settings.Setting setting);
    private System.Func<System.Boolean> GetDisableAction(Game.UI.Menu.AutomaticSettings+IProxyProperty property, Game.Settings.Setting setting);
    private Game.UI.Localization.LocalizedString GetDisplayName(Game.UI.Menu.AutomaticSettings+IProxyProperty property, System.String path);
    private System.Func<Game.UI.Localization.LocalizedString> GetDisplayNameAction(Game.UI.Menu.AutomaticSettings+IProxyProperty property, Game.Settings.Setting setting);
    private System.Func<System.Boolean> GetHideAction(Game.UI.Menu.AutomaticSettings+IProxyProperty property, Game.Settings.Setting setting);
    private System.String GetPath(Game.UI.Menu.AutomaticSettings+IProxyProperty property, System.String prefix);
    private System.Delegate GetSetterAction(Game.UI.Menu.AutomaticSettings+IProxyProperty property, Game.Settings.Setting setting);
    private System.Func<System.Int32> GetValueVersionAction(Game.UI.Menu.AutomaticSettings+IProxyProperty property, Game.Settings.Setting setting);
    private System.Func<System.Boolean> GetWarningAction(Game.UI.Menu.AutomaticSettings+IProxyProperty property, Game.Settings.Setting setting);
    protected virtual Game.UI.Widgets.IWidget GetWidget();
    private System.Boolean IsAdvanced(Game.UI.Menu.AutomaticSettings+IProxyProperty property);
    private System.Boolean IsSearchHidden(Game.UI.Menu.AutomaticSettings+IProxyProperty property);
}
```


## Fields

- `private readonly Game.UI.Menu.AutomaticSettings+WidgetType <widgetType>k__BackingField`  

```csharp
private readonly Game.UI.Menu.AutomaticSettings+WidgetType <widgetType>k__BackingField;
```

- `private readonly Game.Settings.Setting <setting>k__BackingField`  

```csharp
private readonly Game.Settings.Setting <setting>k__BackingField;
```

- `private readonly Game.UI.Menu.AutomaticSettings+IProxyProperty <property>k__BackingField`  

```csharp
private readonly Game.UI.Menu.AutomaticSettings+IProxyProperty <property>k__BackingField;
```

- `private readonly System.String <prefix>k__BackingField`  

```csharp
private readonly System.String <prefix>k__BackingField;
```

- `private readonly System.String <path>k__BackingField`  

```csharp
private readonly System.String <path>k__BackingField;
```

- `private Game.UI.Localization.LocalizedString <displayName>k__BackingField`  

```csharp
private Game.UI.Localization.LocalizedString <displayName>k__BackingField;
```

- `private Game.UI.Localization.LocalizedString <description>k__BackingField`  

```csharp
private Game.UI.Localization.LocalizedString <description>k__BackingField;
```

- `private System.Boolean <isAdvanced>k__BackingField`  

```csharp
private System.Boolean <isAdvanced>k__BackingField;
```

- `private System.String <simpleGroup>k__BackingField`  

```csharp
private System.String <simpleGroup>k__BackingField;
```

- `private System.String <advancedGroup>k__BackingField`  

```csharp
private System.String <advancedGroup>k__BackingField;
```

- `private System.Boolean <isSearchHidden>k__BackingField`  

```csharp
private System.Boolean <isSearchHidden>k__BackingField;
```

- `private System.Delegate <setterAction>k__BackingField`  

```csharp
private System.Delegate <setterAction>k__BackingField;
```

- `private System.Func<System.Boolean> <disableAction>k__BackingField`  

```csharp
private System.Func<System.Boolean> <disableAction>k__BackingField;
```

- `private System.Func<System.Boolean> <hideAction>k__BackingField`  

```csharp
private System.Func<System.Boolean> <hideAction>k__BackingField;
```

- `private System.Func<System.Int32> <valueVersionAction>k__BackingField`  

```csharp
private System.Func<System.Int32> <valueVersionAction>k__BackingField;
```

- `private System.Func<Game.UI.Localization.LocalizedString> <dispayNameAction>k__BackingField`  

```csharp
private System.Func<Game.UI.Localization.LocalizedString> <dispayNameAction>k__BackingField;
```

- `private System.Func<Game.UI.Localization.LocalizedString> <descriptionAction>k__BackingField`  

```csharp
private System.Func<Game.UI.Localization.LocalizedString> <descriptionAction>k__BackingField;
```

- `private System.Func<System.Boolean> <warningAction>k__BackingField`  

```csharp
private System.Func<System.Boolean> <warningAction>k__BackingField;
```

- `private Game.UI.Widgets.IWidget m_Widget`  

```csharp
private Game.UI.Widgets.IWidget m_Widget;
```


## Properties

- `public Game.UI.Menu.AutomaticSettings+WidgetType widgetType { get }`  

```csharp
public Game.UI.Menu.AutomaticSettings+WidgetType widgetType { get; }
```

- `public Game.Settings.Setting setting { get }`  

```csharp
public Game.Settings.Setting setting { get; }
```

- `public Game.UI.Menu.AutomaticSettings+IProxyProperty property { get }`  

```csharp
public Game.UI.Menu.AutomaticSettings+IProxyProperty property { get; }
```

- `public System.String prefix { get }`  

```csharp
public System.String prefix { get; }
```

- `public System.String path { get }`  

```csharp
public System.String path { get; }
```

- `public Game.UI.Localization.LocalizedString displayName { get; set }`  

```csharp
public Game.UI.Localization.LocalizedString displayName { get; set; }
```

- `public Game.UI.Localization.LocalizedString description { get; set }`  

```csharp
public Game.UI.Localization.LocalizedString description { get; set; }
```

- `public System.Boolean isAdvanced { get; set }`  

```csharp
public System.Boolean isAdvanced { get; set; }
```

- `public System.String simpleGroup { get; set }`  

```csharp
public System.String simpleGroup { get; set; }
```

- `public System.String advancedGroup { get; set }`  

```csharp
public System.String advancedGroup { get; set; }
```

- `public System.Boolean isSearchHidden { get; set }`  

```csharp
public System.Boolean isSearchHidden { get; set; }
```

- `public System.Delegate setterAction { get; set }`  

```csharp
public System.Delegate setterAction { get; set; }
```

- `public System.Func<System.Boolean> disableAction { get; set }`  

```csharp
public System.Func<System.Boolean> disableAction { get; set; }
```

- `public System.Func<System.Boolean> hideAction { get; set }`  

```csharp
public System.Func<System.Boolean> hideAction { get; set; }
```

- `public System.Func<System.Int32> valueVersionAction { get; set }`  

```csharp
public System.Func<System.Int32> valueVersionAction { get; set; }
```

- `public System.Func<Game.UI.Localization.LocalizedString> dispayNameAction { get; set }`  

```csharp
public System.Func<Game.UI.Localization.LocalizedString> dispayNameAction { get; set; }
```

- `public System.Func<Game.UI.Localization.LocalizedString> descriptionAction { get; set }`  

```csharp
public System.Func<Game.UI.Localization.LocalizedString> descriptionAction { get; set; }
```

- `public System.Func<System.Boolean> warningAction { get; set }`  

```csharp
public System.Func<System.Boolean> warningAction { get; set; }
```

- `public Game.UI.Widgets.IWidget widget { get }`  

```csharp
public Game.UI.Widgets.IWidget widget { get; }
```


## Constructors

- `public SettingItemData(Game.UI.Menu.AutomaticSettings+WidgetType widgetType, Game.Settings.Setting setting, Game.UI.Menu.AutomaticSettings+IProxyProperty property, System.String prefix)`  

```csharp
public SettingItemData(Game.UI.Menu.AutomaticSettings+WidgetType widgetType, Game.Settings.Setting setting, Game.UI.Menu.AutomaticSettings+IProxyProperty property, System.String prefix);
```


## Methods

- `private GetDescription(Game.UI.Menu.AutomaticSettings+IProxyProperty property, System.String path) : Game.UI.Localization.LocalizedString`  

```csharp
private Game.UI.Localization.LocalizedString GetDescription(Game.UI.Menu.AutomaticSettings+IProxyProperty property, System.String path);
```

- `private GetDescriptionAction(Game.UI.Menu.AutomaticSettings+IProxyProperty property, Game.Settings.Setting setting) : System.Func<Game.UI.Localization.LocalizedString>`  

```csharp
private System.Func<Game.UI.Localization.LocalizedString> GetDescriptionAction(Game.UI.Menu.AutomaticSettings+IProxyProperty property, Game.Settings.Setting setting);
```

- `private GetDisableAction(Game.UI.Menu.AutomaticSettings+IProxyProperty property, Game.Settings.Setting setting) : System.Func<System.Boolean>`  

```csharp
private System.Func<System.Boolean> GetDisableAction(Game.UI.Menu.AutomaticSettings+IProxyProperty property, Game.Settings.Setting setting);
```

- `private GetDisplayName(Game.UI.Menu.AutomaticSettings+IProxyProperty property, System.String path) : Game.UI.Localization.LocalizedString`  

```csharp
private Game.UI.Localization.LocalizedString GetDisplayName(Game.UI.Menu.AutomaticSettings+IProxyProperty property, System.String path);
```

- `private GetDisplayNameAction(Game.UI.Menu.AutomaticSettings+IProxyProperty property, Game.Settings.Setting setting) : System.Func<Game.UI.Localization.LocalizedString>`  

```csharp
private System.Func<Game.UI.Localization.LocalizedString> GetDisplayNameAction(Game.UI.Menu.AutomaticSettings+IProxyProperty property, Game.Settings.Setting setting);
```

- `private GetHideAction(Game.UI.Menu.AutomaticSettings+IProxyProperty property, Game.Settings.Setting setting) : System.Func<System.Boolean>`  

```csharp
private System.Func<System.Boolean> GetHideAction(Game.UI.Menu.AutomaticSettings+IProxyProperty property, Game.Settings.Setting setting);
```

- `private GetPath(Game.UI.Menu.AutomaticSettings+IProxyProperty property, System.String prefix) : System.String`  

```csharp
private System.String GetPath(Game.UI.Menu.AutomaticSettings+IProxyProperty property, System.String prefix);
```

- `private GetSetterAction(Game.UI.Menu.AutomaticSettings+IProxyProperty property, Game.Settings.Setting setting) : System.Delegate`  

```csharp
private System.Delegate GetSetterAction(Game.UI.Menu.AutomaticSettings+IProxyProperty property, Game.Settings.Setting setting);
```

- `private GetValueVersionAction(Game.UI.Menu.AutomaticSettings+IProxyProperty property, Game.Settings.Setting setting) : System.Func<System.Int32>`  

```csharp
private System.Func<System.Int32> GetValueVersionAction(Game.UI.Menu.AutomaticSettings+IProxyProperty property, Game.Settings.Setting setting);
```

- `private GetWarningAction(Game.UI.Menu.AutomaticSettings+IProxyProperty property, Game.Settings.Setting setting) : System.Func<System.Boolean>`  

```csharp
private System.Func<System.Boolean> GetWarningAction(Game.UI.Menu.AutomaticSettings+IProxyProperty property, Game.Settings.Setting setting);
```

- `protected virtual GetWidget() : Game.UI.Widgets.IWidget`  

```csharp
protected virtual Game.UI.Widgets.IWidget GetWidget();
```

- `private IsAdvanced(Game.UI.Menu.AutomaticSettings+IProxyProperty property) : System.Boolean`  

```csharp
private System.Boolean IsAdvanced(Game.UI.Menu.AutomaticSettings+IProxyProperty property);
```

- `private IsSearchHidden(Game.UI.Menu.AutomaticSettings+IProxyProperty property) : System.Boolean`  

```csharp
private System.Boolean IsSearchHidden(Game.UI.Menu.AutomaticSettings+IProxyProperty property);
```


## Nested types

- `Game.UI.Menu.AutomaticSettings+SettingItemData+<>c__DisplayClass81_0`  
- `Game.UI.Menu.AutomaticSettings+SettingItemData+<>c__DisplayClass82_0`  

