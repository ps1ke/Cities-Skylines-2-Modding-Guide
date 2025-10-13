# Game.ArtPipeline.Preview.ColorSlider

**Assembly:** `Game.ArtPipeline`  
**Namespace:** `Game.ArtPipeline.Preview`  

**Type:** class public  

**Base:** `UnityEngine.MonoBehaviour`  

**Attributes:** `RequireComponent`  

## Code

```csharp
public class ColorSlider : UnityEngine.MonoBehaviour
{
    public Game.ArtPipeline.Preview.ColorPicker hsvpicker;
    public Game.ArtPipeline.Preview.ColorValues type;
    private UnityEngine.UI.Slider slider;
    private System.Boolean listen;

    public ColorSlider();

    private System.Void Awake();
    private System.Void ColorChanged(UnityEngine.Color newColor);
    private System.Void HSVChanged(System.Single hue, System.Single saturation, System.Single value);
    private System.Void OnDestroy();
    private System.Void SliderChanged(System.Single newValue);
}
```


## Fields

- `public Game.ArtPipeline.Preview.ColorPicker hsvpicker`  

```csharp
public Game.ArtPipeline.Preview.ColorPicker hsvpicker;
```

- `public Game.ArtPipeline.Preview.ColorValues type`  

```csharp
public Game.ArtPipeline.Preview.ColorValues type;
```

- `private UnityEngine.UI.Slider slider`  

```csharp
private UnityEngine.UI.Slider slider;
```

- `private System.Boolean listen`  

```csharp
private System.Boolean listen;
```


## Constructors

- `public ColorSlider()`  

```csharp
public ColorSlider();
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

- `private SliderChanged(System.Single newValue) : System.Void`  

```csharp
private System.Void SliderChanged(System.Single newValue);
```


