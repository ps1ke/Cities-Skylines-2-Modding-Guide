# Game.Input.InputActivator

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Fields

- `private readonly Game.Input.ProxyAction[] m_Actions`  
- `private readonly System.String m_Name`  
- `private System.Boolean m_Enabled`  
- `private Game.Input.InputManager+DeviceType m_Mask`  
- `private System.Boolean m_Disposed`  

## Properties

- `public System.String name { get }`  
- `public System.Collections.Generic.IReadOnlyList<Game.Input.ProxyAction> actions { get }`  
- `public System.Boolean enabled { get; set }`  
- `public Game.Input.InputManager+DeviceType mask { get; set }`  

## Constructors

- `public InputActivator(System.String activatorName, Game.Input.ProxyAction action, Game.Input.InputManager+DeviceType mask = All, System.Boolean enabled = False)`  
- `internal InputActivator(System.Boolean ignoreIsBuiltIn, System.String activatorName, Game.Input.ProxyAction action, Game.Input.InputManager+DeviceType mask = All, System.Boolean enabled = False)`  
- `public InputActivator(System.String activatorName, System.Collections.Generic.IList<Game.Input.ProxyAction> actions, Game.Input.InputManager+DeviceType mask = All, System.Boolean enabled = False)`  
- `internal InputActivator(System.Boolean ignoreIsBuiltIn, System.String activatorName, System.Collections.Generic.IList<Game.Input.ProxyAction> actions, Game.Input.InputManager+DeviceType mask = All, System.Boolean enabled = False)`  

## Methods

- `public Dispose() : System.Void`  
- `private Update() : System.Void`  

## Nested types

- `Game.Input.InputActivator+<>c`  

