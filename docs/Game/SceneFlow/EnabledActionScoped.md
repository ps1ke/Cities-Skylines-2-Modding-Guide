# Game.SceneFlow.EnabledActionScoped

**Assembly:** `Game`  
**Namespace:** `Game.SceneFlow`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Fields

- `private readonly Game.SceneFlow.OverlayBindings m_Bindings`  
- `private readonly Game.Input.ProxyAction m_Proxy`  
- `private readonly Game.Input.DisplayNameOverride m_NameOverride`  
- `private readonly System.Func<Game.SceneFlow.OverlayScreen, System.Boolean> m_ShouldBeEnabled`  

## Constructors

- `public EnabledActionScoped(Game.SceneFlow.GameManager manager, System.String actionMapName, System.String actionName, System.Func<Game.SceneFlow.OverlayScreen, System.Boolean> shouldBeEnabled = null, System.String displayProperty = null, System.Int32 displayPriority = 20)`  

## Methods

- `public Dispose() : System.Void`  
- `private HandleScreenChange(Game.SceneFlow.OverlayScreen screen) : System.Void`  

