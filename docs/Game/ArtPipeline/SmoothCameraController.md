# Game.ArtPipeline.SmoothCameraController

**Assembly:** `Game.ArtPipeline`  
**Namespace:** `Game.ArtPipeline`  

**Type:** class public  

**Base:** `UnityEngine.MonoBehaviour`  

## Code

```csharp
public class SmoothCameraController : UnityEngine.MonoBehaviour
{
    public System.Single lateralSpeed;
    public System.Single longitudinalSpeed;
    public System.Single verticalSpeed;
    public System.Single mouseMovementSpeed;
    public System.Single fovChangeSpeed;
    public System.Single shiftMultiplier;
    public System.Boolean InvertedY;
    public System.Single verticalFilter;
    public System.Single lateralFilter;
    public System.Single longitudinalFilter;
    public System.Single mouseFilter;
    private System.Single vertical;
    private System.Single lateral;
    private System.Single longitudinal;
    private System.Single speedMultiplyer;
    private UnityEngine.GameObject TransformDummy;
    private UnityEngine.Camera mainCam;

    public SmoothCameraController();

    private System.Void Start();
    private System.Single TimeStep();
    private System.Void Update();
}
```


## Fields

- `public System.Single lateralSpeed`  

```csharp
public System.Single lateralSpeed;
```

- `public System.Single longitudinalSpeed`  

```csharp
public System.Single longitudinalSpeed;
```

- `public System.Single verticalSpeed`  

```csharp
public System.Single verticalSpeed;
```

- `public System.Single mouseMovementSpeed`  

```csharp
public System.Single mouseMovementSpeed;
```

- `public System.Single fovChangeSpeed`  

```csharp
public System.Single fovChangeSpeed;
```

- `public System.Single shiftMultiplier`  

```csharp
public System.Single shiftMultiplier;
```

- `public System.Boolean InvertedY`  

```csharp
public System.Boolean InvertedY;
```

- `public System.Single verticalFilter`  

```csharp
public System.Single verticalFilter;
```

- `public System.Single lateralFilter`  

```csharp
public System.Single lateralFilter;
```

- `public System.Single longitudinalFilter`  

```csharp
public System.Single longitudinalFilter;
```

- `public System.Single mouseFilter`  

```csharp
public System.Single mouseFilter;
```

- `private System.Single vertical`  

```csharp
private System.Single vertical;
```

- `private System.Single lateral`  

```csharp
private System.Single lateral;
```

- `private System.Single longitudinal`  

```csharp
private System.Single longitudinal;
```

- `private System.Single speedMultiplyer`  

```csharp
private System.Single speedMultiplyer;
```

- `private UnityEngine.GameObject TransformDummy`  

```csharp
private UnityEngine.GameObject TransformDummy;
```

- `private UnityEngine.Camera mainCam`  

```csharp
private UnityEngine.Camera mainCam;
```


## Constructors

- `public SmoothCameraController()`  

```csharp
public SmoothCameraController();
```


## Methods

- `private Start() : System.Void`  

```csharp
private System.Void Start();
```

- `private TimeStep() : System.Single`  

```csharp
private System.Single TimeStep();
```

- `private Update() : System.Void`  

```csharp
private System.Void Update();
```


