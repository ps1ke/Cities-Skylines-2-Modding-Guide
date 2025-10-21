# Game.ArtPipeline.Preview.SVBoxSlider

**Assembly:** `Game.ArtPipeline`  
**Namespace:** `Game.ArtPipeline.Preview`  

**Type:** class public  

**Base:** `UnityEngine.MonoBehaviour`  

**Attributes:** `RequireComponent`, `ExecuteInEditMode`  

## Code

```csharp
public class SVBoxSlider : UnityEngine.MonoBehaviour
{
    public Game.ArtPipeline.Preview.ColorPicker picker;
    private Game.ArtPipeline.Preview.BoxSlider slider;
    private UnityEngine.UI.RawImage image;
    private UnityEngine.ComputeShader compute;
    private System.Int32 kernelID;
    private UnityEngine.RenderTexture renderTexture;
    private System.Int32 textureWidth;
    private System.Int32 textureHeight;
    private System.Single lastH;
    private System.Boolean listen;
    private System.Boolean overrideComputeShader;
    private System.Boolean supportsComputeShaders;

    public UnityEngine.RectTransform rectTransform { get; }

    public SVBoxSlider();

    private System.Void Awake();
    private System.Void HSVChanged(System.Single h, System.Single s, System.Single v);
    private System.Void InitializeCompute();
    private System.Void OnDestroy();
    private System.Void OnDisable();
    private System.Void OnEnable();
    private System.Void RegenerateSVTexture();
    private System.Void SliderChanged(System.Single saturation, System.Single value);
}
```


## Fields

- `public Game.ArtPipeline.Preview.ColorPicker picker`  

```csharp
public Game.ArtPipeline.Preview.ColorPicker picker;
```

- `private Game.ArtPipeline.Preview.BoxSlider slider`  

```csharp
private Game.ArtPipeline.Preview.BoxSlider slider;
```

- `private UnityEngine.UI.RawImage image`  

```csharp
private UnityEngine.UI.RawImage image;
```

- `private UnityEngine.ComputeShader compute`  

```csharp
private UnityEngine.ComputeShader compute;
```

- `private System.Int32 kernelID`  

```csharp
private System.Int32 kernelID;
```

- `private UnityEngine.RenderTexture renderTexture`  

```csharp
private UnityEngine.RenderTexture renderTexture;
```

- `private System.Int32 textureWidth`  

```csharp
private System.Int32 textureWidth;
```

- `private System.Int32 textureHeight`  

```csharp
private System.Int32 textureHeight;
```

- `private System.Single lastH`  

```csharp
private System.Single lastH;
```

- `private System.Boolean listen`  

```csharp
private System.Boolean listen;
```

- `private System.Boolean overrideComputeShader`  

```csharp
private System.Boolean overrideComputeShader;
```

- `private System.Boolean supportsComputeShaders`  

```csharp
private System.Boolean supportsComputeShaders;
```


## Properties

- `public UnityEngine.RectTransform rectTransform { get }`  

```csharp
public UnityEngine.RectTransform rectTransform { get; }
```


## Constructors

- `public SVBoxSlider()`  

```csharp
public SVBoxSlider();
```


## Methods

- `private Awake() : System.Void`  

```csharp
private System.Void Awake();
```

- `private HSVChanged(System.Single h, System.Single s, System.Single v) : System.Void`  

```csharp
private System.Void HSVChanged(System.Single h, System.Single s, System.Single v);
```

- `private InitializeCompute() : System.Void`  

```csharp
private System.Void InitializeCompute();
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

- `private RegenerateSVTexture() : System.Void`  

```csharp
private System.Void RegenerateSVTexture();
```

- `private SliderChanged(System.Single saturation, System.Single value) : System.Void`  

```csharp
private System.Void SliderChanged(System.Single saturation, System.Single value);
```


