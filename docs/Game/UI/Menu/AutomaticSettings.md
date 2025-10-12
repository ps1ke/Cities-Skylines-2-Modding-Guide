# Game.UI.Menu.AutomaticSettings

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class static public  

**Base:** `System.Object`  

## Fields

- `private static readonly System.Reflection.MethodInfo s_CustomDropdownMethodInfo`  
- `private static readonly System.Reflection.MethodInfo s_EnumSetterMethodInfo`  
- `private static readonly System.Collections.Generic.Dictionary<System.String, Game.UI.Widgets.ButtonRow> s_ButtonGroups`  

## Methods

- `internal static <AddKeyBindingProperty>g__GetValueVersion|33_0() : System.Int32`  
- `public static AddBoolButtonProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : Game.UI.Widgets.IWidget`  
- `public static AddBoolButtonWithConfirmationProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : Game.UI.Widgets.IWidget`  
- `public static AddBoolToggleProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : Game.UI.Widgets.IWidget`  
- `public static AddCustomDropdownProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : Game.UI.Widgets.IWidget`  
- `public static AddCustomDropdownPropertyGeneric<T>(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : Game.UI.Widgets.IWidget`  
- `public static AddDirectoryPickerBindingProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : Game.UI.Widgets.IWidget`  
- `public static AddEnumDropdownProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : Game.UI.Widgets.IWidget`  
- `public static AddEnumSimpleProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : Game.UI.Widgets.IWidget`  
- `public static AddFloatSliderProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : Game.UI.Widgets.IWidget`  
- `public static AddIntDropdownProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : Game.UI.Widgets.IWidget`  
- `public static AddIntSliderProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : Game.UI.Widgets.IWidget`  
- `public static AddKeyBindingProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : Game.UI.Widgets.IWidget`  
- `public static AddLocalizedStringFieldProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : Game.UI.Widgets.IWidget`  
- `public static AddStringDropdownProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : Game.UI.Widgets.IWidget`  
- `public static AddStringFieldProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : Game.UI.Widgets.IWidget`  
- `public static AddStringTextInputProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : Game.UI.Widgets.IWidget`  
- `public static FillSettingsPage(Game.Settings.Setting setting, System.String id, System.Boolean addPrefix) : Game.UI.Menu.AutomaticSettings+SettingPageData`  
- `public static FillSettingsPage(Game.UI.Menu.AutomaticSettings+SettingPageData pageData, Game.Settings.Setting setting) : System.Void`  
- `private static GetButtonsGroup(System.String groupName, Game.UI.Widgets.ButtonRow& buttons, Game.UI.Widgets.Button item) : System.Boolean`  
- `public static GetConfirmationMessage(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : Game.UI.Localization.LocalizedString`  
- `private static GetDropdownItemAccessor<T>(Game.UI.Menu.AutomaticSettings+IProxyProperty property, Game.Settings.Setting setting) : Game.UI.Menu.AutomaticSettings+DropdownItemsAccessor<Game.UI.Widgets.DropdownItem<T>[]>`  
- `private static GetEnumCustomSetterAction(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : System.Action<System.UInt64>`  
- `private static GetEnumGetter(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : System.Func<System.UInt64>`  
- `private static GetEnumMemberAccessor(Game.UI.Menu.AutomaticSettings+IProxyProperty property, Game.Settings.Setting setting, System.String prefix) : Game.Reflection.DelegateAccessor<Game.UI.Widgets.EnumMember[]>`  
- `private static GetEnumSetter(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : System.Action<System.UInt64>`  
- `public static GetEnumValues(System.Type enumType, System.String prefix) : Game.UI.Widgets.EnumMember[]`  
- `private static GetSections(Game.UI.Menu.AutomaticSettings+IProxyProperty property) : System.Collections.Generic.Dictionary<System.String, Game.UI.Menu.AutomaticSettings+SectionInfo>`  
- `private static GetSetterActionGeneric<T>(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : System.Action<System.UInt64>`  
- `private static GetTabWarningGetters(Game.Settings.Setting setting) : System.Collections.Generic.Dictionary<System.String, System.Func<System.Boolean>>`  
- `private static GetWarningGetter(Game.Settings.Setting setting) : System.Func<System.Boolean>`  
- `public static GetWidgetType(Game.UI.Menu.AutomaticSettings+IProxyProperty property) : Game.UI.Menu.AutomaticSettings+WidgetType`  
- `private static IsDeveloperOnly(Game.UI.Menu.AutomaticSettings+IProxyProperty property) : System.Boolean`  
- `private static IsHidden(Game.UI.Menu.AutomaticSettings+IProxyProperty property) : System.Boolean`  
- `private static IsShowGroupName(Game.Settings.Setting setting, System.Boolean& showAll, System.Collections.ObjectModel.ReadOnlyCollection`1[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& groups) : System.Boolean`  
- `private static IsSupportedOnPlatform(Game.UI.Menu.AutomaticSettings+IProxyProperty property) : System.Boolean`  
- `public static TryGetAction<T>(Game.Settings.Setting setting, System.Type type, System.String name, Func`1& action) : System.Boolean`  

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

