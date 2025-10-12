# Game.Input.InputManager

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`, `UnityEngine.InputSystem.IInputActionCollection`, `System.Collections.Generic.IEnumerable<UnityEngine.InputSystem.InputAction>`, `System.Collections.IEnumerable`  

## Fields

- `private System.Boolean m_NeedUpdate`  
- `private readonly Game.Input.InputConflictResolution m_ConflictResolution`  
- `private readonly UnityEngine.InputSystem.InputActionAsset m_ActionAsset`  
- `private readonly Game.Input.UIInputActionCollection m_UIActionCollection`  
- `private readonly Game.Input.UIInputActionCollection m_ToolActionCollection`  
- `private readonly System.Collections.Generic.Dictionary<System.String, Game.Input.ProxyActionMap> m_Maps`  
- `private System.Action<Game.Input.InputManager+ControlScheme> EventControlSchemeChanged`  
- `private Game.Input.InputManager+ActiveDeviceChanged EventActiveDeviceChanged`  
- `private System.Action EventActiveDeviceDisconnected`  
- `private System.Action EventActiveDeviceAssociationLost`  
- `private System.Action EventDevicePaired`  
- `private System.Action EventActionsChanged`  
- `private System.Action EventEnabledActionsChanged`  
- `private System.Action EventActionMasksChanged`  
- `private System.Action EventActionDisplayNamesChanged`  
- `private System.Action<System.Boolean> EventMouseOverUIChanged`  
- `private System.Action EventPreResolvedActionChanged`  
- `private System.Collections.Generic.Dictionary<UnityEngine.InputSystem.InputDevice, Game.Input.DeviceListener> m_DeviceListeners`  
- `private UnityEngine.InputSystem.InputDevice m_LastActiveDevice`  
- `private System.Boolean m_MouseOverUI`  
- `private System.Single m_AccumulatedIdleDelay`  
- `private System.Boolean m_WasWorldReady`  
- `private System.Boolean m_Idle`  
- `private System.Boolean m_HasFocus`  
- `private System.Boolean m_HasInputFieldFocus`  
- `private System.Boolean m_OverlayActive`  
- `private System.Boolean m_HideCursor`  
- `private Game.Input.InputManager+ControlScheme m_ActiveControlScheme`  
- `private UnityEngine.InputSystem.InputActionMap+DeviceArray m_Devices`  
- `private Game.Input.InputManager+DeviceType m_ConnectedDeviceTypes`  
- `private Game.Input.InputManager+DeviceType m_BlockedControlTypes`  
- `private Game.Input.InputManager+DeviceType m_Mask`  
- `private readonly System.Collections.Generic.Dictionary<Game.Input.ProxyBinding, Game.Input.ProxyBinding+Watcher> m_ProxyBindingWatchers`  
- `private System.ValueTuple<UnityEngine.Vector2, UnityEngine.Vector2> <caretRect>k__BackingField`  
- `private UnityEngine.InputSystem.Users.InputUser <inputUser>k__BackingField`  
- `private System.Int32 <actionVersion>k__BackingField`  
- `private readonly System.Collections.Generic.Dictionary<System.String, System.Collections.Generic.HashSet<Game.Input.ProxyAction>> <keyActionMap>k__BackingField`  
- `private readonly System.Collections.Generic.Dictionary<Game.Input.ProxyAction, System.Collections.Generic.HashSet<System.String>> <actionKeyMap>k__BackingField`  
- `private readonly System.Collections.Generic.Dictionary<System.Int32, Game.Input.ProxyAction> <actionIndex>k__BackingField`  
- `private Game.Input.InputManager+DeviceType <bindingConflicts>k__BackingField`  
- `private static System.Collections.Generic.IReadOnlyList<Game.Input.InputManager+CompositeData> m_Composites`  
- `private static UnityEngine.InputSystem.Layouts.InputControlLayout+Cache m_LayoutCache`  
- `private static System.Text.StringBuilder m_PathBuilder`  
- `private static System.Collections.Generic.Dictionary<Game.Input.InputManager+DeviceType, System.Collections.Generic.HashSet<System.String>> kModifiers`  
- `private static Game.Input.InputManager s_Instance`  
- `public static readonly Colossal.Logging.ILog log`  
- `private static System.String m_ProhibitionModifierProcessor`  
- `private static readonly Game.Input.InputManager+DeferManagerUpdatingWrapper sDeferUpdatingWrapper`  
- `public static const System.String kShiftName`  
- `public static const System.String kCtrlName`  
- `public static const System.String kAltName`  
- `public static const System.String kLeftStick`  
- `public static const System.String kRightStick`  
- `public static const System.String kSplashScreenMap`  
- `public static const System.String kNavigationMap`  
- `public static const System.String kMenuMap`  
- `public static const System.String kCameraMap`  
- `public static const System.String kToolMap`  
- `public static const System.String kShortcutsMap`  
- `public static const System.String kPhotoModeMap`  
- `public static const System.String kEditorMap`  
- `public static const System.String kDebugMap`  
- `public static const System.String kEngagementMap`  
- `public static const System.Int32 kIdleDelay`  
- `private static const System.String kKeyBindingConflict`  
- `private static const System.String kKeyBindingConflictResolved`  

## Properties

- `public System.Collections.Generic.IEnumerable<Game.Input.ProxyAction> actions { get }`  
- `public static Game.Input.InputManager instance { get }`  
- `public System.Boolean mouseOverUI { get; set }`  
- `public System.Boolean hasInputFieldFocus { get; set }`  
- `public System.Boolean overlayActive { get }`  
- `public System.ValueTuple<UnityEngine.Vector2, UnityEngine.Vector2> caretRect { get; set }`  
- `public System.Boolean controlOverWorld { get }`  
- `private System.Nullable<UnityEngine.InputSystem.InputBinding> UnityEngine.InputSystem.IInputActionCollection.bindingMask { private get; private set }`  
- `private System.Nullable<UnityEngine.InputSystem.Utilities.ReadOnlyArray<UnityEngine.InputSystem.InputDevice>> UnityEngine.InputSystem.IInputActionCollection.devices { private get; private set }`  
- `private UnityEngine.InputSystem.Utilities.ReadOnlyArray<UnityEngine.InputSystem.InputControlScheme> UnityEngine.InputSystem.IInputActionCollection.controlSchemes { private get }`  
- `public Game.Input.InputManager+ControlScheme activeControlScheme { get; private set }`  
- `public System.Boolean isGamepadControlSchemeActive { get }`  
- `public System.Boolean isKeyboardAndMouseControlSchemeActive { get }`  
- `public Game.Input.InputManager+DeviceType connectedDeviceTypes { get }`  
- `internal Game.Input.InputManager+DeviceType mask { internal get; internal set }`  
- `internal Game.Input.InputManager+DeviceType blockedControlTypes { internal get; internal set }`  
- `public System.Boolean mouseOnScreen { get }`  
- `public UnityEngine.Vector2 gamepadPointerPosition { get }`  
- `public UnityEngine.Vector3 mousePosition { get }`  
- `public System.Boolean hideCursor { get; set }`  
- `public UnityEngine.CursorLockMode cursorLockMode { get; set }`  
- `public UnityEngine.InputSystem.Users.InputUser inputUser { get; private set }`  
- `public System.Int32 actionVersion { get; private set }`  
- `internal System.Collections.Generic.Dictionary<System.String, System.Collections.Generic.HashSet<Game.Input.ProxyAction>> keyActionMap { internal get }`  
- `internal System.Collections.Generic.Dictionary<Game.Input.ProxyAction, System.Collections.Generic.HashSet<System.String>> actionKeyMap { internal get }`  
- `internal System.Collections.Generic.Dictionary<System.Int32, Game.Input.ProxyAction> actionIndex { internal get }`  
- `private static System.String prohibitionModifierProcessor { private get }`  
- `internal Game.Input.UIInputActionCollection uiActionCollection { internal get }`  
- `internal Game.Input.UIInputActionCollection toolActionCollection { internal get }`  
- `public Game.Input.InputManager+DeviceType bindingConflicts { get; private set }`  
- `public static System.Boolean IsKeyboardConnected { get }`  
- `public static System.Boolean IsMouseConnected { get }`  
- `public static System.Boolean IsGamepadConnected { get }`  

## Constructors

- `public InputManager()`  

## Methods

- `private <SetBuiltInConflictNotification>b__210_0() : System.Void`  
- `private <SetBuiltInConflictNotification>g__Callback|210_1(System.Int32 msg) : System.Void`  
- `private AddActionMap(System.String name) : Game.Input.ProxyActionMap`  
- `internal AddActions(Game.Input.ProxyAction+Info[] actionsToAdd) : System.Void`  
- `public AddInitialDevices() : System.Void`  
- `public AssociateActionsWithUser(System.Boolean associate) : System.Void`  
- `public static CanConflict(Game.Input.ProxyAction action1, Game.Input.ProxyAction action2, Game.Input.InputManager+DeviceType device) : System.Boolean`  
- `internal CheckConflicts() : System.Void`  
- `public CreateActionBarrier(System.String map, System.String name, System.String barrierName) : Game.Input.InputBarrier`  
- `internal CreateCompositeBinding(UnityEngine.InputSystem.InputAction action, Game.Input.ProxyComposite+Info info) : System.Void`  
- `public CreateGlobalBarrier(System.String barrierName) : Game.Input.InputBarrier`  
- `public static CreateInstance() : System.Void`  
- `public CreateMapBarrier(System.String map, System.String barrierName) : Game.Input.InputBarrier`  
- `public CreateOverlayBarrier(System.String barrierName) : Game.Input.InputBarrier`  
- `internal static DeferUpdating() : Game.Input.InputManager+DeferManagerUpdatingWrapper`  
- `public static DestroyInstance() : System.Void`  
- `public Dispose() : System.Void`  
- `public FindAction(System.String mapName, System.String actionName) : Game.Input.ProxyAction`  
- `public FindAction(Game.Input.ProxyBinding binding) : Game.Input.ProxyAction`  
- `public FindAction(UnityEngine.InputSystem.InputAction action) : Game.Input.ProxyAction`  
- `public FindAction(System.Guid guid) : Game.Input.ProxyAction`  
- `public FindActionMap(System.String name) : Game.Input.ProxyActionMap`  
- `internal FindActionMap(UnityEngine.InputSystem.InputActionMap map) : Game.Input.ProxyActionMap`  
- `public static GeneratePathForControl(UnityEngine.InputSystem.InputControl control) : System.String`  
- `public GetActiveGamepadType() : Game.Input.InputManager+GamepadType`  
- `public static GetBindingName(Game.Input.ActionComponent component) : System.String`  
- `public GetBindings(Game.Input.InputManager+PathType pathType, Game.Input.InputManager+BindingOptions bindingOptions) : System.Collections.Generic.List<Game.Input.ProxyBinding>`  
- `public GetComposites(UnityEngine.InputSystem.InputAction action) : System.Collections.Generic.List<Game.Input.ProxyComposite>`  
- `public GetGamepadType(UnityEngine.InputSystem.Gamepad gamepad) : Game.Input.InputManager+GamepadType`  
- `private GetMaskForControlScheme() : Game.Input.InputManager+DeviceType`  
- `public static GetModifierName(Game.Input.ActionComponent component) : System.String`  
- `internal GetOrCreateBindingWatcher(Game.Input.ProxyBinding binding) : Game.Input.ProxyBinding+Watcher`  
- `private GetOrCreateMap(System.String name) : Game.Input.ProxyActionMap`  
- `public static HasConflicts(Game.Input.ProxyAction action1, Game.Input.ProxyAction action2, System.Nullable<Game.Input.InputManager+DeviceType> maskOverride1 = null, System.Nullable<Game.Input.InputManager+DeviceType> maskOverride2 = null) : System.Boolean`  
- `public Initialize() : System.Void`  
- `private InitializeAliases() : System.Void`  
- `private InitializeComposites() : System.Void`  
- `private InitializeLinkedActions() : System.Void`  
- `private InitializeMasks() : System.Void`  
- `internal InitializeMasks(Game.Input.ProxyAction action) : System.Void`  
- `private InitializeModifiers() : System.Void`  
- `private InitializeModifiers(UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax compositeIterator, UnityEngine.InputSystem.InputAction action, Game.Input.CompositeInstance compositeInstance) : System.Void`  
- `private IsDeviceTypePaired<T>() : System.Boolean`  
- `public static IsGamepadActive() : System.Boolean`  
- `internal OnActionChanged() : System.Void`  
- `internal OnActionDisplayNamesChanged() : System.Void`  
- `internal OnActionMasksChanged() : System.Void`  
- `private OnAddDevice(UnityEngine.InputSystem.InputDevice device) : System.Void`  
- `private OnDeviceActivated(UnityEngine.InputSystem.InputDevice newDevice) : System.Void`  
- `private OnDeviceAssociationChanged(Colossal.PSI.Common.IPlatformServiceIntegration psi, Colossal.PSI.Common.DeviceAssociationChange change) : System.Void`  
- `private OnDeviceChange(UnityEngine.InputSystem.InputDevice device, UnityEngine.InputSystem.InputDeviceChange change) : System.Void`  
- `internal OnEnabledActionsChanged() : System.Void`  
- `public OnFocusChanged(System.Boolean hasFocus) : System.Void`  
- `private OnOverlayStateChanged(Colossal.PSI.Common.IOverlaySupport psi, System.Boolean active) : System.Void`  
- `internal OnPreResolvedActionChanged() : System.Void`  
- `private OnRemoveDevice(UnityEngine.InputSystem.InputDevice device) : System.Void`  
- `private OnUnpairedDeviceUsed(UnityEngine.InputSystem.InputDevice device) : System.Void`  
- `private PairDevice(UnityEngine.InputSystem.InputDevice device) : System.Void`  
- `private ProcessActionsUpdate(System.Boolean ignoreDefer = False) : System.Void`  
- `private RefreshActiveControl() : System.Void`  
- `public ResetAllBindings(System.Boolean onlyBuiltIn = True) : System.Void`  
- `public ResetGroupBindings(Game.Input.InputManager+DeviceType device, System.Boolean onlyBuiltIn = True) : System.Void`  
- `public SetBinding(Game.Input.ProxyBinding newBinding, Game.Input.ProxyBinding& result) : System.Boolean`  
- `private SetBindingImpl(Game.Input.ProxyBinding bindingToSet, Game.Input.ProxyBinding& newBinding) : System.Boolean`  
- `public SetBindings(System.Collections.Generic.IEnumerable<Game.Input.ProxyBinding> newBindings, System.Collections.Generic.List`1[[Game.Input.ProxyBinding, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resultBindings) : System.Boolean`  
- `private SetBuiltInConflictNotification(System.Boolean conflict) : System.Void`  
- `public SetDefaultControlScheme() : System.Void`  
- `private SetModConflictNotification(Game.Input.ProxyActionMap map, System.Boolean conflict) : System.Void`  
- `private System.Collections.Generic.IEnumerable<UnityEngine.InputSystem.InputAction>.GetEnumerator() : System.Collections.Generic.IEnumerator<UnityEngine.InputSystem.InputAction>`  
- `private System.Collections.IEnumerable.GetEnumerator() : System.Collections.IEnumerator`  
- `public TryFindAction(System.String mapName, System.String actionName, Game.Input.ProxyAction& action) : System.Boolean`  
- `public TryFindAction(Game.Input.ProxyBinding binding, Game.Input.ProxyAction& action) : System.Boolean`  
- `public TryFindAction(UnityEngine.InputSystem.InputAction action, Game.Input.ProxyAction& proxyAction) : System.Boolean`  
- `public TryFindAction(System.Guid guid, Game.Input.ProxyAction& proxyAction) : System.Boolean`  
- `internal TryFindAction(System.Int32 index, Game.Input.ProxyAction& action) : System.Boolean`  
- `public TryFindActionMap(System.String name, Game.Input.ProxyActionMap& map) : System.Boolean`  
- `internal TryFindActionMap(UnityEngine.InputSystem.InputActionMap map, Game.Input.ProxyActionMap& proxyMap) : System.Boolean`  
- `public TryGetBinding(Game.Input.ProxyBinding bindingToGet, Game.Input.InputManager+PathType pathType, Game.Input.InputManager+BindingOptions bindingOptions, Game.Input.ProxyBinding& foundBinding) : System.Boolean`  
- `private TryGetBinding(UnityEngine.InputSystem.InputAction action, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax compositeIterator, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax bindingIterator, Game.Input.CompositeInstance compositeInstance, Game.Input.InputManager+CompositeComponentData componentData, Game.Input.InputManager+PathType pathType, Game.Input.InputManager+BindingOptions bindingOptions, Game.Input.ProxyBinding& foundBinding) : System.Boolean`  
- `private TryGetComposite(UnityEngine.InputSystem.InputAction action, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax compositeIterator, Game.Input.InputManager+PathType pathType, Game.Input.InputManager+BindingOptions bindingOptions, Game.Input.ProxyComposite& proxyComposite) : System.Boolean`  
- `internal static TryGetCompositeData(System.String name, Game.Input.InputManager+CompositeData& data) : System.Boolean`  
- `internal static TryGetCompositeData(Game.Input.ActionType actionType, Game.Input.InputManager+CompositeData& data) : System.Boolean`  
- `private TryGetCompositeInstance(UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax compositeIterator, Game.Input.CompositeInstance& compositeInstance) : System.Boolean`  
- `private TryGetIterators(Game.Input.ProxyBinding bindingSample, UnityEngine.InputSystem.InputAction action, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax& compositeIterator, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax& bindingIterator, Game.Input.CompositeInstance& compositeInstance, Game.Input.InputManager+CompositeComponentData& componentData) : System.Boolean`  
- `public TryGetMainBinding(UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax iterator, Game.Input.InputManager+PathType pathType, System.String& currentPath, System.String& originalPath) : System.Boolean`  
- `public TryGetModifierBindings(UnityEngine.InputSystem.InputAction action, Game.Input.CompositeInstance compositeInstance, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax compositeIterator, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax iterator, Game.Input.InputManager+PathType pathType, Game.Input.InputManager+CompositeComponentData componentData, Game.Input.ProxyModifier[]& currentModifiers, Game.Input.ProxyModifier[]& originalModifiers) : System.Boolean`  
- `private TryPairDevice(UnityEngine.InputSystem.InputDevice device) : System.Boolean`  
- `private TrySetBindingModifierProcessor(UnityEngine.InputSystem.InputAction action, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax modifierIterator, System.Boolean allow) : System.Boolean`  
- `private TrySetMainBinding(Game.Input.ProxyBinding bindingToSet, UnityEngine.InputSystem.InputAction action, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax bindingIterator, System.Boolean& changed) : System.Boolean`  
- `private TrySetModifierBindings(Game.Input.ProxyBinding bindingToSet, UnityEngine.InputSystem.InputAction action, Game.Input.CompositeInstance compositeInstance, Game.Input.InputManager+CompositeComponentData componentData, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax compositeIterator, UnityEngine.InputSystem.InputActionSetupExtensions+BindingSyntax bindingIterator, System.Boolean& changed) : System.Boolean`  
- `private TryUnpairDevice(UnityEngine.InputSystem.InputDevice device) : System.Boolean`  
- `private UnityEngine.InputSystem.IInputActionCollection.Contains(UnityEngine.InputSystem.InputAction action) : System.Boolean`  
- `private UnityEngine.InputSystem.IInputActionCollection.Disable() : System.Void`  
- `private UnityEngine.InputSystem.IInputActionCollection.Enable() : System.Void`  
- `private UnpairAll<T>() : System.Void`  
- `private UnpairDevice(UnityEngine.InputSystem.InputDevice device) : System.Void`  
- `public Update() : System.Void`  
- `internal UpdateActionInKeyActionMap(Game.Input.ProxyAction action) : System.Void`  
- `private UpdateConnectedDeviceTypes() : System.Void`  
- `private UpdateCursorVisibility() : System.Void`  

## Events

- `EventControlSchemeChanged` : `System.Action<Game.Input.InputManager+ControlScheme>`  
- `EventActiveDeviceChanged` : `Game.Input.InputManager+ActiveDeviceChanged`  
- `EventActiveDeviceDisconnected` : `System.Action`  
- `EventActiveDeviceAssociationLost` : `System.Action`  
- `EventDevicePaired` : `System.Action`  
- `EventActionsChanged` : `System.Action`  
- `EventEnabledActionsChanged` : `System.Action`  
- `EventActionMasksChanged` : `System.Action`  
- `EventActionDisplayNamesChanged` : `System.Action`  
- `EventMouseOverUIChanged` : `System.Action<System.Boolean>`  
- `EventPreResolvedActionChanged` : `System.Action`  

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

