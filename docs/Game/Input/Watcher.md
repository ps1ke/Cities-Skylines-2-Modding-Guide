# Game.Input.ProxyBinding+Watcher

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Fields

- `private System.Boolean m_Disposed`  
- `private Game.Input.ProxyBinding m_Binding`  
- `private readonly Game.Input.ProxyAction m_Action`  
- `private readonly System.Action<Game.Input.ProxyBinding> m_OnChange`  
- `private static readonly Game.Input.ProxyBinding+Comparer comparer`  

## Properties

- `public Game.Input.ProxyBinding binding { get }`  
- `public System.Boolean isValid { get }`  

## Constructors

- `public Watcher(Game.Input.ProxyBinding binding, System.Action<Game.Input.ProxyBinding> onChange = null)`  

## Methods

- `public Dispose() : System.Void`  
- `private OnChanged(Game.Input.ProxyAction action) : System.Void`  

