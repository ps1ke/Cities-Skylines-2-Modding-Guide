# Game.ArtPipeline.Preview.PickerToggle

**Assembly:** `Game.ArtPipeline`  
**Namespace:** `Game.ArtPipeline.Preview`  

**Type:** class public  

**Base:** `UnityEngine.MonoBehaviour`  

## Code

```csharp
public class PickerToggle : UnityEngine.MonoBehaviour
{
    public Game.ArtPipeline.Preview.ColorChangedEvent onValueChanged;
    public Game.ArtPipeline.Preview.ColorPicker m_PickerTarget;
    public UnityEngine.UI.Image m_Background;
    private UnityEngine.UI.Toggle m_Toogle;

    public UnityEngine.Color color { get; set; }

    public PickerToggle();

    private System.Void Awake();
    private System.Void OnValueChanged(System.Boolean active);
    private System.Void PropagateChange(UnityEngine.Color color);
    private System.Void Start();
}
```


## Fields

- `public Game.ArtPipeline.Preview.ColorChangedEvent onValueChanged`  

```csharp
public Game.ArtPipeline.Preview.ColorChangedEvent onValueChanged;
```

- `public Game.ArtPipeline.Preview.ColorPicker m_PickerTarget`  

```csharp
public Game.ArtPipeline.Preview.ColorPicker m_PickerTarget;
```

- `public UnityEngine.UI.Image m_Background`  

```csharp
public UnityEngine.UI.Image m_Background;
```

- `private UnityEngine.UI.Toggle m_Toogle`  

```csharp
private UnityEngine.UI.Toggle m_Toogle;
```


## Properties

- `public UnityEngine.Color color { get; set }`  

```csharp
public UnityEngine.Color color { get; set; }
```


## Constructors

- `public PickerToggle()`  

```csharp
public PickerToggle();
```


## Methods

- `private Awake() : System.Void`  

```csharp
private System.Void Awake();
```

- `private OnValueChanged(System.Boolean active) : System.Void`  

```csharp
private System.Void OnValueChanged(System.Boolean active);
```

- `private PropagateChange(UnityEngine.Color color) : System.Void`  

```csharp
private System.Void PropagateChange(UnityEngine.Color color);
```

- `private Start() : System.Void`  

```csharp
private System.Void Start();
```


