# Game.Rendering.CameraUpdateSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CameraUpdateSystem : Game.GameSystemBase
{
    private Game.Common.RaycastSystem m_RaycastSystem;
    private UnityEngine.Rendering.Volume m_Volume;
    private UnityEngine.Rendering.HighDefinition.DepthOfField m_DepthOfField;
    private UnityEngine.Rendering.HighDefinition.HDShadowSettings m_ShadowSettings;
    private Unity.Mathematics.float4 m_StoredShadowSplitsAndDistance;
    private Unity.Mathematics.float4 m_StoredShadowBorders;
    private Game.Input.InputActivator[] m_CameraActionActivators;
    private Game.Input.InputBarrier[] m_CameraActionBarriers;
    private Game.Rendering.Viewer <activeViewer>k__BackingField;
    private Game.CameraController <gamePlayController>k__BackingField;
    private Game.CinematicCameraController <cinematicCameraController>k__BackingField;
    private Game.OrbitCameraController <orbitCameraController>k__BackingField;
    private System.Single <nearClipPlane>k__BackingField;
    private Unity.Mathematics.float3 <position>k__BackingField;
    private Unity.Mathematics.float3 <direction>k__BackingField;
    private System.Single <zoom>k__BackingField;

    public Game.Rendering.Viewer activeViewer { get; private set; }
    public Game.CameraController gamePlayController { get; set; }
    public Game.CinematicCameraController cinematicCameraController { get; set; }
    public Game.OrbitCameraController orbitCameraController { get; set; }
    public UnityEngine.Camera activeCamera { get; set; }
    public System.Single nearClipPlane { get; private set; }
    public Unity.Mathematics.float3 position { get; private set; }
    public Unity.Mathematics.float3 direction { get; private set; }
    public System.Single zoom { get; private set; }
    public Game.Rendering.IGameCameraController activeCameraController { get; set; }

    public CameraUpdateSystem();

    private System.Boolean CheckOrCacheViewer();
    public Game.Rendering.CameraBlend GetBlendWeight(System.Single& weight);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
    private System.Void RefreshInput();
    public System.Boolean TryGetLODParameters(UnityEngine.Rendering.LODParameters& lodParameters);
    public System.Boolean TryGetViewer(Game.Rendering.Viewer& viewer);
    private System.Void UpdateDepthOfField(System.Single distance);
    private System.Void UpdateShadows(Game.Rendering.Viewer viewer);
}
```


## Fields

- `private Game.Common.RaycastSystem m_RaycastSystem`  

```csharp
private Game.Common.RaycastSystem m_RaycastSystem;
```

- `private UnityEngine.Rendering.Volume m_Volume`  

```csharp
private UnityEngine.Rendering.Volume m_Volume;
```

- `private UnityEngine.Rendering.HighDefinition.DepthOfField m_DepthOfField`  

```csharp
private UnityEngine.Rendering.HighDefinition.DepthOfField m_DepthOfField;
```

- `private UnityEngine.Rendering.HighDefinition.HDShadowSettings m_ShadowSettings`  

```csharp
private UnityEngine.Rendering.HighDefinition.HDShadowSettings m_ShadowSettings;
```

- `private Unity.Mathematics.float4 m_StoredShadowSplitsAndDistance`  

```csharp
private Unity.Mathematics.float4 m_StoredShadowSplitsAndDistance;
```

- `private Unity.Mathematics.float4 m_StoredShadowBorders`  

```csharp
private Unity.Mathematics.float4 m_StoredShadowBorders;
```

- `private Game.Input.InputActivator[] m_CameraActionActivators`  

```csharp
private Game.Input.InputActivator[] m_CameraActionActivators;
```

- `private Game.Input.InputBarrier[] m_CameraActionBarriers`  

```csharp
private Game.Input.InputBarrier[] m_CameraActionBarriers;
```

- `private Game.Rendering.Viewer <activeViewer>k__BackingField`  

```csharp
private Game.Rendering.Viewer <activeViewer>k__BackingField;
```

- `private Game.CameraController <gamePlayController>k__BackingField`  

```csharp
private Game.CameraController <gamePlayController>k__BackingField;
```

- `private Game.CinematicCameraController <cinematicCameraController>k__BackingField`  

```csharp
private Game.CinematicCameraController <cinematicCameraController>k__BackingField;
```

- `private Game.OrbitCameraController <orbitCameraController>k__BackingField`  

```csharp
private Game.OrbitCameraController <orbitCameraController>k__BackingField;
```

- `private System.Single <nearClipPlane>k__BackingField`  

```csharp
private System.Single <nearClipPlane>k__BackingField;
```

- `private Unity.Mathematics.float3 <position>k__BackingField`  

```csharp
private Unity.Mathematics.float3 <position>k__BackingField;
```

- `private Unity.Mathematics.float3 <direction>k__BackingField`  

```csharp
private Unity.Mathematics.float3 <direction>k__BackingField;
```

- `private System.Single <zoom>k__BackingField`  

```csharp
private System.Single <zoom>k__BackingField;
```


## Properties

- `public Game.Rendering.Viewer activeViewer { get; private set }`  

```csharp
public Game.Rendering.Viewer activeViewer { get; private set; }
```

- `public Game.CameraController gamePlayController { get; set }`  

```csharp
public Game.CameraController gamePlayController { get; set; }
```

- `public Game.CinematicCameraController cinematicCameraController { get; set }`  

```csharp
public Game.CinematicCameraController cinematicCameraController { get; set; }
```

- `public Game.OrbitCameraController orbitCameraController { get; set }`  

```csharp
public Game.OrbitCameraController orbitCameraController { get; set; }
```

- `public UnityEngine.Camera activeCamera { get; set }`  

```csharp
public UnityEngine.Camera activeCamera { get; set; }
```

- `public System.Single nearClipPlane { get; private set }`  

```csharp
public System.Single nearClipPlane { get; private set; }
```

- `public Unity.Mathematics.float3 position { get; private set }`  

```csharp
public Unity.Mathematics.float3 position { get; private set; }
```

- `public Unity.Mathematics.float3 direction { get; private set }`  

```csharp
public Unity.Mathematics.float3 direction { get; private set; }
```

- `public System.Single zoom { get; private set }`  

```csharp
public System.Single zoom { get; private set; }
```

- `public Game.Rendering.IGameCameraController activeCameraController { get; set }`  

```csharp
public Game.Rendering.IGameCameraController activeCameraController { get; set; }
```


## Constructors

- `public CameraUpdateSystem()`  

```csharp
public CameraUpdateSystem();
```


## Methods

- `private CheckOrCacheViewer() : System.Boolean`  

```csharp
private System.Boolean CheckOrCacheViewer();
```

- `public GetBlendWeight(System.Single& weight) : Game.Rendering.CameraBlend`  

```csharp
public Game.Rendering.CameraBlend GetBlendWeight(System.Single& weight);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private RefreshInput() : System.Void`  

```csharp
private System.Void RefreshInput();
```

- `public TryGetLODParameters(UnityEngine.Rendering.LODParameters& lodParameters) : System.Boolean`  

```csharp
public System.Boolean TryGetLODParameters(UnityEngine.Rendering.LODParameters& lodParameters);
```

- `public TryGetViewer(Game.Rendering.Viewer& viewer) : System.Boolean`  

```csharp
public System.Boolean TryGetViewer(Game.Rendering.Viewer& viewer);
```

- `private UpdateDepthOfField(System.Single distance) : System.Void`  

```csharp
private System.Void UpdateDepthOfField(System.Single distance);
```

- `private UpdateShadows(Game.Rendering.Viewer viewer) : System.Void`  

```csharp
private System.Void UpdateShadows(Game.Rendering.Viewer viewer);
```


## Nested types

- `Game.Rendering.CameraUpdateSystem+<>c`  

