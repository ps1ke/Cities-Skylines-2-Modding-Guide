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
public static IWidget AddBoolButtonProperty(SettingItemData itemData)
	{
		if (itemData.property.canRead || !itemData.property.canWrite)
		{
			return null;
		}
		Button item = new Button
		{
			path = itemData.path,
			displayName = itemData.displayName,
			description = itemData.description,
			displayNameAction = itemData.dispayNameAction,
			descriptionAction = itemData.descriptionAction,
			action = delegate
			{
				itemData.property.SetValue(itemData.setting, true);
			},
			disabled = itemData.disableAction,
			hidden = itemData.hideAction
		};
		if (GetButtonsGroup(itemData.property.GetAttribute<SettingsUIButtonGroupAttribute>()?.name ?? (itemData.property.declaringType.Name + "." + itemData.property.name + "_ButtonGroup"), out var buttons, item))
		{
			return buttons;
		}
		return null;
	}
```

- `public static AddBoolButtonWithConfirmationProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : Game.UI.Widgets.IWidget`  

```csharp
public static IWidget AddBoolButtonWithConfirmationProperty(SettingItemData itemData)
	{
		ButtonWithConfirmation item = new ButtonWithConfirmation
		{
			path = itemData.path,
			displayName = itemData.displayName,
			description = itemData.description,
			displayNameAction = itemData.dispayNameAction,
			descriptionAction = itemData.descriptionAction,
			action = delegate
			{
				itemData.property.SetValue(itemData.setting, true);
			},
			disabled = itemData.disableAction,
			hidden = itemData.hideAction,
			confirmationMessage = GetConfirmationMessage(itemData)
		};
		if (GetButtonsGroup(itemData.property.GetAttribute<SettingsUIButtonGroupAttribute>()?.name ?? (itemData.property.declaringType.Name + "." + itemData.property.name + "_ButtonGroup"), out var buttons, item))
		{
			return buttons;
		}
		return null;
	}
```

- `public static AddBoolToggleProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : Game.UI.Widgets.IWidget`  

```csharp
public static IWidget AddBoolToggleProperty(SettingItemData itemData)
	{
		if (!itemData.property.canRead || !itemData.property.canWrite)
		{
			return null;
		}
		Action<bool> setterAction = itemData.setterAction as Action<bool>;
		return new ToggleField
		{
			path = itemData.path,
			displayName = itemData.displayName,
			description = itemData.description,
			displayNameAction = itemData.dispayNameAction,
			descriptionAction = itemData.descriptionAction,
			warningAction = itemData.warningAction,
			accessor = new DelegateAccessor<bool>(() => (bool)itemData.property.GetValue(itemData.setting), delegate(bool value)
			{
				setterAction?.Invoke(value);
				itemData.property.SetValue(itemData.setting, value);
				itemData.setting.ApplyAndSave();
			}),
			disabled = itemData.disableAction,
			hidden = itemData.hideAction
		};
	}
```

- `public static AddCustomDropdownProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : Game.UI.Widgets.IWidget`  

```csharp
public static IWidget AddCustomDropdownProperty(SettingItemData itemData)
	{
		if (itemData.property.GetAttribute<SettingsUIDropdownAttribute>() == null)
		{
			return null;
		}
		if (!typeof(IJsonWritable).IsAssignableFrom(itemData.property.propertyType))
		{
			return null;
		}
		if (!typeof(IJsonReadable).IsAssignableFrom(itemData.property.propertyType))
		{
			return null;
		}
		if (!itemData.property.propertyType.IsValueType && itemData.property.propertyType.GetConstructor(Type.EmptyTypes) == null)
		{
			return null;
		}
		return (IWidget)s_CustomDropdownMethodInfo.MakeGenericMethod(itemData.property.propertyType).Invoke(null, new object[1] { itemData });
	}
```

- `public static AddCustomDropdownPropertyGeneric<T>(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : Game.UI.Widgets.IWidget`  

```csharp
public static Game.UI.Widgets.IWidget AddCustomDropdownPropertyGeneric<T>(Game.UI.Menu.AutomaticSettings+SettingItemData itemData);
```

- `public static AddDirectoryPickerBindingProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : Game.UI.Widgets.IWidget`  

```csharp
public static IWidget AddDirectoryPickerBindingProperty(SettingItemData itemData)
	{
		Action<string> setterAction = itemData.setterAction as Action<string>;
		return new DirectoryPickerField
		{
			path = itemData.path,
			displayName = itemData.displayName,
			displayNameAction = itemData.dispayNameAction,
			warningAction = itemData.warningAction,
			accessor = new DelegateAccessor<string>(() => (string)itemData.property.GetValue(itemData.setting), delegate(string value)
			{
				setterAction?.Invoke(value);
				itemData.property.SetValue(itemData.setting, value);
				itemData.setting.ApplyAndSave();
			}),
			disabled = itemData.disableAction,
			hidden = itemData.hideAction,
			action = delegate
			{
				string root = (string)itemData.property.GetValue(itemData.setting);
				(World.DefaultGameObjectInjectionWorld?.GetOrCreateSystemManaged<OptionsUISystem>()).OpenDirectoryBrowser(root, delegate(string value)
				{
					setterAction?.Invoke(value);
					itemData.property.SetValue(itemData.setting, value);
					itemData.setting.ApplyAndSave();
				});
			}
		};
	}
```

- `public static AddEnumDropdownProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : Game.UI.Widgets.IWidget`  

```csharp
public static IWidget AddEnumDropdownProperty(SettingItemData itemData)
	{
		Action<int> customSetterAction = itemData.setterAction as Action<int>;
		return new DropdownField<int>
		{
			path = itemData.path,
			displayName = itemData.displayName,
			description = itemData.description,
			displayNameAction = itemData.dispayNameAction,
			descriptionAction = itemData.descriptionAction,
			warningAction = itemData.warningAction,
			accessor = new DelegateAccessor<int>(() => (int)itemData.property.GetValue(itemData.setting), delegate(int value)
			{
				customSetterAction?.Invoke(value);
				itemData.property.SetValue(itemData.setting, value);
				itemData.setting.ApplyAndSave();
			}),
			itemsAccessor = GetDropdownItemAccessor<int>(itemData.property, itemData.setting),
			itemsVersion = itemData.valueVersionAction,
			disabled = itemData.disableAction,
			hidden = itemData.hideAction
		};
	}
```

- `public static AddEnumSimpleProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : Game.UI.Widgets.IWidget`  

```csharp
public static IWidget AddEnumSimpleProperty(SettingItemData itemData)
	{
		Func<ulong> enumGetter = GetEnumGetter(itemData);
		Action<ulong> setter = GetEnumSetter(itemData);
		Action<ulong> customSetterAction = GetEnumCustomSetterAction(itemData);
		return new EnumField
		{
			path = itemData.path,
			displayName = itemData.displayName,
			description = itemData.description,
			displayNameAction = itemData.dispayNameAction,
			descriptionAction = itemData.descriptionAction,
			warningAction = itemData.warningAction,
			accessor = new DelegateAccessor<ulong>(enumGetter, delegate(ulong value)
			{
				customSetterAction?.Invoke(value);
				setter(value);
				itemData.setting.ApplyAndSave();
			}),
			itemsAccessor = GetEnumMemberAccessor(itemData.property, itemData.setting, itemData.prefix),
			itemsVersion = itemData.valueVersionAction,
			disabled = itemData.disableAction,
			hidden = itemData.hideAction
		};
	}
```

- `public static AddFloatSliderProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : Game.UI.Widgets.IWidget`  

```csharp
public static IWidget AddFloatSliderProperty(SettingItemData itemData)
	{
		SettingsUISliderAttribute attribute = itemData.property.GetAttribute<SettingsUISliderAttribute>();
		Action<float> setterAction = itemData.setterAction as Action<float>;
		FloatSliderField floatSliderField = new FloatSliderField
		{
			path = itemData.path,
			displayName = itemData.displayName,
			description = itemData.description,
			displayNameAction = itemData.dispayNameAction,
			descriptionAction = itemData.descriptionAction,
			warningAction = itemData.warningAction,
			min = attribute.min,
			max = attribute.max,
			step = attribute.step,
			unit = attribute.unit,
			scaleDragVolume = attribute.scaleDragVolume,
			updateOnDragEnd = attribute.updateOnDragEnd,
			accessor = new DelegateAccessor<double>(() => (float)itemData.property.GetValue(itemData.setting) * (float)(int)attribute.scalarMultiplier, delegate(double value)
			{
				setterAction?.Invoke((float)value);
				itemData.property.SetValue(itemData.setting, (float)(value / (double)attribute.scalarMultiplier));
				itemData.setting.ApplyAndSave();
			}),
			disabled = itemData.disableAction,
			hidden = itemData.hideAction
		};
		SettingsUICustomFormatAttribute attribute2 = itemData.property.GetAttribute<SettingsUICustomFormatAttribute>();
		if (attribute2 != null)
		{
			floatSliderField.unit = "custom";
			floatSliderField.fractionDigits = Math.Max(attribute2.fractionDigits, 0);
			floatSliderField.separateThousands = attribute2.separateThousands;
			floatSliderField.maxValueWithFraction = attribute2.maxValueWithFraction;
			floatSliderField.signed = attribute2.signed;
		}
		return floatSliderField;
	}
```

- `public static AddIntDropdownProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : Game.UI.Widgets.IWidget`  

```csharp
public static IWidget AddIntDropdownProperty(SettingItemData itemData)
	{
		if (itemData.property.GetAttribute<SettingsUIDropdownAttribute>() == null)
		{
			return null;
		}
		Action<int> setterAction = itemData.setterAction as Action<int>;
		return new DropdownField<int>
		{
			path = itemData.path,
			displayName = itemData.displayName,
			description = itemData.description,
			displayNameAction = itemData.dispayNameAction,
			descriptionAction = itemData.descriptionAction,
			warningAction = itemData.warningAction,
			accessor = new DelegateAccessor<int>(() => (int)itemData.property.GetValue(itemData.setting), delegate(int value)
			{
				setterAction?.Invoke(value);
				itemData.property.SetValue(itemData.setting, value);
				itemData.setting.ApplyAndSave();
			}),
			itemsAccessor = GetDropdownItemAccessor<int>(itemData.property, itemData.setting),
			itemsVersion = itemData.valueVersionAction,
			disabled = itemData.disableAction,
			hidden = itemData.hideAction
		};
	}
```

- `public static AddIntSliderProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : Game.UI.Widgets.IWidget`  

```csharp
public static IWidget AddIntSliderProperty(SettingItemData itemData)
	{
		SettingsUISliderAttribute sliderAttribute = itemData.property.GetAttribute<SettingsUISliderAttribute>();
		if (sliderAttribute == null)
		{
			return null;
		}
		Action<int> setterAction = itemData.setterAction as Action<int>;
		IntSliderField intSliderField = new IntSliderField
		{
			path = itemData.path,
			displayName = itemData.displayName,
			description = itemData.description,
			displayNameAction = itemData.dispayNameAction,
			descriptionAction = itemData.descriptionAction,
			warningAction = itemData.warningAction,
			min = (int)sliderAttribute.min,
			max = (int)sliderAttribute.max,
			step = (int)sliderAttribute.step,
			unit = sliderAttribute.unit,
			scaleDragVolume = sliderAttribute.scaleDragVolume,
			updateOnDragEnd = sliderAttribute.updateOnDragEnd,
			accessor = new DelegateAccessor<int>(() => (int)itemData.property.GetValue(itemData.setting) * (int)sliderAttribute.scalarMultiplier, delegate(int value)
			{
				setterAction?.Invoke(value);
				itemData.property.SetValue(itemData.setting, Mathf.RoundToInt((float)value / sliderAttribute.scalarMultiplier));
				itemData.setting.ApplyAndSave();
			}),
			disabled = itemData.disableAction,
			hidden = itemData.hideAction
		};
		SettingsUICustomFormatAttribute attribute = itemData.property.GetAttribute<SettingsUICustomFormatAttribute>();
		if (attribute != null)
		{
			intSliderField.unit = "custom";
			intSliderField.separateThousands = attribute.separateThousands;
			intSliderField.signed = attribute.signed;
		}
		return intSliderField;
	}
```

- `public static AddKeyBindingProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : Game.UI.Widgets.IWidget`  

```csharp
public static IWidget AddKeyBindingProperty(SettingItemData itemData)
	{
		Action<ProxyBinding> setterAction = itemData.setterAction as Action<ProxyBinding>;
		return new InputBindingField
		{
			path = itemData.path,
			displayName = itemData.displayName,
			description = itemData.description,
			displayNameAction = itemData.dispayNameAction,
			descriptionAction = itemData.descriptionAction,
			accessor = new DelegateAccessor<ProxyBinding>(delegate
			{
				ProxyBinding binding = (ProxyBinding)itemData.property.GetValue(itemData.setting);
				ProxyBinding binding2 = InputManager.instance.GetOrCreateBindingWatcher(binding).binding;
				binding2.alies = binding.alies;
				return binding2;
			}, delegate(ProxyBinding value)
			{
				if (InputManager.instance.SetBinding(value, out var result))
				{
					setterAction?.Invoke(result);
					itemData.property.SetValue(itemData.setting, result);
					itemData.setting.ApplyAndSave();
				}
			}),
			valueVersion = (itemData.valueVersionAction ?? new Func<int>(GetValueVersion)),
			disabled = itemData.disableAction,
			hidden = itemData.hideAction
		};
		static int GetValueVersion()
		{
			return InputManager.instance.actionVersion;
		}
	}
```

- `public static AddLocalizedStringFieldProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : Game.UI.Widgets.IWidget`  

```csharp
public static IWidget AddLocalizedStringFieldProperty(SettingItemData itemData)
	{
		return new LocalizedValueField
		{
			path = itemData.path,
			displayName = itemData.displayName,
			description = itemData.description,
			displayNameAction = itemData.dispayNameAction,
			descriptionAction = itemData.descriptionAction,
			warningAction = itemData.warningAction,
			accessor = new DelegateAccessor<LocalizedString>(() => (LocalizedString)itemData.property.GetValue(itemData.setting), delegate
			{
			}),
			valueVersion = itemData.valueVersionAction,
			disabled = itemData.disableAction,
			hidden = itemData.hideAction
		};
	}
```

- `public static AddStringDropdownProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : Game.UI.Widgets.IWidget`  

```csharp
public static IWidget AddStringDropdownProperty(SettingItemData itemData)
	{
		if (itemData.property.GetAttribute<SettingsUIDropdownAttribute>() == null)
		{
			return null;
		}
		Action<string> setterAction = itemData.setterAction as Action<string>;
		return new DropdownField<string>
		{
			path = itemData.path,
			displayName = itemData.displayName,
			description = itemData.description,
			displayNameAction = itemData.dispayNameAction,
			descriptionAction = itemData.descriptionAction,
			warningAction = itemData.warningAction,
			accessor = new DelegateAccessor<string>(() => (string)itemData.property.GetValue(itemData.setting), delegate(string value)
			{
				setterAction?.Invoke(value);
				itemData.property.SetValue(itemData.setting, value);
				itemData.setting.ApplyAndSave();
			}),
			itemsAccessor = GetDropdownItemAccessor<string>(itemData.property, itemData.setting),
			itemsVersion = itemData.valueVersionAction,
			disabled = itemData.disableAction,
			hidden = itemData.hideAction
		};
	}
```

- `public static AddStringFieldProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : Game.UI.Widgets.IWidget`  

```csharp
public static IWidget AddStringFieldProperty(SettingItemData itemData)
	{
		return new LocalizedValueField
		{
			path = itemData.path,
			displayName = itemData.displayName,
			description = itemData.description,
			displayNameAction = itemData.dispayNameAction,
			descriptionAction = itemData.descriptionAction,
			warningAction = itemData.warningAction,
			accessor = new DelegateAccessor<LocalizedString>(() => LocalizedString.Value((string)itemData.property.GetValue(itemData.setting)), delegate
			{
			}),
			valueVersion = itemData.valueVersionAction,
			disabled = itemData.disableAction,
			hidden = itemData.hideAction
		};
	}
```

- `public static AddStringTextInputProperty(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : Game.UI.Widgets.IWidget`  

```csharp
public static IWidget AddStringTextInputProperty(SettingItemData itemData)
	{
		Action<string> setterAction = itemData.setterAction as Action<string>;
		return new StringInputField
		{
			path = itemData.path,
			displayName = itemData.displayName,
			description = itemData.description,
			displayNameAction = itemData.dispayNameAction,
			descriptionAction = itemData.descriptionAction,
			warningAction = itemData.warningAction,
			accessor = new DelegateAccessor<string>(() => (string)itemData.property.GetValue(itemData.setting), delegate(string value)
			{
				setterAction?.Invoke(value);
				itemData.property.SetValue(itemData.setting, value);
				itemData.setting.ApplyAndSave();
			}),
			disabled = itemData.disableAction,
			hidden = itemData.hideAction
		};
	}
```

- `public static FillSettingsPage(Game.Settings.Setting setting, System.String id, System.Boolean addPrefix) : Game.UI.Menu.AutomaticSettings+SettingPageData`  

```csharp
public static void FillSettingsPage(SettingPageData pageData, Setting setting)
	{
		if (setting.GetType().TryGetAttribute<SettingsUITabOrderAttribute>(out var attribute))
		{
			if (TryGetAction(setting, attribute.checkType, attribute.checkMethod, out Func<string[]> action))
			{
				string[] array = action();
				foreach (string tab in array)
				{
					pageData.AddTab(tab);
				}
			}
			else
			{
				foreach (string tab2 in attribute.tabs)
				{
					pageData.AddTab(tab2);
				}
			}
		}
		if (setting.GetType().TryGetAttribute<SettingsUIGroupOrderAttribute>(out var attribute2))
		{
			if (TryGetAction(setting, attribute2.checkType, attribute2.checkMethod, out Func<string[]> action2))
			{
				string[] array = action2();
				foreach (string text in array)
				{
					pageData.AddGroup(text);
				}
			}
			else
			{
				foreach (string group in attribute2.groups)
				{
					pageData.AddGroup(group);
				}
			}
		}
		PropertyInfo[] properties = setting.GetType().GetProperties(BindingFlags.Instance | BindingFlags.Public);
		for (int i = 0; i < properties.Length; i++)
		{
			ProxyProperty property = new ProxyProperty(properties[i]);
			if (!IsSupportedOnPlatform(property) || IsHidden(property) || IsDeveloperOnly(property))
			{
				continue;
			}
			WidgetType widgetType = GetWidgetType(property);
			if (widgetType == WidgetType.None)
			{
				continue;
			}
			foreach (SectionInfo value in GetSections(property).Values)
			{
				SettingItemData settingItemData = ((widgetType != WidgetType.MultilineText) ? new SettingItemData(widgetType, setting, property, pageData.prefix) : new MultilineTextSettingItemData(setting, property, pageData.prefix));
				SettingItemData settingItemData2 = settingItemData;
				settingItemData2.simpleGroup = value.m_SimpleGroup;
				settingItemData2.advancedGroup = value.m_AdvancedGroup;
				pageData[value.m_Tab].AddItem(settingItemData2);
				pageData.AddGroup(settingItemData2.simpleGroup);
				pageData.AddGroup(settingItemData2.advancedGroup);
			}
		}
	}
```

- `public static FillSettingsPage(Game.UI.Menu.AutomaticSettings+SettingPageData pageData, Game.Settings.Setting setting) : System.Void`  

```csharp
public static void FillSettingsPage(SettingPageData pageData, Setting setting)
	{
		if (setting.GetType().TryGetAttribute<SettingsUITabOrderAttribute>(out var attribute))
		{
			if (TryGetAction(setting, attribute.checkType, attribute.checkMethod, out Func<string[]> action))
			{
				string[] array = action();
				foreach (string tab in array)
				{
					pageData.AddTab(tab);
				}
			}
			else
			{
				foreach (string tab2 in attribute.tabs)
				{
					pageData.AddTab(tab2);
				}
			}
		}
		if (setting.GetType().TryGetAttribute<SettingsUIGroupOrderAttribute>(out var attribute2))
		{
			if (TryGetAction(setting, attribute2.checkType, attribute2.checkMethod, out Func<string[]> action2))
			{
				string[] array = action2();
				foreach (string text in array)
				{
					pageData.AddGroup(text);
				}
			}
			else
			{
				foreach (string group in attribute2.groups)
				{
					pageData.AddGroup(group);
				}
			}
		}
		PropertyInfo[] properties = setting.GetType().GetProperties(BindingFlags.Instance | BindingFlags.Public);
		for (int i = 0; i < properties.Length; i++)
		{
			ProxyProperty property = new ProxyProperty(properties[i]);
			if (!IsSupportedOnPlatform(property) || IsHidden(property) || IsDeveloperOnly(property))
			{
				continue;
			}
			WidgetType widgetType = GetWidgetType(property);
			if (widgetType == WidgetType.None)
			{
				continue;
			}
			foreach (SectionInfo value in GetSections(property).Values)
			{
				SettingItemData settingItemData = ((widgetType != WidgetType.MultilineText) ? new SettingItemData(widgetType, setting, property, pageData.prefix) : new MultilineTextSettingItemData(setting, property, pageData.prefix));
				SettingItemData settingItemData2 = settingItemData;
				settingItemData2.simpleGroup = value.m_SimpleGroup;
				settingItemData2.advancedGroup = value.m_AdvancedGroup;
				pageData[value.m_Tab].AddItem(settingItemData2);
				pageData.AddGroup(settingItemData2.simpleGroup);
				pageData.AddGroup(settingItemData2.advancedGroup);
			}
		}
	}
```

- `private static GetButtonsGroup(System.String groupName, Game.UI.Widgets.ButtonRow& buttons, Game.UI.Widgets.Button item) : System.Boolean`  

```csharp
private static bool GetButtonsGroup(string groupName, out ButtonRow buttons, Button item)
	{
		if (s_ButtonGroups.TryGetValue(groupName, out buttons))
		{
			List<Button> list = new List<Button>(buttons.children);
			list.Add(item);
			buttons.children = list.ToArray();
			return false;
		}
		buttons = new ButtonRow
		{
			children = new Button[1] { item }
		};
		s_ButtonGroups.Add(groupName, buttons);
		return true;
	}
```

- `public static GetConfirmationMessage(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : Game.UI.Localization.LocalizedString`  

```csharp
public static LocalizedString GetConfirmationMessage(SettingItemData itemData)
	{
		SettingsUIConfirmationAttribute attribute = itemData.property.GetAttribute<SettingsUIConfirmationAttribute>();
		if (attribute != null)
		{
			if (!string.IsNullOrEmpty(attribute.confirmMessageId))
			{
				return LocalizedString.IdWithFallback("Options.WARNING[" + attribute.confirmMessageId + "]", attribute.confirmMessageValue);
			}
			if (!string.IsNullOrEmpty(attribute.confirmMessageValue))
			{
				return LocalizedString.Value(attribute.confirmMessageValue);
			}
		}
		string text = itemData.property.declaringType.Name + "." + itemData.property.name;
		if (!string.IsNullOrEmpty(itemData.prefix))
		{
			text = itemData.prefix + "." + text;
		}
		text = "Options.WARNING[" + text + "]";
		return LocalizedString.Id(text);
	}
```

- `private static GetDropdownItemAccessor<T>(Game.UI.Menu.AutomaticSettings+IProxyProperty property, Game.Settings.Setting setting) : Game.UI.Menu.AutomaticSettings+DropdownItemsAccessor<Game.UI.Widgets.DropdownItem<T>[]>`  

```csharp
private static Game.UI.Menu.AutomaticSettings+DropdownItemsAccessor<Game.UI.Widgets.DropdownItem<T>[]> GetDropdownItemAccessor<T>(Game.UI.Menu.AutomaticSettings+IProxyProperty property, Game.Settings.Setting setting);
```

- `private static GetEnumCustomSetterAction(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : System.Action<System.UInt64>`  

```csharp
private static Action<ulong> GetEnumCustomSetterAction(SettingItemData itemData)
	{
		if ((object)itemData.setterAction == null)
		{
			return null;
		}
		Delegate setterAction = itemData.setterAction;
		Action<int> intSetter = setterAction as Action<int>;
		if (intSetter != null)
		{
			return delegate(ulong value)
			{
				intSetter((int)value);
			};
		}
		Type propertyType = itemData.property.propertyType;
		if (!propertyType.IsEnum)
		{
			return null;
		}
		Type type = typeof(Action<>).MakeGenericType(propertyType);
		if (itemData.setterAction.GetType() == type)
		{
			return (Action<ulong>)s_EnumSetterMethodInfo.MakeGenericMethod(itemData.property.propertyType).Invoke(null, new object[1] { itemData });
		}
		Type enumUnderlyingType = propertyType.GetEnumUnderlyingType();
		if (enumUnderlyingType == typeof(sbyte))
		{
			setterAction = itemData.setterAction;
			Action<sbyte> setter = setterAction as Action<sbyte>;
			if (setter != null)
			{
				return delegate(ulong value)
				{
					setter((sbyte)value);
				};
			}
		}
		else if (enumUnderlyingType == typeof(byte))
		{
			setterAction = itemData.setterAction;
			Action<byte> setter2 = setterAction as Action<byte>;
			if (setter2 != null)
			{
				return delegate(ulong value)
				{
					setter2((byte)value);
				};
			}
		}
		else if (enumUnderlyingType == typeof(short))
		{
			setterAction = itemData.setterAction;
			Action<short> setter3 = setterAction as Action<short>;
			if (setter3 != null)
			{
				return delegate(ulong value)
				{
					setter3((short)value);
				};
			}
		}
		else if (enumUnderlyingType == typeof(ushort))
		{
			setterAction = itemData.setterAction;
			Action<ushort> setter4 = setterAction as Action<ushort>;
			if (setter4 != null)
			{
				return delegate(ulong value)
				{
					setter4((ushort)value);
				};
			}
		}
		else if (enumUnderlyingType == typeof(int))
		{
			setterAction = itemData.setterAction;
			Action<int> setter5 = setterAction as Action<int>;
			if (setter5 != null)
			{
				return delegate(ulong value)
				{
					setter5((int)value);
				};
			}
		}
		else if (enumUnderlyingType == typeof(uint))
		{
			setterAction = itemData.setterAction;
			Action<uint> setter6 = setterAction as Action<uint>;
			if (setter6 != null)
			{
				return delegate(ulong value)
				{
					setter6((uint)value);
				};
			}
		}
		else if (enumUnderlyingType == typeof(long))
		{
			setterAction = itemData.setterAction;
			Action<long> setter7 = setterAction as Action<long>;
			if (setter7 != null)
			{
				return delegate(ulong value)
				{
					setter7((long)value);
				};
			}
		}
		else if (enumUnderlyingType == typeof(ulong) && itemData.setterAction is Action<ulong> result)
		{
			return result;
		}
		return null;
	}
```

- `private static GetEnumGetter(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : System.Func<System.UInt64>`  

```csharp
private static Func<ulong> GetEnumGetter(SettingItemData itemData)
	{
		Type propertyType = itemData.property.propertyType;
		if (!propertyType.IsEnum)
		{
			throw new ArgumentException("Property type is not an enum");
		}
		Type enumUnderlyingType = propertyType.GetEnumUnderlyingType();
		if (enumUnderlyingType == typeof(sbyte))
		{
			return () => (ulong)(sbyte)itemData.property.GetValue(itemData.setting);
		}
		if (enumUnderlyingType == typeof(byte))
		{
			return () => (byte)itemData.property.GetValue(itemData.setting);
		}
		if (enumUnderlyingType == typeof(short))
		{
			return () => (ulong)(short)itemData.property.GetValue(itemData.setting);
		}
		if (enumUnderlyingType == typeof(ushort))
		{
			return () => (ushort)itemData.property.GetValue(itemData.setting);
		}
		if (enumUnderlyingType == typeof(int))
		{
			return () => (ulong)(int)itemData.property.GetValue(itemData.setting);
		}
		if (enumUnderlyingType == typeof(uint))
		{
			return () => (uint)itemData.property.GetValue(itemData.setting);
		}
		if (enumUnderlyingType == typeof(long))
		{
			return () => (ulong)(long)itemData.property.GetValue(itemData.setting);
		}
		if (enumUnderlyingType == typeof(ulong))
		{
			return () => (ulong)itemData.property.GetValue(itemData.setting);
		}
		throw new Exception("Unsupported underlying type");
	}
```

- `private static GetEnumMemberAccessor(Game.UI.Menu.AutomaticSettings+IProxyProperty property, Game.Settings.Setting setting, System.String prefix) : Game.Reflection.DelegateAccessor<Game.UI.Widgets.EnumMember[]>`  

```csharp
private static DelegateAccessor<EnumMember[]> GetEnumMemberAccessor(IProxyProperty property, Setting setting, string prefix)
	{
		SettingsUIDropdownAttribute attribute = property.GetAttribute<SettingsUIDropdownAttribute>();
		if (attribute != null && TryGetAction(setting, attribute.itemsGetterType, attribute.itemsGetterMethod, out Func<EnumMember[]> action))
		{
			return new DelegateAccessor<EnumMember[]>(action);
		}
		prefix = (string.IsNullOrEmpty(prefix) ? "Options" : ("Options." + prefix));
		return new DelegateAccessor<EnumMember[]>(() => GetEnumValues(property.propertyType, prefix));
	}
```

- `private static GetEnumSetter(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : System.Action<System.UInt64>`  

```csharp
private static Action<ulong> GetEnumSetter(SettingItemData itemData)
	{
		Type propertyType = itemData.property.propertyType;
		if (!propertyType.IsEnum)
		{
			throw new ArgumentException("Property type is not an enum");
		}
		Type enumUnderlyingType = propertyType.GetEnumUnderlyingType();
		if (enumUnderlyingType == typeof(sbyte))
		{
			return delegate(ulong value)
			{
				itemData.property.SetValue(itemData.setting, (sbyte)value);
			};
		}
		if (enumUnderlyingType == typeof(byte))
		{
			return delegate(ulong value)
			{
				itemData.property.SetValue(itemData.setting, (byte)value);
			};
		}
		if (enumUnderlyingType == typeof(short))
		{
			return delegate(ulong value)
			{
				itemData.property.SetValue(itemData.setting, (short)value);
			};
		}
		if (enumUnderlyingType == typeof(ushort))
		{
			return delegate(ulong value)
			{
				itemData.property.SetValue(itemData.setting, (ushort)value);
			};
		}
		if (enumUnderlyingType == typeof(int))
		{
			return delegate(ulong value)
			{
				itemData.property.SetValue(itemData.setting, (int)value);
			};
		}
		if (enumUnderlyingType == typeof(uint))
		{
			return delegate(ulong value)
			{
				itemData.property.SetValue(itemData.setting, (uint)value);
			};
		}
		if (enumUnderlyingType == typeof(long))
		{
			return delegate(ulong value)
			{
				itemData.property.SetValue(itemData.setting, (long)value);
			};
		}
		if (enumUnderlyingType == typeof(ulong))
		{
			return delegate(ulong value)
			{
				itemData.property.SetValue(itemData.setting, value);
			};
		}
		throw new Exception("Unsupported underlying type");
	}
```

- `public static GetEnumValues(System.Type enumType, System.String prefix) : Game.UI.Widgets.EnumMember[]`  

```csharp
public static EnumMember[] GetEnumValues(Type enumType, string prefix)
	{
		if (!enumType.IsEnum)
		{
			throw new ArgumentException("Type is not an enum");
		}
		Type enumUnderlyingType = enumType.GetEnumUnderlyingType();
		List<EnumMember> list = new List<EnumMember>();
		string[] names = Enum.GetNames(enumType);
		Array values = Enum.GetValues(enumType);
		for (int i = 0; i < names.Length; i++)
		{
			ulong value;
			if (enumUnderlyingType == typeof(sbyte))
			{
				value = (ulong)(sbyte)values.GetValue(i);
			}
			else if (enumUnderlyingType == typeof(byte))
			{
				value = (byte)values.GetValue(i);
			}
			else if (enumUnderlyingType == typeof(short))
			{
				value = (ulong)(short)values.GetValue(i);
			}
			else if (enumUnderlyingType == typeof(ushort))
			{
				value = (ushort)values.GetValue(i);
			}
			else if (enumUnderlyingType == typeof(int))
			{
				value = (ulong)(int)values.GetValue(i);
			}
			else if (enumUnderlyingType == typeof(uint))
			{
				value = (uint)values.GetValue(i);
			}
			else if (enumUnderlyingType == typeof(long))
			{
				value = (ulong)(long)values.GetValue(i);
			}
			else
			{
				if (!(enumUnderlyingType == typeof(ulong)))
				{
					throw new Exception("Unsupported underlying type");
				}
				value = (ulong)values.GetValue(i);
			}
			if (enumType.GetField(names[i]).GetCustomAttributes(typeof(SettingsUIHiddenAttribute), inherit: false).Length == 0)
			{
				string text = enumType.Name.ToUpperInvariant() + "[" + names[i] + "]";
				if (!string.IsNullOrEmpty(prefix))
				{
					text = prefix + "." + text;
				}
				list.Add(new EnumMember(value, text));
			}
		}
		return list.ToArray();
	}
```

- `private static GetSections(Game.UI.Menu.AutomaticSettings+IProxyProperty property) : System.Collections.Generic.Dictionary<System.String, Game.UI.Menu.AutomaticSettings+SectionInfo>`  

```csharp
private static Dictionary<string, SectionInfo> GetSections(IProxyProperty property)
	{
		Dictionary<string, SectionInfo> dictionary = new Dictionary<string, SectionInfo>();
		foreach (SettingsUISectionAttribute attribute in property.GetAttributes<SettingsUISectionAttribute>())
		{
			dictionary[attribute.tab] = new SectionInfo
			{
				m_Tab = attribute.tab,
				m_SimpleGroup = attribute.simpleGroup,
				m_AdvancedGroup = attribute.advancedGroup
			};
		}
		if (dictionary.Count != 0)
		{
			return dictionary;
		}
		foreach (SettingsUISectionAttribute attribute2 in ReflectionUtils.GetAttributes<SettingsUISectionAttribute>(property.declaringType.GetCustomAttributes(inherit: false)))
		{
			dictionary[attribute2.tab] = new SectionInfo
			{
				m_Tab = attribute2.tab,
				m_SimpleGroup = attribute2.simpleGroup,
				m_AdvancedGroup = attribute2.advancedGroup
			};
		}
		if (dictionary.Count != 0)
		{
			return dictionary;
		}
		dictionary["General"] = new SectionInfo
		{
			m_Tab = "General",
			m_SimpleGroup = string.Empty,
			m_AdvancedGroup = string.Empty
		};
		return dictionary;
	}
```

- `private static GetSetterActionGeneric<T>(Game.UI.Menu.AutomaticSettings+SettingItemData itemData) : System.Action<System.UInt64>`  

```csharp
private static System.Action<System.UInt64> GetSetterActionGeneric<T>(Game.UI.Menu.AutomaticSettings+SettingItemData itemData);
```

- `private static GetTabWarningGetters(Game.Settings.Setting setting) : System.Collections.Generic.Dictionary<System.String, System.Func<System.Boolean>>`  

```csharp
private static Dictionary<string, Func<bool>> GetTabWarningGetters(Setting setting)
	{
		Dictionary<string, Func<bool>> dictionary = new Dictionary<string, Func<bool>>();
		foreach (SettingsUITabWarningAttribute attribute in ReflectionUtils.GetAttributes<SettingsUITabWarningAttribute>(setting.GetType().GetCustomAttributes(inherit: false)))
		{
			if (!string.IsNullOrEmpty(attribute.tab) && TryGetAction(setting, attribute.checkType, attribute.checkMethod, out Func<bool> action))
			{
				dictionary.TryAdd(attribute.tab, action);
			}
		}
		return dictionary;
	}
```

- `private static GetWarningGetter(Game.Settings.Setting setting) : System.Func<System.Boolean>`  

```csharp
private static Func<bool> GetWarningGetter(Setting setting)
	{
		SettingsUIPageWarningAttribute attribute = ReflectionUtils.GetAttribute<SettingsUIPageWarningAttribute>(setting.GetType().GetCustomAttributes(inherit: false));
		if (attribute != null && TryGetAction(setting, attribute.checkType, attribute.checkMethod, out Func<bool> action))
		{
			return action;
		}
		return null;
	}
```

- `public static GetWidgetType(Game.UI.Menu.AutomaticSettings+IProxyProperty property) : Game.UI.Menu.AutomaticSettings+WidgetType`  

```csharp
public static WidgetType GetWidgetType(IProxyProperty property)
	{
		if (property.propertyType == typeof(bool))
		{
			if (property.HasAttribute<SettingsUIButtonAttribute>())
			{
				if (property.HasAttribute<SettingsUIConfirmationAttribute>())
				{
					return WidgetType.BoolButtonWithConfirmation;
				}
				return WidgetType.BoolButton;
			}
			if (property.canRead && property.canWrite)
			{
				return WidgetType.BoolToggle;
			}
			if (!property.canRead && property.canWrite)
			{
				return WidgetType.BoolButton;
			}
			return WidgetType.None;
		}
		if (property.propertyType == typeof(int))
		{
			if (property.HasAttribute<SettingsUIDropdownAttribute>())
			{
				return WidgetType.IntDropdown;
			}
			if (property.HasAttribute<SettingsUISliderAttribute>())
			{
				return WidgetType.IntSlider;
			}
			return WidgetType.None;
		}
		if (property.propertyType == typeof(float))
		{
			if (property.HasAttribute<SettingsUISliderAttribute>())
			{
				return WidgetType.FloatSlider;
			}
			return WidgetType.None;
		}
		if (property.propertyType == typeof(string))
		{
			if (property.canRead && property.canWrite)
			{
				if (property.HasAttribute<SettingsUITextInputAttribute>())
				{
					return WidgetType.StringTextInput;
				}
				if (property.HasAttribute<SettingsUIDropdownAttribute>())
				{
					return WidgetType.StringDropdown;
				}
				if (property.HasAttribute<SettingsUIDirectoryPickerAttribute>())
				{
					return WidgetType.DirectoryPicker;
				}
				return WidgetType.None;
			}
			if (property.canRead && !property.canWrite)
			{
				if (property.HasAttribute<SettingsUIMultilineTextAttribute>())
				{
					return WidgetType.MultilineText;
				}
				return WidgetType.StringField;
			}
			return WidgetType.None;
		}
		if (property.propertyType == typeof(LocalizedString))
		{
			if (property.canRead && !property.canWrite)
			{
				return WidgetType.LocalizedStringField;
			}
			return WidgetType.None;
		}
		if (property.propertyType == typeof(ProxyBinding))
		{
			return WidgetType.KeyBinding;
		}
		if (property.propertyType.IsEnum)
		{
			if (property.HasAttribute<SettingsUIDropdownAttribute>())
			{
				return WidgetType.AdvancedEnumDropdown;
			}
			return WidgetType.EnumDropdown;
		}
		if (property.HasAttribute<SettingsUIDropdownAttribute>())
		{
			return WidgetType.CustomDropdown;
		}
		return WidgetType.None;
	}
```

- `private static IsDeveloperOnly(Game.UI.Menu.AutomaticSettings+IProxyProperty property) : System.Boolean`  

```csharp
private static bool IsDeveloperOnly(IProxyProperty property)
	{
		if (property.GetAttribute<SettingsUIDeveloperAttribute>() != null && !GameManager.instance.configuration.developerMode)
		{
			return true;
		}
		return false;
	}
```

- `private static IsHidden(Game.UI.Menu.AutomaticSettings+IProxyProperty property) : System.Boolean`  

```csharp
private static bool IsHidden(IProxyProperty property)
	{
		if (property.GetAttribute<SettingsUIHiddenAttribute>() != null)
		{
			return true;
		}
		return false;
	}
```

- `private static IsShowGroupName(Game.Settings.Setting setting, System.Boolean& showAll, System.Collections.ObjectModel.ReadOnlyCollection`1[[System.String, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& groups) : System.Boolean`  

```csharp
private static bool IsShowGroupName(Setting setting, out bool showAll, out ReadOnlyCollection<string> groups)
	{
		SettingsUIShowGroupNameAttribute attribute = ReflectionUtils.GetAttribute<SettingsUIShowGroupNameAttribute>(setting.GetType().GetCustomAttributes(inherit: false));
		if (attribute != null)
		{
			showAll = attribute.showAll;
			groups = attribute.groups;
			return true;
		}
		showAll = false;
		groups = null;
		return false;
	}
```

- `private static IsSupportedOnPlatform(Game.UI.Menu.AutomaticSettings+IProxyProperty property) : System.Boolean`  

```csharp
private static bool IsSupportedOnPlatform(IProxyProperty property)
	{
		return property.GetAttribute<SettingsUIPlatformAttribute>()?.IsPlatformSet(Application.platform) ?? true;
	}
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

