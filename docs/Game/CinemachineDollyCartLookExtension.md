# Game.CinemachineDollyCartLookExtension

**Assembly:** `Game`  
**Namespace:** `Game`  

**Type:** class public  

**Base:** `Cinemachine.CinemachineExtension`  

## Code

```csharp
public class CinemachineDollyCartLookExtension : Cinemachine.CinemachineExtension
{
    public Game.CinemachineDollyCartLookExtension+DollyLookAngleOverride[] m_Angles;

    public CinemachineDollyCartLookExtension();

    private UnityEngine.Quaternion GetAngleOffset(Cinemachine.CinemachinePathBase path, System.Int32 t);
    private System.Single GetBoundingIndices(System.Single pos, System.Boolean looped, System.Int32& indexA, System.Int32& indexB);
    public System.Single GetMaxPos(System.Boolean looped);
    protected virtual System.Void PostPipelineStageCallback(Cinemachine.CinemachineVirtualCameraBase vcam, Cinemachine.CinemachineCore+Stage stage, Cinemachine.CameraState& state, System.Single deltaTime);
    public virtual System.Single StandardizePos(System.Single pos, System.Boolean looped);
}
```


## Fields

- `public Game.CinemachineDollyCartLookExtension+DollyLookAngleOverride[] m_Angles`  

```csharp
public Game.CinemachineDollyCartLookExtension+DollyLookAngleOverride[] m_Angles;
```


## Constructors

- `public CinemachineDollyCartLookExtension()`  

```csharp
public CinemachineDollyCartLookExtension();
```


## Methods

- `private GetAngleOffset(Cinemachine.CinemachinePathBase path, System.Int32 t) : UnityEngine.Quaternion`  

```csharp
private UnityEngine.Quaternion GetAngleOffset(Cinemachine.CinemachinePathBase path, System.Int32 t);
```

- `private GetBoundingIndices(System.Single pos, System.Boolean looped, System.Int32& indexA, System.Int32& indexB) : System.Single`  

```csharp
private System.Single GetBoundingIndices(System.Single pos, System.Boolean looped, System.Int32& indexA, System.Int32& indexB);
```

- `public GetMaxPos(System.Boolean looped) : System.Single`  

```csharp
public System.Single GetMaxPos(System.Boolean looped);
```

- `protected virtual PostPipelineStageCallback(Cinemachine.CinemachineVirtualCameraBase vcam, Cinemachine.CinemachineCore+Stage stage, Cinemachine.CameraState& state, System.Single deltaTime) : System.Void`  

```csharp
protected virtual System.Void PostPipelineStageCallback(Cinemachine.CinemachineVirtualCameraBase vcam, Cinemachine.CinemachineCore+Stage stage, Cinemachine.CameraState& state, System.Single deltaTime);
```

- `public virtual StandardizePos(System.Single pos, System.Boolean looped) : System.Single`  

```csharp
public virtual System.Single StandardizePos(System.Single pos, System.Boolean looped);
```


## Nested types

- `Game.CinemachineDollyCartLookExtension+DollyLookAngleOverride`  

