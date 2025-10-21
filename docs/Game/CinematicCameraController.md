# Game.CinematicCameraController

**Assembly:** `Game`  
**Namespace:** `Game`  

**Type:** class public  

**Base:** `UnityEngine.MonoBehaviour`  
**Implements:** `Game.Rendering.IGameCameraController`  

## Code

```csharp
public class CinematicCameraController : UnityEngine.MonoBehaviour, Game.Rendering.IGameCameraController
{
    private System.Single m_MinMoveSpeed;
    private System.Single m_MaxMoveSpeed;
    private System.Single m_MinZoomSpeed;
    private System.Single m_MaxZoomSpeed;
    private System.Single m_RotateSpeed;
    private System.Single m_MaxHeight;
    private System.Single m_MaxMovementSpeedHeight;
    private UnityEngine.Transform m_Anchor;
    private Cinemachine.CinemachineVirtualCamera m_VCam;
    private Game.CinemachineRestrictToTerrain m_RestrictToTerrain;
    private Game.CameraInput m_CameraInput;
    private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
    private System.Action <eventCameraMove>k__BackingField;
    private System.Boolean <inputEnabled>k__BackingField;

    public Cinemachine.ICinemachineCamera virtualCamera { get; }
    public System.Single zoom { get; set; }
    public UnityEngine.Vector3 pivot { get; set; }
    public UnityEngine.Vector3 position { get; set; }
    public UnityEngine.Vector3 rotation { get; set; }
    public System.Boolean controllerEnabled { get; set; }
    public System.Boolean collisionsEnabled { get; set; }
    public Cinemachine.LensSettings& lens { get; }
    public System.Action eventCameraMove { get; set; }
    public System.Single fov { get; set; }
    public System.Single dutch { get; set; }
    public System.Boolean inputEnabled { get; set; }

    public CinematicCameraController();

    private System.Void Awake();
    private System.Void OnDestroy();
    public System.Void TryMatchPosition(Game.Rendering.IGameCameraController other);
    public System.Void UpdateCamera();
    private System.Void UpdateController(Game.CameraInput input);
}
```


## Fields

- `private System.Single m_MinMoveSpeed`  

```csharp
private System.Single m_MinMoveSpeed;
```

- `private System.Single m_MaxMoveSpeed`  

```csharp
private System.Single m_MaxMoveSpeed;
```

- `private System.Single m_MinZoomSpeed`  

```csharp
private System.Single m_MinZoomSpeed;
```

- `private System.Single m_MaxZoomSpeed`  

```csharp
private System.Single m_MaxZoomSpeed;
```

- `private System.Single m_RotateSpeed`  

```csharp
private System.Single m_RotateSpeed;
```

- `private System.Single m_MaxHeight`  

```csharp
private System.Single m_MaxHeight;
```

- `private System.Single m_MaxMovementSpeedHeight`  

```csharp
private System.Single m_MaxMovementSpeedHeight;
```

- `private UnityEngine.Transform m_Anchor`  

```csharp
private UnityEngine.Transform m_Anchor;
```

- `private Cinemachine.CinemachineVirtualCamera m_VCam`  

```csharp
private Cinemachine.CinemachineVirtualCamera m_VCam;
```

- `private Game.CinemachineRestrictToTerrain m_RestrictToTerrain`  

```csharp
private Game.CinemachineRestrictToTerrain m_RestrictToTerrain;
```

- `private Game.CameraInput m_CameraInput`  

```csharp
private Game.CameraInput m_CameraInput;
```

- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  

```csharp
private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
```

- `private System.Action <eventCameraMove>k__BackingField`  

```csharp
private System.Action <eventCameraMove>k__BackingField;
```

- `private System.Boolean <inputEnabled>k__BackingField`  

```csharp
private System.Boolean <inputEnabled>k__BackingField;
```


## Properties

- `public Cinemachine.ICinemachineCamera virtualCamera { get }`  

```csharp
public Cinemachine.ICinemachineCamera virtualCamera { get; }
```

- `public System.Single zoom { get; set }`  

```csharp
public System.Single zoom { get; set; }
```

- `public UnityEngine.Vector3 pivot { get; set }`  

```csharp
public UnityEngine.Vector3 pivot { get; set; }
```

- `public UnityEngine.Vector3 position { get; set }`  

```csharp
public UnityEngine.Vector3 position { get; set; }
```

- `public UnityEngine.Vector3 rotation { get; set }`  

```csharp
public UnityEngine.Vector3 rotation { get; set; }
```

- `public System.Boolean controllerEnabled { get; set }`  

```csharp
public System.Boolean controllerEnabled { get; set; }
```

- `public System.Boolean collisionsEnabled { get; set }`  

```csharp
public System.Boolean collisionsEnabled { get; set; }
```

- `public Cinemachine.LensSettings& lens { get }`  

```csharp
public Cinemachine.LensSettings& lens { get; }
```

- `public System.Action eventCameraMove { get; set }`  

```csharp
public System.Action eventCameraMove { get; set; }
```

- `public System.Single fov { get; set }`  

```csharp
public System.Single fov { get; set; }
```

- `public System.Single dutch { get; set }`  

```csharp
public System.Single dutch { get; set; }
```

- `public System.Boolean inputEnabled { get; set }`  

```csharp
public System.Boolean inputEnabled { get; set; }
```


## Constructors

- `public CinematicCameraController()`  

```csharp
public CinematicCameraController();
```


## Methods

- `private Awake() : System.Void`  

```csharp
private System.Void Awake();
```

- `private OnDestroy() : System.Void`  

```csharp
private System.Void OnDestroy();
```

- `public TryMatchPosition(Game.Rendering.IGameCameraController other) : System.Void`  

```csharp
public System.Void TryMatchPosition(Game.Rendering.IGameCameraController other);
```

- `public UpdateCamera() : System.Void`  

```csharp
public System.Void UpdateCamera();
```

- `private UpdateController(Game.CameraInput input) : System.Void`  

```csharp
private System.Void UpdateController(Game.CameraInput input);
```


## Nested types

- `Game.CinematicCameraController+<Awake>d__48`  

