# Game.Input.CameraMoveProcessor

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class public  

**Base:** `Game.Input.PlatformProcessor<UnityEngine.Vector2>`  

## Code

```csharp
public class CameraMoveProcessor : Game.Input.PlatformProcessor<UnityEngine.Vector2>
{
    public System.Single m_ScaleX;
    public System.Single m_ScaleY;

    public CameraMoveProcessor();

    public virtual UnityEngine.Vector2 Process(UnityEngine.Vector2 value, UnityEngine.InputSystem.InputControl control);
}
```


## Fields

- `public System.Single m_ScaleX`  

```csharp
public System.Single m_ScaleX;
```

- `public System.Single m_ScaleY`  

```csharp
public System.Single m_ScaleY;
```


## Constructors

- `public CameraMoveProcessor()`  

```csharp
public CameraMoveProcessor();
```


## Methods

- `public virtual Process(UnityEngine.Vector2 value, UnityEngine.InputSystem.InputControl control) : UnityEngine.Vector2`  

```csharp
public virtual UnityEngine.Vector2 Process(UnityEngine.Vector2 value, UnityEngine.InputSystem.InputControl control);
```


