# Game.ArtPipeline.Preview.ColorImage

**Assembly:** `Game.ArtPipeline`  
**Namespace:** `Game.ArtPipeline.Preview`  

**Type:** class public  

**Base:** `UnityEngine.MonoBehaviour`  

**Attributes:** `RequireComponent`  

## Code

```csharp
public class ColorImage : UnityEngine.MonoBehaviour
{
    public Game.ArtPipeline.Preview.ColorPicker picker;
    private UnityEngine.UI.Image image;

    public ColorImage();

    private System.Void Awake();
    private System.Void ColorChanged(UnityEngine.Color newColor);
    private System.Void OnDestroy();
}
```


## Fields

- `public Game.ArtPipeline.Preview.ColorPicker picker`  

```csharp
public Game.ArtPipeline.Preview.ColorPicker picker;
```

- `private UnityEngine.UI.Image image`  

```csharp
private UnityEngine.UI.Image image;
```


## Constructors

- `public ColorImage()`  

```csharp
public ColorImage();
```


## Methods

- `private Awake() : System.Void`  

```csharp
private System.Void Awake();
```

- `private ColorChanged(UnityEngine.Color newColor) : System.Void`  

```csharp
private System.Void ColorChanged(UnityEngine.Color newColor);
```

- `private OnDestroy() : System.Void`  

```csharp
private System.Void OnDestroy();
```


