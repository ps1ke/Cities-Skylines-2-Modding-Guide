# Game.ArtPipeline.Preview.CloseOnClick

**Assembly:** `Game.ArtPipeline`  
**Namespace:** `Game.ArtPipeline.Preview`  

**Type:** class public  

**Base:** `UnityEngine.MonoBehaviour`  
**Implements:** `UnityEngine.EventSystems.IPointerClickHandler`, `UnityEngine.EventSystems.IEventSystemHandler`  

## Code

```csharp
public class CloseOnClick : UnityEngine.MonoBehaviour, UnityEngine.EventSystems.IPointerClickHandler, UnityEngine.EventSystems.IEventSystemHandler
{
    public UnityEngine.GameObject[] m_HideObjects;

    public CloseOnClick();

    public System.Void OnPointerClick(UnityEngine.EventSystems.PointerEventData eventData);
    private System.Void Start();
}
```


## Fields

- `public UnityEngine.GameObject[] m_HideObjects`  

```csharp
public UnityEngine.GameObject[] m_HideObjects;
```


## Constructors

- `public CloseOnClick()`  

```csharp
public CloseOnClick();
```


## Methods

- `public OnPointerClick(UnityEngine.EventSystems.PointerEventData eventData) : System.Void`  

```csharp
public System.Void OnPointerClick(UnityEngine.EventSystems.PointerEventData eventData);
```

- `private Start() : System.Void`  

```csharp
private System.Void Start();
```


