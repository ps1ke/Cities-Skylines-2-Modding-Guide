# Game.UI.UISystemBootstrapper

**Assembly:** `Game`  
**Namespace:** `Game.UI`  

**Type:** class public  

**Base:** `UnityEngine.MonoBehaviour`  
**Implements:** `Colossal.UI.IUIViewComponent`  

## Code

```csharp
public class UISystemBootstrapper : UnityEngine.MonoBehaviour, Colossal.UI.IUIViewComponent
{
    private Colossal.UI.UIView m_View;
    private Colossal.UI.UIView m_FatalView;
    private Colossal.UI.UIManager m_UIManager;
    private Colossal.UI.UIInputSystem m_UIInputSystem;
    private Colossal.UI.UIInputSystem m_FallbackUIInputSystem;
    private Game.UI.InputBindings m_InputBindings;
    public System.Boolean m_EnableFatalUI;
    public System.String m_Url;
    public System.String m_FatalUrl;

    public cohtml.Net.View View { get; }
    public Colossal.UI.IUnityViewListener Listener { get; }

    public UISystemBootstrapper();

    private System.Void Awake();
    private System.Boolean Colossal.UI.IUIViewComponent.get_enabled();
    private System.Void LateUpdate();
    private System.Void OnDestroy();
    private System.Void OnReadyForBindings();
    private System.Void Update();
}
```


## Fields

- `private Colossal.UI.UIView m_View`  

```csharp
private Colossal.UI.UIView m_View;
```

- `private Colossal.UI.UIView m_FatalView`  

```csharp
private Colossal.UI.UIView m_FatalView;
```

- `private Colossal.UI.UIManager m_UIManager`  

```csharp
private Colossal.UI.UIManager m_UIManager;
```

- `private Colossal.UI.UIInputSystem m_UIInputSystem`  

```csharp
private Colossal.UI.UIInputSystem m_UIInputSystem;
```

- `private Colossal.UI.UIInputSystem m_FallbackUIInputSystem`  

```csharp
private Colossal.UI.UIInputSystem m_FallbackUIInputSystem;
```

- `private Game.UI.InputBindings m_InputBindings`  

```csharp
private Game.UI.InputBindings m_InputBindings;
```

- `public System.Boolean m_EnableFatalUI`  

```csharp
public System.Boolean m_EnableFatalUI;
```

- `public System.String m_Url`  

```csharp
public System.String m_Url;
```

- `public System.String m_FatalUrl`  

```csharp
public System.String m_FatalUrl;
```


## Properties

- `public cohtml.Net.View View { get }`  

```csharp
public cohtml.Net.View View { get; }
```

- `public Colossal.UI.IUnityViewListener Listener { get }`  

```csharp
public Colossal.UI.IUnityViewListener Listener { get; }
```


## Constructors

- `public UISystemBootstrapper()`  

```csharp
public UISystemBootstrapper();
```


## Methods

- `private Awake() : System.Void`  

```csharp
private System.Void Awake();
```

- `private Colossal.UI.IUIViewComponent.get_enabled() : System.Boolean`  

```csharp
private System.Boolean Colossal.UI.IUIViewComponent.get_enabled();
```

- `private LateUpdate() : System.Void`  

```csharp
private System.Void LateUpdate();
```

- `private OnDestroy() : System.Void`  

```csharp
private System.Void OnDestroy();
```

- `private OnReadyForBindings() : System.Void`  

```csharp
private System.Void OnReadyForBindings();
```

- `private Update() : System.Void`  

```csharp
private System.Void Update();
```


## Nested types

- `Game.UI.UISystemBootstrapper+<>c`  
- `Game.UI.UISystemBootstrapper+<Awake>d__13`  

