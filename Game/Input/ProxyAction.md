# Game.Input.ProxyAction

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.Input.IProxyAction`  

## Code

```csharp
public class ProxyAction : Game.Input.IProxyAction
{
    private System.Action<Game.Input.ProxyAction> onChanged;
    internal readonly System.Int32 m_GlobalIndex;
    private readonly UnityEngine.InputSystem.InputAction m_SourceAction;
    private readonly Game.Input.ProxyActionMap m_Map;
    internal readonly System.Collections.Generic.HashSet<Game.Input.InputBarrier> m_Barriers;
    internal readonly System.Collections.Generic.HashSet<Game.Input.InputActivator> m_Activators;
    internal readonly System.Collections.Generic.HashSet<Game.Input.DisplayNameOverride> m_DisplayOverrides;
    internal readonly System.Collections.Generic.HashSet<Game.Input.UIBaseInputAction> m_UIAliases;
    internal readonly System.Collections.Generic.HashSet<Game.Input.ProxyAction+LinkInfo> m_LinkedActions;
    private Game.Input.InputActivator m_DefaultActivator;
    private Game.Input.InputActivator m_DefaultBuiltInActivator;
    internal System.Boolean m_PreResolvedEnable;
    private Game.Input.InputManager+DeviceType m_AvailableMask;
    private Game.Input.InputManager+DeviceType m_PreResolvedMask;
    private Game.Input.InputManager+DeviceType m_Mask;
    private System.Boolean m_IsSystemAction;
    private readonly System.Collections.Generic.Dictionary<Game.Input.InputManager+DeviceType, Game.Input.ProxyComposite> m_Composites;
    private readonly System.Collections.Generic.List<Game.Input.ProxyBinding> m_Bindings;
    private Game.Input.DisplayNameOverride <displayOverride>k__BackingField;
    private System.Action<Game.Input.ProxyAction, UnityEngine.InputSystem.InputActionPhase> m_OnInteraction;
    private static System.Int32 counter;
    internal static readonly Game.Input.ProxyAction+DeferActionUpdatingWrapper sDeferUpdatingWrapper;
    internal static readonly Game.Input.ProxyAction+DeferActionStateUpdatingWrapper sDeferStateUpdatingWrapper;

    public Game.Input.ProxyActionMap map { get; }
    internal UnityEngine.InputSystem.InputAction sourceAction { internal get; }
    public System.Collections.Generic.IReadOnlyDictionary<Game.Input.InputManager+DeviceType, Game.Input.ProxyComposite> composites { get; }
    public System.Int32 compositesCount { get; }
    internal System.Collections.Generic.IReadOnlyCollection<Game.Input.InputBarrier> barriers { internal get; }
    internal System.Collections.Generic.IReadOnlyCollection<Game.Input.InputActivator> activators { internal get; }
    public System.Collections.Generic.IEnumerable<Game.Input.ProxyBinding> bindings { get; }
    public System.Boolean isSet { get; }
    public System.Boolean isBuiltIn { get; }
    internal System.Boolean isDummy { internal get; }
    internal System.Boolean isSystemAction { internal get; }
    public Game.Input.InputManager+DeviceType availableDevices { get; }
    public System.Boolean isKeyboardAction { get; }
    public System.Boolean isMouseAction { get; }
    public System.Boolean isGamepadAction { get; }
    public System.Boolean isOnlyKeyboardAction { get; }
    public System.Boolean isOnlyMouseAction { get; }
    public System.Boolean isOnlyGamepadAction { get; }
    public System.Boolean isMultiDeviceAction { get; }
    public System.String name { get; }
    public System.String mapName { get; }
    public System.String title { get; }
    public System.Type valueType { get; }
    private System.Boolean Game.Input.IProxyAction.enabled { private get; private set; }
    public System.Boolean enabled { get; internal set; }
    public System.Boolean shouldBeEnabled { get; set; }
    internal System.Boolean preResolvedEnable { internal get; }
    public Game.Input.InputManager+DeviceType mask { get; }
    internal Game.Input.InputManager+DeviceType preResolvedMask { internal get; }
    public Game.Input.DisplayNameOverride displayOverride { get; private set; }
    public System.Collections.Generic.IEnumerable<System.String> usedKeys { get; }

    internal ProxyAction(Game.Input.ProxyActionMap map, UnityEngine.InputSystem.InputAction sourceAction);

    internal System.Void ApplyState(System.Boolean newEnable, Game.Input.InputManager+DeviceType newMask);
    public System.Boolean ContainsComposite(Game.Input.InputManager+DeviceType device);
    public Game.Input.InputActivator CreateActivator(System.String activatorName, Game.Input.InputManager+DeviceType activatorMask);
    public Game.Input.InputBarrier CreateBarrier(System.String barrierName, Game.Input.InputManager+DeviceType barrierMask);
    internal static Game.Input.ProxyAction+DeferActionStateUpdatingWrapper DeferStateUpdating();
    public System.Single GetMagnitude();
    public System.Boolean IsInProgress();
    public System.Boolean IsPressed();
    internal static System.Void LinkActions(Game.Input.ProxyAction+LinkInfo action1, Game.Input.ProxyAction+LinkInfo action2);
    private static System.Void LinkActions(Game.Input.ProxyAction+LinkInfo link1, Game.Input.ProxyAction+LinkInfo link2, System.Boolean addToOther);
    internal T ReadRawValue<T>(System.Boolean disableAll);
    public T ReadValue<T>();
    public System.Object ReadValueAsObject();
    private System.Void SourceOnCanceled(UnityEngine.InputSystem.InputAction+CallbackContext context);
    private System.Void SourceOnPerformed(UnityEngine.InputSystem.InputAction+CallbackContext context);
    private System.Void SourceOnStarted(UnityEngine.InputSystem.InputAction+CallbackContext context);
    public virtual System.String ToString();
    public System.Boolean TryGetBinding(Game.Input.ProxyBinding sampleBinding, Game.Input.ProxyBinding& foundBinding);
    public System.Boolean TryGetComposite(Game.Input.InputManager+DeviceType device, Game.Input.ProxyComposite& composite);
    internal System.Void Update(System.Boolean ignoreDefer);
    internal System.Void UpdateDisplay();
    internal System.Void UpdateState(System.Boolean ignoreDefer);
    public System.Boolean WasPerformedThisFrame();
    public System.Boolean WasPressedThisFrame();
    public System.Boolean WasReleasedThisFrame();
}
```


## Fields

- `private System.Action<Game.Input.ProxyAction> onChanged`  

```csharp
private System.Action<Game.Input.ProxyAction> onChanged;
```

- `internal readonly System.Int32 m_GlobalIndex`  

```csharp
internal readonly System.Int32 m_GlobalIndex;
```

- `private readonly UnityEngine.InputSystem.InputAction m_SourceAction`  

```csharp
private readonly UnityEngine.InputSystem.InputAction m_SourceAction;
```

- `private readonly Game.Input.ProxyActionMap m_Map`  

```csharp
private readonly Game.Input.ProxyActionMap m_Map;
```

- `internal readonly System.Collections.Generic.HashSet<Game.Input.InputBarrier> m_Barriers`  

```csharp
internal readonly System.Collections.Generic.HashSet<Game.Input.InputBarrier> m_Barriers;
```

- `internal readonly System.Collections.Generic.HashSet<Game.Input.InputActivator> m_Activators`  

```csharp
internal readonly System.Collections.Generic.HashSet<Game.Input.InputActivator> m_Activators;
```

- `internal readonly System.Collections.Generic.HashSet<Game.Input.DisplayNameOverride> m_DisplayOverrides`  

```csharp
internal readonly System.Collections.Generic.HashSet<Game.Input.DisplayNameOverride> m_DisplayOverrides;
```

- `internal readonly System.Collections.Generic.HashSet<Game.Input.UIBaseInputAction> m_UIAliases`  

```csharp
internal readonly System.Collections.Generic.HashSet<Game.Input.UIBaseInputAction> m_UIAliases;
```

- `internal readonly System.Collections.Generic.HashSet<Game.Input.ProxyAction+LinkInfo> m_LinkedActions`  

```csharp
internal readonly System.Collections.Generic.HashSet<Game.Input.ProxyAction+LinkInfo> m_LinkedActions;
```

- `private Game.Input.InputActivator m_DefaultActivator`  

```csharp
private Game.Input.InputActivator m_DefaultActivator;
```

- `private Game.Input.InputActivator m_DefaultBuiltInActivator`  

```csharp
private Game.Input.InputActivator m_DefaultBuiltInActivator;
```

- `internal System.Boolean m_PreResolvedEnable`  

```csharp
internal System.Boolean m_PreResolvedEnable;
```

- `private Game.Input.InputManager+DeviceType m_AvailableMask`  

```csharp
private Game.Input.InputManager+DeviceType m_AvailableMask;
```

- `private Game.Input.InputManager+DeviceType m_PreResolvedMask`  

```csharp
private Game.Input.InputManager+DeviceType m_PreResolvedMask;
```

- `private Game.Input.InputManager+DeviceType m_Mask`  

```csharp
private Game.Input.InputManager+DeviceType m_Mask;
```

- `private System.Boolean m_IsSystemAction`  

```csharp
private System.Boolean m_IsSystemAction;
```

- `private readonly System.Collections.Generic.Dictionary<Game.Input.InputManager+DeviceType, Game.Input.ProxyComposite> m_Composites`  

```csharp
private readonly System.Collections.Generic.Dictionary<Game.Input.InputManager+DeviceType, Game.Input.ProxyComposite> m_Composites;
```

- `private readonly System.Collections.Generic.List<Game.Input.ProxyBinding> m_Bindings`  

```csharp
private readonly System.Collections.Generic.List<Game.Input.ProxyBinding> m_Bindings;
```

- `private Game.Input.DisplayNameOverride <displayOverride>k__BackingField`  

```csharp
private Game.Input.DisplayNameOverride <displayOverride>k__BackingField;
```

- `private System.Action<Game.Input.ProxyAction, UnityEngine.InputSystem.InputActionPhase> m_OnInteraction`  

```csharp
private System.Action<Game.Input.ProxyAction, UnityEngine.InputSystem.InputActionPhase> m_OnInteraction;
```

- `private static System.Int32 counter`  

```csharp
private static System.Int32 counter;
```

- `internal static readonly Game.Input.ProxyAction+DeferActionUpdatingWrapper sDeferUpdatingWrapper`  

```csharp
internal static readonly Game.Input.ProxyAction+DeferActionUpdatingWrapper sDeferUpdatingWrapper;
```

- `internal static readonly Game.Input.ProxyAction+DeferActionStateUpdatingWrapper sDeferStateUpdatingWrapper`  

```csharp
internal static readonly Game.Input.ProxyAction+DeferActionStateUpdatingWrapper sDeferStateUpdatingWrapper;
```


## Properties

- `public Game.Input.ProxyActionMap map { get }`  

```csharp
public Game.Input.ProxyActionMap map { get; }
```

- `internal UnityEngine.InputSystem.InputAction sourceAction { internal get }`  

```csharp
internal UnityEngine.InputSystem.InputAction sourceAction { internal get; }
```

- `public System.Collections.Generic.IReadOnlyDictionary<Game.Input.InputManager+DeviceType, Game.Input.ProxyComposite> composites { get }`  

```csharp
public System.Collections.Generic.IReadOnlyDictionary<Game.Input.InputManager+DeviceType, Game.Input.ProxyComposite> composites { get; }
```

- `public System.Int32 compositesCount { get }`  

```csharp
public System.Int32 compositesCount { get; }
```

- `internal System.Collections.Generic.IReadOnlyCollection<Game.Input.InputBarrier> barriers { internal get }`  

```csharp
internal System.Collections.Generic.IReadOnlyCollection<Game.Input.InputBarrier> barriers { internal get; }
```

- `internal System.Collections.Generic.IReadOnlyCollection<Game.Input.InputActivator> activators { internal get }`  

```csharp
internal System.Collections.Generic.IReadOnlyCollection<Game.Input.InputActivator> activators { internal get; }
```

- `public System.Collections.Generic.IEnumerable<Game.Input.ProxyBinding> bindings { get }`  

```csharp
public System.Collections.Generic.IEnumerable<Game.Input.ProxyBinding> bindings { get; }
```

- `public System.Boolean isSet { get }`  

```csharp
public System.Boolean isSet { get; }
```

- `public System.Boolean isBuiltIn { get }`  

```csharp
public System.Boolean isBuiltIn { get; }
```

- `internal System.Boolean isDummy { internal get }`  

```csharp
internal System.Boolean isDummy { internal get; }
```

- `internal System.Boolean isSystemAction { internal get }`  

```csharp
internal System.Boolean isSystemAction { internal get; }
```

- `public Game.Input.InputManager+DeviceType availableDevices { get }`  

```csharp
public Game.Input.InputManager+DeviceType availableDevices { get; }
```

- `public System.Boolean isKeyboardAction { get }`  

```csharp
public System.Boolean isKeyboardAction { get; }
```

- `public System.Boolean isMouseAction { get }`  

```csharp
public System.Boolean isMouseAction { get; }
```

- `public System.Boolean isGamepadAction { get }`  

```csharp
public System.Boolean isGamepadAction { get; }
```

- `public System.Boolean isOnlyKeyboardAction { get }`  

```csharp
public System.Boolean isOnlyKeyboardAction { get; }
```

- `public System.Boolean isOnlyMouseAction { get }`  

```csharp
public System.Boolean isOnlyMouseAction { get; }
```

- `public System.Boolean isOnlyGamepadAction { get }`  

```csharp
public System.Boolean isOnlyGamepadAction { get; }
```

- `public System.Boolean isMultiDeviceAction { get }`  

```csharp
public System.Boolean isMultiDeviceAction { get; }
```

- `public System.String name { get }`  

```csharp
public System.String name { get; }
```

- `public System.String mapName { get }`  

```csharp
public System.String mapName { get; }
```

- `public System.String title { get }`  

```csharp
public System.String title { get; }
```

- `public System.Type valueType { get }`  

```csharp
public System.Type valueType { get; }
```

- `private System.Boolean Game.Input.IProxyAction.enabled { private get; private set }`  

```csharp
private System.Boolean Game.Input.IProxyAction.enabled { private get; private set; }
```

- `public System.Boolean enabled { get; internal set }`  

```csharp
public System.Boolean enabled { get; internal set; }
```

- `public System.Boolean shouldBeEnabled { get; set }`  

```csharp
public System.Boolean shouldBeEnabled { get; set; }
```

- `internal System.Boolean preResolvedEnable { internal get }`  

```csharp
internal System.Boolean preResolvedEnable { internal get; }
```

- `public Game.Input.InputManager+DeviceType mask { get }`  

```csharp
public Game.Input.InputManager+DeviceType mask { get; }
```

- `internal Game.Input.InputManager+DeviceType preResolvedMask { internal get }`  

```csharp
internal Game.Input.InputManager+DeviceType preResolvedMask { internal get; }
```

- `public Game.Input.DisplayNameOverride displayOverride { get; private set }`  

```csharp
public Game.Input.DisplayNameOverride displayOverride { get; private set; }
```

- `public System.Collections.Generic.IEnumerable<System.String> usedKeys { get }`  

```csharp
public System.Collections.Generic.IEnumerable<System.String> usedKeys { get; }
```


## Constructors

- `internal ProxyAction(Game.Input.ProxyActionMap map, UnityEngine.InputSystem.InputAction sourceAction)`  

```csharp
internal ProxyAction(ProxyActionMap map, InputAction sourceAction)
	{
		m_GlobalIndex = counter++;
		m_Map = map ?? throw new ArgumentNullException("map");
		m_SourceAction = sourceAction ?? throw new ArgumentNullException("sourceAction");
		InputManager.instance.actionIndex[m_GlobalIndex] = this;
		Update();
	}
```


## Methods

- `internal ApplyState(System.Boolean newEnable, Game.Input.InputManager+DeviceType newMask) : System.Void`  

```csharp
internal void ApplyState(bool newEnable, InputManager.DeviceType newMask)
	{
		bool num = newMask != m_Mask;
		bool flag = newEnable != m_SourceAction.enabled;
		if (num)
		{
			m_Mask = newMask;
			InputManager.instance?.OnActionMasksChanged();
		}
		if (flag)
		{
			if (newEnable)
			{
				m_SourceAction.Enable();
			}
			else
			{
				m_SourceAction.Disable();
			}
			UpdateDisplay();
			InputManager.instance?.OnEnabledActionsChanged();
		}
	}
```

- `public ContainsComposite(Game.Input.InputManager+DeviceType device) : System.Boolean`  

```csharp
public bool ContainsComposite(InputManager.DeviceType device)
	{
		return (m_AvailableMask & device) != 0;
	}
```

- `public CreateActivator(System.String activatorName = null, Game.Input.InputManager+DeviceType activatorMask = All) : Game.Input.InputActivator`  

```csharp
public InputActivator CreateActivator(string activatorName = null, InputManager.DeviceType activatorMask = InputManager.DeviceType.All)
	{
		return new InputActivator(ignoreIsBuiltIn: false, activatorName, this, activatorMask);
	}
```

- `public CreateBarrier(System.String barrierName = null, Game.Input.InputManager+DeviceType barrierMask = All) : Game.Input.InputBarrier`  

```csharp
public InputBarrier CreateBarrier(string barrierName = null, InputManager.DeviceType barrierMask = InputManager.DeviceType.All)
	{
		return new InputBarrier(barrierName, this, barrierMask);
	}
```

- `internal static DeferStateUpdating() : Game.Input.ProxyAction+DeferActionStateUpdatingWrapper`  

```csharp
internal static DeferActionStateUpdatingWrapper DeferStateUpdating()
	{
		sDeferStateUpdatingWrapper.Acquire();
		return sDeferStateUpdatingWrapper;
	}
```

- `public GetMagnitude() : System.Single`  

```csharp
public unsafe float GetMagnitude()
	{
		InputActionState state = m_SourceAction.GetOrCreateActionMap().m_State;
		if (state != null)
		{
			InputActionState.TriggerState* ptr = state.actionStates + m_SourceAction.m_ActionIndexInState;
			if (ptr->haveMagnitude)
			{
				return ptr->magnitude;
			}
		}
		return 0f;
	}
```

- `public IsInProgress() : System.Boolean`  

```csharp
public bool IsInProgress()
	{
		return m_SourceAction.IsInProgress();
	}
```

- `public IsPressed() : System.Boolean`  

```csharp
public bool IsPressed()
	{
		return m_SourceAction.IsPressed();
	}
```

- `internal static LinkActions(Game.Input.ProxyAction+LinkInfo action1, Game.Input.ProxyAction+LinkInfo action2) : System.Void`  

```csharp
private static void LinkActions(LinkInfo link1, LinkInfo link2, bool addToOther)
	{
		if (link1.m_Action == null || link2.m_Action == null || link1.m_Device != link2.m_Device || link1.m_Action == link2.m_Action)
		{
			return;
		}
		if (addToOther)
		{
			if (!link1.m_Action.m_LinkedActions.Contains(link2))
			{
				foreach (LinkInfo linkedAction in link1.m_Action.m_LinkedActions)
				{
					LinkActions(link2, linkedAction, addToOther: false);
				}
			}
			if (!link2.m_Action.m_LinkedActions.Contains(link1))
			{
				foreach (LinkInfo linkedAction2 in link2.m_Action.m_LinkedActions)
				{
					LinkActions(link1, linkedAction2, addToOther: false);
				}
			}
		}
		link1.m_Action.m_LinkedActions.Add(link2);
		link2.m_Action.m_LinkedActions.Add(link1);
	}
```

- `private static LinkActions(Game.Input.ProxyAction+LinkInfo link1, Game.Input.ProxyAction+LinkInfo link2, System.Boolean addToOther) : System.Void`  

```csharp
private static void LinkActions(LinkInfo link1, LinkInfo link2, bool addToOther)
	{
		if (link1.m_Action == null || link2.m_Action == null || link1.m_Device != link2.m_Device || link1.m_Action == link2.m_Action)
		{
			return;
		}
		if (addToOther)
		{
			if (!link1.m_Action.m_LinkedActions.Contains(link2))
			{
				foreach (LinkInfo linkedAction in link1.m_Action.m_LinkedActions)
				{
					LinkActions(link2, linkedAction, addToOther: false);
				}
			}
			if (!link2.m_Action.m_LinkedActions.Contains(link1))
			{
				foreach (LinkInfo linkedAction2 in link2.m_Action.m_LinkedActions)
				{
					LinkActions(link1, linkedAction2, addToOther: false);
				}
			}
		}
		link1.m_Action.m_LinkedActions.Add(link2);
		link2.m_Action.m_LinkedActions.Add(link1);
	}
```

- `internal ReadRawValue<T>(System.Boolean disableAll = True) : T`  

```csharp
internal T ReadRawValue<T>(System.Boolean disableAll);
```

- `public ReadValue<T>() : T`  

```csharp
public T ReadValue<T>();
```

- `public ReadValueAsObject() : System.Object`  

```csharp
public object ReadValueAsObject()
	{
		return m_SourceAction.ReadValueAsObject();
	}
```

- `private SourceOnCanceled(UnityEngine.InputSystem.InputAction+CallbackContext context) : System.Void`  

```csharp
private void SourceOnCanceled(InputAction.CallbackContext context)
	{
		m_OnInteraction?.Invoke(this, InputActionPhase.Canceled);
	}
```

- `private SourceOnPerformed(UnityEngine.InputSystem.InputAction+CallbackContext context) : System.Void`  

```csharp
private void SourceOnPerformed(InputAction.CallbackContext context)
	{
		m_OnInteraction?.Invoke(this, InputActionPhase.Performed);
	}
```

- `private SourceOnStarted(UnityEngine.InputSystem.InputAction+CallbackContext context) : System.Void`  

```csharp
private void SourceOnStarted(InputAction.CallbackContext context)
	{
		m_OnInteraction?.Invoke(this, InputActionPhase.Started);
	}
```

- `public virtual ToString() : System.String`  

```csharp
public override string ToString()
	{
		return mapName + "/" + name + " ( " + string.Join(" | ", from b in bindings
			where !string.IsNullOrEmpty(b.path)
			select string.Format("{0}: {1}{2}", b.component, string.Join("", b.modifiers.Select((ProxyModifier m) => m.m_Path + " + ")), b.path)) + " )";
	}
```

- `public TryGetBinding(Game.Input.ProxyBinding sampleBinding, Game.Input.ProxyBinding& foundBinding) : System.Boolean`  

```csharp
public bool TryGetBinding(ProxyBinding sampleBinding, out ProxyBinding foundBinding)
	{
		if (TryGetComposite(sampleBinding.device, out var composite))
		{
			return composite.TryGetBinding(sampleBinding, out foundBinding);
		}
		foundBinding = default(ProxyBinding);
		return false;
	}
```

- `public TryGetComposite(Game.Input.InputManager+DeviceType device, Game.Input.ProxyComposite& composite) : System.Boolean`  

```csharp
public bool TryGetComposite(InputManager.DeviceType device, out ProxyComposite composite)
	{
		return m_Composites.TryGetValue(device, out composite);
	}
```

- `internal Update(System.Boolean ignoreDefer = False) : System.Void`  

```csharp
internal void Update(bool ignoreDefer = false)
	{
		if (sDeferUpdatingWrapper.isDeferred && !ignoreDefer)
		{
			sDeferUpdatingWrapper.AddToUpdateQueue(this);
			return;
		}
		m_Composites.Clear();
		m_AvailableMask = InputManager.DeviceType.None;
		foreach (ProxyComposite composite in InputManager.instance.GetComposites(sourceAction))
		{
			foreach (LinkInfo linkedAction in m_LinkedActions)
			{
				if (linkedAction.m_Device == composite.m_Device)
				{
					composite.m_LinkedActions.Add(linkedAction.m_Action);
				}
			}
			m_Composites[composite.m_Device] = composite;
			m_AvailableMask |= composite.m_Device;
		}
		m_Bindings.Clear();
		foreach (KeyValuePair<InputManager.DeviceType, ProxyComposite> composite2 in m_Composites)
		{
			composite2.Deconstruct(out var _, out var value);
			foreach (var (_, item) in value.bindings)
			{
				m_Bindings.Add(item);
			}
		}
		m_IsSystemAction = mapName == "Splash screen" || mapName == "Engagement" || mapName == "Camera" || mapName == "Tool" || mapName == "Editor";
		InputManager.instance.UpdateActionInKeyActionMap(this);
		InputManager.instance.OnActionChanged();
		this.onChanged?.Invoke(this);
	}
```

- `internal UpdateDisplay() : System.Void`  

```csharp
internal void UpdateDisplay()
	{
		displayOverride = (enabled ? (from n in m_DisplayOverrides
			where n.active
			orderby n.priority
			select n).FirstOrDefault() : null);
		InputManager.instance?.OnActionDisplayNamesChanged();
	}
```

- `internal UpdateState(System.Boolean ignoreDefer = False) : System.Void`  

```csharp
internal void UpdateState(bool ignoreDefer = false)
	{
		if (m_SourceAction == null)
		{
			return;
		}
		if (sDeferStateUpdatingWrapper.isDeferred && !ignoreDefer)
		{
			sDeferStateUpdatingWrapper.AddToUpdateQueue(this);
			return;
		}
		m_PreResolvedMask = (m_Map.enabled ? (m_AvailableMask & map.mask) : InputManager.DeviceType.None);
		if (m_PreResolvedMask != InputManager.DeviceType.None)
		{
			InputManager.DeviceType deviceType = InputManager.DeviceType.None;
			foreach (InputActivator activator in m_Activators)
			{
				if (activator.enabled)
				{
					deviceType |= activator.mask & m_PreResolvedMask;
					if ((deviceType & m_PreResolvedMask) == m_PreResolvedMask)
					{
						break;
					}
				}
			}
			if (deviceType != InputManager.DeviceType.None)
			{
				foreach (InputBarrier barrier in m_Barriers)
				{
					if (barrier.blocked)
					{
						deviceType &= ~barrier.mask;
						if (deviceType == InputManager.DeviceType.None)
						{
							break;
						}
					}
				}
			}
			m_PreResolvedMask &= deviceType;
		}
		m_PreResolvedEnable = m_Map.enabled && m_PreResolvedMask != InputManager.DeviceType.None;
		if (InputManager.instance != null && (m_PreResolvedEnable != enabled || m_PreResolvedMask != mask))
		{
			InputManager.instance.OnPreResolvedActionChanged();
		}
		if (isSystemAction)
		{
			ApplyState(m_PreResolvedEnable, m_PreResolvedMask);
		}
	}
```

- `public WasPerformedThisFrame() : System.Boolean`  

```csharp
public bool WasPerformedThisFrame()
	{
		return m_SourceAction.WasPerformedThisFrame();
	}
```

- `public WasPressedThisFrame() : System.Boolean`  

```csharp
public bool WasPressedThisFrame()
	{
		return m_SourceAction.WasPressedThisFrame();
	}
```

- `public WasReleasedThisFrame() : System.Boolean`  

```csharp
public bool WasReleasedThisFrame()
	{
		return m_SourceAction.WasReleasedThisFrame();
	}
```


## Events

- `onChanged` : `System.Action<Game.Input.ProxyAction>`  

```csharp
public event System.Action<Game.Input.ProxyAction> onChanged;
```

- `onInteraction` : `System.Action<Game.Input.ProxyAction, UnityEngine.InputSystem.InputActionPhase>`  

```csharp
public event System.Action<Game.Input.ProxyAction, UnityEngine.InputSystem.InputActionPhase> onInteraction;
```


## Nested types

- `Game.Input.ProxyAction+Info`  
- `Game.Input.ProxyAction+LinkInfo`  
- `Game.Input.ProxyAction+DeferActionUpdatingWrapper`  
- `Game.Input.ProxyAction+DeferActionStateUpdatingWrapper`  
- `Game.Input.ProxyAction+<>c`  
- `Game.Input.ProxyAction+<get_bindings>d__34`  

