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
private async void Awake()
	{
		UnityEngine.Debug.LogWarning("UISystemBootstrapper is only meant for development purpose");
		await Capabilities.CacheCapabilities();
		UIManager.log.Info("Bootstrapping cohtmlUISystem");
		InputManager.CreateInstance();
		m_UIManager = new UIManager(developerMode: true);
		Colossal.UI.UISystem.Settings settings = Colossal.UI.UISystem.Settings.New;
		settings.enableDebugger = true;
		if (GameManager.instance != null)
		{
			settings.localizationManager = new UILocalizationManager(GameManager.instance.localizationManager);
		}
		settings.resourceHandler = new GameUIResourceHandler(this);
		settings.enableDebugger = true;
		Colossal.UI.UISystem uISystem = m_UIManager.CreateUISystem(settings);
		uISystem.AddHostLocation("gameui", EnvPath.kContentPath + "/Game/UI");
		m_View = uISystem.CreateView(m_Url, UIView.Settings.New, GetComponent<Camera>());
		m_View.enabled = true;
		m_View.AudioSource = GetComponent<AudioSource>();
		m_View.Listener.ReadyForBindings += OnReadyForBindings;
		m_UIInputSystem = new UIInputSystem(uISystem);
		m_InputBindings = new InputBindings();
		if (!m_EnableFatalUI)
		{
			return;
		}
		ErrorPage errorPage = new ErrorPage();
		errorPage.AddAction("quit", delegate
		{
			Application.Quit();
		});
		errorPage.AddAction("visit", delegate
		{
			try
			{
				Process.Start(new ProcessStartInfo
				{
					FileName = "https://pdxint.at/3Do979W",
					UseShellExecute = true
				});
			}
			catch
			{
				Application.Quit();
			}
		});
		errorPage.SetRoot(EnvPath.kContentPath + "/Game/UI/.fatal", EnvPath.kContentPath + "/Game/.fatal");
		errorPage.SetFonts(EnvPath.kContentPath + "/Game/UI/Fonts", EnvPath.kContentPath + "/Game/Fonts.cok");
		errorPage.SetStopCode(new AggregateException());
		Colossal.UI.UISystem.Settings settings2 = Colossal.UI.UISystem.Settings.New;
		settings2.resourceHandler = new FatalResourceHandler(errorPage);
		settings2.enableDebugger = true;
		settings2.debuggerPort = 9445;
		Colossal.UI.UISystem uISystem2 = m_UIManager.CreateUISystem(settings2);
		UIView.Settings settings3 = UIView.Settings.New;
		settings3.liveReload = true;
		m_FatalView = uISystem2.CreateView(m_FatalUrl, settings3, GetComponent<Camera>());
		m_FatalView.enabled = true;
		m_FallbackUIInputSystem = new UIInputSystem(uISystem2);
	}
```

- `private Colossal.UI.IUIViewComponent.get_enabled() : System.Boolean`  

```csharp
private System.Boolean Colossal.UI.IUIViewComponent.get_enabled();
```

- `private LateUpdate() : System.Void`  

```csharp
private void LateUpdate()
	{
		m_UIInputSystem?.DispatchInputEvents();
		m_FallbackUIInputSystem?.DispatchInputEvents();
	}
```

- `private OnDestroy() : System.Void`  

```csharp
private void OnDestroy()
	{
		if (m_View != null)
		{
			m_View.Listener.ReadyForBindings -= OnReadyForBindings;
		}
		m_InputBindings?.Detach();
		m_InputBindings?.Dispose();
		m_UIInputSystem?.Dispose();
		m_FallbackUIInputSystem?.Dispose();
		m_UIManager?.Dispose();
		InputManager.DestroyInstance();
	}
```

- `private OnReadyForBindings() : System.Void`  

```csharp
private void OnReadyForBindings()
	{
		m_InputBindings?.Attach(m_View.View);
	}
```

- `private Update() : System.Void`  

```csharp
private void Update()
	{
		if (m_FatalView != null)
		{
			m_FatalView.enabled = m_EnableFatalUI;
		}
		InputManager.instance?.Update();
		m_UIManager?.Update();
		m_InputBindings?.Update();
	}
```


## Nested types

- `Game.UI.UISystemBootstrapper+<>c`  
- `Game.UI.UISystemBootstrapper+<Awake>d__13`  

