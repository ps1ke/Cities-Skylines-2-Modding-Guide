# Game.CameraInput

**Assembly:** `Game`  
**Namespace:** `Game`  

**Type:** class public  

**Base:** `UnityEngine.MonoBehaviour`  

## Code

```csharp
public class CameraInput : UnityEngine.MonoBehaviour
{
    public System.Single m_MoveSmoothing;
    public System.Single m_RotateSmoothing;
    public System.Single m_ZoomSmoothing;
    private Game.Input.ProxyAction m_MoveAction;
    private Game.Input.ProxyAction m_FastMoveAction;
    private Game.Input.ProxyAction m_RotateAction;
    private Game.Input.ProxyAction m_ZoomAction;
    private UnityEngine.Vector2 <move>k__BackingField;
    private UnityEngine.Vector2 <rotate>k__BackingField;
    private System.Single <zoom>k__BackingField;

    public UnityEngine.Vector2 move { get; private set; }
    public UnityEngine.Vector2 rotate { get; private set; }
    public System.Single zoom { get; private set; }
    public System.Boolean isMoving { get; }
    public System.Boolean any { get; }

    public CameraInput();

    public System.Void Initialize();
    public System.Void Refresh();
}
```


## Fields

- `public System.Single m_MoveSmoothing`  

```csharp
public System.Single m_MoveSmoothing;
```

- `public System.Single m_RotateSmoothing`  

```csharp
public System.Single m_RotateSmoothing;
```

- `public System.Single m_ZoomSmoothing`  

```csharp
public System.Single m_ZoomSmoothing;
```

- `private Game.Input.ProxyAction m_MoveAction`  

```csharp
private Game.Input.ProxyAction m_MoveAction;
```

- `private Game.Input.ProxyAction m_FastMoveAction`  

```csharp
private Game.Input.ProxyAction m_FastMoveAction;
```

- `private Game.Input.ProxyAction m_RotateAction`  

```csharp
private Game.Input.ProxyAction m_RotateAction;
```

- `private Game.Input.ProxyAction m_ZoomAction`  

```csharp
private Game.Input.ProxyAction m_ZoomAction;
```

- `private UnityEngine.Vector2 <move>k__BackingField`  

```csharp
private UnityEngine.Vector2 <move>k__BackingField;
```

- `private UnityEngine.Vector2 <rotate>k__BackingField`  

```csharp
private UnityEngine.Vector2 <rotate>k__BackingField;
```

- `private System.Single <zoom>k__BackingField`  

```csharp
private System.Single <zoom>k__BackingField;
```


## Properties

- `public UnityEngine.Vector2 move { get; private set }`  

```csharp
public UnityEngine.Vector2 move { get; private set; }
```

- `public UnityEngine.Vector2 rotate { get; private set }`  

```csharp
public UnityEngine.Vector2 rotate { get; private set; }
```

- `public System.Single zoom { get; private set }`  

```csharp
public System.Single zoom { get; private set; }
```

- `public System.Boolean isMoving { get }`  

```csharp
public System.Boolean isMoving { get; }
```

- `public System.Boolean any { get }`  

```csharp
public System.Boolean any { get; }
```


## Constructors

- `public CameraInput()`  

```csharp
public CameraInput();
```


## Methods

- `public Initialize() : System.Void`  

```csharp
public System.Void Initialize();
```

- `public Refresh() : System.Void`  

```csharp
public System.Void Refresh();
```


