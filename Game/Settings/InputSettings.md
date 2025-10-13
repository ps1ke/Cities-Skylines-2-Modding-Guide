# Game.Settings.InputSettings

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.Setting`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

**Attributes:** `FileLocation`, `SettingsUITabOrder`, `SettingsUIGroupOrder`, `SettingsUITabWarning`, `SettingsUITabWarning`, `SettingsUITabWarning`  

## Code

```csharp
public class InputSettings : Game.Settings.Setting, System.IEquatable<Game.Settings.Setting>
{
    private System.Boolean <elevationDraggingEnabled>k__BackingField;
    private System.Single <mouseScrollSensitivity>k__BackingField;
    private System.Single <keyboardMoveSensitivity>k__BackingField;
    private System.Single <keyboardRotateSensitivity>k__BackingField;
    private System.Single <keyboardZoomSensitivity>k__BackingField;
    private System.Single <mouseMoveSensitivity>k__BackingField;
    private System.Single <mouseRotateSensitivity>k__BackingField;
    private System.Single <mouseZoomSensitivity>k__BackingField;
    private System.Boolean <mouseInvertX>k__BackingField;
    private System.Boolean <mouseInvertY>k__BackingField;
    private System.Single <gamepadMoveSensitivity>k__BackingField;
    private System.Single <gamepadRotateSensitivity>k__BackingField;
    private System.Single <gamepadZoomSensitivity>k__BackingField;
    private System.Boolean <gamepadInvertX>k__BackingField;
    private System.Boolean <gamepadInvertY>k__BackingField;
    public static const System.String kName;
    public static const System.String kMiscTab;

    public System.Boolean elevationDraggingEnabled { get; set; }
    public System.Single mouseScrollSensitivity { get; set; }
    public System.Single finalScrollSensitivity { get; }
    public System.Single keyboardMoveSensitivity { get; set; }
    public System.Single keyboardRotateSensitivity { get; set; }
    public System.Single keyboardZoomSensitivity { get; set; }
    public System.Single mouseMoveSensitivity { get; set; }
    public System.Single mouseRotateSensitivity { get; set; }
    public System.Single mouseZoomSensitivity { get; set; }
    public System.Boolean mouseInvertX { get; set; }
    public System.Boolean mouseInvertY { get; set; }
    public System.Single gamepadMoveSensitivity { get; set; }
    public System.Single gamepadRotateSensitivity { get; set; }
    public System.Single gamepadZoomSensitivity { get; set; }
    public System.Boolean gamepadInvertX { get; set; }
    public System.Boolean gamepadInvertY { get; set; }
    private System.Boolean isKeyboardConflict { private get; }
    private System.Boolean isMouseConflict { private get; }
    private System.Boolean isGamepadConflict { private get; }

    public InputSettings();

    public virtual Game.UI.Menu.AutomaticSettings+SettingPageData GetPageData(System.String id, System.Boolean addPrefix);
    private System.Void GetPageSection(Game.UI.Menu.AutomaticSettings+SettingPageData pageData, Game.Input.InputManager+DeviceType device);
    private System.String[] GetTabOrder();
    public virtual System.Void SetDefaults();
    private System.Void SetDefaultsForDevice(Game.Input.InputManager+DeviceType device);
}
```


## Fields

- `private System.Boolean <elevationDraggingEnabled>k__BackingField`  

```csharp
private System.Boolean <elevationDraggingEnabled>k__BackingField;
```

- `private System.Single <mouseScrollSensitivity>k__BackingField`  

```csharp
private System.Single <mouseScrollSensitivity>k__BackingField;
```

- `private System.Single <keyboardMoveSensitivity>k__BackingField`  

```csharp
private System.Single <keyboardMoveSensitivity>k__BackingField;
```

- `private System.Single <keyboardRotateSensitivity>k__BackingField`  

```csharp
private System.Single <keyboardRotateSensitivity>k__BackingField;
```

- `private System.Single <keyboardZoomSensitivity>k__BackingField`  

```csharp
private System.Single <keyboardZoomSensitivity>k__BackingField;
```

- `private System.Single <mouseMoveSensitivity>k__BackingField`  

```csharp
private System.Single <mouseMoveSensitivity>k__BackingField;
```

- `private System.Single <mouseRotateSensitivity>k__BackingField`  

```csharp
private System.Single <mouseRotateSensitivity>k__BackingField;
```

- `private System.Single <mouseZoomSensitivity>k__BackingField`  

```csharp
private System.Single <mouseZoomSensitivity>k__BackingField;
```

- `private System.Boolean <mouseInvertX>k__BackingField`  

```csharp
private System.Boolean <mouseInvertX>k__BackingField;
```

- `private System.Boolean <mouseInvertY>k__BackingField`  

```csharp
private System.Boolean <mouseInvertY>k__BackingField;
```

- `private System.Single <gamepadMoveSensitivity>k__BackingField`  

```csharp
private System.Single <gamepadMoveSensitivity>k__BackingField;
```

- `private System.Single <gamepadRotateSensitivity>k__BackingField`  

```csharp
private System.Single <gamepadRotateSensitivity>k__BackingField;
```

- `private System.Single <gamepadZoomSensitivity>k__BackingField`  

```csharp
private System.Single <gamepadZoomSensitivity>k__BackingField;
```

- `private System.Boolean <gamepadInvertX>k__BackingField`  

```csharp
private System.Boolean <gamepadInvertX>k__BackingField;
```

- `private System.Boolean <gamepadInvertY>k__BackingField`  

```csharp
private System.Boolean <gamepadInvertY>k__BackingField;
```

- `public static const System.String kName`  

```csharp
public static const System.String kName;
```

- `public static const System.String kMiscTab`  

```csharp
public static const System.String kMiscTab;
```


## Properties

- `public System.Boolean elevationDraggingEnabled { get; set }`  

```csharp
public System.Boolean elevationDraggingEnabled { get; set; }
```

- `public System.Single mouseScrollSensitivity { get; set }`  

```csharp
public System.Single mouseScrollSensitivity { get; set; }
```

- `public System.Single finalScrollSensitivity { get }`  

```csharp
public System.Single finalScrollSensitivity { get; }
```

- `public System.Single keyboardMoveSensitivity { get; set }`  

```csharp
public System.Single keyboardMoveSensitivity { get; set; }
```

- `public System.Single keyboardRotateSensitivity { get; set }`  

```csharp
public System.Single keyboardRotateSensitivity { get; set; }
```

- `public System.Single keyboardZoomSensitivity { get; set }`  

```csharp
public System.Single keyboardZoomSensitivity { get; set; }
```

- `public System.Single mouseMoveSensitivity { get; set }`  

```csharp
public System.Single mouseMoveSensitivity { get; set; }
```

- `public System.Single mouseRotateSensitivity { get; set }`  

```csharp
public System.Single mouseRotateSensitivity { get; set; }
```

- `public System.Single mouseZoomSensitivity { get; set }`  

```csharp
public System.Single mouseZoomSensitivity { get; set; }
```

- `public System.Boolean mouseInvertX { get; set }`  

```csharp
public System.Boolean mouseInvertX { get; set; }
```

- `public System.Boolean mouseInvertY { get; set }`  

```csharp
public System.Boolean mouseInvertY { get; set; }
```

- `public System.Single gamepadMoveSensitivity { get; set }`  

```csharp
public System.Single gamepadMoveSensitivity { get; set; }
```

- `public System.Single gamepadRotateSensitivity { get; set }`  

```csharp
public System.Single gamepadRotateSensitivity { get; set; }
```

- `public System.Single gamepadZoomSensitivity { get; set }`  

```csharp
public System.Single gamepadZoomSensitivity { get; set; }
```

- `public System.Boolean gamepadInvertX { get; set }`  

```csharp
public System.Boolean gamepadInvertX { get; set; }
```

- `public System.Boolean gamepadInvertY { get; set }`  

```csharp
public System.Boolean gamepadInvertY { get; set; }
```

- `private System.Boolean isKeyboardConflict { private get }`  

```csharp
private System.Boolean isKeyboardConflict { private get; }
```

- `private System.Boolean isMouseConflict { private get }`  

```csharp
private System.Boolean isMouseConflict { private get; }
```

- `private System.Boolean isGamepadConflict { private get }`  

```csharp
private System.Boolean isGamepadConflict { private get; }
```


## Constructors

- `public InputSettings()`  

```csharp
public InputSettings()
	{
		SetDefaults();
	}
```


## Methods

- `public virtual GetPageData(System.String id, System.Boolean addPrefix) : Game.UI.Menu.AutomaticSettings+SettingPageData`  

```csharp
public override AutomaticSettings.SettingPageData GetPageData(string id, bool addPrefix)
	{
		AutomaticSettings.SettingPageData pageData = base.GetPageData(id, addPrefix);
		if (InputSystem.devices.Count != 0)
		{
			if (InputSystem.devices.Any((InputDevice d) => d.added && d is Keyboard))
			{
				GetPageSection(pageData, Game.Input.InputManager.DeviceType.Keyboard);
			}
			if (InputSystem.devices.Any((InputDevice d) => d.added && d is Mouse))
			{
				GetPageSection(pageData, Game.Input.InputManager.DeviceType.Mouse);
			}
			if (InputSystem.devices.Any((InputDevice d) => d.added && d is Gamepad))
			{
				GetPageSection(pageData, Game.Input.InputManager.DeviceType.Gamepad);
			}
		}
		return pageData;
	}
```

- `private GetPageSection(Game.UI.Menu.AutomaticSettings+SettingPageData pageData, Game.Input.InputManager+DeviceType device) : System.Void`  

```csharp
private void GetPageSection(AutomaticSettings.SettingPageData pageData, Game.Input.InputManager.DeviceType device)
	{
		AutomaticSettings.ManualProperty property = new AutomaticSettings.ManualProperty(typeof(InputSettings), typeof(bool), "resetButton")
		{
			canRead = false,
			canWrite = true,
			attributes = 
			{
				(Attribute)new SettingsUIButtonAttribute(),
				(Attribute)new SettingsUIPathAttribute(string.Format("{0}.{1}.resetbutton", "InputSettings", device)),
				(Attribute)new SettingsUIButtonGroupAttribute(string.Format("{0}.{1}.resetbutton_Group", "InputSettings", device)),
				(Attribute)new SettingsUIConfirmationAttribute(string.Format("{0}.{1}.resetbutton", "InputSettings", device)),
				(Attribute)new SettingsUIDisplayNameAttribute(string.Format("{0}.{1}.resetbutton", "InputSettings", device))
			},
			setter = delegate
			{
				Game.Input.InputManager.instance.ResetGroupBindings(device);
				SetDefaultsForDevice(device);
				ApplyAndSave();
			}
		};
		AutomaticSettings.SettingItemData item = new AutomaticSettings.SettingItemData(AutomaticSettings.WidgetType.BoolButtonWithConfirmation, this, property, pageData.prefix)
		{
			simpleGroup = "General"
		};
		pageData[device.ToString()].AddItem(item);
		pageData.AddGroup("General");
		foreach (ProxyAction action in Game.Input.InputManager.instance.actions)
		{
			foreach (var (_, proxyComposite2) in action.composites)
			{
				if (proxyComposite2.m_Device != device || !action.isBuiltIn || proxyComposite2.isDummy)
				{
					continue;
				}
				ActionComponent key;
				ProxyBinding value;
				if (!proxyComposite2.isHidden)
				{
					foreach (KeyValuePair<ActionComponent, ProxyBinding> binding2 in proxyComposite2.bindings)
					{
						binding2.Deconstruct(out key, out value);
						ProxyBinding binding = value;
						AutomaticSettings.ManualProperty property2 = new AutomaticSettings.ManualProperty(typeof(InputSettings), binding.GetType(), binding.name)
						{
							attributes = { (Attribute)new SettingsUIPathAttribute(string.Format("{0}.{1}.{2}", "InputSettings", device, binding.title)) },
							getter = (object _) => binding
						};
						AutomaticSettings.SettingItemData settingItemData = new AutomaticSettings.SettingItemData(AutomaticSettings.WidgetType.KeyBinding, this, property2, pageData.prefix)
						{
							simpleGroup = binding.GetOptionsGroup()
						};
						pageData[device.ToString()].AddItem(settingItemData);
						pageData.AddGroup(settingItemData.simpleGroup);
						pageData.AddGroupToShowName(settingItemData.simpleGroup);
					}
				}
				foreach (UIBaseInputAction uIAlias in action.m_UIAliases)
				{
					if (!uIAlias.showInOptions)
					{
						continue;
					}
					foreach (UIInputActionPart actionPart in uIAlias.actionParts)
					{
						if ((actionPart.m_Mask & device) == 0)
						{
							continue;
						}
						foreach (KeyValuePair<ActionComponent, ProxyBinding> binding3 in proxyComposite2.bindings)
						{
							binding3.Deconstruct(out key, out value);
							ProxyBinding proxyBinding = value;
							if (actionPart.m_Transform == UIBaseInputAction.Transform.None || (proxyBinding.component.ToTransform() & actionPart.m_Transform) != UIBaseInputAction.Transform.None)
							{
								ProxyBinding aliasBinding = proxyBinding.Copy();
								aliasBinding.alies = uIAlias;
								AutomaticSettings.ManualProperty property3 = new AutomaticSettings.ManualProperty(typeof(InputSettings), aliasBinding.GetType(), aliasBinding.name)
								{
									attributes = { (Attribute)new SettingsUIPathAttribute(string.Format("{0}.{1}.{2}", "InputSettings", device, aliasBinding.title)) },
									getter = (object _) => aliasBinding
								};
								AutomaticSettings.SettingItemData settingItemData2 = new AutomaticSettings.SettingItemData(AutomaticSettings.WidgetType.KeyBinding, this, property3, pageData.prefix)
								{
									simpleGroup = aliasBinding.GetOptionsGroup()
								};
								pageData[device.ToString()].AddItem(settingItemData2);
								pageData.AddGroup(settingItemData2.simpleGroup);
								pageData.AddGroupToShowName(settingItemData2.simpleGroup);
							}
						}
					}
				}
			}
		}
	}
```

- `private GetTabOrder() : System.String[]`  

```csharp
private string[] GetTabOrder()
	{
		if (Game.Input.InputManager.instance.activeControlScheme != Game.Input.InputManager.ControlScheme.Gamepad)
		{
			return new string[4] { "Keyboard", "Mouse", "Gamepad", "Misc" };
		}
		return new string[4] { "Gamepad", "Keyboard", "Mouse", "Misc" };
	}
```

- `public virtual SetDefaults() : System.Void`  

```csharp
public override void SetDefaults()
	{
		elevationDraggingEnabled = false;
		SetDefaultsForDevice(Game.Input.InputManager.DeviceType.Keyboard);
		SetDefaultsForDevice(Game.Input.InputManager.DeviceType.Mouse);
		SetDefaultsForDevice(Game.Input.InputManager.DeviceType.Gamepad);
	}
```

- `private SetDefaultsForDevice(Game.Input.InputManager+DeviceType device) : System.Void`  

```csharp
private void SetDefaultsForDevice(Game.Input.InputManager.DeviceType device)
	{
		switch (device)
		{
		case Game.Input.InputManager.DeviceType.Keyboard:
			keyboardMoveSensitivity = 1f;
			keyboardZoomSensitivity = 1f;
			keyboardRotateSensitivity = 1f;
			break;
		case Game.Input.InputManager.DeviceType.Mouse:
			mouseMoveSensitivity = 1f;
			mouseRotateSensitivity = 1f;
			mouseZoomSensitivity = 1f;
			mouseInvertX = false;
			mouseInvertY = false;
			mouseScrollSensitivity = 1f;
			break;
		case Game.Input.InputManager.DeviceType.Gamepad:
			gamepadMoveSensitivity = 1f;
			gamepadZoomSensitivity = 1f;
			gamepadRotateSensitivity = 1f;
			gamepadInvertX = false;
			gamepadInvertY = false;
			break;
		case Game.Input.InputManager.DeviceType.Keyboard | Game.Input.InputManager.DeviceType.Mouse:
			break;
		}
	}
```


## Nested types

- `Game.Settings.InputSettings+<>c`  
- `Game.Settings.InputSettings+<>c__DisplayClass75_0`  
- `Game.Settings.InputSettings+<>c__DisplayClass75_1`  
- `Game.Settings.InputSettings+<>c__DisplayClass75_2`  

