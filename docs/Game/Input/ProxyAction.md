# Game.Input.ProxyAction

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.Input.IProxyAction`  

## Fields

- `private System.Action<Game.Input.ProxyAction> onChanged`  
- `internal readonly System.Int32 m_GlobalIndex`  
- `private readonly UnityEngine.InputSystem.InputAction m_SourceAction`  
- `private readonly Game.Input.ProxyActionMap m_Map`  
- `internal readonly System.Collections.Generic.HashSet<Game.Input.InputBarrier> m_Barriers`  
- `internal readonly System.Collections.Generic.HashSet<Game.Input.InputActivator> m_Activators`  
- `internal readonly System.Collections.Generic.HashSet<Game.Input.DisplayNameOverride> m_DisplayOverrides`  
- `internal readonly System.Collections.Generic.HashSet<Game.Input.UIBaseInputAction> m_UIAliases`  
- `internal readonly System.Collections.Generic.HashSet<Game.Input.ProxyAction+LinkInfo> m_LinkedActions`  
- `private Game.Input.InputActivator m_DefaultActivator`  
- `private Game.Input.InputActivator m_DefaultBuiltInActivator`  
- `internal System.Boolean m_PreResolvedEnable`  
- `private Game.Input.InputManager+DeviceType m_AvailableMask`  
- `private Game.Input.InputManager+DeviceType m_PreResolvedMask`  
- `private Game.Input.InputManager+DeviceType m_Mask`  
- `private System.Boolean m_IsSystemAction`  
- `private readonly System.Collections.Generic.Dictionary<Game.Input.InputManager+DeviceType, Game.Input.ProxyComposite> m_Composites`  
- `private readonly System.Collections.Generic.List<Game.Input.ProxyBinding> m_Bindings`  
- `private Game.Input.DisplayNameOverride <displayOverride>k__BackingField`  
- `private System.Action<Game.Input.ProxyAction, UnityEngine.InputSystem.InputActionPhase> m_OnInteraction`  
- `private static System.Int32 counter`  
- `internal static readonly Game.Input.ProxyAction+DeferActionUpdatingWrapper sDeferUpdatingWrapper`  
- `internal static readonly Game.Input.ProxyAction+DeferActionStateUpdatingWrapper sDeferStateUpdatingWrapper`  

## Properties

- `public Game.Input.ProxyActionMap map { get }`  
- `internal UnityEngine.InputSystem.InputAction sourceAction { internal get }`  
- `public System.Collections.Generic.IReadOnlyDictionary<Game.Input.InputManager+DeviceType, Game.Input.ProxyComposite> composites { get }`  
- `public System.Int32 compositesCount { get }`  
- `internal System.Collections.Generic.IReadOnlyCollection<Game.Input.InputBarrier> barriers { internal get }`  
- `internal System.Collections.Generic.IReadOnlyCollection<Game.Input.InputActivator> activators { internal get }`  
- `public System.Collections.Generic.IEnumerable<Game.Input.ProxyBinding> bindings { get }`  
- `public System.Boolean isSet { get }`  
- `public System.Boolean isBuiltIn { get }`  
- `internal System.Boolean isDummy { internal get }`  
- `internal System.Boolean isSystemAction { internal get }`  
- `public Game.Input.InputManager+DeviceType availableDevices { get }`  
- `public System.Boolean isKeyboardAction { get }`  
- `public System.Boolean isMouseAction { get }`  
- `public System.Boolean isGamepadAction { get }`  
- `public System.Boolean isOnlyKeyboardAction { get }`  
- `public System.Boolean isOnlyMouseAction { get }`  
- `public System.Boolean isOnlyGamepadAction { get }`  
- `public System.Boolean isMultiDeviceAction { get }`  
- `public System.String name { get }`  
- `public System.String mapName { get }`  
- `public System.String title { get }`  
- `public System.Type valueType { get }`  
- `private System.Boolean Game.Input.IProxyAction.enabled { private get; private set }`  
- `public System.Boolean enabled { get; internal set }`  
- `public System.Boolean shouldBeEnabled { get; set }`  
- `internal System.Boolean preResolvedEnable { internal get }`  
- `public Game.Input.InputManager+DeviceType mask { get }`  
- `internal Game.Input.InputManager+DeviceType preResolvedMask { internal get }`  
- `public Game.Input.DisplayNameOverride displayOverride { get; private set }`  
- `public System.Collections.Generic.IEnumerable<System.String> usedKeys { get }`  

## Constructors

- `internal ProxyAction(Game.Input.ProxyActionMap map, UnityEngine.InputSystem.InputAction sourceAction)`  

## Methods

- `internal ApplyState(System.Boolean newEnable, Game.Input.InputManager+DeviceType newMask) : System.Void`  
- `public ContainsComposite(Game.Input.InputManager+DeviceType device) : System.Boolean`  
- `public CreateActivator(System.String activatorName = null, Game.Input.InputManager+DeviceType activatorMask = All) : Game.Input.InputActivator`  
- `public CreateBarrier(System.String barrierName = null, Game.Input.InputManager+DeviceType barrierMask = All) : Game.Input.InputBarrier`  
- `internal static DeferStateUpdating() : Game.Input.ProxyAction+DeferActionStateUpdatingWrapper`  
- `public GetMagnitude() : System.Single`  
- `public IsInProgress() : System.Boolean`  
- `public IsPressed() : System.Boolean`  
- `internal static LinkActions(Game.Input.ProxyAction+LinkInfo action1, Game.Input.ProxyAction+LinkInfo action2) : System.Void`  
- `private static LinkActions(Game.Input.ProxyAction+LinkInfo link1, Game.Input.ProxyAction+LinkInfo link2, System.Boolean addToOther) : System.Void`  
- `internal ReadRawValue<T>(System.Boolean disableAll = True) : T`  
- `public ReadValue<T>() : T`  
- `public ReadValueAsObject() : System.Object`  
- `private SourceOnCanceled(UnityEngine.InputSystem.InputAction+CallbackContext context) : System.Void`  
- `private SourceOnPerformed(UnityEngine.InputSystem.InputAction+CallbackContext context) : System.Void`  
- `private SourceOnStarted(UnityEngine.InputSystem.InputAction+CallbackContext context) : System.Void`  
- `public virtual ToString() : System.String`  
- `public TryGetBinding(Game.Input.ProxyBinding sampleBinding, Game.Input.ProxyBinding& foundBinding) : System.Boolean`  
- `public TryGetComposite(Game.Input.InputManager+DeviceType device, Game.Input.ProxyComposite& composite) : System.Boolean`  
- `internal Update(System.Boolean ignoreDefer = False) : System.Void`  
- `internal UpdateDisplay() : System.Void`  
- `internal UpdateState(System.Boolean ignoreDefer = False) : System.Void`  
- `public WasPerformedThisFrame() : System.Boolean`  
- `public WasPressedThisFrame() : System.Boolean`  
- `public WasReleasedThisFrame() : System.Boolean`  

## Events

- `onChanged` : `System.Action<Game.Input.ProxyAction>`  
- `onInteraction` : `System.Action<Game.Input.ProxyAction, UnityEngine.InputSystem.InputActionPhase>`  

## Nested types

- `Game.Input.ProxyAction+Info`  
- `Game.Input.ProxyAction+LinkInfo`  
- `Game.Input.ProxyAction+DeferActionUpdatingWrapper`  
- `Game.Input.ProxyAction+DeferActionStateUpdatingWrapper`  
- `Game.Input.ProxyAction+<>c`  
- `Game.Input.ProxyAction+<get_bindings>d__34`  

