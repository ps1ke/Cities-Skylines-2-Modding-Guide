# Game.UI.UISystemBootstrapper

**Assembly:** `Game`  
**Namespace:** `Game.UI`  

**Type:** class public  

**Base:** `UnityEngine.MonoBehaviour`  
**Implements:** `Colossal.UI.IUIViewComponent`  

## Fields

- `private Colossal.UI.UIView m_View`  
- `private Colossal.UI.UIView m_FatalView`  
- `private Colossal.UI.UIManager m_UIManager`  
- `private Colossal.UI.UIInputSystem m_UIInputSystem`  
- `private Colossal.UI.UIInputSystem m_FallbackUIInputSystem`  
- `private Game.UI.InputBindings m_InputBindings`  
- `public System.Boolean m_EnableFatalUI`  
- `public System.String m_Url`  
- `public System.String m_FatalUrl`  

## Properties

- `public cohtml.Net.View View { get }`  
- `public Colossal.UI.IUnityViewListener Listener { get }`  

## Constructors

- `public UISystemBootstrapper()`  

## Methods

- `private Awake() : System.Void`  
- `private Colossal.UI.IUIViewComponent.get_enabled() : System.Boolean`  
- `private LateUpdate() : System.Void`  
- `private OnDestroy() : System.Void`  
- `private OnReadyForBindings() : System.Void`  
- `private Update() : System.Void`  

## Nested types

- `Game.UI.UISystemBootstrapper+<>c`  
- `Game.UI.UISystemBootstrapper+<Awake>d__13`  

