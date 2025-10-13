# Game.Modding.ModSetting

**Assembly:** `Game`  
**Namespace:** `Game.Modding`  

**Type:** class abstract public  

**Base:** `Game.Settings.Setting`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

## Code

```csharp
public abstract class ModSetting : Game.Settings.Setting, System.IEquatable<Game.Settings.Setting>
{
    private readonly Game.Modding.IMod <mod>k__BackingField;
    private readonly System.String <id>k__BackingField;
    private readonly System.String <name>k__BackingField;
    private System.Boolean <keyBindingRegistered>k__BackingField;
    private System.Reflection.PropertyInfo[] m_keyBindingProperties;
    private static readonly System.Collections.Generic.Dictionary<System.String, Game.Modding.ModSetting> <instances>k__BackingField;

    internal static System.Collections.Generic.Dictionary<System.String, Game.Modding.ModSetting> instances { internal get; }
    internal Game.Modding.IMod mod { internal get; }
    private System.Boolean builtIn { private get; }
    public System.String id { get; }
    public System.String name { get; }
    public System.Boolean keyBindingRegistered { get; private set; }
    private System.Reflection.PropertyInfo[] keyBindingProperties { private get; }

    public ModSetting(Game.Modding.IMod mod);

    private Game.Input.ProxyBinding <ApplyKeyBindings>b__30_0(System.Reflection.PropertyInfo p);
    private System.Void ApplyKeyBindings();
    private Game.Input.ProxyBinding CreateBinding(Game.Input.InputManager+DeviceType device, System.String actionName, Game.Input.ActionType type, Game.Input.ActionComponent component, System.String control, System.Collections.Generic.IEnumerable<System.String> modifierControls);
    private Game.Input.ProxyBinding CreateMimicBinding(Game.Input.InputManager+DeviceType device, System.String actionName, Game.Input.ActionType type, Game.Input.ActionComponent component, Game.Input.ProxyBinding sourceBinding);
    private Game.Input.ProxyBinding GenerateBinding(System.Reflection.PropertyInfo property);
    public Game.Input.ProxyAction GetAction(System.String name);
    public System.Collections.Generic.IEnumerable<Game.Input.ProxyAction> GetActions();
    public System.String GetBindingKeyHintLocaleID(System.String actionName);
    public System.String GetBindingKeyLocaleID(System.String actionName);
    public System.String GetBindingKeyLocaleID(System.String actionName, Game.Input.AxisComponent component);
    public System.String GetBindingKeyLocaleID(System.String actionName, Game.Input.Vector2Component component);
    private System.String GetBindingKeyLocaleID(System.String actionName, System.String componentName);
    public System.String GetBindingMapLocaleID();
    public System.String GetEnumValueLocaleID<T>(T value);
    public System.String GetOptionDescLocaleID(System.String optionName);
    public System.String GetOptionFormatLocaleID(System.String optionName);
    public System.String GetOptionGroupLocaleID(System.String groupName);
    public System.String GetOptionLabelLocaleID(System.String optionName);
    public System.String GetOptionTabLocaleID(System.String tabName);
    public System.String GetOptionWarningLocaleID(System.String optionName);
    public System.String GetSettingsLocaleID();
    private System.Void InitializeKeyBindings();
    public System.Void RegisterInOptionsUI();
    public System.Void RegisterKeyBindings();
    protected System.Void ResetKeyBindings();
    private System.Boolean TryGetSourceBindingForMimic(System.Reflection.PropertyInfo property, Game.Input.InputManager+DeviceType device, Game.Input.ActionComponent component, Game.Input.ProxyBinding& sourceBinding);
    public System.Void UnregisterInOptionsUI();
}
```


## Fields

- `private readonly Game.Modding.IMod <mod>k__BackingField`  

```csharp
private readonly Game.Modding.IMod <mod>k__BackingField;
```

- `private readonly System.String <id>k__BackingField`  

```csharp
private readonly System.String <id>k__BackingField;
```

- `private readonly System.String <name>k__BackingField`  

```csharp
private readonly System.String <name>k__BackingField;
```

- `private System.Boolean <keyBindingRegistered>k__BackingField`  

```csharp
private System.Boolean <keyBindingRegistered>k__BackingField;
```

- `private System.Reflection.PropertyInfo[] m_keyBindingProperties`  

```csharp
private System.Reflection.PropertyInfo[] m_keyBindingProperties;
```

- `private static readonly System.Collections.Generic.Dictionary<System.String, Game.Modding.ModSetting> <instances>k__BackingField`  

```csharp
private static readonly System.Collections.Generic.Dictionary<System.String, Game.Modding.ModSetting> <instances>k__BackingField;
```


## Properties

- `internal static System.Collections.Generic.Dictionary<System.String, Game.Modding.ModSetting> instances { internal get }`  

```csharp
internal static System.Collections.Generic.Dictionary<System.String, Game.Modding.ModSetting> instances { internal get; }
```

- `internal Game.Modding.IMod mod { internal get }`  

```csharp
internal Game.Modding.IMod mod { internal get; }
```

- `private System.Boolean builtIn { private get }`  

```csharp
private System.Boolean builtIn { private get; }
```

- `public System.String id { get }`  

```csharp
public System.String id { get; }
```

- `public System.String name { get }`  

```csharp
public System.String name { get; }
```

- `public System.Boolean keyBindingRegistered { get; private set }`  

```csharp
public System.Boolean keyBindingRegistered { get; private set; }
```

- `private System.Reflection.PropertyInfo[] keyBindingProperties { private get }`  

```csharp
private System.Reflection.PropertyInfo[] keyBindingProperties { private get; }
```


## Constructors

- `public ModSetting(Game.Modding.IMod mod)`  

```csharp
public ModSetting(IMod mod)
	{
		Type type = mod.GetType();
		id = type.Assembly.GetName().Name + "." + type.Namespace + "." + type.Name;
		name = GetType().Name;
		this.mod = mod;
		instances[id] = this;
		InitializeKeyBindings();
	}
```


## Methods

- `private <ApplyKeyBindings>b__30_0(System.Reflection.PropertyInfo p) : Game.Input.ProxyBinding`  

```csharp
private Game.Input.ProxyBinding <ApplyKeyBindings>b__30_0(System.Reflection.PropertyInfo p);
```

- `private ApplyKeyBindings() : System.Void`  

```csharp
[AfterDecode]
	protected internal void ApplyKeyBindings()
	{
		if (keyBindingRegistered)
		{
			ProxyBinding[] newBindings = keyBindingProperties.Select((PropertyInfo p) => (ProxyBinding)p.GetValue(this)).ToArray();
			InputManager.instance.SetBindings(newBindings, out var _);
		}
	}
```

- `private CreateBinding(Game.Input.InputManager+DeviceType device, System.String actionName, Game.Input.ActionType type, Game.Input.ActionComponent component, System.String control, System.Collections.Generic.IEnumerable<System.String> modifierControls) : Game.Input.ProxyBinding`  

```csharp
private ProxyBinding CreateBinding(InputManager.DeviceType device, string actionName, ActionType type, ActionComponent component, string control, IEnumerable<string> modifierControls)
	{
		if (!InputManager.TryGetCompositeData(type, out var data) || !data.TryGetData(component, out var componentData))
		{
			componentData = InputManager.CompositeComponentData.defaultData;
		}
		ProxyModifier[] array = modifierControls.Select((string modifierControl) => new ProxyModifier
		{
			m_Component = component,
			m_Name = componentData.m_ModifierName,
			m_Path = modifierControl
		}).ToArray();
		ProxyBinding result = new ProxyBinding(id, actionName, component, componentData.m_BindingName, new CompositeInstance(device.ToString()));
		result.device = device;
		result.path = control;
		result.originalPath = control;
		result.modifiers = array;
		result.originalModifiers = array;
		return result;
	}
```

- `private CreateMimicBinding(Game.Input.InputManager+DeviceType device, System.String actionName, Game.Input.ActionType type, Game.Input.ActionComponent component, Game.Input.ProxyBinding sourceBinding) : Game.Input.ProxyBinding`  

```csharp
private ProxyBinding CreateMimicBinding(InputManager.DeviceType device, string actionName, ActionType type, ActionComponent component, ProxyBinding sourceBinding)
	{
		if (!InputManager.TryGetCompositeData(type, out var data) || !data.TryGetData(component, out var data2))
		{
			data2 = InputManager.CompositeComponentData.defaultData;
		}
		ProxyBinding result = new ProxyBinding(id, actionName, component, data2.m_BindingName, new CompositeInstance(device.ToString()));
		result.device = device;
		result.path = sourceBinding.path;
		result.originalPath = sourceBinding.originalPath;
		result.modifiers = sourceBinding.modifiers;
		result.originalModifiers = sourceBinding.modifiers;
		return result;
	}
```

- `private GenerateBinding(System.Reflection.PropertyInfo property) : Game.Input.ProxyBinding`  

```csharp
private ProxyBinding GenerateBinding(PropertyInfo property)
	{
		string actionName;
		InputManager.DeviceType device;
		ActionType type;
		ActionComponent component;
		string control;
		IEnumerable<string> modifierControls;
		SettingsUIGamepadBindingAttribute attribute2;
		SettingsUIMouseBindingAttribute attribute3;
		if (((MemberInfo)property).TryGetAttribute(out SettingsUIKeyboardBindingAttribute attribute, inherit: false))
		{
			actionName = attribute.actionName ?? property.Name;
			device = attribute.device;
			type = attribute.type;
			component = attribute.component;
			control = attribute.control;
			modifierControls = attribute.modifierControls;
		}
		else if (((MemberInfo)property).TryGetAttribute(out attribute2, inherit: false))
		{
			actionName = attribute2.actionName ?? property.Name;
			device = attribute2.device;
			type = attribute2.type;
			component = attribute2.component;
			control = attribute2.control;
			modifierControls = attribute2.modifierControls;
		}
		else if (((MemberInfo)property).TryGetAttribute(out attribute3, inherit: false))
		{
			actionName = attribute3.actionName ?? property.Name;
			device = attribute3.device;
			type = attribute3.type;
			component = attribute3.component;
			control = attribute3.control;
			modifierControls = attribute3.modifierControls;
		}
		else
		{
			actionName = property.Name;
			device = InputManager.DeviceType.Keyboard;
			type = ActionType.Button;
			component = ActionComponent.Press;
			control = string.Empty;
			modifierControls = Array.Empty<string>();
		}
		if (!TryGetSourceBindingForMimic(property, device, component, out var sourceBinding))
		{
			return CreateBinding(device, actionName, type, component, control, modifierControls);
		}
		return CreateMimicBinding(device, actionName, type, component, sourceBinding);
	}
```

- `public GetAction(System.String name) : Game.Input.ProxyAction`  

```csharp
public ProxyAction GetAction(string name)
	{
		return InputManager.instance.FindAction(id, name);
	}
```

- `public GetActions() : System.Collections.Generic.IEnumerable<Game.Input.ProxyAction>`  

```csharp
public IEnumerable<ProxyAction> GetActions()
	{
		if (!InputManager.instance.TryFindActionMap(id, out var map))
		{
			return Array.Empty<ProxyAction>();
		}
		return map.actions.Values;
	}
```

- `public GetBindingKeyHintLocaleID(System.String actionName) : System.String`  

```csharp
public string GetBindingKeyHintLocaleID(string actionName)
	{
		return "Common.ACTION[" + id + "/" + actionName + "]";
	}
```

- `public GetBindingKeyLocaleID(System.String actionName) : System.String`  

```csharp
private string GetBindingKeyLocaleID(string actionName, string componentName)
	{
		return "Options.OPTION[" + id + "/" + actionName + "/" + componentName + "]";
	}
```

- `public GetBindingKeyLocaleID(System.String actionName, Game.Input.AxisComponent component) : System.String`  

```csharp
private string GetBindingKeyLocaleID(string actionName, string componentName)
	{
		return "Options.OPTION[" + id + "/" + actionName + "/" + componentName + "]";
	}
```

- `public GetBindingKeyLocaleID(System.String actionName, Game.Input.Vector2Component component) : System.String`  

```csharp
private string GetBindingKeyLocaleID(string actionName, string componentName)
	{
		return "Options.OPTION[" + id + "/" + actionName + "/" + componentName + "]";
	}
```

- `private GetBindingKeyLocaleID(System.String actionName, System.String componentName) : System.String`  

```csharp
private string GetBindingKeyLocaleID(string actionName, string componentName)
	{
		return "Options.OPTION[" + id + "/" + actionName + "/" + componentName + "]";
	}
```

- `public GetBindingMapLocaleID() : System.String`  

```csharp
public string GetBindingMapLocaleID()
	{
		return "Options.INPUT_MAP[" + id + "]";
	}
```

- `public GetEnumValueLocaleID<T>(T value) : System.String`  

```csharp
public System.String GetEnumValueLocaleID<T>(T value);
```

- `public GetOptionDescLocaleID(System.String optionName) : System.String`  

```csharp
public string GetOptionDescLocaleID(string optionName)
	{
		return "Options.OPTION_DESCRIPTION[" + id + "." + name + "." + optionName + "]";
	}
```

- `public GetOptionFormatLocaleID(System.String optionName) : System.String`  

```csharp
public string GetOptionFormatLocaleID(string optionName)
	{
		return "Options.FORMAT[" + id + "." + name + "." + optionName + "]";
	}
```

- `public GetOptionGroupLocaleID(System.String groupName) : System.String`  

```csharp
public string GetOptionGroupLocaleID(string groupName)
	{
		return "Options.GROUP[" + id + "." + groupName + "]";
	}
```

- `public GetOptionLabelLocaleID(System.String optionName) : System.String`  

```csharp
public string GetOptionLabelLocaleID(string optionName)
	{
		return "Options.OPTION[" + id + "." + name + "." + optionName + "]";
	}
```

- `public GetOptionTabLocaleID(System.String tabName) : System.String`  

```csharp
public string GetOptionTabLocaleID(string tabName)
	{
		return "Options.TAB[" + id + "." + tabName + "]";
	}
```

- `public GetOptionWarningLocaleID(System.String optionName) : System.String`  

```csharp
public string GetOptionWarningLocaleID(string optionName)
	{
		return "Options.WARNING[" + id + "." + name + "." + optionName + "]";
	}
```

- `public GetSettingsLocaleID() : System.String`  

```csharp
public string GetSettingsLocaleID()
	{
		return "Options.SECTION[" + id + "]";
	}
```

- `private InitializeKeyBindings() : System.Void`  

```csharp
private void InitializeKeyBindings()
	{
		PropertyInfo[] array = keyBindingProperties;
		foreach (PropertyInfo propertyInfo in array)
		{
			ProxyBinding proxyBinding = GenerateBinding(propertyInfo);
			propertyInfo.SetValue(this, proxyBinding);
		}
	}
```

- `public RegisterInOptionsUI() : System.Void`  

```csharp
public void RegisterInOptionsUI()
	{
		RegisterInOptionsUI(id, addPrefix: true);
	}
```

- `public RegisterKeyBindings() : System.Void`  

```csharp
public void RegisterKeyBindings()
	{
		if (keyBindingRegistered)
		{
			return;
		}
		PropertyInfo[] array = keyBindingProperties;
		Dictionary<string, (ProxyAction.Info, List<PropertyInfo>)> dictionary = new Dictionary<string, (ProxyAction.Info, List<PropertyInfo>)>();
		Dictionary<(string, InputManager.DeviceType), SettingsUIInputActionAttribute> dictionary2 = new Dictionary<(string, InputManager.DeviceType), SettingsUIInputActionAttribute>();
		foreach (SettingsUIInputActionAttribute attribute in ReflectionUtils.GetAttributes<SettingsUIInputActionAttribute>(GetType().GetCustomAttributes(inherit: false)))
		{
			dictionary2.TryAdd((attribute.name, attribute.device), attribute);
		}
		foreach (PropertyInfo propertyInfo in array)
		{
			ProxyBinding binding = (ProxyBinding)propertyInfo.GetValue(this);
			if (!dictionary.TryGetValue(binding.actionName, out var value))
			{
				value = (new ProxyAction.Info
				{
					m_Map = binding.mapName,
					m_Name = binding.actionName,
					m_Type = binding.component.GetActionType(),
					m_Composites = new List<ProxyComposite.Info>()
				}, new List<PropertyInfo>());
			}
			if (binding.component.GetActionType() != value.Item1.m_Type)
			{
				continue;
			}
			value.Item2.Add(propertyInfo);
			ProxyComposite.Info item = value.Item1.m_Composites.FirstOrDefault((ProxyComposite.Info info) => info.m_Device == binding.device);
			if (item.m_Source == null)
			{
				if (!InputManager.TryGetCompositeData(binding.component.GetActionType(), out var data))
				{
					continue;
				}
				CompositeInstance compositeInstance = new CompositeInstance(data.m_TypeName)
				{
					builtIn = false
				};
				if (dictionary2.TryGetValue((binding.actionName, binding.device), out var value2))
				{
					compositeInstance.allowModifiers = value2.allowModifiers;
					compositeInstance.developerOnly = value2.developerOnly;
					compositeInstance.mode = value2.mode;
					compositeInstance.usages = value2.usages;
					compositeInstance.interactions.AddRange(value2.interactions.Select(NameAndParameters.Parse));
					compositeInstance.processors.AddRange(value2.processors.Select(NameAndParameters.Parse));
				}
				else
				{
					compositeInstance.allowModifiers = true;
				}
				item = new ProxyComposite.Info
				{
					m_Device = binding.device,
					m_Source = compositeInstance,
					m_Bindings = new List<ProxyBinding>()
				};
				value.Item1.m_Composites.Add(item);
			}
			item.m_Bindings.Add(binding);
			dictionary[binding.actionName] = value;
		}
		ProxyAction.Info[] actionsToAdd = dictionary.Values.Select<(ProxyAction.Info, List<PropertyInfo>), ProxyAction.Info>(((ProxyAction.Info actionInfo, List<PropertyInfo> properties) d) => d.actionInfo).ToArray();
		InputManager.instance.AddActions(actionsToAdd);
		PropertyInfo[] array2 = array;
		foreach (PropertyInfo property in array2)
		{
			ProxyBinding binding2 = (ProxyBinding)property.GetValue(this);
			binding2.CreateWatcher(delegate(ProxyBinding newBinding)
			{
				property.SetValue(this, newBinding);
			});
			if (TryGetSourceBindingForMimic(property, binding2.device, binding2.component, out var sourceBinding))
			{
				sourceBinding.CreateWatcher(delegate(ProxyBinding newSourceBinding)
				{
					ProxyBinding newBinding = binding2.Copy();
					newBinding.path = newSourceBinding.path;
					newBinding.modifiers = newSourceBinding.modifiers;
					InputManager.instance.SetBinding(newBinding, out var _);
				});
			}
		}
		keyBindingRegistered = true;
	}
```

- `protected ResetKeyBindings() : System.Void`  

```csharp
protected void ResetKeyBindings()
	{
		if (keyBindingRegistered)
		{
			ProxyBinding[] newBindings = keyBindingProperties.Select(GenerateBinding).ToArray();
			InputManager.instance.SetBindings(newBindings, out var _);
			ApplyAndSave();
		}
	}
```

- `private TryGetSourceBindingForMimic(System.Reflection.PropertyInfo property, Game.Input.InputManager+DeviceType device, Game.Input.ActionComponent component, Game.Input.ProxyBinding& sourceBinding) : System.Boolean`  

```csharp
private bool TryGetSourceBindingForMimic(PropertyInfo property, InputManager.DeviceType device, ActionComponent component, out ProxyBinding sourceBinding)
	{
		sourceBinding = default(ProxyBinding);
		if (!((MemberInfo)property).TryGetAttribute(out SettingsUIBindingMimicAttribute attribute, inherit: false))
		{
			return false;
		}
		if (!InputManager.instance.TryFindAction(attribute.map, attribute.action, out var action) || !action.isBuiltIn)
		{
			return false;
		}
		if (!action.TryGetComposite(device, out var composite))
		{
			return false;
		}
		if (!composite.TryGetBinding(component, out sourceBinding))
		{
			return false;
		}
		return true;
	}
```

- `public UnregisterInOptionsUI() : System.Void`  

```csharp
public void UnregisterInOptionsUI()
	{
		Setting.UnregisterInOptionsUI(id);
	}
```


## Nested types

- `Game.Modding.ModSetting+<>c`  
- `Game.Modding.ModSetting+<>c__DisplayClass27_0`  
- `Game.Modding.ModSetting+<>c__DisplayClass27_1`  
- `Game.Modding.ModSetting+<>c__DisplayClass27_2`  
- `Game.Modding.ModSetting+<>c__DisplayClass28_0`  

