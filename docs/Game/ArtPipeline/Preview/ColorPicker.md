# Game.ArtPipeline.Preview.ColorPicker

**Assembly:** `Game.ArtPipeline`  
**Namespace:** `Game.ArtPipeline.Preview`  

**Type:** class public  

**Base:** `UnityEngine.MonoBehaviour`  

## Code

```csharp
public class ColorPicker : UnityEngine.MonoBehaviour
{
    private System.Single _hue;
    private System.Single _saturation;
    private System.Single _brightness;
    private System.Single _red;
    private System.Single _green;
    private System.Single _blue;
    private System.Single _alpha;
    public Game.ArtPipeline.Preview.ColorPickerSetup Setup;
    public Game.ArtPipeline.Preview.ColorChangedEvent onValueChanged;
    public Game.ArtPipeline.Preview.HSVChangedEvent onHSVChanged;
    private System.Collections.Generic.List<UnityEngine.UI.ToggleGroup> toggleGroups;

    public UnityEngine.Color CurrentColor { get; set; }
    public System.Single H { get; set; }
    public System.Single S { get; set; }
    public System.Single V { get; set; }
    public System.Single R { get; set; }
    public System.Single G { get; set; }
    public System.Single B { get; set; }
    private System.Single A { private get; private set; }

    public ColorPicker();

    public System.Void AssignColor(Game.ArtPipeline.Preview.ColorValues type, System.Single value);
    public System.Single GetValue(Game.ArtPipeline.Preview.ColorValues type);
    private System.Void HandleHeaderSetting(Game.ArtPipeline.Preview.ColorPickerSetup+ColorHeaderShowing setupShowHeader);
    private System.Void HSVChanged();
    private System.Void LateUpdate();
    public System.Void RegisterToggle(UnityEngine.UI.ToggleGroup tg);
    private System.Void RGBChanged();
    private System.Void SendChangedEvent();
    private System.Void Start();
    public System.Void ToggleColorSliders();
    private System.Void UpdateColorToggleText();
}
```


## Fields

- `private System.Single _hue`  

```csharp
private System.Single _hue;
```

- `private System.Single _saturation`  

```csharp
private System.Single _saturation;
```

- `private System.Single _brightness`  

```csharp
private System.Single _brightness;
```

- `private System.Single _red`  

```csharp
private System.Single _red;
```

- `private System.Single _green`  

```csharp
private System.Single _green;
```

- `private System.Single _blue`  

```csharp
private System.Single _blue;
```

- `private System.Single _alpha`  

```csharp
private System.Single _alpha;
```

- `public Game.ArtPipeline.Preview.ColorPickerSetup Setup`  

```csharp
public Game.ArtPipeline.Preview.ColorPickerSetup Setup;
```

- `public Game.ArtPipeline.Preview.ColorChangedEvent onValueChanged`  

```csharp
public Game.ArtPipeline.Preview.ColorChangedEvent onValueChanged;
```

- `public Game.ArtPipeline.Preview.HSVChangedEvent onHSVChanged`  

```csharp
public Game.ArtPipeline.Preview.HSVChangedEvent onHSVChanged;
```

- `private System.Collections.Generic.List<UnityEngine.UI.ToggleGroup> toggleGroups`  

```csharp
private System.Collections.Generic.List<UnityEngine.UI.ToggleGroup> toggleGroups;
```


## Properties

- `public UnityEngine.Color CurrentColor { get; set }`  

```csharp
public UnityEngine.Color CurrentColor { get; set; }
```

- `public System.Single H { get; set }`  

```csharp
public System.Single H { get; set; }
```

- `public System.Single S { get; set }`  

```csharp
public System.Single S { get; set; }
```

- `public System.Single V { get; set }`  

```csharp
public System.Single V { get; set; }
```

- `public System.Single R { get; set }`  

```csharp
public System.Single R { get; set; }
```

- `public System.Single G { get; set }`  

```csharp
public System.Single G { get; set; }
```

- `public System.Single B { get; set }`  

```csharp
public System.Single B { get; set; }
```

- `private System.Single A { private get; private set }`  

```csharp
private System.Single A { private get; private set; }
```


## Constructors

- `public ColorPicker()`  

```csharp
public ColorPicker();
```


## Methods

- `public AssignColor(Game.ArtPipeline.Preview.ColorValues type, System.Single value) : System.Void`  

```csharp
public System.Void AssignColor(Game.ArtPipeline.Preview.ColorValues type, System.Single value);
```

- `public GetValue(Game.ArtPipeline.Preview.ColorValues type) : System.Single`  

```csharp
public System.Single GetValue(Game.ArtPipeline.Preview.ColorValues type);
```

- `private HandleHeaderSetting(Game.ArtPipeline.Preview.ColorPickerSetup+ColorHeaderShowing setupShowHeader) : System.Void`  

```csharp
private System.Void HandleHeaderSetting(Game.ArtPipeline.Preview.ColorPickerSetup+ColorHeaderShowing setupShowHeader);
```

- `private HSVChanged() : System.Void`  

```csharp
private System.Void HSVChanged();
```

- `private LateUpdate() : System.Void`  

```csharp
private System.Void LateUpdate();
```

- `public RegisterToggle(UnityEngine.UI.ToggleGroup tg) : System.Void`  

```csharp
public System.Void RegisterToggle(UnityEngine.UI.ToggleGroup tg);
```

- `private RGBChanged() : System.Void`  

```csharp
private System.Void RGBChanged();
```

- `private SendChangedEvent() : System.Void`  

```csharp
private System.Void SendChangedEvent();
```

- `private Start() : System.Void`  

```csharp
private System.Void Start();
```

- `public ToggleColorSliders() : System.Void`  

```csharp
public System.Void ToggleColorSliders();
```

- `private UpdateColorToggleText() : System.Void`  

```csharp
private System.Void UpdateColorToggleText();
```


