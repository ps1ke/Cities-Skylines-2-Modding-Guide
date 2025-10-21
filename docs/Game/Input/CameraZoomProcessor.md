# Game.Input.CameraZoomProcessor

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class public  

**Base:** `Game.Input.PlatformProcessor<System.Single>`  

## Code

```csharp
public class CameraZoomProcessor : Game.Input.PlatformProcessor<System.Single>
{
    public System.Single m_Scale;

    public CameraZoomProcessor();

    public virtual System.Single Process(System.Single value, UnityEngine.InputSystem.InputControl control);
}
```


## Fields

- `public System.Single m_Scale`  

```csharp
public System.Single m_Scale;
```


## Constructors

- `public CameraZoomProcessor()`  

```csharp
public CameraZoomProcessor();
```


## Methods

- `public virtual Process(System.Single value, UnityEngine.InputSystem.InputControl control) : System.Single`  

```csharp
public virtual System.Single Process(System.Single value, UnityEngine.InputSystem.InputControl control);
```


