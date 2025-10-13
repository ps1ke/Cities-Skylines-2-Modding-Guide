# Game.ArtPipeline.Preview.HexColorField

**Assembly:** `Game.ArtPipeline`  
**Namespace:** `Game.ArtPipeline.Preview`  

**Type:** class public  

**Base:** `UnityEngine.MonoBehaviour`  

**Attributes:** `RequireComponent`  

## Code

```csharp
public class HexColorField : UnityEngine.MonoBehaviour
{
    public Game.ArtPipeline.Preview.ColorPicker hsvpicker;
    public System.Boolean displayAlpha;
    private UnityEngine.UI.InputField hexInputField;

    public HexColorField();

    private System.Void Awake();
    private System.String ColorToHex(UnityEngine.Color32 color);
    private System.Void OnDestroy();
    private System.Void UpdateColor(System.String newHex);
    private System.Void UpdateHex(UnityEngine.Color newColor);
}
```


## Fields

- `public Game.ArtPipeline.Preview.ColorPicker hsvpicker`  

```csharp
public Game.ArtPipeline.Preview.ColorPicker hsvpicker;
```

- `public System.Boolean displayAlpha`  

```csharp
public System.Boolean displayAlpha;
```

- `private UnityEngine.UI.InputField hexInputField`  

```csharp
private UnityEngine.UI.InputField hexInputField;
```


## Constructors

- `public HexColorField()`  

```csharp
public HexColorField();
```


## Methods

- `private Awake() : System.Void`  

```csharp
private System.Void Awake();
```

- `private ColorToHex(UnityEngine.Color32 color) : System.String`  

```csharp
private System.String ColorToHex(UnityEngine.Color32 color);
```

- `private OnDestroy() : System.Void`  

```csharp
private System.Void OnDestroy();
```

- `private UpdateColor(System.String newHex) : System.Void`  

```csharp
private System.Void UpdateColor(System.String newHex);
```

- `private UpdateHex(UnityEngine.Color newColor) : System.Void`  

```csharp
private System.Void UpdateHex(UnityEngine.Color newColor);
```


