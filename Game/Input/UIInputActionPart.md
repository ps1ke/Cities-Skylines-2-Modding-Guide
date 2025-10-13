# Game.Input.UIInputActionPart

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class public  

**Base:** `System.Object`  

**Attributes:** `Serializable`  

## Code

```csharp
public class UIInputActionPart
{
    public UnityEngine.InputSystem.InputActionReference m_Action;
    public Game.Input.UIBaseInputAction+ProcessAs m_ProcessAs;
    public Game.Input.UIBaseInputAction+Transform m_Transform;
    public Game.Input.InputManager+DeviceType m_Mask;

    public UIInputActionPart();

    public Game.Input.ProxyAction GetProxyAction();
    public System.Boolean TryGetProxyAction(Game.Input.ProxyAction& action);
}
```


## Fields

- `public UnityEngine.InputSystem.InputActionReference m_Action`  

```csharp
public UnityEngine.InputSystem.InputActionReference m_Action;
```

- `public Game.Input.UIBaseInputAction+ProcessAs m_ProcessAs`  

```csharp
public Game.Input.UIBaseInputAction+ProcessAs m_ProcessAs;
```

- `public Game.Input.UIBaseInputAction+Transform m_Transform`  

```csharp
public Game.Input.UIBaseInputAction+Transform m_Transform;
```

- `public Game.Input.InputManager+DeviceType m_Mask`  

```csharp
public Game.Input.InputManager+DeviceType m_Mask;
```


## Constructors

- `public UIInputActionPart()`  

```csharp
public UIInputActionPart();
```


## Methods

- `public GetProxyAction() : Game.Input.ProxyAction`  

```csharp
public ProxyAction GetProxyAction()
	{
		return InputManager.instance.FindAction(m_Action.action);
	}
```

- `public TryGetProxyAction(Game.Input.ProxyAction& action) : System.Boolean`  

```csharp
public bool TryGetProxyAction(out ProxyAction action)
	{
		return InputManager.instance.TryFindAction(m_Action.action, out action);
	}
```


