# Game.Input.DisplayNameOverride

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Fields

- `private readonly Game.Input.ProxyAction m_Action`  
- `private readonly System.String m_Source`  
- `private System.Boolean m_Disposed`  
- `private System.Int32 m_Priority`  
- `private Game.Input.UIBaseInputAction+Transform m_Transform`  
- `private System.String m_DisplayName`  
- `private System.Boolean m_Active`  
- `public static const System.Int32 kDisabledPriority`  
- `public static const System.Int32 kToolTipPriority`  

## Properties

- `public System.String source { get }`  
- `public System.Boolean isDisposed { get }`  
- `public System.Boolean active { get; set }`  
- `public System.String displayName { get; set }`  
- `public System.Int32 priority { get; set }`  
- `public Game.Input.UIBaseInputAction+Transform transform { get; set }`  

## Constructors

- `public DisplayNameOverride(System.String overrideSource, Game.Input.ProxyAction action, System.String displayName = null, System.Int32 priority = -1, Game.Input.UIBaseInputAction+Transform transform = None)`  

## Methods

- `public Dispose() : System.Void`  
- `public Equals(Game.Input.DisplayNameOverride other) : System.Boolean`  

