# Game.ArtPipeline.Preview.ColorPresets

**Assembly:** `Game.ArtPipeline`  
**Namespace:** `Game.ArtPipeline.Preview`  

**Type:** class public  

**Base:** `UnityEngine.MonoBehaviour`  

## Code

```csharp
public class ColorPresets : UnityEngine.MonoBehaviour
{
    public Game.ArtPipeline.Preview.ColorPicker picker;
    public UnityEngine.GameObject[] presets;
    public UnityEngine.UI.Image createPresetImage;
    private Game.ArtPipeline.Preview.ColorPresetList _colors;

    public ColorPresets();

    private System.Void Awake();
    private System.Void ColorChanged(UnityEngine.Color color);
    public System.Void CreatePresetButton();
    private System.Void OnColorsUpdate(System.Collections.Generic.List<UnityEngine.Color> colors);
    public System.Void PresetSelect(UnityEngine.UI.Image sender);
    private System.Void Start();
}
```


## Fields

- `public Game.ArtPipeline.Preview.ColorPicker picker`  

```csharp
public Game.ArtPipeline.Preview.ColorPicker picker;
```

- `public UnityEngine.GameObject[] presets`  

```csharp
public UnityEngine.GameObject[] presets;
```

- `public UnityEngine.UI.Image createPresetImage`  

```csharp
public UnityEngine.UI.Image createPresetImage;
```

- `private Game.ArtPipeline.Preview.ColorPresetList _colors`  

```csharp
private Game.ArtPipeline.Preview.ColorPresetList _colors;
```


## Constructors

- `public ColorPresets()`  

```csharp
public ColorPresets();
```


## Methods

- `private Awake() : System.Void`  

```csharp
private System.Void Awake();
```

- `private ColorChanged(UnityEngine.Color color) : System.Void`  

```csharp
private System.Void ColorChanged(UnityEngine.Color color);
```

- `public CreatePresetButton() : System.Void`  

```csharp
public System.Void CreatePresetButton();
```

- `private OnColorsUpdate(System.Collections.Generic.List<UnityEngine.Color> colors) : System.Void`  

```csharp
private System.Void OnColorsUpdate(System.Collections.Generic.List<UnityEngine.Color> colors);
```

- `public PresetSelect(UnityEngine.UI.Image sender) : System.Void`  

```csharp
public System.Void PresetSelect(UnityEngine.UI.Image sender);
```

- `private Start() : System.Void`  

```csharp
private System.Void Start();
```


