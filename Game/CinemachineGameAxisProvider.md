# Game.CinemachineGameAxisProvider

**Assembly:** `Game`  
**Namespace:** `Game`  

**Type:** class public  

**Base:** `UnityEngine.MonoBehaviour`  
**Implements:** `Cinemachine.AxisState+IInputAxisProvider`  

## Code

```csharp
public class CinemachineGameAxisProvider : UnityEngine.MonoBehaviour, Cinemachine.AxisState+IInputAxisProvider
{
    private Game.Input.ProxyAction m_RotateAction;
    private Game.Input.ProxyAction m_ZoomAction;

    public CinemachineGameAxisProvider();

    private System.Void Awake();
    public System.Single GetAxisValue(System.Int32 axis);
}
```


## Fields

- `private Game.Input.ProxyAction m_RotateAction`  

```csharp
private Game.Input.ProxyAction m_RotateAction;
```

- `private Game.Input.ProxyAction m_ZoomAction`  

```csharp
private Game.Input.ProxyAction m_ZoomAction;
```


## Constructors

- `public CinemachineGameAxisProvider()`  

```csharp
public CinemachineGameAxisProvider();
```


## Methods

- `private Awake() : System.Void`  

```csharp
private System.Void Awake();
```

- `public GetAxisValue(System.Int32 axis) : System.Single`  

```csharp
public System.Single GetAxisValue(System.Int32 axis);
```


