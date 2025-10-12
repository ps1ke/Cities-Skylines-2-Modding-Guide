# Game.Rendering.IGameCameraController

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** interface abstract public  


## Properties

- `public System.Single zoom { get; set }`  
- `public UnityEngine.Vector3 pivot { get; set }`  
- `public UnityEngine.Vector3 position { get; set }`  
- `public UnityEngine.Vector3 rotation { get; set }`  
- `public System.Boolean controllerEnabled { get; set }`  
- `public System.Boolean inputEnabled { get; set }`  
- `public Cinemachine.ICinemachineCamera virtualCamera { get }`  
- `public Cinemachine.LensSettings& lens { get }`  

## Methods

- `public abstract TryMatchPosition(Game.Rendering.IGameCameraController other) : System.Void`  
- `public abstract UpdateCamera() : System.Void`  

