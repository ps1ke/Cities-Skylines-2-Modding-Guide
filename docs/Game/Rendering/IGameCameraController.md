# Game.Rendering.IGameCameraController

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IGameCameraController
{
    public System.Single zoom { get; set; }
    public UnityEngine.Vector3 pivot { get; set; }
    public UnityEngine.Vector3 position { get; set; }
    public UnityEngine.Vector3 rotation { get; set; }
    public System.Boolean controllerEnabled { get; set; }
    public System.Boolean inputEnabled { get; set; }
    public Cinemachine.ICinemachineCamera virtualCamera { get; }
    public Cinemachine.LensSettings& lens { get; }

    public abstract System.Void TryMatchPosition(Game.Rendering.IGameCameraController other);
    public abstract System.Void UpdateCamera();
}
```


## Properties

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

- `public System.Boolean inputEnabled { get; set }`  

```csharp
public System.Boolean inputEnabled { get; set; }
```

- `public Cinemachine.ICinemachineCamera virtualCamera { get }`  

```csharp
public Cinemachine.ICinemachineCamera virtualCamera { get; }
```

- `public Cinemachine.LensSettings& lens { get }`  

```csharp
public Cinemachine.LensSettings& lens { get; }
```


## Methods

- `public abstract TryMatchPosition(Game.Rendering.IGameCameraController other) : System.Void`  

```csharp
public abstract System.Void TryMatchPosition(Game.Rendering.IGameCameraController other);
```

- `public abstract UpdateCamera() : System.Void`  

```csharp
public abstract System.Void UpdateCamera();
```


