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
public InputManager();
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
private Game.Input.ProxyActionMap AddActionMap(System.String name);
```

- `internal AddActions(Game.Input.ProxyAction+Info[] actionsToAdd) : System.Void`  

```csharp
internal System.Void AddActions(Game.Input.ProxyAction+Info[] actionsToAdd);
```

- `public AddInitialDevices() : System.Void`  

```csharp
public System.Void AddInitialDevices();
```

- `public AssociateActionsWithUser(System.Boolean associate) : System.Void`  

```csharp
public System.Void AssociateActionsWithUser(System.Boolean associate);
```

- `public static CanConflict(Game.Input.ProxyAction action1, Game.Input.ProxyAction action2, Game.Input.InputManager+DeviceType device) : System.Boolean`  

```csharp
public static System.Boolean CanConflict(Game.Input.ProxyAction action1, Game.Input.ProxyAction action2, Game.Input.InputManager+DeviceType device);
```

- `internal CheckConflicts() : System.Void`  

```csharp
internal System.Void CheckConflicts();
```

- `public CreateActionBarrier(System.String map, System.String name, System.String barrierName) : Game.Input.InputBarrier`  

```csharp
public Game.Input.InputBarrier CreateActionBarrier(System.String map, System.String name, System.String barrierName);
```

- `internal CreateCompositeBinding(UnityEngine.InputSystem.InputAction action, Game.Input.ProxyComposite+Info info) : System.Void`  

```csharp
internal System.Void CreateCompositeBinding(UnityEngine.InputSystem.InputAction action, Game.Input.ProxyComposite+Info info);
```

- `public CreateGlobalBarrier(System.String barrierName) : Game.Input.InputBarrier`  

```csharp
public Game.Input.InputBarrier CreateGlobalBarrier(System.String barrierName);
```

- `public static CreateInstance() : System.Void`  

```csharp
public static System.Void CreateInstance();
```

- `public CreateMapBarrier(System.String map, System.String barrierName) : Game.Input.InputBarrier`  

```csharp
public Game.Input.InputBarrier CreateMapBarrier(System.String map, System.String barrierName);
```

- `public CreateOverlayBarrier(System.String barrierName) : Game.Input.InputBarrier`  

```csharp
public Game.Input.InputBarrier CreateOverlayBarrier(System.String barrierName);
```

- `internal static DeferUpdating() : Game.Input.InputManager+DeferManagerUpdatingWrapper`  

```csharp
internal static Game.Input.InputManager+DeferManagerUpdatingWrapper DeferUpdating();
```

- `public static DestroyInstance() : System.Void`  

```csharp
public static System.Void DestroyInstance();
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public FindAction(System.String mapName, System.String actionName) : Game.Input.ProxyAction`  

```csharp
public Game.Input.ProxyAction FindAction(System.String mapName, System.String actionName);
```

- `public FindAction(Game.Input.ProxyBinding binding) : Game.Input.ProxyAction`  

```csharp
public Game.Input.ProxyAction FindAction(Game.Input.ProxyBinding binding);
```

- `public FindAction(UnityEngine.InputSystem.InputAction action) : Game.Input.ProxyAction`  

```csharp
public Game.Input.ProxyAction FindAction(UnityEngine.InputSystem.InputAction action);
```

- `public FindAction(System.Guid guid) : Game.Input.ProxyAction`  

```csharp
public Game.Input.ProxyAction FindAction(System.Guid guid);
```

- `public FindActionMap(System.String name) : Game.Input.ProxyActionMap`  

```csharp
public Game.Input.ProxyActionMap FindActionMap(System.String name);
```

- `internal FindActionMap(UnityEngine.InputSystem.InputActionMap map) : Game.Input.ProxyActionMap`  

```csharp
internal Game.Input.ProxyActionMap FindActionMap(UnityEngine.InputSystem.InputActionMap map);
```

- `public static GeneratePathForControl(UnityEngine.InputSystem.InputControl control) : System.String`  

```csharp
public static System.String GeneratePathForControl(UnityEngine.InputSystem.InputControl control);
```

- `public GetActiveGamepadType() : Game.Input.InputManager+GamepadType`  

```csharp
public Game.Input.InputManager+GamepadType GetActiveGamepadType();
```

- `public static GetBindingName(Game.Input.ActionComponent component) : System.String`  

```csharp
public static System.String GetBindingName(Game.Input.ActionComponent component);
```

- `public GetBindings(Game.Input.InputManager+PathType pathType, Game.Input.InputManager+BindingOptions bindingOptions) : System.Collections.Generic.List<Game.Input.ProxyBinding>`  

```csharp
public System.Collections.Generic.List<Game.Input.ProxyBinding> GetBindings(Game.Input.InputManager+PathType pathType, Game.Input.InputManager+BindingOptions bindingOptions);
```

- `public GetComposites(UnityEngine.InputSystem.InputAction action) : System.Collections.Generic.List<Game.Input.ProxyComposite>`  

```csharp
public System.Collections.Generic.List<Game.Input.ProxyComposite> GetComposites(UnityEngine.InputSystem.InputAction action);
```

- `public GetGamepadType(UnityEngine.InputSystem.Gamepad gamepad) : Game.Input.InputManager+GamepadType`  

```csharp
public Game.Input.InputManager+GamepadType GetGamepadType(UnityEngine.InputSystem.Gamepad gamepad);
```

- `private GetMaskForControlScheme() : Game.Input.InputManager+DeviceType`  

```csharp
private Game.Input.InputManager+DeviceType GetMaskForControlScheme();
```

- `public static GetModifierName(Game.Input.ActionComponent component) : System.String`  

```csharp
public static System.String GetModifierName(Game.Input.ActionComponent component);
```

- `internal GetOrCreateBindingWatcher(Game.Input.ProxyBinding binding) : Game.Input.ProxyBinding+Watcher`  

```csharp
internal Game.Input.ProxyBinding+Watcher GetOrCreateBindingWatcher(Game.Input.ProxyBinding binding);
```

- `private GetOrCreateMap(System.String name) : Game.Input.ProxyActionMap`  

```csharp
private Game.Input.ProxyActionMap GetOrCreateMap(System.String name);
```

- `public static HasConflicts(Game.Input.ProxyAction action1, Game.Input.ProxyAction action2, System.Nullable<Game.Input.InputManager+DeviceType> maskOverride1 = null, System.Nullable<Game.Input.InputManager+DeviceType> maskOverride2 = null) : System.Boolean`  

```csharp
public static System.Boolean HasConflicts(Game.Input.ProxyAction action1, Game.Input.ProxyAction action2, System.Nullable<Game.Input.InputManager+DeviceType> maskOverride1, System.Nullable<Game.Input.InputManager+DeviceType> maskOverride2);
```

- `public Initialize() : System.Void`  

```csharp
public System.Void Initialize();
```

- `private InitializeAliases() : System.Void`  

```csharp
private System.Void InitializeAliases();
```

- `private InitializeComposites() : System.Void`  

```csharp
private System.Void InitializeComposites();
```

- `private InitializeLinkedActions() : System.Void`  

```csharp
private System.Void InitializeLinkedActions();
```

- `private InitializeMasks() : System.Void`  

```csharp
private System.Void InitializeMasks();
```

- `internal InitializeMasks(Game.Input.ProxyAction action) : System.Void`  

```csharp
internal System.Void InitializeMasks(Game.Input.ProxyAction action);
```

- `private InitializeModifiers() : System.Void`  

```csharp
private System.Void InitializeModifiers();
```

- `private InitializeModifiers(UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax compositeIterator, UnityEngine.InputSystem.InputAction action, Game.Input.CompositeInstance compositeInstance) : System.Void`  

```csharp
private System.Void InitializeModifiers(UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax compositeIterator, UnityEngine.InputSystem.InputAction action, Game.Input.CompositeInstance compositeInstance);
```

- `private IsDeviceTypePaired<T>() : System.Boolean`  

```csharp
private System.Boolean IsDeviceTypePaired<T>();
```

- `public static IsGamepadActive() : System.Boolean`  

```csharp
public static System.Boolean IsGamepadActive();
```

- `internal OnActionChanged() : System.Void`  

```csharp
internal System.Void OnActionChanged();
```

- `internal OnActionDisplayNamesChanged() : System.Void`  

```csharp
internal System.Void OnActionDisplayNamesChanged();
```

- `internal OnActionMasksChanged() : System.Void`  

```csharp
internal System.Void OnActionMasksChanged();
```

- `private OnAddDevice(UnityEngine.InputSystem.InputDevice device) : System.Void`  

```csharp
private System.Void OnAddDevice(UnityEngine.InputSystem.InputDevice device);
```

- `private OnDeviceActivated(UnityEngine.InputSystem.InputDevice newDevice) : System.Void`  

```csharp
private System.Void OnDeviceActivated(UnityEngine.InputSystem.InputDevice newDevice);
```

- `private OnDeviceAssociationChanged(Colossal.PSI.Common.IPlatformServiceIntegration psi, Colossal.PSI.Common.DeviceAssociationChange change) : System.Void`  

```csharp
private System.Void OnDeviceAssociationChanged(Colossal.PSI.Common.IPlatformServiceIntegration psi, Colossal.PSI.Common.DeviceAssociationChange change);
```

- `private OnDeviceChange(UnityEngine.InputSystem.InputDevice device, UnityEngine.InputSystem.InputDeviceChange change) : System.Void`  

```csharp
private System.Void OnDeviceChange(UnityEngine.InputSystem.InputDevice device, UnityEngine.InputSystem.InputDeviceChange change);
```

- `internal OnEnabledActionsChanged() : System.Void`  

```csharp
internal System.Void OnEnabledActionsChanged();
```

- `public OnFocusChanged(System.Boolean hasFocus) : System.Void`  

```csharp
public System.Void OnFocusChanged(System.Boolean hasFocus);
```

- `private OnOverlayStateChanged(Colossal.PSI.Common.IOverlaySupport psi, System.Boolean active) : System.Void`  

```csharp
private System.Void OnOverlayStateChanged(Colossal.PSI.Common.IOverlaySupport psi, System.Boolean active);
```

- `internal OnPreResolvedActionChanged() : System.Void`  

```csharp
internal System.Void OnPreResolvedActionChanged();
```

- `private OnRemoveDevice(UnityEngine.InputSystem.InputDevice device) : System.Void`  

```csharp
private System.Void OnRemoveDevice(UnityEngine.InputSystem.InputDevice device);
```

- `private OnUnpairedDeviceUsed(UnityEngine.InputSystem.InputDevice device) : System.Void`  

```csharp
private System.Void OnUnpairedDeviceUsed(UnityEngine.InputSystem.InputDevice device);
```

- `private PairDevice(UnityEngine.InputSystem.InputDevice device) : System.Void`  

```csharp
private System.Void PairDevice(UnityEngine.InputSystem.InputDevice device);
```

- `private ProcessActionsUpdate(System.Boolean ignoreDefer = False) : System.Void`  

```csharp
private System.Void ProcessActionsUpdate(System.Boolean ignoreDefer);
```

- `private RefreshActiveControl() : System.Void`  

```csharp
private System.Void RefreshActiveControl();
```

- `public ResetAllBindings(System.Boolean onlyBuiltIn = True) : System.Void`  

```csharp
public System.Void ResetAllBindings(System.Boolean onlyBuiltIn);
```

- `public ResetGroupBindings(Game.Input.InputManager+DeviceType device, System.Boolean onlyBuiltIn = True) : System.Void`  

```csharp
public System.Void ResetGroupBindings(Game.Input.InputManager+DeviceType device, System.Boolean onlyBuiltIn);
```

- `public SetBinding(Game.Input.ProxyBinding newBinding, Game.Input.ProxyBinding& result) : System.Boolean`  

```csharp
public System.Boolean SetBinding(Game.Input.ProxyBinding newBinding, Game.Input.ProxyBinding& result);
```

- `private SetBindingImpl(Game.Input.ProxyBinding bindingToSet, Game.Input.ProxyBinding& newBinding) : System.Boolean`  

```csharp
private System.Boolean SetBindingImpl(Game.Input.ProxyBinding bindingToSet, Game.Input.ProxyBinding& newBinding);
```

- `public SetBindings(System.Collections.Generic.IEnumerable<Game.Input.ProxyBinding> newBindings, System.Collections.Generic.List`1[[Game.Input.ProxyBinding, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resultBindings) : System.Boolean`  

```csharp
public System.Boolean SetBindings(System.Collections.Generic.IEnumerable<Game.Input.ProxyBinding> newBindings, System.Collections.Generic.List`1[[Game.Input.ProxyBinding, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resultBindings);
```

- `private SetBuiltInConflictNotification(System.Boolean conflict) : System.Void`  

```csharp
private System.Void SetBuiltInConflictNotification(System.Boolean conflict);
```

- `public SetDefaultControlScheme() : System.Void`  

```csharp
public System.Void SetDefaultControlScheme();
```

- `private SetModConflictNotification(Game.Input.ProxyActionMap map, System.Boolean conflict) : System.Void`  

```csharp
private System.Void SetModConflictNotification(Game.Input.ProxyActionMap map, System.Boolean conflict);
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
public System.Boolean TryFindAction(System.String mapName, System.String actionName, Game.Input.ProxyAction& action);
```

- `public TryFindAction(Game.Input.ProxyBinding binding, Game.Input.ProxyAction& action) : System.Boolean`  

```csharp
public System.Boolean TryFindAction(Game.Input.ProxyBinding binding, Game.Input.ProxyAction& action);
```

- `public TryFindAction(UnityEngine.InputSystem.InputAction action, Game.Input.ProxyAction& proxyAction) : System.Boolean`  

```csharp
public System.Boolean TryFindAction(UnityEngine.InputSystem.InputAction action, Game.Input.ProxyAction& proxyAction);
```

- `public TryFindAction(System.Guid guid, Game.Input.ProxyAction& proxyAction) : System.Boolean`  

```csharp
public System.Boolean TryFindAction(System.Guid guid, Game.Input.ProxyAction& proxyAction);
```

- `internal TryFindAction(System.Int32 index, Game.Input.ProxyAction& action) : System.Boolean`  

```csharp
internal System.Boolean TryFindAction(System.Int32 index, Game.Input.ProxyAction& action);
```

- `public TryFindActionMap(System.String name, Game.Input.ProxyActionMap& map) : System.Boolean`  

```csharp
public System.Boolean TryFindActionMap(System.String name, Game.Input.ProxyActionMap& map);
```

- `internal TryFindActionMap(UnityEngine.InputSystem.InputActionMap map, Game.Input.ProxyActionMap& proxyMap) : System.Boolean`  

```csharp
internal System.Boolean TryFindActionMap(UnityEngine.InputSystem.InputActionMap map, Game.Input.ProxyActionMap& proxyMap);
```

- `public TryGetBinding(Game.Input.ProxyBinding bindingToGet, Game.Input.InputManager+PathType pathType, Game.Input.InputManager+BindingOptions bindingOptions, Game.Input.ProxyBinding& foundBinding) : System.Boolean`  

```csharp
public System.Boolean TryGetBinding(Game.Input.ProxyBinding bindingToGet, Game.Input.InputManager+PathType pathType, Game.Input.InputManager+BindingOptions bindingOptions, Game.Input.ProxyBinding& foundBinding);
```

- `private TryGetBinding(UnityEngine.InputSystem.InputAction action, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax compositeIterator, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax bindingIterator, Game.Input.CompositeInstance compositeInstance, Game.Input.InputManager+CompositeComponentData componentData, Game.Input.InputManager+PathType pathType, Game.Input.InputManager+BindingOptions bindingOptions, Game.Input.ProxyBinding& foundBinding) : System.Boolean`  

```csharp
private System.Boolean TryGetBinding(UnityEngine.InputSystem.InputAction action, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax compositeIterator, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax bindingIterator, Game.Input.CompositeInstance compositeInstance, Game.Input.InputManager+CompositeComponentData componentData, Game.Input.InputManager+PathType pathType, Game.Input.InputManager+BindingOptions bindingOptions, Game.Input.ProxyBinding& foundBinding);
```

- `private TryGetComposite(UnityEngine.InputSystem.InputAction action, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax compositeIterator, Game.Input.InputManager+PathType pathType, Game.Input.InputManager+BindingOptions bindingOptions, Game.Input.ProxyComposite& proxyComposite) : System.Boolean`  

```csharp
private System.Boolean TryGetComposite(UnityEngine.InputSystem.InputAction action, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax compositeIterator, Game.Input.InputManager+PathType pathType, Game.Input.InputManager+BindingOptions bindingOptions, Game.Input.ProxyComposite& proxyComposite);
```

- `internal static TryGetCompositeData(System.String name, Game.Input.InputManager+CompositeData& data) : System.Boolean`  

```csharp
internal static System.Boolean TryGetCompositeData(System.String name, Game.Input.InputManager+CompositeData& data);
```

- `internal static TryGetCompositeData(Game.Input.ActionType actionType, Game.Input.InputManager+CompositeData& data) : System.Boolean`  

```csharp
internal static System.Boolean TryGetCompositeData(Game.Input.ActionType actionType, Game.Input.InputManager+CompositeData& data);
```

- `private TryGetCompositeInstance(UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax compositeIterator, Game.Input.CompositeInstance& compositeInstance) : System.Boolean`  

```csharp
private System.Boolean TryGetCompositeInstance(UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax compositeIterator, Game.Input.CompositeInstance& compositeInstance);
```

- `private TryGetIterators(Game.Input.ProxyBinding bindingSample, UnityEngine.InputSystem.InputAction action, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax& compositeIterator, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax& bindingIterator, Game.Input.CompositeInstance& compositeInstance, Game.Input.InputManager+CompositeComponentData& componentData) : System.Boolean`  

```csharp
private System.Boolean TryGetIterators(Game.Input.ProxyBinding bindingSample, UnityEngine.InputSystem.InputAction action, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax& compositeIterator, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax& bindingIterator, Game.Input.CompositeInstance& compositeInstance, Game.Input.InputManager+CompositeComponentData& componentData);
```

- `public TryGetMainBinding(UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax iterator, Game.Input.InputManager+PathType pathType, System.String& currentPath, System.String& originalPath) : System.Boolean`  

```csharp
public System.Boolean TryGetMainBinding(UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax iterator, Game.Input.InputManager+PathType pathType, System.String& currentPath, System.String& originalPath);
```

- `public TryGetModifierBindings(UnityEngine.InputSystem.InputAction action, Game.Input.CompositeInstance compositeInstance, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax compositeIterator, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax iterator, Game.Input.InputManager+PathType pathType, Game.Input.InputManager+CompositeComponentData componentData, Game.Input.ProxyModifier[]& currentModifiers, Game.Input.ProxyModifier[]& originalModifiers) : System.Boolean`  

```csharp
public System.Boolean TryGetModifierBindings(UnityEngine.InputSystem.InputAction action, Game.Input.CompositeInstance compositeInstance, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax compositeIterator, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax iterator, Game.Input.InputManager+PathType pathType, Game.Input.InputManager+CompositeComponentData componentData, Game.Input.ProxyModifier[]& currentModifiers, Game.Input.ProxyModifier[]& originalModifiers);
```

- `private TryPairDevice(UnityEngine.InputSystem.InputDevice device) : System.Boolean`  

```csharp
private System.Boolean TryPairDevice(UnityEngine.InputSystem.InputDevice device);
```

- `private TrySetBindingModifierProcessor(UnityEngine.InputSystem.InputAction action, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax modifierIterator, System.Boolean allow) : System.Boolean`  

```csharp
private System.Boolean TrySetBindingModifierProcessor(UnityEngine.InputSystem.InputAction action, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax modifierIterator, System.Boolean allow);
```

- `private TrySetMainBinding(Game.Input.ProxyBinding bindingToSet, UnityEngine.InputSystem.InputAction action, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax bindingIterator, System.Boolean& changed) : System.Boolean`  

```csharp
private System.Boolean TrySetMainBinding(Game.Input.ProxyBinding bindingToSet, UnityEngine.InputSystem.InputAction action, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax bindingIterator, System.Boolean& changed);
```

- `private TrySetModifierBindings(Game.Input.ProxyBinding bindingToSet, UnityEngine.InputSystem.InputAction action, Game.Input.CompositeInstance compositeInstance, Game.Input.InputManager+CompositeComponentData componentData, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax compositeIterator, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax bindingIterator, System.Boolean& changed) : System.Boolean`  

```csharp
private System.Boolean TrySetModifierBindings(Game.Input.ProxyBinding bindingToSet, UnityEngine.InputSystem.InputAction action, Game.Input.CompositeInstance compositeInstance, Game.Input.InputManager+CompositeComponentData componentData, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax compositeIterator, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax bindingIterator, System.Boolean& changed);
```

- `private TryUnpairDevice(UnityEngine.InputSystem.InputDevice device) : System.Boolean`  

```csharp
private System.Boolean TryUnpairDevice(UnityEngine.InputSystem.InputDevice device);
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
private System.Void UnpairDevice(UnityEngine.InputSystem.InputDevice device);
```

- `public Update() : System.Void`  

```csharp
public System.Void Update();
```

- `internal UpdateActionInKeyActionMap(Game.Input.ProxyAction action) : System.Void`  

```csharp
internal System.Void UpdateActionInKeyActionMap(Game.Input.ProxyAction action);
```

- `private UpdateConnectedDeviceTypes() : System.Void`  

```csharp
private System.Void UpdateConnectedDeviceTypes();
```

- `private UpdateCursorVisibility() : System.Void`  

```csharp
private System.Void UpdateCursorVisibility();
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

