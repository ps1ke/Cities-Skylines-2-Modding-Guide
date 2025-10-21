# Game.UI.Menu.AutomaticSettings

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class AutomaticSettings
{
    private static readonly System.Reflection.MethodInfo s_CustomDropdownMethodInfo;
    private static readonly System.Reflection.MethodInfo s_EnumSetterMethodInfo;
    private static readonly System.Collections.Generic.Dictionary<System.String, Game.UI.Widgets.ButtonRow> s_ButtonGroups;

    internal static System.Int32 <AddKeyBindingProperty>g__GetValueVersion|33_0();
    public static Game.UI.Widgets.IWidget AddBoolButtonProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData);
    public static Game.UI.Widgets.IWidget AddBoolButtonWithConfirmationProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData);
    public static Game.UI.Widgets.IWidget AddBoolToggleProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData);
    public static Game.UI.Widgets.IWidget AddCustomDropdownProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData);
    public static Game.UI.Widgets.IWidget AddCustomDropdownPropertyGeneric<T>(Game.UI.Menu.AutomaticSettings+SettingItemData itemData);
    public static Game.UI.Widgets.IWidget AddDirectoryPickerBindingProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData);
    public static Game.UI.Widgets.IWidget AddEnumDropdownProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData);
    public static Game.UI.Widgets.IWidget AddEnumSimpleProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData);
    public static Game.UI.Widgets.IWidget AddFloatSliderProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData);
    public static Game.UI.Widgets.IWidget AddIntDropdownProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData);
    public static Game.UI.Widgets.IWidget AddIntSliderProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData);
    public static Game.UI.Widgets.IWidget AddKeyBindingProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData);
    public static Game.UI.Widgets.IWidget AddLocalizedStringFieldProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData);
    public static Game.UI.Widgets.IWidget AddStringDropdownProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData);
    public static Game.UI.Widgets.IWidget AddStringFieldProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData);
    public static Game.UI.Widgets.IWidget AddStringTextInputProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData);
    public static Game.UI.Menu.AutomaticSettings+SettingPageData FillSettingsPage(Game.Settings.Setting setting, System.String id, System.Boolean addPrefix);
    public static System.Void FillSettingsPage(Game.UI.Menu.AutomaticSettings+SettingPageData pageData, Game.Settings.Setting setting);
    private static System.Boolean GetButtonsGroup(System.String groupName, Game.UI.Widgets.ButtonRow& buttons, Game.UI.Widgets.Button item);
    public static Game.UI.Localization.LocalizedString GetConfirmationMessage(Game.UI.Menu.AutomaticSettings+SettingItemData itemData);
    private static Game.UI.Menu.AutomaticSettings+DropdownItemsAccessor<Game.UI.Widgets.DropdownItem<T>[]> GetDropdownItemAccessor<T>(Game.UI.Menu.AutomaticSettings+IProxyProperty property, Game.Settings.Setting setting);
    private static System.Action<System.UInt64> GetEnumCustomSetterAction(Game.UI.Menu.AutomaticSettings+SettingItemData itemData);
    private static System.Func<System.UInt64> GetEnumGetter(Game.UI.Menu.AutomaticSettings+SettingItemData itemData);
    private static Game.Reflection.DelegateAccessor<Game.UI.Widgets.EnumMember[]> GetEnumMemberAccessor(Game.UI.Menu.AutomaticSettings+IProxyProperty property, Game.Settings.Setting setting, System.String prefix);
    private static System.Action<System.UInt64> GetEnumSetter(Game.UI.Menu.AutomaticSettings+SettingItemData itemData);
    public static Game.UI.Widgets.EnumMember[] GetEnumValues(System.Type enumType, System.String prefix);
    private static System.Collections.Generic.Dictionary<System.String, Game.UI.Menu.AutomaticSettings+SectionInfo> GetSections(Game.UI.Menu.AutomaticSettings+IProxyProperty property);
    private static System.Action<System.UInt64> GetSetterActionGeneric<T>(Game.UI.Menu.AutomaticSettings+SettingItemData itemData);
    private static System.Collections.Generic.Dictionary<System.String, System.Func<System.Boolean>> GetTabWarningGetters(Game.Settings.Setting setting);
    private static System.Func<System.Boolean> GetWarningGetter(Game.Settings.Setting setting);
    public static Game.UI.Menu.AutomaticSettings+WidgetType GetWidgetType(Game.UI.Menu.AutomaticSettings+IProxyProperty property);
    private static System.Boolean IsDeveloperOnly(Game.UI.Menu.AutomaticSettings+IProxyProperty property);
    private static System.Boolean IsHidden(Game.UI.Menu.AutomaticSettings+IProxyProperty property);
    private static System.Boolean IsShowGroupName(Game.Settings.Setting setting, System.Boolean& showAll, System.Collections.ObjectModel.ReadOnlyCollection`1[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& groups);
    private static System.Boolean IsSupportedOnPlatform(Game.UI.Menu.AutomaticSettings+IProxyProperty property);
    public static System.Boolean TryGetAction<T>(Game.Settings.Setting setting, System.Type type, System.String name, Func`1& action);
}
```


## Fields

- `private static readonly System.Reflection.MethodInfo s_CustomDropdownMethodInfo`  

```csharp
private static readonly System.Reflection.MethodInfo s_CustomDropdownMethodInfo;
```

- `private static readonly System.Reflection.MethodInfo s_EnumSetterMethodInfo`  

```csharp
private static readonly System.Reflection.MethodInfo s_EnumSetterMethodInfo;
```

- `private static readonly System.Collections.Generic.Dictionary<System.String, Game.UI.Widgets.ButtonRow> s_ButtonGroups`  

```csharp
private static readonly System.Collections.Generic.Dictionary<System.String, Game.UI.Widgets.ButtonRow> s_ButtonGroups;
```


## Methods

- `internal static <AddKeyBindingProperty>g__GetValueVersion|33_0() : System.Int32`  

```csharp
internal static System.Int32 <AddKeyBindingProperty>g__GetValueVersion|33_0();
```

- `public static AddBoolButtonProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : Game.UI.Widgets.IWidget`  

```csharp
public static Game.UI.Widgets.IWidget AddBoolButtonProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData);
```

- `public static AddBoolButtonWithConfirmationProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : Game.UI.Widgets.IWidget`  

```csharp
public static Game.UI.Widgets.IWidget AddBoolButtonWithConfirmationProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData);
```

- `public static AddBoolToggleProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : Game.UI.Widgets.IWidget`  

```csharp
public static Game.UI.Widgets.IWidget AddBoolToggleProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData);
```

- `public static AddCustomDropdownProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : Game.UI.Widgets.IWidget`  

```csharp
public static Game.UI.Widgets.IWidget AddCustomDropdownProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData);
```

- `public static AddCustomDropdownPropertyGeneric<T>(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : Game.UI.Widgets.IWidget`  

```csharp
public static Game.UI.Widgets.IWidget AddCustomDropdownPropertyGeneric<T>(Game.UI.Menu.AutomaticSettings+SettingItemData itemData);
```

- `public static AddDirectoryPickerBindingProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : Game.UI.Widgets.IWidget`  

```csharp
public static Game.UI.Widgets.IWidget AddDirectoryPickerBindingProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData);
```

- `public static AddEnumDropdownProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : Game.UI.Widgets.IWidget`  

```csharp
public static Game.UI.Widgets.IWidget AddEnumDropdownProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData);
```

- `public static AddEnumSimpleProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : Game.UI.Widgets.IWidget`  

```csharp
public static Game.UI.Widgets.IWidget AddEnumSimpleProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData);
```

- `public static AddFloatSliderProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : Game.UI.Widgets.IWidget`  

```csharp
public static Game.UI.Widgets.IWidget AddFloatSliderProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData);
```

- `public static AddIntDropdownProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : Game.UI.Widgets.IWidget`  

```csharp
public static Game.UI.Widgets.IWidget AddIntDropdownProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData);
```

- `public static AddIntSliderProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : Game.UI.Widgets.IWidget`  

```csharp
public static Game.UI.Widgets.IWidget AddIntSliderProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData);
```

- `public static AddKeyBindingProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : Game.UI.Widgets.IWidget`  

```csharp
public static Game.UI.Widgets.IWidget AddKeyBindingProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData);
```

- `public static AddLocalizedStringFieldProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : Game.UI.Widgets.IWidget`  

```csharp
public static Game.UI.Widgets.IWidget AddLocalizedStringFieldProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData);
```

- `public static AddStringDropdownProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : Game.UI.Widgets.IWidget`  

```csharp
public static Game.UI.Widgets.IWidget AddStringDropdownProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData);
```

- `public static AddStringFieldProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : Game.UI.Widgets.IWidget`  

```csharp
public static Game.UI.Widgets.IWidget AddStringFieldProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData);
```

- `public static AddStringTextInputProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : Game.UI.Widgets.IWidget`  

```csharp
public static Game.UI.Widgets.IWidget AddStringTextInputProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData);
```

- `public static FillSettingsPage(Game.Settings.Setting setting, System.String id, System.Boolean addPrefix) : Game.UI.Menu.AutomaticSettings+SettingPageData`  

```csharp
public static Game.UI.Menu.AutomaticSettings+SettingPageData FillSettingsPage(Game.Settings.Setting setting, System.String id, System.Boolean addPrefix);
```

- `public static FillSettingsPage(Game.UI.Menu.AutomaticSettings+SettingPageData pageData, Game.Settings.Setting setting) : System.Void`  

```csharp
public static System.Void FillSettingsPage(Game.UI.Menu.AutomaticSettings+SettingPageData pageData, Game.Settings.Setting setting);
```

- `private static GetButtonsGroup(System.String groupName, Game.UI.Widgets.ButtonRow& buttons, Game.UI.Widgets.Button item) : System.Boolean`  

```csharp
private static System.Boolean GetButtonsGroup(System.String groupName, Game.UI.Widgets.ButtonRow& buttons, Game.UI.Widgets.Button item);
```

- `public static GetConfirmationMessage(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : Game.UI.Localization.LocalizedString`  

```csharp
public static Game.UI.Localization.LocalizedString GetConfirmationMessage(Game.UI.Menu.AutomaticSettings+SettingItemData itemData);
```

- `private static GetDropdownItemAccessor<T>(Game.UI.Menu.AutomaticSettings+IProxyProperty property, Game.Settings.Setting setting) : Game.UI.Menu.AutomaticSettings+DropdownItemsAccessor<Game.UI.Widgets.DropdownItem<T>[]>`  

```csharp
private static Game.UI.Menu.AutomaticSettings+DropdownItemsAccessor<Game.UI.Widgets.DropdownItem<T>[]> GetDropdownItemAccessor<T>(Game.UI.Menu.AutomaticSettings+IProxyProperty property, Game.Settings.Setting setting);
```

- `private static GetEnumCustomSetterAction(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : System.Action<System.UInt64>`  

```csharp
private static System.Action<System.UInt64> GetEnumCustomSetterAction(Game.UI.Menu.AutomaticSettings+SettingItemData itemData);
```

- `private static GetEnumGetter(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : System.Func<System.UInt64>`  

```csharp
private static System.Func<System.UInt64> GetEnumGetter(Game.UI.Menu.AutomaticSettings+SettingItemData itemData);
```

- `private static GetEnumMemberAccessor(Game.UI.Menu.AutomaticSettings+IProxyProperty property, Game.Settings.Setting setting, System.String prefix) : Game.Reflection.DelegateAccessor<Game.UI.Widgets.EnumMember[]>`  

```csharp
private static Game.Reflection.DelegateAccessor<Game.UI.Widgets.EnumMember[]> GetEnumMemberAccessor(Game.UI.Menu.AutomaticSettings+IProxyProperty property, Game.Settings.Setting setting, System.String prefix);
```

- `private static GetEnumSetter(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : System.Action<System.UInt64>`  

```csharp
private static System.Action<System.UInt64> GetEnumSetter(Game.UI.Menu.AutomaticSettings+SettingItemData itemData);
```

- `public static GetEnumValues(System.Type enumType, System.String prefix) : Game.UI.Widgets.EnumMember[]`  

```csharp
public static Game.UI.Widgets.EnumMember[] GetEnumValues(System.Type enumType, System.String prefix);
```

- `private static GetSections(Game.UI.Menu.AutomaticSettings+IProxyProperty property) : System.Collections.Generic.Dictionary<System.String, Game.UI.Menu.AutomaticSettings+SectionInfo>`  

```csharp
private static System.Collections.Generic.Dictionary<System.String, Game.UI.Menu.AutomaticSettings+SectionInfo> GetSections(Game.UI.Menu.AutomaticSettings+IProxyProperty property);
```

- `private static GetSetterActionGeneric<T>(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : System.Action<System.UInt64>`  

```csharp
private static System.Action<System.UInt64> GetSetterActionGeneric<T>(Game.UI.Menu.AutomaticSettings+SettingItemData itemData);
```

- `private static GetTabWarningGetters(Game.Settings.Setting setting) : System.Collections.Generic.Dictionary<System.String, System.Func<System.Boolean>>`  

```csharp
private static System.Collections.Generic.Dictionary<System.String, System.Func<System.Boolean>> GetTabWarningGetters(Game.Settings.Setting setting);
```

- `private static GetWarningGetter(Game.Settings.Setting setting) : System.Func<System.Boolean>`  

```csharp
private static System.Func<System.Boolean> GetWarningGetter(Game.Settings.Setting setting);
```

- `public static GetWidgetType(Game.UI.Menu.AutomaticSettings+IProxyProperty property) : Game.UI.Menu.AutomaticSettings+WidgetType`  

```csharp
public static Game.UI.Menu.AutomaticSettings+WidgetType GetWidgetType(Game.UI.Menu.AutomaticSettings+IProxyProperty property);
```

- `private static IsDeveloperOnly(Game.UI.Menu.AutomaticSettings+IProxyProperty property) : System.Boolean`  

```csharp
private static System.Boolean IsDeveloperOnly(Game.UI.Menu.AutomaticSettings+IProxyProperty property);
```

- `private static IsHidden(Game.UI.Menu.AutomaticSettings+IProxyProperty property) : System.Boolean`  

```csharp
private static System.Boolean IsHidden(Game.UI.Menu.AutomaticSettings+IProxyProperty property);
```

- `private static IsShowGroupName(Game.Settings.Setting setting, System.Boolean& showAll, System.Collections.ObjectModel.ReadOnlyCollection`1[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& groups) : System.Boolean`  

```csharp
private static System.Boolean IsShowGroupName(Game.Settings.Setting setting, System.Boolean& showAll, System.Collections.ObjectModel.ReadOnlyCollection`1[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& groups);
```

- `private static IsSupportedOnPlatform(Game.UI.Menu.AutomaticSettings+IProxyProperty property) : System.Boolean`  

```csharp
private static System.Boolean IsSupportedOnPlatform(Game.UI.Menu.AutomaticSettings+IProxyProperty property);
```

- `public static TryGetAction<T>(Game.Settings.Setting setting, System.Type type, System.String name, Func`1& action) : System.Boolean`  

```csharp
public static System.Boolean TryGetAction<T>(Game.Settings.Setting setting, System.Type type, System.String name, Func`1& action);
```


## Nested types

- `Game.UI.Menu.AutomaticSettings+SectionInfo`  
- `Game.UI.Menu.AutomaticSettings+WidgetType`  
- `Game.UI.Menu.AutomaticSettings+SettingPageData`  
- `Game.UI.Menu.AutomaticSettings+SettingTabData`  
- `Game.UI.Menu.AutomaticSettings+SettingItemData`  
- `Game.UI.Menu.AutomaticSettings+IProxyProperty`  
- `Game.UI.Menu.AutomaticSettings+ProxyProperty`  
- `Game.UI.Menu.AutomaticSettings+ManualProperty`  
- `Game.UI.Menu.AutomaticSettings+DropdownItemsAccessor<T>`  
- `Game.UI.Menu.AutomaticSettings+<>c`  
- `Game.UI.Menu.AutomaticSettings+<>c__DisplayClass12_0`  
- `Game.UI.Menu.AutomaticSettings+<>c__DisplayClass21_0`  
- `Game.UI.Menu.AutomaticSettings+<>c__DisplayClass22_0`  
- `Game.UI.Menu.AutomaticSettings+<>c__DisplayClass23_0`  
- `Game.UI.Menu.AutomaticSettings+<>c__DisplayClass24_0`  
- `Game.UI.Menu.AutomaticSettings+<>c__DisplayClass25_0`  
- `Game.UI.Menu.AutomaticSettings+<>c__DisplayClass26_0`  
- `Game.UI.Menu.AutomaticSettings+<>c__DisplayClass27_0`  
- `Game.UI.Menu.AutomaticSettings+<>c__DisplayClass28_0`  
- `Game.UI.Menu.AutomaticSettings+<>c__DisplayClass29_0`  
- `Game.UI.Menu.AutomaticSettings+<>c__DisplayClass30_0`  
- `Game.UI.Menu.AutomaticSettings+<>c__DisplayClass31_0`  
- `Game.UI.Menu.AutomaticSettings+<>c__DisplayClass32_0`  
- `Game.UI.Menu.AutomaticSettings+<>c__DisplayClass33_0`  
- `Game.UI.Menu.AutomaticSettings+<>c__DisplayClass34_0`  
- `Game.UI.Menu.AutomaticSettings+<>c__DisplayClass36_0<T>`  
- `Game.UI.Menu.AutomaticSettings+<>c__DisplayClass37_0`  
- `Game.UI.Menu.AutomaticSettings+<>c__DisplayClass38_0`  
- `Game.UI.Menu.AutomaticSettings+<>c__DisplayClass39_0`  
- `Game.UI.Menu.AutomaticSettings+<>c__DisplayClass39_1`  
- `Game.UI.Menu.AutomaticSettings+<>c__DisplayClass39_2`  
- `Game.UI.Menu.AutomaticSettings+<>c__DisplayClass39_3`  
- `Game.UI.Menu.AutomaticSettings+<>c__DisplayClass39_4`  
- `Game.UI.Menu.AutomaticSettings+<>c__DisplayClass39_5`  
- `Game.UI.Menu.AutomaticSettings+<>c__DisplayClass39_6`  
- `Game.UI.Menu.AutomaticSettings+<>c__DisplayClass39_7`  
- `Game.UI.Menu.AutomaticSettings+<>c__DisplayClass40_0<T>`  

