# Game.Input.InputBarrier

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Fields

- `private readonly Game.Input.ProxyActionMap[] m_Maps`  
- `private readonly Game.Input.ProxyAction[] m_Actions`  
- `private readonly System.String m_Name`  
- `private System.Boolean m_Blocked`  
- `private Game.Input.InputManager+DeviceType m_Mask`  
- `private System.Boolean m_Disposed`  

## Properties

- `public System.String name { get }`  
- `public System.Collections.Generic.IReadOnlyList<Game.Input.ProxyActionMap> maps { get }`  
- `public System.Collections.Generic.IReadOnlyList<Game.Input.ProxyAction> actions { get }`  
- `public System.Boolean blocked { get; set }`  
- `public Game.Input.InputManager+DeviceType mask { get; set }`  

## Constructors

- `public InputBarrier(System.String barrierName, Game.Input.ProxyActionMap map, Game.Input.InputManager+DeviceType mask = All, System.Boolean blocked = False)`  
- `public InputBarrier(System.String barrierName, Game.Input.ProxyAction action, Game.Input.InputManager+DeviceType mask = All, System.Boolean blocked = False)`  
- `public InputBarrier(System.String barrierName, System.Collections.Generic.IList<Game.Input.ProxyActionMap> maps, System.Collections.Generic.IList<Game.Input.ProxyAction> actions, Game.Input.InputManager+DeviceType mask = All, System.Boolean blocked = False)`  
- `public InputBarrier(System.String barrierName, System.Collections.Generic.IList<Game.Input.ProxyActionMap> maps, Game.Input.InputManager+DeviceType mask = All, System.Boolean blocked = False)`  
- `public InputBarrier(System.String barrierName, System.Collections.Generic.IList<Game.Input.ProxyAction> actions, Game.Input.InputManager+DeviceType mask = All, System.Boolean blocked = False)`  

## Methods

- `public Dispose() : System.Void`  
- `private Update() : System.Void`  

## Nested types

- `Game.Input.InputBarrier+<>c`  

