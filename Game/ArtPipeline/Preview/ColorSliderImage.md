# Game.ArtPipeline.Preview.ColorSliderImage

**Assembly:** `Game.ArtPipeline`  
**Namespace:** `Game.ArtPipeline.Preview`  

**Type:** class public  

**Base:** `UnityEngine.MonoBehaviour`  

**Attributes:** `RequireComponent`, `ExecuteInEditMode`  

## Code

```csharp
public class ColorSliderImage : UnityEngine.MonoBehaviour
{
    public Game.ArtPipeline.Preview.ColorPicker picker;
    public Game.ArtPipeline.Preview.ColorValues type;
    public UnityEngine.UI.Slider+Direction direction;
    private UnityEngine.UI.RawImage image;

    private UnityEngine.RectTransform rectTransform { private get; }

    public ColorSliderImage();

    private System.Void Awake();
    private System.Void ColorChanged(UnityEngine.Color newColor);
    private System.Void HSVChanged(System.Single hue, System.Single saturation, System.Single value);
    private System.Void OnDestroy();
    private System.Void OnDisable();
    private System.Void OnEnable();
    private System.Void RegenerateTexture();
}
```


## Fields

- `public Game.ArtPipeline.Preview.ColorPicker picker`  

```csharp
public Game.ArtPipeline.Preview.ColorPicker picker;
```

- `public Game.ArtPipeline.Preview.ColorValues type`  

```csharp
public Game.ArtPipeline.Preview.ColorValues type;
```

- `public UnityEngine.UI.Slider+Direction direction`  

```csharp
public UnityEngine.UI.Slider+Direction direction;
```

- `private UnityEngine.UI.RawImage image`  

```csharp
private UnityEngine.UI.RawImage image;
```


## Properties

- `private UnityEngine.RectTransform rectTransform { private get }`  

```csharp
private UnityEngine.RectTransform rectTransform { private get; }
```


## Constructors

- `public ColorSliderImage()`  

```csharp
public ColorSliderImage();
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

- `private HSVChanged(System.Single hue, System.Single saturation, System.Single value) : System.Void`  

```csharp
private System.Void HSVChanged(System.Single hue, System.Single saturation, System.Single value);
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

- `private RegenerateTexture() : System.Void`  

```csharp
private System.Void RegenerateTexture();
```


