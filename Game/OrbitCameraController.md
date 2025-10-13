# Game.OrbitCameraController

**Assembly:** `Game`  
**Namespace:** `Game`  

**Type:** class public  

**Base:** `UnityEngine.MonoBehaviour`  
**Implements:** `Game.Rendering.IGameCameraController`  

## Code

```csharp
public class OrbitCameraController : UnityEngine.MonoBehaviour, Game.Rendering.IGameCameraController
{
    public Unity.Mathematics.float2 m_ZoomRange;
    public System.Single m_FollowSmoothing;
    private Unity.Entities.Entity m_Entity;
    private System.Single m_FollowTimer;
    private Game.OrbitCameraController+Mode <mode>k__BackingField;
    private Unity.Mathematics.float2 m_Rotation;
    private UnityEngine.GameObject m_Anchor;
    private Cinemachine.CinemachineVirtualCamera m_VCam;
    private Cinemachine.CinemachineOrbitalTransposer m_Transposer;
    private Game.CinemachineRestrictToTerrain m_Collider;
    private Game.CameraInput m_CameraInput;
    private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
    private System.Boolean <inputEnabled>k__BackingField;
    private System.Single <zoom>k__BackingField;
    private System.Single <yOffset>k__BackingField;
    private System.Single <xOffset>k__BackingField;
    private System.Action <EventCameraMove>k__BackingField;
    private static readonly System.Single kPivotVerticalOffset;

    public Unity.Entities.Entity followedEntity { get; set; }
    public Game.OrbitCameraController+Mode mode { get; set; }
    public UnityEngine.Vector3 pivot { get; set; }
    public UnityEngine.Vector3 position { get; set; }
    public System.Boolean controllerEnabled { get; set; }
    public System.Boolean inputEnabled { get; set; }
    public UnityEngine.Vector3 rotation { get; set; }
    public System.Single zoom { get; set; }
    public System.Single yOffset { get; set; }
    public System.Single xOffset { get; set; }
    public Cinemachine.ICinemachineCamera virtualCamera { get; }
    public Cinemachine.LensSettings& lens { get; }
    public System.Boolean collisionsEnabled { get; set; }
    public System.Action EventCameraMove { get; set; }

    public OrbitCameraController();

    private System.Void Awake();
    private System.Void OnDestroy();
    private System.Void OnDisable();
    private System.Void OnEnable();
    private System.Void RefreshAudioFollow(System.Boolean active);
    private static System.Boolean TryGetPosition(Unity.Entities.Entity e, Unity.Entities.EntityManager entityManager, Unity.Mathematics.float3& position, Unity.Mathematics.quaternion& rotation, System.Single& radius);
    public System.Void TryMatchPosition(Game.Rendering.IGameCameraController other);
    public System.Void UpdateCamera();
}
```


## Fields

- `public Unity.Mathematics.float2 m_ZoomRange`  

```csharp
public Unity.Mathematics.float2 m_ZoomRange;
```

- `public System.Single m_FollowSmoothing`  

```csharp
public System.Single m_FollowSmoothing;
```

- `private Unity.Entities.Entity m_Entity`  

```csharp
private Unity.Entities.Entity m_Entity;
```

- `private System.Single m_FollowTimer`  

```csharp
private System.Single m_FollowTimer;
```

- `private Game.OrbitCameraController+Mode <mode>k__BackingField`  

```csharp
private Game.OrbitCameraController+Mode <mode>k__BackingField;
```

- `private Unity.Mathematics.float2 m_Rotation`  

```csharp
private Unity.Mathematics.float2 m_Rotation;
```

- `private UnityEngine.GameObject m_Anchor`  

```csharp
private UnityEngine.GameObject m_Anchor;
```

- `private Cinemachine.CinemachineVirtualCamera m_VCam`  

```csharp
private Cinemachine.CinemachineVirtualCamera m_VCam;
```

- `private Cinemachine.CinemachineOrbitalTransposer m_Transposer`  

```csharp
private Cinemachine.CinemachineOrbitalTransposer m_Transposer;
```

- `private Game.CinemachineRestrictToTerrain m_Collider`  

```csharp
private Game.CinemachineRestrictToTerrain m_Collider;
```

- `private Game.CameraInput m_CameraInput`  

```csharp
private Game.CameraInput m_CameraInput;
```

- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  

```csharp
private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
```

- `private System.Boolean <inputEnabled>k__BackingField`  

```csharp
private System.Boolean <inputEnabled>k__BackingField;
```

- `private System.Single <zoom>k__BackingField`  

```csharp
private System.Single <zoom>k__BackingField;
```

- `private System.Single <yOffset>k__BackingField`  

```csharp
private System.Single <yOffset>k__BackingField;
```

- `private System.Single <xOffset>k__BackingField`  

```csharp
private System.Single <xOffset>k__BackingField;
```

- `private System.Action <EventCameraMove>k__BackingField`  

```csharp
private System.Action <EventCameraMove>k__BackingField;
```

- `private static readonly System.Single kPivotVerticalOffset`  

```csharp
private static readonly System.Single kPivotVerticalOffset;
```


## Properties

- `public Unity.Entities.Entity followedEntity { get; set }`  

```csharp
public Unity.Entities.Entity followedEntity { get; set; }
```

- `public Game.OrbitCameraController+Mode mode { get; set }`  

```csharp
public Game.OrbitCameraController+Mode mode { get; set; }
```

- `public UnityEngine.Vector3 pivot { get; set }`  

```csharp
public UnityEngine.Vector3 pivot { get; set; }
```

- `public UnityEngine.Vector3 position { get; set }`  

```csharp
public UnityEngine.Vector3 position { get; set; }
```

- `public System.Boolean controllerEnabled { get; set }`  

```csharp
public System.Boolean controllerEnabled { get; set; }
```

- `public System.Boolean inputEnabled { get; set }`  

```csharp
public System.Boolean inputEnabled { get; set; }
```

- `public UnityEngine.Vector3 rotation { get; set }`  

```csharp
public UnityEngine.Vector3 rotation { get; set; }
```

- `public System.Single zoom { get; set }`  

```csharp
public System.Single zoom { get; set; }
```

- `public System.Single yOffset { get; set }`  

```csharp
public System.Single yOffset { get; set; }
```

- `public System.Single xOffset { get; set }`  

```csharp
public System.Single xOffset { get; set; }
```

- `public Cinemachine.ICinemachineCamera virtualCamera { get }`  

```csharp
public Cinemachine.ICinemachineCamera virtualCamera { get; }
```

- `public Cinemachine.LensSettings& lens { get }`  

```csharp
public Cinemachine.LensSettings& lens { get; }
```

- `public System.Boolean collisionsEnabled { get; set }`  

```csharp
public System.Boolean collisionsEnabled { get; set; }
```

- `public System.Action EventCameraMove { get; set }`  

```csharp
public System.Action EventCameraMove { get; set; }
```


## Constructors

- `public OrbitCameraController()`  

```csharp
public OrbitCameraController();
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

- `private OnDisable() : System.Void`  

```csharp
private System.Void OnDisable();
```

- `private OnEnable() : System.Void`  

```csharp
private System.Void OnEnable();
```

- `private RefreshAudioFollow(System.Boolean active) : System.Void`  

```csharp
private System.Void RefreshAudioFollow(System.Boolean active);
```

- `private static TryGetPosition(Unity.Entities.Entity e, Unity.Entities.EntityManager entityManager, Unity.Mathematics.float3& position, Unity.Mathematics.quaternion& rotation, System.Single& radius) : System.Boolean`  

```csharp
private static System.Boolean TryGetPosition(Unity.Entities.Entity e, Unity.Entities.EntityManager entityManager, Unity.Mathematics.float3& position, Unity.Mathematics.quaternion& rotation, System.Single& radius);
```

- `public TryMatchPosition(Game.Rendering.IGameCameraController other) : System.Void`  

```csharp
public System.Void TryMatchPosition(Game.Rendering.IGameCameraController other);
```

- `public UpdateCamera() : System.Void`  

```csharp
public System.Void UpdateCamera();
```


## Nested types

- `Game.OrbitCameraController+Mode`  
- `Game.OrbitCameraController+<Awake>d__59`  

