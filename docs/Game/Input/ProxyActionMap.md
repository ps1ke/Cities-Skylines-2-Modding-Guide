# Game.Input.ProxyActionMap

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class public  

**Base:** `System.Object`  

**Attributes:** `DebuggerDisplay`  

## Fields

- `private readonly UnityEngine.InputSystem.InputActionMap m_SourceMap`  
- `private readonly System.Collections.Generic.Dictionary<System.String, Game.Input.ProxyAction> m_Actions`  
- `internal System.Collections.Generic.HashSet<Game.Input.InputBarrier> m_Barriers`  
- `private System.Boolean m_Enabled`  
- `private Game.Input.InputManager+DeviceType m_Mask`  

## Properties

- `internal UnityEngine.InputSystem.InputActionMap sourceMap { internal get }`  
- `public System.String name { get }`  
- `public System.Collections.Generic.IReadOnlyDictionary<System.String, Game.Input.ProxyAction> actions { get }`  
- `internal System.Collections.Generic.IReadOnlyCollection<Game.Input.InputBarrier> barriers { internal get }`  
- `public System.Collections.Generic.IEnumerable<Game.Input.ProxyBinding> bindings { get }`  
- `public System.Boolean enabled { get }`  
- `public Game.Input.InputManager+DeviceType mask { get; internal set }`  

## Constructors

- `internal ProxyActionMap(UnityEngine.InputSystem.InputActionMap sourceMap)`  

## Methods

- `public AddAction(Game.Input.ProxyAction+Info actionInfo, System.Boolean bulk = False) : Game.Input.ProxyAction`  
- `public FindAction(System.String name) : Game.Input.ProxyAction`  
- `internal FindAction(UnityEngine.InputSystem.InputAction action) : Game.Input.ProxyAction`  
- `internal InitActions() : System.Void`  
- `public TryFindAction(System.String name, Game.Input.ProxyAction& action) : System.Boolean`  
- `internal UpdateState() : System.Void`  

## Nested types

- `Game.Input.ProxyActionMap+<>c`  
- `Game.Input.ProxyActionMap+<>c__DisplayClass25_0`  
- `Game.Input.ProxyActionMap+<get_bindings>d__14`  

