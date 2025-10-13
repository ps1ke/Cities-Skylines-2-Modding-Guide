# Game.UI.InputHintBindings

**Assembly:** `Game`  
**Namespace:** `Game.UI`  

**Type:** class public  

**Base:** `Colossal.UI.Binding.CompositeBinding`  
**Implements:** `Colossal.UI.Binding.IUpdateBinding`, `Colossal.UI.Binding.IBinding`, `Colossal.UI.Binding.IBindingRegistry`, `Colossal.UI.Binding.IBindingGroup`, `System.IDisposable`  

## Code

```csharp
public class InputHintBindings : Colossal.UI.Binding.CompositeBinding, Colossal.UI.Binding.IUpdateBinding, Colossal.UI.Binding.IBinding, Colossal.UI.Binding.IBindingRegistry, Colossal.UI.Binding.IBindingGroup, System.IDisposable
{
    private readonly Colossal.UI.Binding.ValueBinding<Game.UI.InputHintBindings+InputHint[]> m_ActiveHintsBinding;
    private readonly Colossal.UI.Binding.GetterMapBinding<Game.UI.InputHintBindings+InputHintQuery, Game.UI.InputHintBindings+InputHint> m_HintsMapBinding;
    private readonly Colossal.UI.Binding.ValueBinding<System.Int32> m_GamepadTypeBinding;
    private readonly Colossal.UI.Binding.GetterMapBinding<Game.UI.InputHintBindings+TutorialInputHintQuery, Game.UI.InputHintBindings+InputHint[]> m_TutorialHints;
    private System.Collections.Generic.Dictionary<System.ValueTuple<System.String, System.Int32>, Game.UI.InputHintBindings+InputHint> m_Hints;
    private System.Boolean m_HintsDirty;
    private System.Boolean m_TutorialHintsDirty;
    private System.Action<Game.Input.ProxyAction> onInputHintPerformed;
    private static readonly System.String[] axisControls;
    private static readonly System.String[] allDirs;
    private static readonly System.String[] horizontal;
    private static readonly System.String[] vertical;
    private static readonly System.String[] axes;
    private static System.Collections.Generic.Dictionary<System.Collections.Generic.IReadOnlyList<Game.Input.ProxyModifier>, System.Collections.Generic.List<Game.Input.ProxyBinding>> modifiersGroups;
    private static const System.String kGroup;

    public InputHintBindings();

    internal static System.Void CollectHintItems(Game.UI.InputHintBindings+InputHint hint, Game.Input.ProxyAction action, Game.Input.InputManager+DeviceType device, Game.Input.UIBaseInputAction+Transform transform, System.Boolean ignoreMask);
    private static System.Void CollectHints(System.Collections.Generic.Dictionary<System.ValueTuple<System.String, System.Int32>, Game.UI.InputHintBindings+InputHint> hints, Game.Input.ProxyAction action, Game.Input.InputManager+DeviceType device, System.Boolean ignoreMask);
    public System.Void Dispose();
    private Game.UI.InputHintBindings+InputHint GetInputHint(Game.UI.InputHintBindings+InputHintQuery query);
    private static Game.UI.InputHintBindings+InputHint[] GetTutorialHints(Game.UI.InputHintBindings+TutorialInputHintQuery query);
    private System.Void HandleInputHintPerformed(System.String action);
    private static System.Boolean MatchesControlScheme(Game.Input.ProxyBinding binding, Game.Input.InputManager+ControlScheme controlScheme);
    private static System.Boolean MatchesDirections(System.String[] bindings, System.String basePath, System.String[] dirs);
    private System.Void OnActionDisplayNamesChanged();
    private System.Void OnActionsChanged();
    private System.Void OnActiveDeviceChanged(UnityEngine.InputSystem.InputDevice newDevice, UnityEngine.InputSystem.InputDevice oldDevice, System.Boolean schemeChanged);
    private System.Void OnControlSchemeChanged(Game.Input.InputManager+ControlScheme controlScheme);
    private System.Void OnEnabledActionsChanged();
    private System.Void RebuildHints();
    private static System.Void SimplifyPaths(System.String[]& paths);
    public virtual System.Boolean Update();
}
```


## Fields

- `private readonly Colossal.UI.Binding.ValueBinding<Game.UI.InputHintBindings+InputHint[]> m_ActiveHintsBinding`  

```csharp
private readonly Colossal.UI.Binding.ValueBinding<Game.UI.InputHintBindings+InputHint[]> m_ActiveHintsBinding;
```

- `private readonly Colossal.UI.Binding.GetterMapBinding<Game.UI.InputHintBindings+InputHintQuery, Game.UI.InputHintBindings+InputHint> m_HintsMapBinding`  

```csharp
private readonly Colossal.UI.Binding.GetterMapBinding<Game.UI.InputHintBindings+InputHintQuery, Game.UI.InputHintBindings+InputHint> m_HintsMapBinding;
```

- `private readonly Colossal.UI.Binding.ValueBinding<System.Int32> m_GamepadTypeBinding`  

```csharp
private readonly Colossal.UI.Binding.ValueBinding<System.Int32> m_GamepadTypeBinding;
```

- `private readonly Colossal.UI.Binding.GetterMapBinding<Game.UI.InputHintBindings+TutorialInputHintQuery, Game.UI.InputHintBindings+InputHint[]> m_TutorialHints`  

```csharp
private readonly Colossal.UI.Binding.GetterMapBinding<Game.UI.InputHintBindings+TutorialInputHintQuery, Game.UI.InputHintBindings+InputHint[]> m_TutorialHints;
```

- `private System.Collections.Generic.Dictionary<System.ValueTuple<System.String, System.Int32>, Game.UI.InputHintBindings+InputHint> m_Hints`  

```csharp
private System.Collections.Generic.Dictionary<System.ValueTuple<System.String, System.Int32>, Game.UI.InputHintBindings+InputHint> m_Hints;
```

- `private System.Boolean m_HintsDirty`  

```csharp
private System.Boolean m_HintsDirty;
```

- `private System.Boolean m_TutorialHintsDirty`  

```csharp
private System.Boolean m_TutorialHintsDirty;
```

- `private System.Action<Game.Input.ProxyAction> onInputHintPerformed`  

```csharp
private System.Action<Game.Input.ProxyAction> onInputHintPerformed;
```

- `private static readonly System.String[] axisControls`  

```csharp
private static readonly System.String[] axisControls;
```

- `private static readonly System.String[] allDirs`  

```csharp
private static readonly System.String[] allDirs;
```

- `private static readonly System.String[] horizontal`  

```csharp
private static readonly System.String[] horizontal;
```

- `private static readonly System.String[] vertical`  

```csharp
private static readonly System.String[] vertical;
```

- `private static readonly System.String[] axes`  

```csharp
private static readonly System.String[] axes;
```

- `private static System.Collections.Generic.Dictionary<System.Collections.Generic.IReadOnlyList<Game.Input.ProxyModifier>, System.Collections.Generic.List<Game.Input.ProxyBinding>> modifiersGroups`  

```csharp
private static System.Collections.Generic.Dictionary<System.Collections.Generic.IReadOnlyList<Game.Input.ProxyModifier>, System.Collections.Generic.List<Game.Input.ProxyBinding>> modifiersGroups;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Constructors

- `public InputHintBindings()`  

```csharp
public InputHintBindings()
	{
		AddBinding(m_HintsMapBinding = new GetterMapBinding<InputHintQuery, InputHint>("input", "hints", GetInputHint, new ValueReader<InputHintQuery>(), new ValueWriter<InputHintQuery>(), new ValueWriter<InputHint>()));
		AddBinding(m_ActiveHintsBinding = new ValueBinding<InputHint[]>("input", "activeHints", Array.Empty<InputHint>(), new ArrayWriter<InputHint>(new ValueWriter<InputHint>())));
		AddBinding(m_GamepadTypeBinding = new ValueBinding<int>("input", "gamepadType", (int)Game.Input.InputManager.instance.GetActiveGamepadType()));
		AddBinding(m_TutorialHints = new GetterMapBinding<TutorialInputHintQuery, InputHint[]>("input", "tutorialHints", GetTutorialHints, new ValueReader<TutorialInputHintQuery>(), new ValueWriter<TutorialInputHintQuery>(), new ArrayWriter<InputHint>(new ValueWriter<InputHint>())));
		AddBinding(new TriggerBinding<string>("input", "onInputHintPerformed", HandleInputHintPerformed));
		Game.Input.InputManager.instance.EventActionsChanged += OnActionsChanged;
		Game.Input.InputManager.instance.EventEnabledActionsChanged += OnEnabledActionsChanged;
		Game.Input.InputManager.instance.EventActionDisplayNamesChanged += OnActionDisplayNamesChanged;
		Game.Input.InputManager.instance.EventControlSchemeChanged += OnControlSchemeChanged;
		Game.Input.InputManager.instance.EventActiveDeviceChanged += OnActiveDeviceChanged;
	}
```


## Methods

- `internal static CollectHintItems(Game.UI.InputHintBindings+InputHint hint, Game.Input.ProxyAction action, Game.Input.InputManager+DeviceType device, Game.Input.UIBaseInputAction+Transform transform, System.Boolean ignoreMask = True) : System.Void`  

```csharp
internal static void CollectHintItems(InputHint hint, ProxyAction action, Game.Input.InputManager.DeviceType device, UIBaseInputAction.Transform transform, bool ignoreMask = true)
	{
		foreach (var (_, proxyComposite2) in action.composites)
		{
			if ((!ignoreMask && (proxyComposite2.m_Device & action.mask) == 0) || (proxyComposite2.m_Device & device) == 0)
			{
				continue;
			}
			modifiersGroups.Clear();
			ProxyBinding value;
			foreach (KeyValuePair<ActionComponent, ProxyBinding> binding in proxyComposite2.bindings)
			{
				binding.Deconstruct(out var _, out value);
				ProxyBinding item = value;
				if (item.isSet && !item.isDummy && (transform == UIBaseInputAction.Transform.None || (item.component.ToTransform() & transform) != UIBaseInputAction.Transform.None))
				{
					if (!modifiersGroups.TryGetValue(item.modifiers, out var value2))
					{
						value2 = new List<ProxyBinding>();
						modifiersGroups[item.modifiers] = value2;
					}
					value2.Add(item);
				}
			}
			foreach (KeyValuePair<IReadOnlyList<ProxyModifier>, List<ProxyBinding>> modifiersGroup in modifiersGroups)
			{
				modifiersGroup.Deconstruct(out var key2, out var value3);
				IReadOnlyList<ProxyModifier> readOnlyList = key2;
				List<ProxyBinding> list = value3;
				string[] paths = new string[list.Count];
				for (int i = 0; i < list.Count; i++)
				{
					string[] array = paths;
					int num = i;
					value = list[i];
					array[num] = value.path;
				}
				SimplifyPaths(ref paths);
				ControlPath[] array2 = new ControlPath[paths.Length];
				for (int j = 0; j < array2.Length; j++)
				{
					array2[j] = ControlPath.Get(paths[j]);
				}
				ControlPath[] array3 = new ControlPath[readOnlyList.Count];
				for (int k = 0; k < array3.Length; k++)
				{
					array3[k] = ControlPath.Get(readOnlyList[k].m_Path);
				}
				hint.items.Add(new InputHintItem
				{
					bindings = array2,
					modifiers = array3
				});
			}
		}
	}
```

- `private static CollectHints(System.Collections.Generic.Dictionary<System.ValueTuple<System.String, System.Int32>, Game.UI.InputHintBindings+InputHint> hints, Game.Input.ProxyAction action, Game.Input.InputManager+DeviceType device, System.Boolean ignoreMask = False) : System.Void`  

```csharp
private static System.Void CollectHints(System.Collections.Generic.Dictionary<System.ValueTuple<System.String, System.Int32>, Game.UI.InputHintBindings+InputHint> hints, Game.Input.ProxyAction action, Game.Input.InputManager+DeviceType device, System.Boolean ignoreMask);
```

- `public Dispose() : System.Void`  

```csharp
public void Dispose()
	{
		Game.Input.InputManager.instance.EventActionsChanged -= OnActionsChanged;
		Game.Input.InputManager.instance.EventEnabledActionsChanged -= OnEnabledActionsChanged;
		Game.Input.InputManager.instance.EventActionDisplayNamesChanged -= OnActionDisplayNamesChanged;
		Game.Input.InputManager.instance.EventControlSchemeChanged -= OnControlSchemeChanged;
		Game.Input.InputManager.instance.EventActiveDeviceChanged -= OnActiveDeviceChanged;
	}
```

- `private GetInputHint(Game.UI.InputHintBindings+InputHintQuery query) : Game.UI.InputHintBindings+InputHint`  

```csharp
private InputHint GetInputHint(InputHintQuery query)
	{
		if (m_HintsMapBinding.values.TryGetValue(query, out var value) && value.version == Game.Input.InputManager.instance.actionVersion)
		{
			return value;
		}
		UIBaseInputAction[] inputActions = Game.Input.InputManager.instance.uiActionCollection.m_InputActions;
		UIBaseInputAction uIBaseInputAction = null;
		for (int i = 0; i < inputActions.Length; i++)
		{
			if (inputActions[i].aliasName == query.action)
			{
				uIBaseInputAction = inputActions[i];
				break;
			}
		}
		if (uIBaseInputAction == null)
		{
			return null;
		}
		value = new InputHint(null)
		{
			name = uIBaseInputAction.aliasName,
			priority = uIBaseInputAction.displayPriority,
			show = true
		};
		foreach (UIInputActionPart actionPart in uIBaseInputAction.actionParts)
		{
			if (Game.Input.InputManager.instance.TryFindAction(actionPart.m_Action, out var proxyAction))
			{
				Game.Input.InputManager.ControlScheme controlScheme = query.controlScheme;
				CollectHintItems(value, proxyAction, controlScheme switch
				{
					Game.Input.InputManager.ControlScheme.Gamepad => Game.Input.InputManager.DeviceType.Gamepad, 
					Game.Input.InputManager.ControlScheme.KeyboardAndMouse => Game.Input.InputManager.DeviceType.Keyboard | Game.Input.InputManager.DeviceType.Mouse, 
					_ => Game.Input.InputManager.DeviceType.None, 
				}, actionPart.m_Transform);
			}
		}
		return value;
	}
```

- `private static GetTutorialHints(Game.UI.InputHintBindings+TutorialInputHintQuery query) : Game.UI.InputHintBindings+InputHint[]`  

```csharp
private static InputHint[] GetTutorialHints(TutorialInputHintQuery query)
	{
		switch (query.action)
		{
		case "Rotate Mouse":
			query.action = "Rotate";
			break;
		case "Zoom Mouse":
			query.action = "Zoom";
			break;
		case "Tool Options":
			query.map = "Navigation";
			query.action = "Secondary Action";
			break;
		case "Cancel":
			if (query.map == "Tool")
			{
				query.map = "Navigation";
				query.action = "Back";
			}
			break;
		}
		ProxyAction action = Game.Input.InputManager.instance.FindAction(query.map, query.action);
		if (action == null)
		{
			return Array.Empty<InputHint>();
		}
		if (query.controlScheme == Game.Input.InputManager.ControlScheme.Gamepad)
		{
			Dictionary<(string, int), InputHint> dictionary = new Dictionary<(string, int), InputHint>();
			Game.Input.InputManager.ControlScheme controlScheme = query.controlScheme;
			CollectHints(dictionary, action, controlScheme switch
			{
				Game.Input.InputManager.ControlScheme.Gamepad => Game.Input.InputManager.DeviceType.Gamepad, 
				Game.Input.InputManager.ControlScheme.KeyboardAndMouse => Game.Input.InputManager.DeviceType.Keyboard | Game.Input.InputManager.DeviceType.Mouse, 
				_ => Game.Input.InputManager.DeviceType.None, 
			}, ignoreMask: true);
			return dictionary.Values.OrderBy((InputHint h) => h.priority).ToArray();
		}
		if (query.index >= 0)
		{
			ProxyBinding proxyBinding = action.bindings.Where((ProxyBinding b) => MatchesControlScheme(b, query.controlScheme)).Skip(query.index).FirstOrDefault();
			return new InputHint[1]
			{
				new InputHint(action)
				{
					name = action.title,
					items = 
					{
						new InputHintItem
						{
							bindings = new ControlPath[1] { ControlPath.Get(proxyBinding.path) },
							modifiers = proxyBinding.modifiers.Select((ProxyModifier m) => ControlPath.Get(m.m_Path)).ToArray()
						}
					}
				}
			};
		}
		return (from b in action.bindings
			where b.isSet && MatchesControlScheme(b, query.controlScheme)
			select new InputHint(action)
			{
				name = action.title,
				items = 
				{
					new InputHintItem
					{
						bindings = new ControlPath[1] { ControlPath.Get(b.path) },
						modifiers = b.modifiers.Select((ProxyModifier m) => ControlPath.Get(m.m_Path)).ToArray()
					}
				}
			}).ToArray();
	}
```

- `private HandleInputHintPerformed(System.String action) : System.Void`  

```csharp
private void HandleInputHintPerformed(string action)
	{
		foreach (InputHint value in m_Hints.Values)
		{
			if (value.name == action)
			{
				this.onInputHintPerformed?.Invoke(value.action);
				break;
			}
		}
	}
```

- `private static MatchesControlScheme(Game.Input.ProxyBinding binding, Game.Input.InputManager+ControlScheme controlScheme) : System.Boolean`  

```csharp
private static bool MatchesControlScheme(ProxyBinding binding, Game.Input.InputManager.ControlScheme controlScheme)
	{
		if (controlScheme != Game.Input.InputManager.ControlScheme.Gamepad || !binding.isGamepad)
		{
			if (controlScheme == Game.Input.InputManager.ControlScheme.KeyboardAndMouse)
			{
				if (!binding.isKeyboard)
				{
					return binding.isMouse;
				}
				return true;
			}
			return false;
		}
		return true;
	}
```

- `private static MatchesDirections(System.String[] bindings, System.String basePath, System.String[] dirs) : System.Boolean`  

```csharp
private static bool MatchesDirections(string[] bindings, string basePath, string[] dirs)
	{
		if (bindings.Length != dirs.Length)
		{
			return false;
		}
		foreach (string text in dirs)
		{
			bool flag = false;
			foreach (string text2 in bindings)
			{
				if (text2.Length == basePath.Length + text.Length && text2.StartsWith(basePath) && text2.EndsWith(text))
				{
					flag = true;
					break;
				}
			}
			if (!flag)
			{
				return false;
			}
		}
		return true;
	}
```

- `private OnActionDisplayNamesChanged() : System.Void`  

```csharp
private void OnActionDisplayNamesChanged()
	{
		m_HintsDirty = true;
	}
```

- `private OnActionsChanged() : System.Void`  

```csharp
private void OnActionsChanged()
	{
		m_HintsDirty = true;
		m_TutorialHintsDirty = true;
		m_HintsMapBinding.UpdateAll();
	}
```

- `private OnActiveDeviceChanged(UnityEngine.InputSystem.InputDevice newDevice, UnityEngine.InputSystem.InputDevice oldDevice, System.Boolean schemeChanged) : System.Void`  

```csharp
private void OnActiveDeviceChanged(InputDevice newDevice, InputDevice oldDevice, bool schemeChanged)
	{
		if (Game.Input.InputManager.instance.activeControlScheme == Game.Input.InputManager.ControlScheme.Gamepad)
		{
			m_GamepadTypeBinding.Update((int)Game.Input.InputManager.instance.GetActiveGamepadType());
		}
	}
```

- `private OnControlSchemeChanged(Game.Input.InputManager+ControlScheme controlScheme) : System.Void`  

```csharp
private void OnControlSchemeChanged(Game.Input.InputManager.ControlScheme controlScheme)
	{
		m_HintsDirty = true;
	}
```

- `private OnEnabledActionsChanged() : System.Void`  

```csharp
private void OnEnabledActionsChanged()
	{
		m_HintsDirty = true;
	}
```

- `private RebuildHints() : System.Void`  

```csharp
private void RebuildHints()
	{
		m_Hints.Clear();
		foreach (ProxyAction action in Game.Input.InputManager.instance.actions)
		{
			if (action.displayOverride != null)
			{
				Game.Input.InputManager.ControlScheme activeControlScheme = Game.Input.InputManager.instance.activeControlScheme;
				CollectHints(m_Hints, action, activeControlScheme switch
				{
					Game.Input.InputManager.ControlScheme.Gamepad => Game.Input.InputManager.DeviceType.Gamepad, 
					Game.Input.InputManager.ControlScheme.KeyboardAndMouse => Game.Input.InputManager.DeviceType.Keyboard | Game.Input.InputManager.DeviceType.Mouse, 
					_ => Game.Input.InputManager.DeviceType.None, 
				});
			}
		}
	}
```

- `private static SimplifyPaths(System.String[]& paths) : System.Void`  

```csharp
private static void SimplifyPaths(ref string[] paths)
	{
		for (int i = 0; i < axisControls.Length; i++)
		{
			string text = axisControls[i];
			if (MatchesDirections(paths, text, allDirs) || MatchesDirections(paths, text, axes))
			{
				paths = new string[1] { text };
				break;
			}
			if (MatchesDirections(paths, text, horizontal))
			{
				paths = new string[1] { text + "/x" };
				break;
			}
			if (MatchesDirections(paths, text, vertical))
			{
				paths = new string[1] { text + "/y" };
				break;
			}
		}
	}
```

- `public virtual Update() : System.Boolean`  

```csharp
public override bool Update()
	{
		if (m_TutorialHintsDirty)
		{
			m_TutorialHints.Update();
			m_TutorialHintsDirty = false;
		}
		if (m_HintsDirty)
		{
			m_HintsDirty = false;
			RebuildHints();
			m_ActiveHintsBinding.Update(m_Hints.Values.OrderBy((InputHint h) => h.priority).ToArray());
		}
		return base.Update();
	}
```


## Events

- `onInputHintPerformed` : `System.Action<Game.Input.ProxyAction>`  

```csharp
public event System.Action<Game.Input.ProxyAction> onInputHintPerformed;
```


## Nested types

- `Game.UI.InputHintBindings+InputHint`  
- `Game.UI.InputHintBindings+InputHintItem`  
- `Game.UI.InputHintBindings+TutorialInputHintQuery`  
- `Game.UI.InputHintBindings+InputHintQuery`  
- `Game.UI.InputHintBindings+<>c`  
- `Game.UI.InputHintBindings+<>c__DisplayClass29_0`  

