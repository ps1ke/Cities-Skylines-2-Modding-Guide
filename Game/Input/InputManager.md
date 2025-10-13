# Game.Input.InputManager

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`, `UnityEngine.InputSystem.IInputActionCollection`, `System.Collections.Generic.IEnumerable<UnityEngine.InputSystem.InputAction>`, `System.Collections.IEnumerable`  

## Code

```csharp
public class InputManager : System.IDisposable, UnityEngine.InputSystem.IInputActionCollection, System.Collections.Generic.IEnumerable<UnityEngine.InputSystem.InputAction>, System.Collections.IEnumerable
{
    private System.Boolean m_NeedUpdate;
    private readonly Game.Input.InputConflictResolution m_ConflictResolution;
    private readonly UnityEngine.InputSystem.InputActionAsset m_ActionAsset;
    private readonly Game.Input.UIInputActionCollection m_UIActionCollection;
    private readonly Game.Input.UIInputActionCollection m_ToolActionCollection;
    private readonly System.Collections.Generic.Dictionary<System.String, Game.Input.ProxyActionMap> m_Maps;
    private System.Action<Game.Input.InputManager+ControlScheme> EventControlSchemeChanged;
    private Game.Input.InputManager+ActiveDeviceChanged EventActiveDeviceChanged;
    private System.Action EventActiveDeviceDisconnected;
    private System.Action EventActiveDeviceAssociationLost;
    private System.Action EventDevicePaired;
    private System.Action EventActionsChanged;
    private System.Action EventEnabledActionsChanged;
    private System.Action EventActionMasksChanged;
    private System.Action EventActionDisplayNamesChanged;
    private System.Action<System.Boolean> EventMouseOverUIChanged;
    private System.Action EventPreResolvedActionChanged;
    private System.Collections.Generic.Dictionary<UnityEngine.InputSystem.InputDevice, Game.Input.DeviceListener> m_DeviceListeners;
    private UnityEngine.InputSystem.InputDevice m_LastActiveDevice;
    private System.Boolean m_MouseOverUI;
    private System.Single m_AccumulatedIdleDelay;
    private System.Boolean m_WasWorldReady;
    private System.Boolean m_Idle;
    private System.Boolean m_HasFocus;
    private System.Boolean m_HasInputFieldFocus;
    private System.Boolean m_OverlayActive;
    private System.Boolean m_HideCursor;
    private Game.Input.InputManager+ControlScheme m_ActiveControlScheme;
    private UnityEngine.InputSystem.InputActionMap+DeviceArray m_Devices;
    private Game.Input.InputManager+DeviceType m_ConnectedDeviceTypes;
    private Game.Input.InputManager+DeviceType m_BlockedControlTypes;
    private Game.Input.InputManager+DeviceType m_Mask;
    private readonly System.Collections.Generic.Dictionary<Game.Input.ProxyBinding, Game.Input.ProxyBinding+Watcher> m_ProxyBindingWatchers;
    private System.ValueTuple<UnityEngine.Vector2, UnityEngine.Vector2> <caretRect>k__BackingField;
    private UnityEngine.InputSystem.Users.InputUser <inputUser>k__BackingField;
    private System.Int32 <actionVersion>k__BackingField;
    private readonly System.Collections.Generic.Dictionary<System.String, System.Collections.Generic.HashSet<Game.Input.ProxyAction>> <keyActionMap>k__BackingField;
    private readonly System.Collections.Generic.Dictionary<Game.Input.ProxyAction, System.Collections.Generic.HashSet<System.String>> <actionKeyMap>k__BackingField;
    private readonly System.Collections.Generic.Dictionary<System.Int32, Game.Input.ProxyAction> <actionIndex>k__BackingField;
    private Game.Input.InputManager+DeviceType <bindingConflicts>k__BackingField;
    private static System.Collections.Generic.IReadOnlyList<Game.Input.InputManager+CompositeData> m_Composites;
    private static UnityEngine.InputSystem.Layouts.InputControlLayout+Cache m_LayoutCache;
    private static System.Text.StringBuilder m_PathBuilder;
    private static System.Collections.Generic.Dictionary<Game.Input.InputManager+DeviceType, System.Collections.Generic.HashSet<System.String>> kModifiers;
    private static Game.Input.InputManager s_Instance;
    public static readonly Colossal.Logging.ILog log;
    private static System.String m_ProhibitionModifierProcessor;
    private static readonly Game.Input.InputManager+DeferManagerUpdatingWrapper sDeferUpdatingWrapper;
    public static const System.String kShiftName;
    public static const System.String kCtrlName;
    public static const System.String kAltName;
    public static const System.String kLeftStick;
    public static const System.String kRightStick;
    public static const System.String kSplashScreenMap;
    public static const System.String kNavigationMap;
    public static const System.String kMenuMap;
    public static const System.String kCameraMap;
    public static const System.String kToolMap;
    public static const System.String kShortcutsMap;
    public static const System.String kPhotoModeMap;
    public static const System.String kEditorMap;
    public static const System.String kDebugMap;
    public static const System.String kEngagementMap;
    public static const System.Int32 kIdleDelay;
    private static const System.String kKeyBindingConflict;
    private static const System.String kKeyBindingConflictResolved;

    public System.Collections.Generic.IEnumerable<Game.Input.ProxyAction> actions { get; }
    public static Game.Input.InputManager instance { get; }
    public System.Boolean mouseOverUI { get; set; }
    public System.Boolean hasInputFieldFocus { get; set; }
    public System.Boolean overlayActive { get; }
    public System.ValueTuple<UnityEngine.Vector2, UnityEngine.Vector2> caretRect { get; set; }
    public System.Boolean controlOverWorld { get; }
    private System.Nullable<UnityEngine.InputSystem.InputBinding> UnityEngine.InputSystem.IInputActionCollection.bindingMask { private get; private set; }
    private System.Nullable<UnityEngine.InputSystem.Utilities.ReadOnlyArray<UnityEngine.InputSystem.InputDevice>> UnityEngine.InputSystem.IInputActionCollection.devices { private get; private set; }
    private UnityEngine.InputSystem.Utilities.ReadOnlyArray<UnityEngine.InputSystem.InputControlScheme> UnityEngine.InputSystem.IInputActionCollection.controlSchemes { private get; }
    public Game.Input.InputManager+ControlScheme activeControlScheme { get; private set; }
    public System.Boolean isGamepadControlSchemeActive { get; }
    public System.Boolean isKeyboardAndMouseControlSchemeActive { get; }
    public Game.Input.InputManager+DeviceType connectedDeviceTypes { get; }
    internal Game.Input.InputManager+DeviceType mask { internal get; internal set; }
    internal Game.Input.InputManager+DeviceType blockedControlTypes { internal get; internal set; }
    public System.Boolean mouseOnScreen { get; }
    public UnityEngine.Vector2 gamepadPointerPosition { get; }
    public UnityEngine.Vector3 mousePosition { get; }
    public System.Boolean hideCursor { get; set; }
    public UnityEngine.CursorLockMode cursorLockMode { get; set; }
    public UnityEngine.InputSystem.Users.InputUser inputUser { get; private set; }
    public System.Int32 actionVersion { get; private set; }
    internal System.Collections.Generic.Dictionary<System.String, System.Collections.Generic.HashSet<Game.Input.ProxyAction>> keyActionMap { internal get; }
    internal System.Collections.Generic.Dictionary<Game.Input.ProxyAction, System.Collections.Generic.HashSet<System.String>> actionKeyMap { internal get; }
    internal System.Collections.Generic.Dictionary<System.Int32, Game.Input.ProxyAction> actionIndex { internal get; }
    private static System.String prohibitionModifierProcessor { private get; }
    internal Game.Input.UIInputActionCollection uiActionCollection { internal get; }
    internal Game.Input.UIInputActionCollection toolActionCollection { internal get; }
    public Game.Input.InputManager+DeviceType bindingConflicts { get; private set; }
    public static System.Boolean IsKeyboardConnected { get; }
    public static System.Boolean IsMouseConnected { get; }
    public static System.Boolean IsGamepadConnected { get; }

    public InputManager();

    private System.Void <SetBuiltInConflictNotification>b__210_0();
    private System.Void <SetBuiltInConflictNotification>g__Callback|210_1(System.Int32 msg);
    private Game.Input.ProxyActionMap AddActionMap(System.String name);
    internal System.Void AddActions(Game.Input.ProxyAction+Info[] actionsToAdd);
    public System.Void AddInitialDevices();
    public System.Void AssociateActionsWithUser(System.Boolean associate);
    public static System.Boolean CanConflict(Game.Input.ProxyAction action1, Game.Input.ProxyAction action2, Game.Input.InputManager+DeviceType device);
    internal System.Void CheckConflicts();
    public Game.Input.InputBarrier CreateActionBarrier(System.String map, System.String name, System.String barrierName);
    internal System.Void CreateCompositeBinding(UnityEngine.InputSystem.InputAction action, Game.Input.ProxyComposite+Info info);
    public Game.Input.InputBarrier CreateGlobalBarrier(System.String barrierName);
    public static System.Void CreateInstance();
    public Game.Input.InputBarrier CreateMapBarrier(System.String map, System.String barrierName);
    public Game.Input.InputBarrier CreateOverlayBarrier(System.String barrierName);
    internal static Game.Input.InputManager+DeferManagerUpdatingWrapper DeferUpdating();
    public static System.Void DestroyInstance();
    public System.Void Dispose();
    public Game.Input.ProxyAction FindAction(System.String mapName, System.String actionName);
    public Game.Input.ProxyAction FindAction(Game.Input.ProxyBinding binding);
    public Game.Input.ProxyAction FindAction(UnityEngine.InputSystem.InputAction action);
    public Game.Input.ProxyAction FindAction(System.Guid guid);
    public Game.Input.ProxyActionMap FindActionMap(System.String name);
    internal Game.Input.ProxyActionMap FindActionMap(UnityEngine.InputSystem.InputActionMap map);
    public static System.String GeneratePathForControl(UnityEngine.InputSystem.InputControl control);
    public Game.Input.InputManager+GamepadType GetActiveGamepadType();
    public static System.String GetBindingName(Game.Input.ActionComponent component);
    public System.Collections.Generic.List<Game.Input.ProxyBinding> GetBindings(Game.Input.InputManager+PathType pathType, Game.Input.InputManager+BindingOptions bindingOptions);
    public System.Collections.Generic.List<Game.Input.ProxyComposite> GetComposites(UnityEngine.InputSystem.InputAction action);
    public Game.Input.InputManager+GamepadType GetGamepadType(UnityEngine.InputSystem.Gamepad gamepad);
    private Game.Input.InputManager+DeviceType GetMaskForControlScheme();
    public static System.String GetModifierName(Game.Input.ActionComponent component);
    internal Game.Input.ProxyBinding+Watcher GetOrCreateBindingWatcher(Game.Input.ProxyBinding binding);
    private Game.Input.ProxyActionMap GetOrCreateMap(System.String name);
    public static System.Boolean HasConflicts(Game.Input.ProxyAction action1, Game.Input.ProxyAction action2, System.Nullable<Game.Input.InputManager+DeviceType> maskOverride1, System.Nullable<Game.Input.InputManager+DeviceType> maskOverride2);
    public System.Void Initialize();
    private System.Void InitializeAliases();
    private System.Void InitializeComposites();
    private System.Void InitializeLinkedActions();
    private System.Void InitializeMasks();
    internal System.Void InitializeMasks(Game.Input.ProxyAction action);
    private System.Void InitializeModifiers();
    private System.Void InitializeModifiers(UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax compositeIterator, UnityEngine.InputSystem.InputAction action, Game.Input.CompositeInstance compositeInstance);
    private System.Boolean IsDeviceTypePaired<T>();
    public static System.Boolean IsGamepadActive();
    internal System.Void OnActionChanged();
    internal System.Void OnActionDisplayNamesChanged();
    internal System.Void OnActionMasksChanged();
    private System.Void OnAddDevice(UnityEngine.InputSystem.InputDevice device);
    private System.Void OnDeviceActivated(UnityEngine.InputSystem.InputDevice newDevice);
    private System.Void OnDeviceAssociationChanged(Colossal.PSI.Common.IPlatformServiceIntegration psi, Colossal.PSI.Common.DeviceAssociationChange change);
    private System.Void OnDeviceChange(UnityEngine.InputSystem.InputDevice device, UnityEngine.InputSystem.InputDeviceChange change);
    internal System.Void OnEnabledActionsChanged();
    public System.Void OnFocusChanged(System.Boolean hasFocus);
    private System.Void OnOverlayStateChanged(Colossal.PSI.Common.IOverlaySupport psi, System.Boolean active);
    internal System.Void OnPreResolvedActionChanged();
    private System.Void OnRemoveDevice(UnityEngine.InputSystem.InputDevice device);
    private System.Void OnUnpairedDeviceUsed(UnityEngine.InputSystem.InputDevice device);
    private System.Void PairDevice(UnityEngine.InputSystem.InputDevice device);
    private System.Void ProcessActionsUpdate(System.Boolean ignoreDefer);
    private System.Void RefreshActiveControl();
    public System.Void ResetAllBindings(System.Boolean onlyBuiltIn);
    public System.Void ResetGroupBindings(Game.Input.InputManager+DeviceType device, System.Boolean onlyBuiltIn);
    public System.Boolean SetBinding(Game.Input.ProxyBinding newBinding, Game.Input.ProxyBinding& result);
    private System.Boolean SetBindingImpl(Game.Input.ProxyBinding bindingToSet, Game.Input.ProxyBinding& newBinding);
    public System.Boolean SetBindings(System.Collections.Generic.IEnumerable<Game.Input.ProxyBinding> newBindings, System.Collections.Generic.List`1[[Game.Input.ProxyBinding, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resultBindings);
    private System.Void SetBuiltInConflictNotification(System.Boolean conflict);
    public System.Void SetDefaultControlScheme();
    private System.Void SetModConflictNotification(Game.Input.ProxyActionMap map, System.Boolean conflict);
    private System.Collections.Generic.IEnumerator<UnityEngine.InputSystem.InputAction> System.Collections.Generic.IEnumerable<UnityEngine.InputSystem.InputAction>.GetEnumerator();
    private System.Collections.IEnumerator System.Collections.IEnumerable.GetEnumerator();
    public System.Boolean TryFindAction(System.String mapName, System.String actionName, Game.Input.ProxyAction& action);
    public System.Boolean TryFindAction(Game.Input.ProxyBinding binding, Game.Input.ProxyAction& action);
    public System.Boolean TryFindAction(UnityEngine.InputSystem.InputAction action, Game.Input.ProxyAction& proxyAction);
    public System.Boolean TryFindAction(System.Guid guid, Game.Input.ProxyAction& proxyAction);
    internal System.Boolean TryFindAction(System.Int32 index, Game.Input.ProxyAction& action);
    public System.Boolean TryFindActionMap(System.String name, Game.Input.ProxyActionMap& map);
    internal System.Boolean TryFindActionMap(UnityEngine.InputSystem.InputActionMap map, Game.Input.ProxyActionMap& proxyMap);
    public System.Boolean TryGetBinding(Game.Input.ProxyBinding bindingToGet, Game.Input.InputManager+PathType pathType, Game.Input.InputManager+BindingOptions bindingOptions, Game.Input.ProxyBinding& foundBinding);
    private System.Boolean TryGetBinding(UnityEngine.InputSystem.InputAction action, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax compositeIterator, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax bindingIterator, Game.Input.CompositeInstance compositeInstance, Game.Input.InputManager+CompositeComponentData componentData, Game.Input.InputManager+PathType pathType, Game.Input.InputManager+BindingOptions bindingOptions, Game.Input.ProxyBinding& foundBinding);
    private System.Boolean TryGetComposite(UnityEngine.InputSystem.InputAction action, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax compositeIterator, Game.Input.InputManager+PathType pathType, Game.Input.InputManager+BindingOptions bindingOptions, Game.Input.ProxyComposite& proxyComposite);
    internal static System.Boolean TryGetCompositeData(System.String name, Game.Input.InputManager+CompositeData& data);
    internal static System.Boolean TryGetCompositeData(Game.Input.ActionType actionType, Game.Input.InputManager+CompositeData& data);
    private System.Boolean TryGetCompositeInstance(UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax compositeIterator, Game.Input.CompositeInstance& compositeInstance);
    private System.Boolean TryGetIterators(Game.Input.ProxyBinding bindingSample, UnityEngine.InputSystem.InputAction action, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax& compositeIterator, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax& bindingIterator, Game.Input.CompositeInstance& compositeInstance, Game.Input.InputManager+CompositeComponentData& componentData);
    public System.Boolean TryGetMainBinding(UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax iterator, Game.Input.InputManager+PathType pathType, System.String& currentPath, System.String& originalPath);
    public System.Boolean TryGetModifierBindings(UnityEngine.InputSystem.InputAction action, Game.Input.CompositeInstance compositeInstance, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax compositeIterator, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax iterator, Game.Input.InputManager+PathType pathType, Game.Input.InputManager+CompositeComponentData componentData, Game.Input.ProxyModifier[]& currentModifiers, Game.Input.ProxyModifier[]& originalModifiers);
    private System.Boolean TryPairDevice(UnityEngine.InputSystem.InputDevice device);
    private System.Boolean TrySetBindingModifierProcessor(UnityEngine.InputSystem.InputAction action, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax modifierIterator, System.Boolean allow);
    private System.Boolean TrySetMainBinding(Game.Input.ProxyBinding bindingToSet, UnityEngine.InputSystem.InputAction action, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax bindingIterator, System.Boolean& changed);
    private System.Boolean TrySetModifierBindings(Game.Input.ProxyBinding bindingToSet, UnityEngine.InputSystem.InputAction action, Game.Input.CompositeInstance compositeInstance, Game.Input.InputManager+CompositeComponentData componentData, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax compositeIterator, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax bindingIterator, System.Boolean& changed);
    private System.Boolean TryUnpairDevice(UnityEngine.InputSystem.InputDevice device);
    private System.Boolean UnityEngine.InputSystem.IInputActionCollection.Contains(UnityEngine.InputSystem.InputAction action);
    private System.Void UnityEngine.InputSystem.IInputActionCollection.Disable();
    private System.Void UnityEngine.InputSystem.IInputActionCollection.Enable();
    private System.Void UnpairAll<T>();
    private System.Void UnpairDevice(UnityEngine.InputSystem.InputDevice device);
    public System.Void Update();
    internal System.Void UpdateActionInKeyActionMap(Game.Input.ProxyAction action);
    private System.Void UpdateConnectedDeviceTypes();
    private System.Void UpdateCursorVisibility();
}
```


## Fields

- `private System.Boolean m_NeedUpdate`  

```csharp
private System.Boolean m_NeedUpdate;
```

- `private readonly Game.Input.InputConflictResolution m_ConflictResolution`  

```csharp
private readonly Game.Input.InputConflictResolution m_ConflictResolution;
```

- `private readonly UnityEngine.InputSystem.InputActionAsset m_ActionAsset`  

```csharp
private readonly UnityEngine.InputSystem.InputActionAsset m_ActionAsset;
```

- `private readonly Game.Input.UIInputActionCollection m_UIActionCollection`  

```csharp
private readonly Game.Input.UIInputActionCollection m_UIActionCollection;
```

- `private readonly Game.Input.UIInputActionCollection m_ToolActionCollection`  

```csharp
private readonly Game.Input.UIInputActionCollection m_ToolActionCollection;
```

- `private readonly System.Collections.Generic.Dictionary<System.String, Game.Input.ProxyActionMap> m_Maps`  

```csharp
private readonly System.Collections.Generic.Dictionary<System.String, Game.Input.ProxyActionMap> m_Maps;
```

- `private System.Action<Game.Input.InputManager+ControlScheme> EventControlSchemeChanged`  

```csharp
private System.Action<Game.Input.InputManager+ControlScheme> EventControlSchemeChanged;
```

- `private Game.Input.InputManager+ActiveDeviceChanged EventActiveDeviceChanged`  

```csharp
private Game.Input.InputManager+ActiveDeviceChanged EventActiveDeviceChanged;
```

- `private System.Action EventActiveDeviceDisconnected`  

```csharp
private System.Action EventActiveDeviceDisconnected;
```

- `private System.Action EventActiveDeviceAssociationLost`  

```csharp
private System.Action EventActiveDeviceAssociationLost;
```

- `private System.Action EventDevicePaired`  

```csharp
private System.Action EventDevicePaired;
```

- `private System.Action EventActionsChanged`  

```csharp
private System.Action EventActionsChanged;
```

- `private System.Action EventEnabledActionsChanged`  

```csharp
private System.Action EventEnabledActionsChanged;
```

- `private System.Action EventActionMasksChanged`  

```csharp
private System.Action EventActionMasksChanged;
```

- `private System.Action EventActionDisplayNamesChanged`  

```csharp
private System.Action EventActionDisplayNamesChanged;
```

- `private System.Action<System.Boolean> EventMouseOverUIChanged`  

```csharp
private System.Action<System.Boolean> EventMouseOverUIChanged;
```

- `private System.Action EventPreResolvedActionChanged`  

```csharp
private System.Action EventPreResolvedActionChanged;
```

- `private System.Collections.Generic.Dictionary<UnityEngine.InputSystem.InputDevice, Game.Input.DeviceListener> m_DeviceListeners`  

```csharp
private System.Collections.Generic.Dictionary<UnityEngine.InputSystem.InputDevice, Game.Input.DeviceListener> m_DeviceListeners;
```

- `private UnityEngine.InputSystem.InputDevice m_LastActiveDevice`  

```csharp
private UnityEngine.InputSystem.InputDevice m_LastActiveDevice;
```

- `private System.Boolean m_MouseOverUI`  

```csharp
private System.Boolean m_MouseOverUI;
```

- `private System.Single m_AccumulatedIdleDelay`  

```csharp
private System.Single m_AccumulatedIdleDelay;
```

- `private System.Boolean m_WasWorldReady`  

```csharp
private System.Boolean m_WasWorldReady;
```

- `private System.Boolean m_Idle`  

```csharp
private System.Boolean m_Idle;
```

- `private System.Boolean m_HasFocus`  

```csharp
private System.Boolean m_HasFocus;
```

- `private System.Boolean m_HasInputFieldFocus`  

```csharp
private System.Boolean m_HasInputFieldFocus;
```

- `private System.Boolean m_OverlayActive`  

```csharp
private System.Boolean m_OverlayActive;
```

- `private System.Boolean m_HideCursor`  

```csharp
private System.Boolean m_HideCursor;
```

- `private Game.Input.InputManager+ControlScheme m_ActiveControlScheme`  

```csharp
private Game.Input.InputManager+ControlScheme m_ActiveControlScheme;
```

- `private UnityEngine.InputSystem.InputActionMap+DeviceArray m_Devices`  

```csharp
private UnityEngine.InputSystem.InputActionMap+DeviceArray m_Devices;
```

- `private Game.Input.InputManager+DeviceType m_ConnectedDeviceTypes`  

```csharp
private Game.Input.InputManager+DeviceType m_ConnectedDeviceTypes;
```

- `private Game.Input.InputManager+DeviceType m_BlockedControlTypes`  

```csharp
private Game.Input.InputManager+DeviceType m_BlockedControlTypes;
```

- `private Game.Input.InputManager+DeviceType m_Mask`  

```csharp
private Game.Input.InputManager+DeviceType m_Mask;
```

- `private readonly System.Collections.Generic.Dictionary<Game.Input.ProxyBinding, Game.Input.ProxyBinding+Watcher> m_ProxyBindingWatchers`  

```csharp
private readonly System.Collections.Generic.Dictionary<Game.Input.ProxyBinding, Game.Input.ProxyBinding+Watcher> m_ProxyBindingWatchers;
```

- `private System.ValueTuple<UnityEngine.Vector2, UnityEngine.Vector2> <caretRect>k__BackingField`  

```csharp
private System.ValueTuple<UnityEngine.Vector2, UnityEngine.Vector2> <caretRect>k__BackingField;
```

- `private UnityEngine.InputSystem.Users.InputUser <inputUser>k__BackingField`  

```csharp
private UnityEngine.InputSystem.Users.InputUser <inputUser>k__BackingField;
```

- `private System.Int32 <actionVersion>k__BackingField`  

```csharp
private System.Int32 <actionVersion>k__BackingField;
```

- `private readonly System.Collections.Generic.Dictionary<System.String, System.Collections.Generic.HashSet<Game.Input.ProxyAction>> <keyActionMap>k__BackingField`  

```csharp
private readonly System.Collections.Generic.Dictionary<System.String, System.Collections.Generic.HashSet<Game.Input.ProxyAction>> <keyActionMap>k__BackingField;
```

- `private readonly System.Collections.Generic.Dictionary<Game.Input.ProxyAction, System.Collections.Generic.HashSet<System.String>> <actionKeyMap>k__BackingField`  

```csharp
private readonly System.Collections.Generic.Dictionary<Game.Input.ProxyAction, System.Collections.Generic.HashSet<System.String>> <actionKeyMap>k__BackingField;
```

- `private readonly System.Collections.Generic.Dictionary<System.Int32, Game.Input.ProxyAction> <actionIndex>k__BackingField`  

```csharp
private readonly System.Collections.Generic.Dictionary<System.Int32, Game.Input.ProxyAction> <actionIndex>k__BackingField;
```

- `private Game.Input.InputManager+DeviceType <bindingConflicts>k__BackingField`  

```csharp
private Game.Input.InputManager+DeviceType <bindingConflicts>k__BackingField;
```

- `private static System.Collections.Generic.IReadOnlyList<Game.Input.InputManager+CompositeData> m_Composites`  

```csharp
private static System.Collections.Generic.IReadOnlyList<Game.Input.InputManager+CompositeData> m_Composites;
```

- `private static UnityEngine.InputSystem.Layouts.InputControlLayout+Cache m_LayoutCache`  

```csharp
private static UnityEngine.InputSystem.Layouts.InputControlLayout+Cache m_LayoutCache;
```

- `private static System.Text.StringBuilder m_PathBuilder`  

```csharp
private static System.Text.StringBuilder m_PathBuilder;
```

- `private static System.Collections.Generic.Dictionary<Game.Input.InputManager+DeviceType, System.Collections.Generic.HashSet<System.String>> kModifiers`  

```csharp
private static System.Collections.Generic.Dictionary<Game.Input.InputManager+DeviceType, System.Collections.Generic.HashSet<System.String>> kModifiers;
```

- `private static Game.Input.InputManager s_Instance`  

```csharp
private static Game.Input.InputManager s_Instance;
```

- `public static readonly Colossal.Logging.ILog log`  

```csharp
public static readonly Colossal.Logging.ILog log;
```

- `private static System.String m_ProhibitionModifierProcessor`  

```csharp
private static System.String m_ProhibitionModifierProcessor;
```

- `private static readonly Game.Input.InputManager+DeferManagerUpdatingWrapper sDeferUpdatingWrapper`  

```csharp
private static readonly Game.Input.InputManager+DeferManagerUpdatingWrapper sDeferUpdatingWrapper;
```

- `public static const System.String kShiftName`  

```csharp
public static const System.String kShiftName;
```

- `public static const System.String kCtrlName`  

```csharp
public static const System.String kCtrlName;
```

- `public static const System.String kAltName`  

```csharp
public static const System.String kAltName;
```

- `public static const System.String kLeftStick`  

```csharp
public static const System.String kLeftStick;
```

- `public static const System.String kRightStick`  

```csharp
public static const System.String kRightStick;
```

- `public static const System.String kSplashScreenMap`  

```csharp
public static const System.String kSplashScreenMap;
```

- `public static const System.String kNavigationMap`  

```csharp
public static const System.String kNavigationMap;
```

- `public static const System.String kMenuMap`  

```csharp
public static const System.String kMenuMap;
```

- `public static const System.String kCameraMap`  

```csharp
public static const System.String kCameraMap;
```

- `public static const System.String kToolMap`  

```csharp
public static const System.String kToolMap;
```

- `public static const System.String kShortcutsMap`  

```csharp
public static const System.String kShortcutsMap;
```

- `public static const System.String kPhotoModeMap`  

```csharp
public static const System.String kPhotoModeMap;
```

- `public static const System.String kEditorMap`  

```csharp
public static const System.String kEditorMap;
```

- `public static const System.String kDebugMap`  

```csharp
public static const System.String kDebugMap;
```

- `public static const System.String kEngagementMap`  

```csharp
public static const System.String kEngagementMap;
```

- `public static const System.Int32 kIdleDelay`  

```csharp
public static const System.Int32 kIdleDelay;
```

- `private static const System.String kKeyBindingConflict`  

```csharp
private static const System.String kKeyBindingConflict;
```

- `private static const System.String kKeyBindingConflictResolved`  

```csharp
private static const System.String kKeyBindingConflictResolved;
```


## Properties

- `public System.Collections.Generic.IEnumerable<Game.Input.ProxyAction> actions { get }`  

```csharp
public System.Collections.Generic.IEnumerable<Game.Input.ProxyAction> actions { get; }
```

- `public static Game.Input.InputManager instance { get }`  

```csharp
public static Game.Input.InputManager instance { get; }
```

- `public System.Boolean mouseOverUI { get; set }`  

```csharp
public System.Boolean mouseOverUI { get; set; }
```

- `public System.Boolean hasInputFieldFocus { get; set }`  

```csharp
public System.Boolean hasInputFieldFocus { get; set; }
```

- `public System.Boolean overlayActive { get }`  

```csharp
public System.Boolean overlayActive { get; }
```

- `public System.ValueTuple<UnityEngine.Vector2, UnityEngine.Vector2> caretRect { get; set }`  

```csharp
public System.ValueTuple<UnityEngine.Vector2, UnityEngine.Vector2> caretRect { get; set; }
```

- `public System.Boolean controlOverWorld { get }`  

```csharp
public System.Boolean controlOverWorld { get; }
```

- `private System.Nullable<UnityEngine.InputSystem.InputBinding> UnityEngine.InputSystem.IInputActionCollection.bindingMask { private get; private set }`  

```csharp
private System.Nullable<UnityEngine.InputSystem.InputBinding> UnityEngine.InputSystem.IInputActionCollection.bindingMask { private get; private set; }
```

- `private System.Nullable<UnityEngine.InputSystem.Utilities.ReadOnlyArray<UnityEngine.InputSystem.InputDevice>> UnityEngine.InputSystem.IInputActionCollection.devices { private get; private set }`  

```csharp
private System.Nullable<UnityEngine.InputSystem.Utilities.ReadOnlyArray<UnityEngine.InputSystem.InputDevice>> UnityEngine.InputSystem.IInputActionCollection.devices { private get; private set; }
```

- `private UnityEngine.InputSystem.Utilities.ReadOnlyArray<UnityEngine.InputSystem.InputControlScheme> UnityEngine.InputSystem.IInputActionCollection.controlSchemes { private get }`  

```csharp
private UnityEngine.InputSystem.Utilities.ReadOnlyArray<UnityEngine.InputSystem.InputControlScheme> UnityEngine.InputSystem.IInputActionCollection.controlSchemes { private get; }
```

- `public Game.Input.InputManager+ControlScheme activeControlScheme { get; private set }`  

```csharp
public Game.Input.InputManager+ControlScheme activeControlScheme { get; private set; }
```

- `public System.Boolean isGamepadControlSchemeActive { get }`  

```csharp
public System.Boolean isGamepadControlSchemeActive { get; }
```

- `public System.Boolean isKeyboardAndMouseControlSchemeActive { get }`  

```csharp
public System.Boolean isKeyboardAndMouseControlSchemeActive { get; }
```

- `public Game.Input.InputManager+DeviceType connectedDeviceTypes { get }`  

```csharp
public Game.Input.InputManager+DeviceType connectedDeviceTypes { get; }
```

- `internal Game.Input.InputManager+DeviceType mask { internal get; internal set }`  

```csharp
internal Game.Input.InputManager+DeviceType mask { internal get; internal set; }
```

- `internal Game.Input.InputManager+DeviceType blockedControlTypes { internal get; internal set }`  

```csharp
internal Game.Input.InputManager+DeviceType blockedControlTypes { internal get; internal set; }
```

- `public System.Boolean mouseOnScreen { get }`  

```csharp
public System.Boolean mouseOnScreen { get; }
```

- `public UnityEngine.Vector2 gamepadPointerPosition { get }`  

```csharp
public UnityEngine.Vector2 gamepadPointerPosition { get; }
```

- `public UnityEngine.Vector3 mousePosition { get }`  

```csharp
public UnityEngine.Vector3 mousePosition { get; }
```

- `public System.Boolean hideCursor { get; set }`  

```csharp
public System.Boolean hideCursor { get; set; }
```

- `public UnityEngine.CursorLockMode cursorLockMode { get; set }`  

```csharp
public UnityEngine.CursorLockMode cursorLockMode { get; set; }
```

- `public UnityEngine.InputSystem.Users.InputUser inputUser { get; private set }`  

```csharp
public UnityEngine.InputSystem.Users.InputUser inputUser { get; private set; }
```

- `public System.Int32 actionVersion { get; private set }`  

```csharp
public System.Int32 actionVersion { get; private set; }
```

- `internal System.Collections.Generic.Dictionary<System.String, System.Collections.Generic.HashSet<Game.Input.ProxyAction>> keyActionMap { internal get }`  

```csharp
internal System.Collections.Generic.Dictionary<System.String, System.Collections.Generic.HashSet<Game.Input.ProxyAction>> keyActionMap { internal get; }
```

- `internal System.Collections.Generic.Dictionary<Game.Input.ProxyAction, System.Collections.Generic.HashSet<System.String>> actionKeyMap { internal get }`  

```csharp
internal System.Collections.Generic.Dictionary<Game.Input.ProxyAction, System.Collections.Generic.HashSet<System.String>> actionKeyMap { internal get; }
```

- `internal System.Collections.Generic.Dictionary<System.Int32, Game.Input.ProxyAction> actionIndex { internal get }`  

```csharp
internal System.Collections.Generic.Dictionary<System.Int32, Game.Input.ProxyAction> actionIndex { internal get; }
```

- `private static System.String prohibitionModifierProcessor { private get }`  

```csharp
private static System.String prohibitionModifierProcessor { private get; }
```

- `internal Game.Input.UIInputActionCollection uiActionCollection { internal get }`  

```csharp
internal Game.Input.UIInputActionCollection uiActionCollection { internal get; }
```

- `internal Game.Input.UIInputActionCollection toolActionCollection { internal get }`  

```csharp
internal Game.Input.UIInputActionCollection toolActionCollection { internal get; }
```

- `public Game.Input.InputManager+DeviceType bindingConflicts { get; private set }`  

```csharp
public Game.Input.InputManager+DeviceType bindingConflicts { get; private set; }
```

- `public static System.Boolean IsKeyboardConnected { get }`  

```csharp
public static System.Boolean IsKeyboardConnected { get; }
```

- `public static System.Boolean IsMouseConnected { get }`  

```csharp
public static System.Boolean IsMouseConnected { get; }
```

- `public static System.Boolean IsGamepadConnected { get }`  

```csharp
public static System.Boolean IsGamepadConnected { get; }
```


## Constructors

- `public InputManager()`  

```csharp
public InputManager()
	{
		log.Debug("Creating InputManager");
		OnFocusChanged(Application.isFocused);
		m_ActionAsset = Resources.Load<InputActionAsset>("Input/InputActions");
		m_UIActionCollection = Resources.Load<UIInputActionCollection>("Input/UI Input Actions");
		m_ToolActionCollection = Resources.Load<UIInputActionCollection>("Input/Tool Input Actions");
		InputActionMap[] actionMaps = m_ActionAsset.m_ActionMaps;
		foreach (InputActionMap obj in actionMaps)
		{
			obj.m_Asset = null;
			ProxyActionMap proxyActionMap = new ProxyActionMap(obj);
			m_Maps.Add(proxyActionMap.name, proxyActionMap);
		}
	}
```


## Methods

- `private <SetBuiltInConflictNotification>b__210_0() : System.Void`  

```csharp
private System.Void <SetBuiltInConflictNotification>b__210_0();
```

- `private <SetBuiltInConflictNotification>g__Callback|210_1(System.Int32 msg) : System.Void`  

```csharp
private System.Void <SetBuiltInConflictNotification>g__Callback|210_1(System.Int32 msg);
```

- `private AddActionMap(System.String name) : Game.Input.ProxyActionMap`  

```csharp
private ProxyActionMap AddActionMap(string name)
	{
		using (DeferUpdating())
		{
			InputActionMap inputActionMap = new InputActionMap(name);
			inputActionMap.GenerateId();
			ProxyActionMap proxyActionMap = new ProxyActionMap(inputActionMap);
			m_Maps.Add(proxyActionMap.name, proxyActionMap);
			return proxyActionMap;
		}
	}
```

- `internal AddActions(Game.Input.ProxyAction+Info[] actionsToAdd) : System.Void`  

```csharp
internal void AddActions(ProxyAction.Info[] actionsToAdd)
	{
		ProxyAction[] array = new ProxyAction[actionsToAdd.Length];
		using (DeferUpdating())
		{
			for (int i = 0; i < actionsToAdd.Length; i++)
			{
				ProxyActionMap orCreateMap = GetOrCreateMap(actionsToAdd[i].m_Map);
				array[i] = orCreateMap.AddAction(actionsToAdd[i], bulk: true);
			}
		}
		ProxyActionMap[] array2 = array.Select((ProxyAction a) => a.map).Distinct().ToArray();
		for (int num = 0; num < array2.Length; num++)
		{
			array2[num].UpdateState();
		}
	}
```

- `public AddInitialDevices() : System.Void`  

```csharp
public void AddInitialDevices()
	{
		foreach (InputDevice device in InputSystem.devices)
		{
			OnAddDevice(device);
		}
	}
```

- `public AssociateActionsWithUser(System.Boolean associate) : System.Void`  

```csharp
public void AssociateActionsWithUser(bool associate)
	{
		if (inputUser.valid)
		{
			if (associate)
			{
				inputUser.AssociateActionsWithUser(this);
			}
			else
			{
				inputUser.AssociateActionsWithUser(null);
			}
		}
	}
```

- `public static CanConflict(Game.Input.ProxyAction action1, Game.Input.ProxyAction action2, Game.Input.InputManager+DeviceType device) : System.Boolean`  

```csharp
public static bool CanConflict(ProxyAction action1, ProxyAction action2, DeviceType device)
	{
		if (action1 == action2)
		{
			return false;
		}
		if (action1.m_LinkedActions.Contains(new ProxyAction.LinkInfo
		{
			m_Action = action2,
			m_Device = device
		}))
		{
			return false;
		}
		if (action2.m_LinkedActions.Contains(new ProxyAction.LinkInfo
		{
			m_Action = action1,
			m_Device = device
		}))
		{
			return false;
		}
		return true;
	}
```

- `internal CheckConflicts() : System.Void`  

```csharp
internal void CheckConflicts()
	{
		if (GameManager.instance != null && GameManager.instance.state < GameManager.State.UIReady)
		{
			return;
		}
		bindingConflicts = DeviceType.None;
		foreach (KeyValuePair<string, ProxyActionMap> map in m_Maps)
		{
			map.Deconstruct(out var key, out var value);
			ProxyActionMap proxyActionMap = value;
			bool flag = false;
			foreach (KeyValuePair<string, ProxyAction> action in proxyActionMap.actions)
			{
				action.Deconstruct(out key, out var value2);
				ProxyAction proxyAction = value2;
				if ((proxyAction.availableDevices & ~bindingConflicts) == 0)
				{
					continue;
				}
				foreach (var (_, proxyComposite2) in proxyAction.composites)
				{
					if ((proxyComposite2.m_Device & ~bindingConflicts) == 0)
					{
						continue;
					}
					foreach (var (_, proxyBinding2) in proxyComposite2.bindings)
					{
						if ((proxyBinding2.hasConflicts & ProxyBinding.ConflictType.WithBuiltIn) != ProxyBinding.ConflictType.None)
						{
							if (proxyBinding2.isBuiltIn)
							{
								bindingConflicts |= proxyBinding2.device;
							}
							else
							{
								flag = true;
							}
						}
					}
				}
				if (bindingConflicts == DeviceType.All && flag)
				{
					break;
				}
			}
			SetModConflictNotification(proxyActionMap, flag);
		}
		SetBuiltInConflictNotification(bindingConflicts != DeviceType.None);
	}
```

- `public CreateActionBarrier(System.String map, System.String name, System.String barrierName) : Game.Input.InputBarrier`  

```csharp
public InputBarrier CreateActionBarrier(string map, string name, string barrierName)
	{
		return new InputBarrier(barrierName, FindAction(map, name));
	}
```

- `internal CreateCompositeBinding(UnityEngine.InputSystem.InputAction action, Game.Input.ProxyComposite+Info info) : System.Void`  

```csharp
internal void CreateCompositeBinding(InputAction action, ProxyComposite.Info info)
	{
		string composite = $"{info.m_Source.parameters}{';'}{info.m_Source.usages.parameters}";
		string interactions = string.Join(";", info.m_Source.interactions);
		string processors = string.Join(";", info.m_Source.processors);
		InputActionSetupExtensions.CompositeSyntax compositeSyntax = action.AddCompositeBinding(composite, interactions, processors);
		new InputActionSetupExtensions.BindingSyntax(action.m_ActionMap, action.BindingIndexOnActionToBindingIndexOnMap(compositeSyntax.bindingIndex), action).WithName(info.m_Device.ToString());
		foreach (ProxyBinding binding in info.m_Bindings)
		{
			if (!info.m_Source.compositeData.TryGetData(binding.component, out var data))
			{
				continue;
			}
			compositeSyntax.With(data.m_BindingName, binding.path, binding.device.ToString());
			if (!info.m_Source.allowModifiers || !kModifiers.TryGetValue(binding.device, out var value))
			{
				continue;
			}
			foreach (string supportedModifier in value)
			{
				string processors2 = (binding.modifiers.Any((ProxyModifier m) => m.m_Path == supportedModifier) ? string.Empty : prohibitionModifierProcessor);
				compositeSyntax.With(data.m_ModifierName, supportedModifier, binding.device.ToString(), processors2);
			}
		}
	}
```

- `public CreateGlobalBarrier(System.String barrierName) : Game.Input.InputBarrier`  

```csharp
public InputBarrier CreateGlobalBarrier(string barrierName)
	{
		return new InputBarrier(barrierName, m_Maps.Values.ToArray());
	}
```

- `public static CreateInstance() : System.Void`  

```csharp
public static void CreateInstance()
	{
		s_Instance = new InputManager();
		s_Instance.Initialize();
	}
```

- `public CreateMapBarrier(System.String map, System.String barrierName) : Game.Input.InputBarrier`  

```csharp
public InputBarrier CreateMapBarrier(string map, string barrierName)
	{
		return new InputBarrier(barrierName, FindActionMap(map));
	}
```

- `public CreateOverlayBarrier(System.String barrierName) : Game.Input.InputBarrier`  

```csharp
public InputBarrier CreateOverlayBarrier(string barrierName)
	{
		ProxyActionMap[] maps = m_Maps.Values.Where((ProxyActionMap actionMap) => actionMap.name != "Engagement" && actionMap.name != "Splash screen").ToArray();
		return new InputBarrier(barrierName, maps, DeviceType.All, blocked: true);
	}
```

- `internal static DeferUpdating() : Game.Input.InputManager+DeferManagerUpdatingWrapper`  

```csharp
internal static DeferManagerUpdatingWrapper DeferUpdating()
	{
		sDeferUpdatingWrapper.Acquire();
		return sDeferUpdatingWrapper;
	}
```

- `public static DestroyInstance() : System.Void`  

```csharp
public static void DestroyInstance()
	{
		s_Instance?.Dispose();
		s_Instance = null;
	}
```

- `public Dispose() : System.Void`  

```csharp
public void Dispose()
	{
		log.Debug("Disposing InputManager");
		if (inputUser.valid)
		{
			inputUser.UnpairDevicesAndRemoveUser();
		}
		InputSystem.onDeviceChange -= OnDeviceChange;
		foreach (KeyValuePair<InputDevice, DeviceListener> deviceListener in m_DeviceListeners)
		{
			deviceListener.Deconstruct(out var _, out var value);
			value.StopListening();
		}
		PlatformManager.instance.onDeviceAssociationChanged -= OnDeviceAssociationChanged;
		PlatformManager.instance.onOverlayStateChanged -= OnOverlayStateChanged;
	}
```

- `public FindAction(System.String mapName, System.String actionName) : Game.Input.ProxyAction`  

```csharp
public ProxyAction FindAction(Guid guid)
	{
		foreach (KeyValuePair<string, ProxyActionMap> map in m_Maps)
		{
			map.Deconstruct(out var key, out var value);
			foreach (KeyValuePair<string, ProxyAction> action in value.actions)
			{
				action.Deconstruct(out key, out var value2);
				ProxyAction proxyAction = value2;
				if (proxyAction.sourceAction.id == guid)
				{
					value2 = proxyAction;
					return value2;
				}
			}
		}
		return null;
	}
```

- `public FindAction(Game.Input.ProxyBinding binding) : Game.Input.ProxyAction`  

```csharp
public ProxyAction FindAction(Guid guid)
	{
		foreach (KeyValuePair<string, ProxyActionMap> map in m_Maps)
		{
			map.Deconstruct(out var key, out var value);
			foreach (KeyValuePair<string, ProxyAction> action in value.actions)
			{
				action.Deconstruct(out key, out var value2);
				ProxyAction proxyAction = value2;
				if (proxyAction.sourceAction.id == guid)
				{
					value2 = proxyAction;
					return value2;
				}
			}
		}
		return null;
	}
```

- `public FindAction(UnityEngine.InputSystem.InputAction action) : Game.Input.ProxyAction`  

```csharp
public ProxyAction FindAction(Guid guid)
	{
		foreach (KeyValuePair<string, ProxyActionMap> map in m_Maps)
		{
			map.Deconstruct(out var key, out var value);
			foreach (KeyValuePair<string, ProxyAction> action in value.actions)
			{
				action.Deconstruct(out key, out var value2);
				ProxyAction proxyAction = value2;
				if (proxyAction.sourceAction.id == guid)
				{
					value2 = proxyAction;
					return value2;
				}
			}
		}
		return null;
	}
```

- `public FindAction(System.Guid guid) : Game.Input.ProxyAction`  

```csharp
public ProxyAction FindAction(Guid guid)
	{
		foreach (KeyValuePair<string, ProxyActionMap> map in m_Maps)
		{
			map.Deconstruct(out var key, out var value);
			foreach (KeyValuePair<string, ProxyAction> action in value.actions)
			{
				action.Deconstruct(out key, out var value2);
				ProxyAction proxyAction = value2;
				if (proxyAction.sourceAction.id == guid)
				{
					value2 = proxyAction;
					return value2;
				}
			}
		}
		return null;
	}
```

- `public FindActionMap(System.String name) : Game.Input.ProxyActionMap`  

```csharp
internal ProxyActionMap FindActionMap(InputActionMap map)
	{
		return FindActionMap(map?.name);
	}
```

- `internal FindActionMap(UnityEngine.InputSystem.InputActionMap map) : Game.Input.ProxyActionMap`  

```csharp
internal ProxyActionMap FindActionMap(InputActionMap map)
	{
		return FindActionMap(map?.name);
	}
```

- `public static GeneratePathForControl(UnityEngine.InputSystem.InputControl control) : System.String`  

```csharp
public static string GeneratePathForControl(InputControl control)
	{
		InputDevice device = control.device;
		UnityEngine.Debug.Assert(control != device, "Control must not be a device");
		InternedString internedString = InputControlLayout.s_Layouts.FindLayoutThatIntroducesControl(control, m_LayoutCache);
		if (m_PathBuilder == null)
		{
			m_PathBuilder = new StringBuilder();
		}
		m_PathBuilder.Length = 0;
		control.BuildPath(internedString, m_PathBuilder);
		return m_PathBuilder.ToString();
	}
```

- `public GetActiveGamepadType() : Game.Input.InputManager+GamepadType`  

```csharp
public GamepadType GetActiveGamepadType()
	{
		return GetGamepadType(Gamepad.current);
	}
```

- `public static GetBindingName(Game.Input.ActionComponent component) : System.String`  

```csharp
public static string GetBindingName(ActionComponent component)
	{
		if (TryGetCompositeData(component.GetActionType(), out var data) && data.TryGetData(component, out var data2))
		{
			return data2.m_BindingName;
		}
		return CompositeComponentData.defaultData.m_BindingName;
	}
```

- `public GetBindings(Game.Input.InputManager+PathType pathType, Game.Input.InputManager+BindingOptions bindingOptions) : System.Collections.Generic.List<Game.Input.ProxyBinding>`  

```csharp
public List<ProxyBinding> GetBindings(PathType pathType, BindingOptions bindingOptions)
	{
		using (PerformanceCounter.Start(delegate(TimeSpan t)
		{
			log.TraceFormat("Get {1} bindings {2} in {0}ms", t.TotalMilliseconds, pathType, bindingOptions);
		}))
		{
			List<ProxyBinding> bindingsList = new List<ProxyBinding>();
			foreach (ProxyActionMap value in m_Maps.Values)
			{
				InputAction[] array = value.sourceMap.m_Actions;
				foreach (InputAction action in array)
				{
					action.ForEachCompositeOfAction(delegate(InputActionSetupExtensions.BindingSyntax iterator)
					{
						if (TryGetComposite(action, iterator, pathType, bindingOptions, out var proxyComposite))
						{
							foreach (var (_, item) in proxyComposite.bindings)
							{
								bindingsList.Add(item);
							}
						}
						return true;
					});
				}
			}
			return bindingsList;
		}
	}
```

- `public GetComposites(UnityEngine.InputSystem.InputAction action) : System.Collections.Generic.List<Game.Input.ProxyComposite>`  

```csharp
public List<ProxyComposite> GetComposites(InputAction action)
	{
		List<ProxyComposite> composites = new List<ProxyComposite>();
		action.ForEachCompositeOfAction(delegate(InputActionSetupExtensions.BindingSyntax iterator)
		{
			if (TryGetComposite(action, iterator, PathType.Effective, BindingOptions.None, out var proxyComposite))
			{
				composites.Add(proxyComposite);
			}
			return true;
		});
		return composites;
	}
```

- `public GetGamepadType(UnityEngine.InputSystem.Gamepad gamepad) : Game.Input.InputManager+GamepadType`  

```csharp
public GamepadType GetGamepadType(Gamepad gamepad)
	{
		if (!(gamepad is DualShockGamepad))
		{
			if (gamepad is XInputController)
			{
				return GamepadType.Xbox;
			}
			return GamepadType.Xbox;
		}
		return GamepadType.PS;
	}
```

- `private GetMaskForControlScheme() : Game.Input.InputManager+DeviceType`  

```csharp
private DeviceType GetMaskForControlScheme()
	{
		return (DeviceType)((activeControlScheme switch
		{
			ControlScheme.KeyboardAndMouse => (!overlayActive) ? (hasInputFieldFocus ? 2 : 3) : 0, 
			ControlScheme.Gamepad => (!overlayActive) ? 4 : 0, 
			_ => 0, 
		}) & (int)(~blockedControlTypes));
	}
```

- `public static GetModifierName(Game.Input.ActionComponent component) : System.String`  

```csharp
public static string GetModifierName(ActionComponent component)
	{
		if (TryGetCompositeData(component.GetActionType(), out var data) && data.TryGetData(component, out var data2))
		{
			return data2.m_ModifierName;
		}
		return CompositeComponentData.defaultData.m_ModifierName;
	}
```

- `internal GetOrCreateBindingWatcher(Game.Input.ProxyBinding binding) : Game.Input.ProxyBinding+Watcher`  

```csharp
internal ProxyBinding.Watcher GetOrCreateBindingWatcher(ProxyBinding binding)
	{
		if (!m_ProxyBindingWatchers.TryGetValue(binding, out var value))
		{
			value = new ProxyBinding.Watcher(binding);
			if (value.isValid)
			{
				m_ProxyBindingWatchers[binding] = value;
			}
		}
		return value;
	}
```

- `private GetOrCreateMap(System.String name) : Game.Input.ProxyActionMap`  

```csharp
private ProxyActionMap GetOrCreateMap(string name)
	{
		if (!TryFindActionMap(name, out var map))
		{
			return AddActionMap(name);
		}
		return map;
	}
```

- `public static HasConflicts(Game.Input.ProxyAction action1, Game.Input.ProxyAction action2, System.Nullable<Game.Input.InputManager+DeviceType> maskOverride1 = null, System.Nullable<Game.Input.InputManager+DeviceType> maskOverride2 = null) : System.Boolean`  

```csharp
public static bool HasConflicts(ProxyAction action1, ProxyAction action2, DeviceType? maskOverride1 = null, DeviceType? maskOverride2 = null)
	{
		DeviceType deviceType = maskOverride1 ?? action1.mask;
		DeviceType deviceType2 = maskOverride2 ?? action2.mask;
		foreach (KeyValuePair<DeviceType, ProxyComposite> composite in action1.composites)
		{
			composite.Deconstruct(out var key, out var value);
			ProxyComposite proxyComposite = value;
			if ((proxyComposite.m_Device & deviceType) == 0)
			{
				continue;
			}
			foreach (KeyValuePair<DeviceType, ProxyComposite> composite2 in action2.composites)
			{
				composite2.Deconstruct(out key, out value);
				ProxyComposite proxyComposite2 = value;
				if ((proxyComposite2.m_Device & deviceType2) == 0)
				{
					continue;
				}
				foreach (KeyValuePair<ActionComponent, ProxyBinding> binding in proxyComposite.bindings)
				{
					binding.Deconstruct(out var key2, out var value2);
					ProxyBinding x = value2;
					foreach (KeyValuePair<ActionComponent, ProxyBinding> binding2 in proxyComposite2.bindings)
					{
						binding2.Deconstruct(out key2, out value2);
						ProxyBinding y = value2;
						if ((action1 != action2 || x.component != y.component) && ProxyBinding.ConflictsWith(x, y, checkUsage: false))
						{
							return true;
						}
					}
				}
			}
		}
		return false;
	}
```

- `public Initialize() : System.Void`  

```csharp
public void Initialize()
	{
		m_DeviceListeners = new Dictionary<InputDevice, DeviceListener>();
		using (PerformanceCounter.Start(delegate(TimeSpan t)
		{
			log.InfoFormat("Input initialized in {0}ms", t.TotalMilliseconds);
		}))
		{
			using (DeferUpdating())
			{
				InitializeComposites();
				InitializeModifiers();
				foreach (KeyValuePair<string, ProxyActionMap> map in m_Maps)
				{
					map.Deconstruct(out var _, out var value);
					value.InitActions();
				}
				InitializeMasks();
				InitializeAliases();
				InitializeLinkedActions();
			}
		}
		inputUser = InputUser.CreateUserWithoutPairedDevices();
		AssociateActionsWithUser(associate: true);
		InputSystem.onDeviceChange += OnDeviceChange;
		AddInitialDevices();
		PlatformManager.instance.onDeviceAssociationChanged += OnDeviceAssociationChanged;
		PlatformManager.instance.onOverlayStateChanged += OnOverlayStateChanged;
		m_ConflictResolution.Initialize();
	}
```

- `private InitializeAliases() : System.Void`  

```csharp
private void InitializeAliases()
	{
		UIBaseInputAction[] inputActions = uiActionCollection.m_InputActions;
		foreach (UIBaseInputAction uIBaseInputAction in inputActions)
		{
			foreach (UIInputActionPart actionPart in uIBaseInputAction.actionParts)
			{
				if (actionPart.TryGetProxyAction(out var action))
				{
					action.m_UIAliases.Add(uIBaseInputAction);
				}
			}
		}
		inputActions = toolActionCollection.m_InputActions;
		foreach (UIBaseInputAction uIBaseInputAction2 in inputActions)
		{
			foreach (UIInputActionPart actionPart2 in uIBaseInputAction2.actionParts)
			{
				if (actionPart2.TryGetProxyAction(out var action2))
				{
					action2.m_UIAliases.Add(uIBaseInputAction2);
				}
			}
		}
	}
```

- `private InitializeComposites() : System.Void`  

```csharp
private void InitializeComposites()
	{
		m_Composites = new List<CompositeData>
		{
			AxisSeparatedWithModifiersComposite.GetCompositeData(),
			AxisWithModifiersComposite.GetCompositeData(),
			ButtonWithModifiersComposite.GetCompositeData(),
			CameraVector2WithModifiersComposite.GetCompositeData(),
			Vector2SeparatedWithModifiersComposite.GetCompositeData(),
			Vector2WithModifiersComposite.GetCompositeData()
		};
	}
```

- `private InitializeLinkedActions() : System.Void`  

```csharp
private void InitializeLinkedActions()
	{
		foreach (KeyValuePair<string, ProxyActionMap> map in m_Maps)
		{
			map.Deconstruct(out var key, out var value);
			foreach (KeyValuePair<string, ProxyAction> action2 in value.actions)
			{
				action2.Deconstruct(out key, out var value2);
				ProxyAction action = value2;
				action.sourceAction.ForEachCompositeOfAction(delegate(InputActionSetupExtensions.BindingSyntax iterator)
				{
					DeviceType deviceType = iterator.binding.name.ToDeviceType();
					if (deviceType == DeviceType.None)
					{
						return true;
					}
					CompositeInstance compositeInstance = new CompositeInstance(NameAndParameters.Parse(iterator.binding.effectivePath));
					if (compositeInstance.linkedGuid != Guid.Empty && TryFindAction(compositeInstance.linkedGuid, out var proxyAction))
					{
						ProxyAction.LinkActions(new ProxyAction.LinkInfo
						{
							m_Action = action,
							m_Device = deviceType
						}, new ProxyAction.LinkInfo
						{
							m_Action = proxyAction,
							m_Device = deviceType
						});
					}
					return true;
				});
			}
		}
	}
```

- `private InitializeMasks() : System.Void`  

```csharp
internal void InitializeMasks(ProxyAction action)
	{
		InputAction sourceAction = action.sourceAction;
		string expectedControlType = sourceAction.expectedControlType;
		Type typeFromHandle;
		switch (expectedControlType)
		{
		default:
			if (expectedControlType.Length == 0)
			{
				goto case "Button";
			}
			goto case null;
		case "Dpad":
			typeFromHandle = typeof(MaskVector2Processor);
			break;
		case "Stick":
			typeFromHandle = typeof(MaskVector2Processor);
			break;
		case "Vector2":
			typeFromHandle = typeof(MaskVector2Processor);
			break;
		case "Axis":
			typeFromHandle = typeof(MaskFloatProcessor);
			break;
		case "Button":
			typeFromHandle = typeof(MaskFloatProcessor);
			break;
		case null:
			throw new ArgumentException("Unexpected type of control", "expectedControlType");
		}
		InternedString processorName = InputProcessor.s_Processors.FindNameForType(typeFromHandle);
		sourceAction.ForEachCompositeOfAction(delegate(InputActionSetupExtensions.BindingSyntax iterator)
		{
			NameAndParameters nameAndParameters = new NameAndParameters
			{
				name = processorName,
				parameters = new ReadOnlyArray<NamedValue>(new NamedValue[2]
				{
					NamedValue.From("m_Index", action.m_GlobalIndex),
					NamedValue.From("m_Mask", iterator.binding.name.ToDeviceType())
				})
			};
			sourceAction.m_ActionMap.m_Bindings[iterator.m_BindingIndexInMap].processors = (string.IsNullOrEmpty(iterator.binding.processors) ? nameAndParameters.ToString() : string.Format("{0}{1}{2}", iterator.binding.processors, ",", nameAndParameters));
			sourceAction.m_ActionMap.OnBindingModified();
			return true;
		});
	}
```

- `internal InitializeMasks(Game.Input.ProxyAction action) : System.Void`  

```csharp
internal void InitializeMasks(ProxyAction action)
	{
		InputAction sourceAction = action.sourceAction;
		string expectedControlType = sourceAction.expectedControlType;
		Type typeFromHandle;
		switch (expectedControlType)
		{
		default:
			if (expectedControlType.Length == 0)
			{
				goto case "Button";
			}
			goto case null;
		case "Dpad":
			typeFromHandle = typeof(MaskVector2Processor);
			break;
		case "Stick":
			typeFromHandle = typeof(MaskVector2Processor);
			break;
		case "Vector2":
			typeFromHandle = typeof(MaskVector2Processor);
			break;
		case "Axis":
			typeFromHandle = typeof(MaskFloatProcessor);
			break;
		case "Button":
			typeFromHandle = typeof(MaskFloatProcessor);
			break;
		case null:
			throw new ArgumentException("Unexpected type of control", "expectedControlType");
		}
		InternedString processorName = InputProcessor.s_Processors.FindNameForType(typeFromHandle);
		sourceAction.ForEachCompositeOfAction(delegate(InputActionSetupExtensions.BindingSyntax iterator)
		{
			NameAndParameters nameAndParameters = new NameAndParameters
			{
				name = processorName,
				parameters = new ReadOnlyArray<NamedValue>(new NamedValue[2]
				{
					NamedValue.From("m_Index", action.m_GlobalIndex),
					NamedValue.From("m_Mask", iterator.binding.name.ToDeviceType())
				})
			};
			sourceAction.m_ActionMap.m_Bindings[iterator.m_BindingIndexInMap].processors = (string.IsNullOrEmpty(iterator.binding.processors) ? nameAndParameters.ToString() : string.Format("{0}{1}{2}", iterator.binding.processors, ",", nameAndParameters));
			sourceAction.m_ActionMap.OnBindingModified();
			return true;
		});
	}
```

- `private InitializeModifiers() : System.Void`  

```csharp
private void InitializeModifiers(InputActionSetupExtensions.BindingSyntax compositeIterator, InputAction action, CompositeInstance compositeInstance)
	{
		if (!compositeInstance.allowModifiers)
		{
			return;
		}
		foreach (CompositeComponentData componentData in compositeInstance.compositeData.m_Data.Values)
		{
			action.ForEachPartOfCompositeWithName(compositeIterator, componentData.m_BindingName, delegate(InputActionSetupExtensions.BindingSyntax mainIterator)
			{
				InputBinding binding = mainIterator.binding;
				if (!kModifiers.TryGetValue(compositeIterator.binding.name.ToDeviceType(), out var value))
				{
					return true;
				}
				HashSet<string> missedModifiers = new HashSet<string>(value, StringComparer.OrdinalIgnoreCase);
				action.ForEachPartOfCompositeWithName(mainIterator, componentData.m_ModifierName, delegate(InputActionSetupExtensions.BindingSyntax modifierIterator)
				{
					InputBinding binding2 = modifierIterator.binding;
					if (!string.Equals(binding2.name, componentData.m_ModifierName, StringComparison.Ordinal))
					{
						return true;
					}
					if (string.IsNullOrEmpty(binding2.path))
					{
						return true;
					}
					missedModifiers.Remove(binding2.path);
					return true;
				}, out var endIterator2);
				foreach (string item in missedModifiers)
				{
					endIterator2 = endIterator2.InsertPartBinding(componentData.m_ModifierName, item).WithGroups(binding.groups).WithProcessor(prohibitionModifierProcessor)
						.Triggering(action);
				}
				return true;
			}, out var _);
		}
	}
```

- `private InitializeModifiers(UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax compositeIterator, UnityEngine.InputSystem.InputAction action, Game.Input.CompositeInstance compositeInstance) : System.Void`  

```csharp
private void InitializeModifiers(InputActionSetupExtensions.BindingSyntax compositeIterator, InputAction action, CompositeInstance compositeInstance)
	{
		if (!compositeInstance.allowModifiers)
		{
			return;
		}
		foreach (CompositeComponentData componentData in compositeInstance.compositeData.m_Data.Values)
		{
			action.ForEachPartOfCompositeWithName(compositeIterator, componentData.m_BindingName, delegate(InputActionSetupExtensions.BindingSyntax mainIterator)
			{
				InputBinding binding = mainIterator.binding;
				if (!kModifiers.TryGetValue(compositeIterator.binding.name.ToDeviceType(), out var value))
				{
					return true;
				}
				HashSet<string> missedModifiers = new HashSet<string>(value, StringComparer.OrdinalIgnoreCase);
				action.ForEachPartOfCompositeWithName(mainIterator, componentData.m_ModifierName, delegate(InputActionSetupExtensions.BindingSyntax modifierIterator)
				{
					InputBinding binding2 = modifierIterator.binding;
					if (!string.Equals(binding2.name, componentData.m_ModifierName, StringComparison.Ordinal))
					{
						return true;
					}
					if (string.IsNullOrEmpty(binding2.path))
					{
						return true;
					}
					missedModifiers.Remove(binding2.path);
					return true;
				}, out var endIterator2);
				foreach (string item in missedModifiers)
				{
					endIterator2 = endIterator2.InsertPartBinding(componentData.m_ModifierName, item).WithGroups(binding.groups).WithProcessor(prohibitionModifierProcessor)
						.Triggering(action);
				}
				return true;
			}, out var _);
		}
	}
```

- `private IsDeviceTypePaired<T>() : System.Boolean`  

```csharp
private System.Boolean IsDeviceTypePaired<T>();
```

- `public static IsGamepadActive() : System.Boolean`  

```csharp
public static bool IsGamepadActive()
	{
		return instance.activeControlScheme == ControlScheme.Gamepad;
	}
```

- `internal OnActionChanged() : System.Void`  

```csharp
internal void OnActionChanged()
	{
		if (sDeferUpdatingWrapper.isDeferred)
		{
			m_NeedUpdate = true;
		}
		else
		{
			ProcessActionsUpdate();
		}
	}
```

- `internal OnActionDisplayNamesChanged() : System.Void`  

```csharp
internal void OnActionDisplayNamesChanged()
	{
		this.EventActionDisplayNamesChanged?.Invoke();
	}
```

- `internal OnActionMasksChanged() : System.Void`  

```csharp
internal void OnActionMasksChanged()
	{
		this.EventActionMasksChanged?.Invoke();
	}
```

- `private OnAddDevice(UnityEngine.InputSystem.InputDevice device) : System.Void`  

```csharp
private void OnAddDevice(InputDevice device)
	{
		if (!m_DeviceListeners.TryGetValue(device, out var value))
		{
			value = new DeviceListener(device, 50f);
			value.EventDeviceActivated.AddListener(OnDeviceActivated);
			m_DeviceListeners.Add(device, value);
			value.StartListening();
		}
		value.StartListening();
		TryPairDevice(device);
	}
```

- `private OnDeviceActivated(UnityEngine.InputSystem.InputDevice newDevice) : System.Void`  

```csharp
private void OnDeviceActivated(InputDevice newDevice)
	{
		if (newDevice != m_LastActiveDevice)
		{
			InputDevice lastActiveDevice = m_LastActiveDevice;
			ControlScheme controlScheme = activeControlScheme;
			m_LastActiveDevice = newDevice;
			if (!(newDevice is Mouse) && !(newDevice is Keyboard))
			{
				if (newDevice is Gamepad)
				{
					activeControlScheme = ControlScheme.Gamepad;
				}
			}
			else
			{
				activeControlScheme = ControlScheme.KeyboardAndMouse;
			}
			this.EventActiveDeviceChanged?.Invoke(newDevice, lastActiveDevice, activeControlScheme != controlScheme);
		}
		if (m_Idle)
		{
			m_Idle = false;
			Telemetry.InputIdleEnd();
		}
		m_AccumulatedIdleDelay = 0f;
		if (!Enumerable.Contains(inputUser.pairedDevices, newDevice))
		{
			OnUnpairedDeviceUsed(newDevice);
		}
	}
```

- `private OnDeviceAssociationChanged(Colossal.PSI.Common.IPlatformServiceIntegration psi, Colossal.PSI.Common.DeviceAssociationChange change) : System.Void`  

```csharp
private void OnDeviceAssociationChanged(IPlatformServiceIntegration psi, DeviceAssociationChange change)
	{
		if (!PlatformManager.instance.IsPrincipalDeviceAssociationIntegration(psi))
		{
			return;
		}
		InputDevice inputDevice = InputSystem.devices.FirstOrDefault((InputDevice device) => device.deviceId == change.deviceId) ?? InputSystem.disconnectedDevices.FirstOrDefault((InputDevice device) => device.deviceId == change.deviceId);
		if (inputDevice != null)
		{
			if (!change.associated)
			{
				if (TryUnpairDevice(inputDevice))
				{
					this.EventActiveDeviceAssociationLost?.Invoke();
				}
			}
			else if (change.associated)
			{
				TryPairDevice(inputDevice);
			}
		}
		else
		{
			log.Error($"No matching device found with ID: {change.deviceId}.");
		}
	}
```

- `private OnDeviceChange(UnityEngine.InputSystem.InputDevice device, UnityEngine.InputSystem.InputDeviceChange change) : System.Void`  

```csharp
private void OnDeviceChange(InputDevice device, InputDeviceChange change)
	{
		switch (change)
		{
		case InputDeviceChange.Added:
			OnAddDevice(device);
			break;
		case InputDeviceChange.Removed:
			OnRemoveDevice(device);
			break;
		}
	}
```

- `internal OnEnabledActionsChanged() : System.Void`  

```csharp
internal void OnEnabledActionsChanged()
	{
		this.EventEnabledActionsChanged?.Invoke();
	}
```

- `public OnFocusChanged(System.Boolean hasFocus) : System.Void`  

```csharp
public void OnFocusChanged(bool hasFocus)
	{
		log.VerboseFormat("Has focus {0}", hasFocus);
		m_HasFocus = hasFocus;
	}
```

- `private OnOverlayStateChanged(Colossal.PSI.Common.IOverlaySupport psi, System.Boolean active) : System.Void`  

```csharp
private void OnOverlayStateChanged(IOverlaySupport psi, bool active)
	{
		log.VerboseFormat("Overlay active {0}", active);
		m_OverlayActive = active;
	}
```

- `internal OnPreResolvedActionChanged() : System.Void`  

```csharp
internal void OnPreResolvedActionChanged()
	{
		this.EventPreResolvedActionChanged?.Invoke();
	}
```

- `private OnRemoveDevice(UnityEngine.InputSystem.InputDevice device) : System.Void`  

```csharp
private void OnRemoveDevice(InputDevice device)
	{
		if (m_DeviceListeners.TryGetValue(device, out var value))
		{
			value.StopListening();
		}
		if (TryUnpairDevice(device) && ((activeControlScheme == ControlScheme.KeyboardAndMouse && (device is Keyboard || device is Mouse)) || (activeControlScheme == ControlScheme.Gamepad && device is Gamepad)))
		{
			this.EventActiveDeviceDisconnected?.Invoke();
		}
	}
```

- `private OnUnpairedDeviceUsed(UnityEngine.InputSystem.InputDevice device) : System.Void`  

```csharp
private void OnUnpairedDeviceUsed(InputDevice device)
	{
		if (!(device is Mouse))
		{
			if (!(device is Keyboard))
			{
				if (device is Gamepad)
				{
					if (!PlatformManager.instance.IsDeviceAssociated(device))
					{
						return;
					}
					UnpairAll<Gamepad>();
				}
			}
			else
			{
				UnpairAll<Keyboard>();
			}
		}
		else
		{
			UnpairAll<Mouse>();
		}
		PairDevice(device);
	}
```

- `private PairDevice(UnityEngine.InputSystem.InputDevice device) : System.Void`  

```csharp
private void PairDevice(InputDevice device)
	{
		log.InfoFormat("Pair {0} [{1}]", device.displayName, device.deviceId);
		InputUser.PerformPairingWithDevice(device, inputUser);
		this.EventDevicePaired?.Invoke();
		UpdateConnectedDeviceTypes();
	}
```

- `private ProcessActionsUpdate(System.Boolean ignoreDefer = False) : System.Void`  

```csharp
private void ProcessActionsUpdate(bool ignoreDefer = false)
	{
		if ((!sDeferUpdatingWrapper.isDeferred || ignoreDefer) && m_NeedUpdate)
		{
			m_NeedUpdate = false;
			actionVersion++;
			CheckConflicts();
			this.EventActionsChanged?.Invoke();
		}
	}
```

- `private RefreshActiveControl() : System.Void`  

```csharp
private void RefreshActiveControl()
	{
		mask = GetMaskForControlScheme();
		if (m_ActiveControlScheme == ControlScheme.KeyboardAndMouse && Keyboard.current.added)
		{
			UnityEngine.Input.imeCompositionMode = (hasInputFieldFocus ? IMECompositionMode.On : IMECompositionMode.Off);
			Keyboard.current.SetIMEEnabled(hasInputFieldFocus);
			Keyboard.current.SetIMECursorPosition(caretRect.Item1 + caretRect.Item2);
		}
	}
```

- `public ResetAllBindings(System.Boolean onlyBuiltIn = True) : System.Void`  

```csharp
public void ResetAllBindings(bool onlyBuiltIn = true)
	{
		List<ProxyBinding> bindings = GetBindings(PathType.Original, (BindingOptions)(4 | (onlyBuiltIn ? 8 : 0)));
		SetBindings(bindings, out var _);
	}
```

- `public ResetGroupBindings(Game.Input.InputManager+DeviceType device, System.Boolean onlyBuiltIn = True) : System.Void`  

```csharp
public void ResetGroupBindings(DeviceType device, bool onlyBuiltIn = true)
	{
		List<ProxyBinding> bindings = GetBindings(PathType.Original, (BindingOptions)(4 | (onlyBuiltIn ? 8 : 0)));
		SetBindings(bindings.Where((ProxyBinding b) => b.device == device), out var _);
	}
```

- `public SetBinding(Game.Input.ProxyBinding newBinding, Game.Input.ProxyBinding& result) : System.Boolean`  

```csharp
public bool SetBinding(ProxyBinding newBinding, out ProxyBinding result)
	{
		string bindingName = newBinding.ToString();
		using (PerformanceCounter.Start(delegate(TimeSpan t)
		{
			log.TraceFormat("Set binding {1} in {0}ms", t.TotalMilliseconds, bindingName);
		}))
		{
			using (DeferUpdating())
			{
				if (!SetBindingImpl(newBinding, out result))
				{
					return false;
				}
			}
			return true;
		}
	}
```

- `private SetBindingImpl(Game.Input.ProxyBinding bindingToSet, Game.Input.ProxyBinding& newBinding) : System.Boolean`  

```csharp
private bool SetBindingImpl(ProxyBinding bindingToSet, out ProxyBinding newBinding)
	{
		if (!TryFindAction(bindingToSet.mapName, bindingToSet.actionName, out var action) || action.sourceAction == null)
		{
			newBinding = default(ProxyBinding);
			return false;
		}
		if (!TryGetIterators(bindingToSet, action.sourceAction, out var compositeIterator, out var bindingIterator, out var compositeInstance, out var componentData))
		{
			newBinding = default(ProxyBinding);
			return false;
		}
		if (!compositeInstance.isRebindable)
		{
			newBinding = default(ProxyBinding);
			return false;
		}
		if (!compositeInstance.isModifiersRebindable && TryGetModifierBindings(action.sourceAction, compositeInstance, compositeIterator, bindingIterator, PathType.Original, componentData, out var _, out var originalModifiers) && !ProxyBinding.ModifiersListComparer.defaultComparer.Equals(bindingToSet.modifiers, (IReadOnlyCollection<ProxyModifier>)(object)originalModifiers))
		{
			newBinding = default(ProxyBinding);
			return false;
		}
		if (string.IsNullOrEmpty(bindingToSet.path) && !compositeInstance.canBeEmpty)
		{
			newBinding = default(ProxyBinding);
			return false;
		}
		if (!TrySetMainBinding(bindingToSet, action.sourceAction, bindingIterator, out var changed) || !TrySetModifierBindings(bindingToSet, action.sourceAction, compositeInstance, componentData, compositeIterator, bindingIterator, out var changed2))
		{
			newBinding = default(ProxyBinding);
			return false;
		}
		if (!changed && !changed2)
		{
			newBinding = default(ProxyBinding);
			return false;
		}
		action.Update();
		return TryGetBinding(action.sourceAction, compositeIterator, bindingIterator, compositeInstance, componentData, PathType.Effective, BindingOptions.None, out newBinding);
	}
```

- `public SetBindings(System.Collections.Generic.IEnumerable<Game.Input.ProxyBinding> newBindings, System.Collections.Generic.List`1[[Game.Input.ProxyBinding, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resultBindings) : System.Boolean`  

```csharp
public bool SetBindings(IEnumerable<ProxyBinding> newBindings, out List<ProxyBinding> resultBindings)
	{
		using (PerformanceCounter.Start(delegate(TimeSpan t)
		{
			log.TraceFormat("Set bindings in {0}ms", t.TotalMilliseconds);
		}))
		{
			resultBindings = new List<ProxyBinding>();
			using (DeferUpdating())
			{
				foreach (ProxyBinding newBinding2 in newBindings)
				{
					SetBindingImpl(newBinding2, out var newBinding);
					resultBindings.Add(newBinding);
				}
			}
			return true;
		}
	}
```

- `private SetBuiltInConflictNotification(System.Boolean conflict) : System.Void`  

```csharp
private void SetBuiltInConflictNotification(bool conflict)
	{
		if (conflict == NotificationSystem.Exist("KeyBindingConflict"))
		{
			return;
		}
		if (conflict)
		{
			ProgressState? progressState = ProgressState.Warning;
			NotificationSystem.Push("KeyBindingConflict", null, null, "KeyBindingConflict", "KeyBindingConflict", null, progressState, null, delegate
			{
				LocalizedString value = LocalizedString.Id("Common.DIALOG_TITLE_INPUT");
				LocalizedString message = LocalizedString.Id("Common.DIALOG_MESSAGE_INPUT");
				LocalizedString confirmAction = LocalizedString.Id("Common.OK");
				LocalizedString localizedString = LocalizedString.Id("Common.DIALOG_ACTION_INPUT[Reset]");
				LocalizedString localizedString2 = LocalizedString.Id("Common.DIALOG_ACTION_INPUT[OpenOptions]");
				MessageDialog dialog = new MessageDialog(value, message, confirmAction, localizedString, localizedString2);
				GameManager.instance.userInterface.appBindings.ShowMessageDialog(dialog, Callback);
			});
		}
		else
		{
			ProgressState? progressState = ProgressState.Complete;
			NotificationSystem.Pop("KeyBindingConflict", 2f, null, null, null, "KeyBindingConflictResolved", null, progressState);
		}
		void Callback(int msg)
		{
			switch (msg)
			{
			case 0:
				NotificationSystem.Pop("KeyBindingConflict");
				break;
			case 2:
				ResetAllBindings();
				break;
			case 3:
			{
				OptionsUISystem orCreateSystemManaged = World.DefaultGameObjectInjectionWorld.GetOrCreateSystemManaged<OptionsUISystem>();
				string sectionID = bindingConflicts switch
				{
					DeviceType.Keyboard => "Keyboard", 
					DeviceType.Mouse => "Mouse", 
					DeviceType.Gamepad => "Gamepad", 
					DeviceType.Keyboard | DeviceType.Mouse => "Keyboard", 
					DeviceType.Keyboard | DeviceType.Gamepad => (activeControlScheme == ControlScheme.Gamepad) ? "Gamepad" : "Keyboard", 
					DeviceType.Mouse | DeviceType.Gamepad => (activeControlScheme == ControlScheme.Gamepad) ? "Gamepad" : "Mouse", 
					DeviceType.All => (activeControlScheme == ControlScheme.Gamepad) ? "Gamepad" : "Keyboard", 
					_ => null, 
				};
				orCreateSystemManaged?.OpenPage("Input", sectionID, isAdvanced: false);
				break;
			}
			case 1:
				break;
			}
		}
	}
```

- `public SetDefaultControlScheme() : System.Void`  

```csharp
public void SetDefaultControlScheme()
	{
		activeControlScheme = ControlScheme.KeyboardAndMouse;
	}
```

- `private SetModConflictNotification(Game.Input.ProxyActionMap map, System.Boolean conflict) : System.Void`  

```csharp
private void SetModConflictNotification(ProxyActionMap map, bool conflict)
	{
		if (conflict == NotificationSystem.Exist(map.name))
		{
			return;
		}
		if (conflict)
		{
			string text = null;
			Action action = null;
			LocalizedString value = LocalizedString.IdWithFallback("Options.INPUT_MAP[" + map.name + "]", map.name);
			if (ModSetting.instances.TryGetValue(map.name, out var value2) && GameManager.instance.modManager.TryGetExecutableAsset(value2.mod, out var asset))
			{
				value = LocalizedString.Value(asset.mod.displayName);
				if (!string.IsNullOrEmpty(asset.mod.thumbnailPath))
				{
					text = $"{asset.mod.thumbnailPath}?width={NotificationUISystem.width})";
				}
				action = delegate
				{
					World.DefaultGameObjectInjectionWorld.GetOrCreateSystemManaged<OptionsUISystem>()?.OpenPage(map.name, null, isAdvanced: false);
				};
			}
			string name = map.name;
			LocalizedString? title = value;
			string thumbnail = text;
			ProgressState? progressState = ProgressState.Warning;
			Action onClicked = action;
			NotificationSystem.Push(name, title, null, null, "KeyBindingConflict", thumbnail, progressState, null, onClicked);
		}
		else
		{
			string name2 = map.name;
			ProgressState? progressState = ProgressState.Complete;
			NotificationSystem.Pop(name2, 2f, null, null, null, "KeyBindingConflictResolved", null, progressState);
		}
	}
```

- `private System.Collections.Generic.IEnumerable<UnityEngine.InputSystem.InputAction>.GetEnumerator() : System.Collections.Generic.IEnumerator<UnityEngine.InputSystem.InputAction>`  

```csharp
private System.Collections.Generic.IEnumerator<UnityEngine.InputSystem.InputAction> System.Collections.Generic.IEnumerable<UnityEngine.InputSystem.InputAction>.GetEnumerator();
```

- `private System.Collections.IEnumerable.GetEnumerator() : System.Collections.IEnumerator`  

```csharp
private System.Collections.IEnumerator System.Collections.IEnumerable.GetEnumerator();
```

- `public TryFindAction(System.String mapName, System.String actionName, Game.Input.ProxyAction& action) : System.Boolean`  

```csharp
internal bool TryFindAction(int index, out ProxyAction action)
	{
		return actionIndex.TryGetValue(index, out action);
	}
```

- `public TryFindAction(Game.Input.ProxyBinding binding, Game.Input.ProxyAction& action) : System.Boolean`  

```csharp
internal bool TryFindAction(int index, out ProxyAction action)
	{
		return actionIndex.TryGetValue(index, out action);
	}
```

- `public TryFindAction(UnityEngine.InputSystem.InputAction action, Game.Input.ProxyAction& proxyAction) : System.Boolean`  

```csharp
internal bool TryFindAction(int index, out ProxyAction action)
	{
		return actionIndex.TryGetValue(index, out action);
	}
```

- `public TryFindAction(System.Guid guid, Game.Input.ProxyAction& proxyAction) : System.Boolean`  

```csharp
internal bool TryFindAction(int index, out ProxyAction action)
	{
		return actionIndex.TryGetValue(index, out action);
	}
```

- `internal TryFindAction(System.Int32 index, Game.Input.ProxyAction& action) : System.Boolean`  

```csharp
internal bool TryFindAction(int index, out ProxyAction action)
	{
		return actionIndex.TryGetValue(index, out action);
	}
```

- `public TryFindActionMap(System.String name, Game.Input.ProxyActionMap& map) : System.Boolean`  

```csharp
internal bool TryFindActionMap(InputActionMap map, out ProxyActionMap proxyMap)
	{
		return TryFindActionMap(map.name, out proxyMap);
	}
```

- `internal TryFindActionMap(UnityEngine.InputSystem.InputActionMap map, Game.Input.ProxyActionMap& proxyMap) : System.Boolean`  

```csharp
internal bool TryFindActionMap(InputActionMap map, out ProxyActionMap proxyMap)
	{
		return TryFindActionMap(map.name, out proxyMap);
	}
```

- `public TryGetBinding(Game.Input.ProxyBinding bindingToGet, Game.Input.InputManager+PathType pathType, Game.Input.InputManager+BindingOptions bindingOptions, Game.Input.ProxyBinding& foundBinding) : System.Boolean`  

```csharp
private bool TryGetBinding(InputAction action, InputActionSetupExtensions.BindingSyntax compositeIterator, InputActionSetupExtensions.BindingSyntax bindingIterator, CompositeInstance compositeInstance, CompositeComponentData componentData, PathType pathType, BindingOptions bindingOptions, out ProxyBinding foundBinding)
	{
		bool num = (bindingOptions & BindingOptions.OnlyRebound) != 0;
		InputBinding binding = bindingIterator.binding;
		bool flag = TryGetMainBinding(bindingIterator, pathType, out var currentPath, out var originalPath);
		flag |= TryGetModifierBindings(action, compositeInstance, compositeIterator, bindingIterator, pathType, componentData, out var currentModifiers, out var originalModifiers);
		if (num && !flag)
		{
			foundBinding = default(ProxyBinding);
			return false;
		}
		foundBinding = new ProxyBinding(action, componentData.m_Component, binding.name, compositeInstance)
		{
			path = currentPath,
			modifiers = currentModifiers,
			originalPath = originalPath,
			originalModifiers = originalModifiers,
			device = compositeIterator.binding.name.ToDeviceType()
		};
		return true;
	}
```

- `private TryGetBinding(UnityEngine.InputSystem.InputAction action, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax compositeIterator, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax bindingIterator, Game.Input.CompositeInstance compositeInstance, Game.Input.InputManager+CompositeComponentData componentData, Game.Input.InputManager+PathType pathType, Game.Input.InputManager+BindingOptions bindingOptions, Game.Input.ProxyBinding& foundBinding) : System.Boolean`  

```csharp
private bool TryGetBinding(InputAction action, InputActionSetupExtensions.BindingSyntax compositeIterator, InputActionSetupExtensions.BindingSyntax bindingIterator, CompositeInstance compositeInstance, CompositeComponentData componentData, PathType pathType, BindingOptions bindingOptions, out ProxyBinding foundBinding)
	{
		bool num = (bindingOptions & BindingOptions.OnlyRebound) != 0;
		InputBinding binding = bindingIterator.binding;
		bool flag = TryGetMainBinding(bindingIterator, pathType, out var currentPath, out var originalPath);
		flag |= TryGetModifierBindings(action, compositeInstance, compositeIterator, bindingIterator, pathType, componentData, out var currentModifiers, out var originalModifiers);
		if (num && !flag)
		{
			foundBinding = default(ProxyBinding);
			return false;
		}
		foundBinding = new ProxyBinding(action, componentData.m_Component, binding.name, compositeInstance)
		{
			path = currentPath,
			modifiers = currentModifiers,
			originalPath = originalPath,
			originalModifiers = originalModifiers,
			device = compositeIterator.binding.name.ToDeviceType()
		};
		return true;
	}
```

- `private TryGetComposite(UnityEngine.InputSystem.InputAction action, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax compositeIterator, Game.Input.InputManager+PathType pathType, Game.Input.InputManager+BindingOptions bindingOptions, Game.Input.ProxyComposite& proxyComposite) : System.Boolean`  

```csharp
private bool TryGetComposite(InputAction action, InputActionSetupExtensions.BindingSyntax compositeIterator, PathType pathType, BindingOptions bindingOptions, out ProxyComposite proxyComposite)
	{
		List<ProxyBinding> bindingsList = new List<ProxyBinding>();
		proxyComposite = null;
		if (!TryGetCompositeInstance(compositeIterator, out var compositeInstance))
		{
			return false;
		}
		if (compositeInstance.developerOnly && GameManager.instance != null && !GameManager.instance.configuration.developerMode)
		{
			return false;
		}
		if (!compositeInstance.platform.IsPlatformSet(Application.platform))
		{
			return false;
		}
		if (!compositeInstance.builtIn && (bindingOptions & BindingOptions.OnlyBuiltIn) != BindingOptions.None)
		{
			return false;
		}
		if (!compositeInstance.isRebindable && (bindingOptions & BindingOptions.OnlyRebindable) != BindingOptions.None)
		{
			return false;
		}
		if (compositeInstance.isDummy && (bindingOptions & BindingOptions.ExcludeDummy) != BindingOptions.None)
		{
			return false;
		}
		if (compositeInstance.isHidden && (bindingOptions & BindingOptions.ExcludeHidden) != BindingOptions.None)
		{
			return false;
		}
		foreach (CompositeComponentData componentData in compositeInstance.compositeData.m_Data.Values)
		{
			action.ForEachPartOfCompositeWithName(compositeIterator, componentData.m_BindingName, delegate(InputActionSetupExtensions.BindingSyntax bindingIterator)
			{
				if (TryGetBinding(action, compositeIterator, bindingIterator, compositeInstance, componentData, pathType, bindingOptions, out var foundBinding))
				{
					bindingsList.Add(foundBinding);
				}
				return true;
			}, out var _);
		}
		if (bindingsList.Count == 0)
		{
			return false;
		}
		proxyComposite = new ProxyComposite(compositeIterator.binding.name.ToDeviceType(), compositeInstance.compositeData.m_ActionType, compositeInstance, bindingsList);
		return true;
	}
```

- `internal static TryGetCompositeData(System.String name, Game.Input.InputManager+CompositeData& data) : System.Boolean`  

```csharp
internal static bool TryGetCompositeData(ActionType actionType, out CompositeData data)
	{
		return TryGetCompositeData(actionType.GetCompositeTypeName(), out data);
	}
```

- `internal static TryGetCompositeData(Game.Input.ActionType actionType, Game.Input.InputManager+CompositeData& data) : System.Boolean`  

```csharp
internal static bool TryGetCompositeData(ActionType actionType, out CompositeData data)
	{
		return TryGetCompositeData(actionType.GetCompositeTypeName(), out data);
	}
```

- `private TryGetCompositeInstance(UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax compositeIterator, Game.Input.CompositeInstance& compositeInstance) : System.Boolean`  

```csharp
private bool TryGetCompositeInstance(InputActionSetupExtensions.BindingSyntax compositeIterator, out CompositeInstance compositeInstance)
	{
		NameAndParameters[] array = NameAndParameters.ParseMultiple(compositeIterator.binding.effectivePath).ToArray();
		if (array.Length == 2 && array[1].name == "Usages")
		{
			compositeInstance = new CompositeInstance(array[0], array[1]);
		}
		else
		{
			compositeInstance = new CompositeInstance(array[0]);
		}
		return compositeInstance != null;
	}
```

- `private TryGetIterators(Game.Input.ProxyBinding bindingSample, UnityEngine.InputSystem.InputAction action, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax& compositeIterator, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax& bindingIterator, Game.Input.CompositeInstance& compositeInstance, Game.Input.InputManager+CompositeComponentData& componentData) : System.Boolean`  

```csharp
private bool TryGetIterators(ProxyBinding bindingSample, InputAction action, out InputActionSetupExtensions.BindingSyntax compositeIterator, out InputActionSetupExtensions.BindingSyntax bindingIterator, out CompositeInstance compositeInstance, out CompositeComponentData componentData)
	{
		compositeIterator = default(InputActionSetupExtensions.BindingSyntax);
		bindingIterator = default(InputActionSetupExtensions.BindingSyntax);
		compositeInstance = null;
		componentData = default(CompositeComponentData);
		if (!action.TryGetCompositeOfActionWithName(bindingSample.device.ToString(), out compositeIterator))
		{
			return false;
		}
		if (!TryGetCompositeInstance(compositeIterator, out compositeInstance))
		{
			return false;
		}
		if (bindingSample.component == ActionComponent.None)
		{
			if (!compositeInstance.compositeData.TryFindByBindingName(bindingSample.name, out componentData))
			{
				return false;
			}
		}
		else if (!compositeInstance.compositeData.TryGetData(bindingSample.component, out componentData))
		{
			return false;
		}
		bindingIterator = compositeIterator.NextPartBinding(componentData.m_BindingName);
		return bindingIterator.valid;
	}
```

- `public TryGetMainBinding(UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax iterator, Game.Input.InputManager+PathType pathType, System.String& currentPath, System.String& originalPath) : System.Boolean`  

```csharp
public bool TryGetMainBinding(InputActionSetupExtensions.BindingSyntax iterator, PathType pathType, out string currentPath, out string originalPath)
	{
		InputBinding binding = iterator.binding;
		currentPath = binding.GetPath(pathType);
		originalPath = binding.path;
		return binding.overridePath != null;
	}
```

- `public TryGetModifierBindings(UnityEngine.InputSystem.InputAction action, Game.Input.CompositeInstance compositeInstance, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax compositeIterator, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax iterator, Game.Input.InputManager+PathType pathType, Game.Input.InputManager+CompositeComponentData componentData, Game.Input.ProxyModifier[]& currentModifiers, Game.Input.ProxyModifier[]& originalModifiers) : System.Boolean`  

```csharp
public bool TryGetModifierBindings(InputAction action, CompositeInstance compositeInstance, InputActionSetupExtensions.BindingSyntax compositeIterator, InputActionSetupExtensions.BindingSyntax iterator, PathType pathType, CompositeComponentData componentData, out ProxyModifier[] currentModifiers, out ProxyModifier[] originalModifiers)
	{
		currentModifiers = null;
		originalModifiers = null;
		if (!compositeInstance.allowModifiers)
		{
			return false;
		}
		if (!kModifiers.TryGetValue(compositeIterator.binding.name.ToDeviceType(), out var supportedModifiers))
		{
			return false;
		}
		bool isRebound = false;
		List<ProxyModifier> currentModifierList = new List<ProxyModifier>();
		List<ProxyModifier> originalModifierList = new List<ProxyModifier>();
		action.ForEachPartOfCompositeWithName(compositeIterator, componentData.m_ModifierName, delegate(InputActionSetupExtensions.BindingSyntax modifierIterator)
		{
			InputBinding binding = modifierIterator.binding;
			if (string.IsNullOrEmpty(binding.path))
			{
				return true;
			}
			if (!supportedModifiers.Contains(binding.path))
			{
				return true;
			}
			isRebound |= binding.overrideProcessors != null;
			if (!binding.GetProcessors(pathType).Contains(prohibitionModifierProcessor))
			{
				currentModifierList.Add(new ProxyModifier
				{
					m_Component = componentData.m_Component,
					m_Name = binding.name,
					m_Path = binding.path
				});
			}
			if (!binding.processors.Contains(prohibitionModifierProcessor))
			{
				originalModifierList.Add(new ProxyModifier
				{
					m_Component = componentData.m_Component,
					m_Name = binding.name,
					m_Path = binding.path
				});
			}
			return true;
		}, out var _);
		currentModifiers = currentModifierList.ToArray();
		originalModifiers = originalModifierList.ToArray();
		return isRebound;
	}
```

- `private TryPairDevice(UnityEngine.InputSystem.InputDevice device) : System.Boolean`  

```csharp
private bool TryPairDevice(InputDevice device)
	{
		if ((device is Mouse && !IsDeviceTypePaired<Mouse>()) || (device is Keyboard && !IsDeviceTypePaired<Keyboard>()) || (device is Gamepad && !IsDeviceTypePaired<Gamepad>() && PlatformManager.instance.IsDeviceAssociated(device)))
		{
			PairDevice(device);
			return true;
		}
		return false;
	}
```

- `private TrySetBindingModifierProcessor(UnityEngine.InputSystem.InputAction action, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax modifierIterator, System.Boolean allow) : System.Boolean`  

```csharp
private bool TrySetBindingModifierProcessor(InputAction action, InputActionSetupExtensions.BindingSyntax modifierIterator, bool allow)
	{
		InputBinding binding = modifierIterator.binding;
		string text;
		if (allow)
		{
			if (string.IsNullOrEmpty(binding.effectiveProcessors) || binding.effectiveProcessors == prohibitionModifierProcessor)
			{
				text = string.Empty;
			}
			else
			{
				string[] source = binding.effectiveProcessors.Split(';', StringSplitOptions.RemoveEmptyEntries);
				text = string.Join(";", source.Select((string p) => p != prohibitionModifierProcessor));
			}
		}
		else if (string.IsNullOrEmpty(binding.effectiveProcessors) || binding.effectiveProcessors == prohibitionModifierProcessor)
		{
			text = prohibitionModifierProcessor;
		}
		else
		{
			string[] source2 = binding.effectiveProcessors.Split(';', StringSplitOptions.RemoveEmptyEntries);
			text = (source2.Any((string p) => p == prohibitionModifierProcessor) ? binding.effectiveProcessors : string.Join(";", source2.Append(prohibitionModifierProcessor)));
		}
		if (text == binding.processors)
		{
			if (binding.overrideProcessors != null)
			{
				binding.overrideProcessors = null;
				action.actionMap.ApplyBindingOverride(modifierIterator.m_BindingIndexInMap, binding);
				return true;
			}
		}
		else if (text != binding.overrideProcessors)
		{
			binding.overrideProcessors = text;
			action.actionMap.ApplyBindingOverride(modifierIterator.m_BindingIndexInMap, binding);
			return true;
		}
		return false;
	}
```

- `private TrySetMainBinding(Game.Input.ProxyBinding bindingToSet, UnityEngine.InputSystem.InputAction action, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax bindingIterator, System.Boolean& changed) : System.Boolean`  

```csharp
private bool TrySetMainBinding(ProxyBinding bindingToSet, InputAction action, InputActionSetupExtensions.BindingSyntax bindingIterator, out bool changed)
	{
		InputBinding binding = bindingIterator.binding;
		if (bindingToSet.path == binding.path)
		{
			if (binding.overridePath != null)
			{
				binding.overridePath = null;
				action.actionMap.ApplyBindingOverride(bindingIterator.m_BindingIndexInMap, binding);
				changed = true;
				return true;
			}
		}
		else if (bindingToSet.path != binding.overridePath)
		{
			binding.overridePath = bindingToSet.path;
			action.actionMap.ApplyBindingOverride(bindingIterator.m_BindingIndexInMap, binding);
			changed = true;
			return true;
		}
		changed = false;
		return true;
	}
```

- `private TrySetModifierBindings(Game.Input.ProxyBinding bindingToSet, UnityEngine.InputSystem.InputAction action, Game.Input.CompositeInstance compositeInstance, Game.Input.InputManager+CompositeComponentData componentData, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax compositeIterator, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax bindingIterator, System.Boolean& changed) : System.Boolean`  

```csharp
private bool TrySetModifierBindings(ProxyBinding bindingToSet, InputAction action, CompositeInstance compositeInstance, CompositeComponentData componentData, InputActionSetupExtensions.BindingSyntax compositeIterator, InputActionSetupExtensions.BindingSyntax bindingIterator, out bool changed)
	{
		if (!compositeInstance.allowModifiers)
		{
			changed = false;
			return true;
		}
		if (!kModifiers.TryGetValue(compositeIterator.binding.name.ToDeviceType(), out var supportedModifiers))
		{
			supportedModifiers = new HashSet<string>();
		}
		bool changedModifier = false;
		IReadOnlyList<ProxyModifier> modifiers = bindingToSet.modifiers;
		action.ForEachPartOfCompositeWithName(compositeIterator, componentData.m_ModifierName, delegate(InputActionSetupExtensions.BindingSyntax modifierIterator)
		{
			InputBinding modifierBinding = modifierIterator.binding;
			if (string.IsNullOrEmpty(modifierBinding.path))
			{
				return true;
			}
			if (!supportedModifiers.Contains(modifierBinding.path))
			{
				return true;
			}
			bool allow = modifiers.Any((ProxyModifier m) => StringComparer.OrdinalIgnoreCase.Equals(m.m_Path, modifierBinding.path));
			changedModifier |= TrySetBindingModifierProcessor(action, modifierIterator, allow);
			return true;
		}, out var _);
		changed = changedModifier;
		return true;
	}
```

- `private TryUnpairDevice(UnityEngine.InputSystem.InputDevice device) : System.Boolean`  

```csharp
private bool TryUnpairDevice(InputDevice device)
	{
		if (Enumerable.Contains(inputUser.pairedDevices, device) || Enumerable.Contains(inputUser.lostDevices, device))
		{
			UnpairDevice(device);
			return true;
		}
		return false;
	}
```

- `private UnityEngine.InputSystem.IInputActionCollection.Contains(UnityEngine.InputSystem.InputAction action) : System.Boolean`  

```csharp
private System.Boolean UnityEngine.InputSystem.IInputActionCollection.Contains(UnityEngine.InputSystem.InputAction action);
```

- `private UnityEngine.InputSystem.IInputActionCollection.Disable() : System.Void`  

```csharp
private System.Void UnityEngine.InputSystem.IInputActionCollection.Disable();
```

- `private UnityEngine.InputSystem.IInputActionCollection.Enable() : System.Void`  

```csharp
private System.Void UnityEngine.InputSystem.IInputActionCollection.Enable();
```

- `private UnpairAll<T>() : System.Void`  

```csharp
private System.Void UnpairAll<T>();
```

- `private UnpairDevice(UnityEngine.InputSystem.InputDevice device) : System.Void`  

```csharp
private void UnpairDevice(InputDevice device)
	{
		log.InfoFormat("Unpair {0} [{1}]", device.displayName, device.deviceId);
		inputUser.UnpairDevice(device);
		UpdateConnectedDeviceTypes();
	}
```

- `public Update() : System.Void`  

```csharp
public void Update()
	{
		if (!m_OverlayActive)
		{
			foreach (KeyValuePair<InputDevice, DeviceListener> deviceListener in m_DeviceListeners)
			{
				deviceListener.Deconstruct(out var _, out var value);
				value.Tick();
			}
		}
		if (m_ActiveControlScheme == ControlScheme.KeyboardAndMouse)
		{
			Mouse current = Mouse.current;
			if (current != null && current.delta.value.magnitude > 0.2f)
			{
				m_AccumulatedIdleDelay = 0f;
				if (m_Idle)
				{
					m_Idle = false;
					Telemetry.InputIdleEnd();
				}
			}
		}
		if (!m_Idle)
		{
			if (GameManager.instance.state == GameManager.State.WorldReady)
			{
				if (m_WasWorldReady)
				{
					m_AccumulatedIdleDelay += Time.unscaledDeltaTime;
				}
				m_WasWorldReady = true;
			}
			else
			{
				m_AccumulatedIdleDelay = 0f;
				m_WasWorldReady = false;
			}
			if (m_AccumulatedIdleDelay >= 30f)
			{
				m_AccumulatedIdleDelay = 30f;
				m_Idle = true;
				log.Debug("Input idle");
				Telemetry.InputIdleStart();
			}
		}
		m_ConflictResolution.Update();
		RefreshActiveControl();
	}
```

- `internal UpdateActionInKeyActionMap(Game.Input.ProxyAction action) : System.Void`  

```csharp
internal void UpdateActionInKeyActionMap(ProxyAction action)
	{
		string[] array;
		string[] array2;
		if (!actionKeyMap.TryGetValue(action, out var value))
		{
			array = action.usedKeys.ToArray();
			array2 = Array.Empty<string>();
			actionKeyMap[action] = new HashSet<string>(array);
		}
		else
		{
			HashSet<string> hashSet = action.usedKeys.ToHashSet();
			array = hashSet.Except(value).ToArray();
			array2 = value.Except(hashSet).ToArray();
			actionKeyMap[action] = hashSet;
		}
		string[] array3 = array2;
		foreach (string key in array3)
		{
			if (keyActionMap.TryGetValue(key, out var value2))
			{
				value2.Remove(action);
			}
		}
		array3 = array;
		foreach (string key2 in array3)
		{
			if (!keyActionMap.TryGetValue(key2, out var value3))
			{
				value3 = new HashSet<ProxyAction>();
				keyActionMap.Add(key2, value3);
			}
			value3.Add(action);
		}
	}
```

- `private UpdateConnectedDeviceTypes() : System.Void`  

```csharp
private void UpdateConnectedDeviceTypes()
	{
		m_ConnectedDeviceTypes = inputUser.pairedDevices.Aggregate(DeviceType.None, delegate(DeviceType result, InputDevice device)
		{
			DeviceType deviceType = ((device is Keyboard) ? DeviceType.Keyboard : ((device is Mouse) ? DeviceType.Mouse : ((device is Gamepad) ? DeviceType.Gamepad : DeviceType.None)));
			return result | deviceType;
		});
	}
```

- `private UpdateCursorVisibility() : System.Void`  

```csharp
private void UpdateCursorVisibility()
	{
		Cursor.visible = activeControlScheme == ControlScheme.KeyboardAndMouse && !hideCursor;
	}
```


## Events

- `EventControlSchemeChanged` : `System.Action<Game.Input.InputManager+ControlScheme>`  

```csharp
public event System.Action<Game.Input.InputManager+ControlScheme> EventControlSchemeChanged;
```

- `EventActiveDeviceChanged` : `Game.Input.InputManager+ActiveDeviceChanged`  

```csharp
public event Game.Input.InputManager+ActiveDeviceChanged EventActiveDeviceChanged;
```

- `EventActiveDeviceDisconnected` : `System.Action`  

```csharp
public event System.Action EventActiveDeviceDisconnected;
```

- `EventActiveDeviceAssociationLost` : `System.Action`  

```csharp
public event System.Action EventActiveDeviceAssociationLost;
```

- `EventDevicePaired` : `System.Action`  

```csharp
public event System.Action EventDevicePaired;
```

- `EventActionsChanged` : `System.Action`  

```csharp
public event System.Action EventActionsChanged;
```

- `EventEnabledActionsChanged` : `System.Action`  

```csharp
public event System.Action EventEnabledActionsChanged;
```

- `EventActionMasksChanged` : `System.Action`  

```csharp
public event System.Action EventActionMasksChanged;
```

- `EventActionDisplayNamesChanged` : `System.Action`  

```csharp
public event System.Action EventActionDisplayNamesChanged;
```

- `EventMouseOverUIChanged` : `System.Action<System.Boolean>`  

```csharp
public event System.Action<System.Boolean> EventMouseOverUIChanged;
```

- `EventPreResolvedActionChanged` : `System.Action`  

```csharp
public event System.Action EventPreResolvedActionChanged;
```


## Nested types

- `Game.Input.InputManager+CompositeData`  
- `Game.Input.InputManager+CompositeComponentData`  
- `Game.Input.InputManager+ActiveDeviceChanged`  
- `Game.Input.InputManager+PathType`  
- `Game.Input.InputManager+BindingOptions`  
- `Game.Input.InputManager+ControlScheme`  
- `Game.Input.InputManager+DeviceType`  
- `Game.Input.InputManager+GamepadType`  
- `Game.Input.InputManager+DeferManagerUpdatingWrapper`  
- `Game.Input.InputManager+<>c`  
- `Game.Input.InputManager+<>c__243<T>`  
- `Game.Input.InputManager+<>c__244<T>`  
- `Game.Input.InputManager+<>c__DisplayClass20_0`  
- `Game.Input.InputManager+<>c__DisplayClass20_1`  
- `Game.Input.InputManager+<>c__DisplayClass20_2`  
- `Game.Input.InputManager+<>c__DisplayClass211_0`  
- `Game.Input.InputManager+<>c__DisplayClass214_0`  
- `Game.Input.InputManager+<>c__DisplayClass237_0`  
- `Game.Input.InputManager+<>c__DisplayClass23_0`  
- `Game.Input.InputManager+<>c__DisplayClass257_0`  
- `Game.Input.InputManager+<>c__DisplayClass258_0`  
- `Game.Input.InputManager+<>c__DisplayClass258_1`  
- `Game.Input.InputManager+<>c__DisplayClass258_2`  
- `Game.Input.InputManager+<>c__DisplayClass260_0`  
- `Game.Input.InputManager+<>c__DisplayClass262_0`  
- `Game.Input.InputManager+<>c__DisplayClass263_0`  
- `Game.Input.InputManager+<>c__DisplayClass26_0`  
- `Game.Input.InputManager+<>c__DisplayClass29_0`  
- `Game.Input.InputManager+<>c__DisplayClass29_1`  
- `Game.Input.InputManager+<>c__DisplayClass33_0`  
- `Game.Input.InputManager+<>c__DisplayClass38_0`  
- `Game.Input.InputManager+<>c__DisplayClass39_0`  
- `Game.Input.InputManager+<>c__DisplayClass39_1`  
- `Game.Input.InputManager+<get_actions>d__1`  

