# Game.ArtPipeline.Preview.ColorLabel

**Assembly:** `Game.ArtPipeline`  
**Namespace:** `Game.ArtPipeline.Preview`  

**Type:** class public  

**Base:** `UnityEngine.MonoBehaviour`  

**Attributes:** `RequireComponent`  

## Code

```csharp
public class ColorLabel : UnityEngine.MonoBehaviour
{
    public Game.ArtPipeline.Preview.ColorPicker picker;
    public Game.ArtPipeline.Preview.ColorValues type;
    public System.String prefix;
    public System.Single minValue;
    public System.Single maxValue;
    public System.Int32 precision;
    private UnityEngine.UI.Text label;

    public ColorLabel();

    private System.Void Awake();
    private System.Void ColorChanged(UnityEngine.Color color);
    private System.String ConvertToDisplayString(System.Single value);
    private System.Void HSVChanged(System.Single hue, System.Single sateration, System.Single value);
    private System.Void OnDestroy();
    private System.Void OnEnable();
    private System.Void UpdateValue();
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

- `public System.String prefix`  

```csharp
public System.String prefix;
```

- `public System.Single minValue`  

```csharp
public System.Single minValue;
```

- `public System.Single maxValue`  

```csharp
public System.Single maxValue;
```

- `public System.Int32 precision`  

```csharp
public System.Int32 precision;
```

- `private UnityEngine.UI.Text label`  

```csharp
private UnityEngine.UI.Text label;
```


## Constructors

- `public ColorLabel()`  

```csharp
public ColorLabel();
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

- `private ConvertToDisplayString(System.Single value) : System.String`  

```csharp
private System.String ConvertToDisplayString(System.Single value);
```

- `private HSVChanged(System.Single hue, System.Single sateration, System.Single value) : System.Void`  

```csharp
private System.Void HSVChanged(System.Single hue, System.Single sateration, System.Single value);
```

- `private OnDestroy() : System.Void`  

```csharp
private System.Void OnDestroy();
```

- `private OnEnable() : System.Void`  

```csharp
private System.Void OnEnable();
```

- `private UpdateValue() : System.Void`  

```csharp
private System.Void UpdateValue();
```


