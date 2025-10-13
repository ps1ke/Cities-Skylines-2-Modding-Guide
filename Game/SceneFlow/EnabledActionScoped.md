# Game.SceneFlow.EnabledActionScoped

**Assembly:** `Game`  
**Namespace:** `Game.SceneFlow`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public class EnabledActionScoped : System.IDisposable
{
    private readonly Game.SceneFlow.OverlayBindings m_Bindings;
    private readonly Game.Input.ProxyAction m_Proxy;
    private readonly Game.Input.DisplayNameOverride m_NameOverride;
    private readonly System.Func<Game.SceneFlow.OverlayScreen, System.Boolean> m_ShouldBeEnabled;

    public EnabledActionScoped(Game.SceneFlow.GameManager manager, System.String actionMapName, System.String actionName, System.Func<Game.SceneFlow.OverlayScreen, System.Boolean> shouldBeEnabled, System.String displayProperty, System.Int32 displayPriority);

    public System.Void Dispose();
    private System.Void HandleScreenChange(Game.SceneFlow.OverlayScreen screen);
}
```


## Fields

- `private readonly Game.SceneFlow.OverlayBindings m_Bindings`  

```csharp
private readonly Game.SceneFlow.OverlayBindings m_Bindings;
```

- `private readonly Game.Input.ProxyAction m_Proxy`  

```csharp
private readonly Game.Input.ProxyAction m_Proxy;
```

- `private readonly Game.Input.DisplayNameOverride m_NameOverride`  

```csharp
private readonly Game.Input.DisplayNameOverride m_NameOverride;
```

- `private readonly System.Func<Game.SceneFlow.OverlayScreen, System.Boolean> m_ShouldBeEnabled`  

```csharp
private readonly System.Func<Game.SceneFlow.OverlayScreen, System.Boolean> m_ShouldBeEnabled;
```


## Constructors

- `public EnabledActionScoped(Game.SceneFlow.GameManager manager, System.String actionMapName, System.String actionName, System.Func<Game.SceneFlow.OverlayScreen, System.Boolean> shouldBeEnabled = null, System.String displayProperty = null, System.Int32 displayPriority = 20)`  

```csharp
public EnabledActionScoped(GameManager manager, string actionMapName, string actionName, Func<OverlayScreen, bool> shouldBeEnabled = null, string displayProperty = null, int displayPriority = 20)
	{
		m_Proxy = Game.Input.InputManager.instance.FindAction(actionMapName, actionName);
		m_Bindings = manager.userInterface.overlayBindings;
		m_NameOverride = new DisplayNameOverride("EnabledActionScoped", m_Proxy, displayProperty, displayPriority);
		Assert.IsNotNull(m_Proxy);
		m_ShouldBeEnabled = shouldBeEnabled;
		m_Bindings.onScreenActivated += HandleScreenChange;
	}
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public void Dispose()
	{
		m_Bindings.onScreenActivated -= HandleScreenChange;
		m_Proxy.enabled = false;
		m_NameOverride.Dispose();
	}
```

- `private HandleScreenChange(Game.SceneFlow.OverlayScreen screen) : System.Void`  

```csharp
private void HandleScreenChange(OverlayScreen screen)
	{
		bool flag = m_ShouldBeEnabled == null || m_ShouldBeEnabled(screen);
		m_Proxy.enabled = flag;
		m_NameOverride.active = flag;
	}
```


