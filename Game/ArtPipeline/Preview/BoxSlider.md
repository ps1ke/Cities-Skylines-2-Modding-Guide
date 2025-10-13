# Game.ArtPipeline.Preview.BoxSlider

**Assembly:** `Game.ArtPipeline`  
**Namespace:** `Game.ArtPipeline.Preview`  

**Type:** class public  

**Base:** `UnityEngine.UI.Selectable`  
**Implements:** `UnityEngine.EventSystems.IMoveHandler`, `UnityEngine.EventSystems.IEventSystemHandler`, `UnityEngine.EventSystems.IPointerDownHandler`, `UnityEngine.EventSystems.IPointerUpHandler`, `UnityEngine.EventSystems.IPointerEnterHandler`, `UnityEngine.EventSystems.IPointerExitHandler`, `UnityEngine.EventSystems.ISelectHandler`, `UnityEngine.EventSystems.IDeselectHandler`, `UnityEngine.EventSystems.IDragHandler`, `UnityEngine.EventSystems.IInitializePotentialDragHandler`, `UnityEngine.UI.ICanvasElement`  

**Attributes:** `AddComponentMenu`, `RequireComponent`  

## Code

```csharp
public class BoxSlider : UnityEngine.UI.Selectable, UnityEngine.EventSystems.IMoveHandler, UnityEngine.EventSystems.IEventSystemHandler, UnityEngine.EventSystems.IPointerDownHandler, UnityEngine.EventSystems.IPointerUpHandler, UnityEngine.EventSystems.IPointerEnterHandler, UnityEngine.EventSystems.IPointerExitHandler, UnityEngine.EventSystems.ISelectHandler, UnityEngine.EventSystems.IDeselectHandler, UnityEngine.EventSystems.IDragHandler, UnityEngine.EventSystems.IInitializePotentialDragHandler, UnityEngine.UI.ICanvasElement
{
    private UnityEngine.RectTransform m_HandleRect;
    private System.Single m_MinValue;
    private System.Single m_MaxValue;
    private System.Boolean m_WholeNumbers;
    private System.Single m_Value;
    private System.Single m_ValueY;
    private Game.ArtPipeline.Preview.BoxSlider+BoxSliderEvent m_OnValueChanged;
    private UnityEngine.Transform m_HandleTransform;
    private UnityEngine.RectTransform m_HandleContainerRect;
    private UnityEngine.Vector2 m_Offset;
    private UnityEngine.DrivenRectTransformTracker m_Tracker;

    public UnityEngine.RectTransform handleRect { get; set; }
    public System.Single minValue { get; set; }
    public System.Single maxValue { get; set; }
    public System.Boolean wholeNumbers { get; set; }
    public System.Single value { get; set; }
    public System.Single normalizedValue { get; set; }
    public System.Single valueY { get; set; }
    public System.Single normalizedValueY { get; set; }
    public Game.ArtPipeline.Preview.BoxSlider+BoxSliderEvent onValueChanged { get; set; }
    private System.Single stepSize { private get; }

    protected BoxSlider();

    public System.Void GraphicUpdateComplete();
    public System.Void LayoutComplete();
    private System.Boolean MayDrag(UnityEngine.EventSystems.PointerEventData eventData);
    protected virtual System.Void OnDisable();
    public virtual System.Void OnDrag(UnityEngine.EventSystems.PointerEventData eventData);
    protected virtual System.Void OnEnable();
    public virtual System.Void OnInitializePotentialDrag(UnityEngine.EventSystems.PointerEventData eventData);
    public virtual System.Void OnPointerDown(UnityEngine.EventSystems.PointerEventData eventData);
    protected virtual System.Void OnRectTransformDimensionsChange();
    public virtual System.Void Rebuild(UnityEngine.UI.CanvasUpdate executing);
    private System.Void Set(System.Single input);
    private System.Void Set(System.Single input, System.Boolean sendCallback);
    public static System.Boolean SetClass<T>(T& currentValue, T newValue);
    public static System.Boolean SetStruct<T>(T& currentValue, T newValue);
    private System.Void SetY(System.Single input);
    private System.Void SetY(System.Single input, System.Boolean sendCallback);
    private UnityEngine.Transform UnityEngine.UI.ICanvasElement.get_transform();
    private System.Void UpdateCachedReferences();
    private System.Void UpdateDrag(UnityEngine.EventSystems.PointerEventData eventData, UnityEngine.Camera cam);
    private System.Void UpdateVisuals();
}
```


## Fields

- `private UnityEngine.RectTransform m_HandleRect`  

```csharp
private UnityEngine.RectTransform m_HandleRect;
```

- `private System.Single m_MinValue`  

```csharp
private System.Single m_MinValue;
```

- `private System.Single m_MaxValue`  

```csharp
private System.Single m_MaxValue;
```

- `private System.Boolean m_WholeNumbers`  

```csharp
private System.Boolean m_WholeNumbers;
```

- `private System.Single m_Value`  

```csharp
private System.Single m_Value;
```

- `private System.Single m_ValueY`  

```csharp
private System.Single m_ValueY;
```

- `private Game.ArtPipeline.Preview.BoxSlider+BoxSliderEvent m_OnValueChanged`  

```csharp
private Game.ArtPipeline.Preview.BoxSlider+BoxSliderEvent m_OnValueChanged;
```

- `private UnityEngine.Transform m_HandleTransform`  

```csharp
private UnityEngine.Transform m_HandleTransform;
```

- `private UnityEngine.RectTransform m_HandleContainerRect`  

```csharp
private UnityEngine.RectTransform m_HandleContainerRect;
```

- `private UnityEngine.Vector2 m_Offset`  

```csharp
private UnityEngine.Vector2 m_Offset;
```

- `private UnityEngine.DrivenRectTransformTracker m_Tracker`  

```csharp
private UnityEngine.DrivenRectTransformTracker m_Tracker;
```


## Properties

- `public UnityEngine.RectTransform handleRect { get; set }`  

```csharp
public UnityEngine.RectTransform handleRect { get; set; }
```

- `public System.Single minValue { get; set }`  

```csharp
public System.Single minValue { get; set; }
```

- `public System.Single maxValue { get; set }`  

```csharp
public System.Single maxValue { get; set; }
```

- `public System.Boolean wholeNumbers { get; set }`  

```csharp
public System.Boolean wholeNumbers { get; set; }
```

- `public System.Single value { get; set }`  

```csharp
public System.Single value { get; set; }
```

- `public System.Single normalizedValue { get; set }`  

```csharp
public System.Single normalizedValue { get; set; }
```

- `public System.Single valueY { get; set }`  

```csharp
public System.Single valueY { get; set; }
```

- `public System.Single normalizedValueY { get; set }`  

```csharp
public System.Single normalizedValueY { get; set; }
```

- `public Game.ArtPipeline.Preview.BoxSlider+BoxSliderEvent onValueChanged { get; set }`  

```csharp
public Game.ArtPipeline.Preview.BoxSlider+BoxSliderEvent onValueChanged { get; set; }
```

- `private System.Single stepSize { private get }`  

```csharp
private System.Single stepSize { private get; }
```


## Constructors

- `protected BoxSlider()`  

```csharp
protected BoxSlider();
```


## Methods

- `public GraphicUpdateComplete() : System.Void`  

```csharp
public System.Void GraphicUpdateComplete();
```

- `public LayoutComplete() : System.Void`  

```csharp
public System.Void LayoutComplete();
```

- `private MayDrag(UnityEngine.EventSystems.PointerEventData eventData) : System.Boolean`  

```csharp
private System.Boolean MayDrag(UnityEngine.EventSystems.PointerEventData eventData);
```

- `protected virtual OnDisable() : System.Void`  

```csharp
protected virtual System.Void OnDisable();
```

- `public virtual OnDrag(UnityEngine.EventSystems.PointerEventData eventData) : System.Void`  

```csharp
public virtual System.Void OnDrag(UnityEngine.EventSystems.PointerEventData eventData);
```

- `protected virtual OnEnable() : System.Void`  

```csharp
protected virtual System.Void OnEnable();
```

- `public virtual OnInitializePotentialDrag(UnityEngine.EventSystems.PointerEventData eventData) : System.Void`  

```csharp
public virtual System.Void OnInitializePotentialDrag(UnityEngine.EventSystems.PointerEventData eventData);
```

- `public virtual OnPointerDown(UnityEngine.EventSystems.PointerEventData eventData) : System.Void`  

```csharp
public virtual System.Void OnPointerDown(UnityEngine.EventSystems.PointerEventData eventData);
```

- `protected virtual OnRectTransformDimensionsChange() : System.Void`  

```csharp
protected virtual System.Void OnRectTransformDimensionsChange();
```

- `public virtual Rebuild(UnityEngine.UI.CanvasUpdate executing) : System.Void`  

```csharp
public virtual System.Void Rebuild(UnityEngine.UI.CanvasUpdate executing);
```

- `private Set(System.Single input) : System.Void`  

```csharp
private System.Void Set(System.Single input);
```

- `private Set(System.Single input, System.Boolean sendCallback) : System.Void`  

```csharp
private System.Void Set(System.Single input, System.Boolean sendCallback);
```

- `public static SetClass<T>(T& currentValue, T newValue) : System.Boolean`  

```csharp
public static System.Boolean SetClass<T>(T& currentValue, T newValue);
```

- `public static SetStruct<T>(T& currentValue, T newValue) : System.Boolean`  

```csharp
public static System.Boolean SetStruct<T>(T& currentValue, T newValue);
```

- `private SetY(System.Single input) : System.Void`  

```csharp
private System.Void SetY(System.Single input);
```

- `private SetY(System.Single input, System.Boolean sendCallback) : System.Void`  

```csharp
private System.Void SetY(System.Single input, System.Boolean sendCallback);
```

- `private UnityEngine.UI.ICanvasElement.get_transform() : UnityEngine.Transform`  

```csharp
private UnityEngine.Transform UnityEngine.UI.ICanvasElement.get_transform();
```

- `private UpdateCachedReferences() : System.Void`  

```csharp
private System.Void UpdateCachedReferences();
```

- `private UpdateDrag(UnityEngine.EventSystems.PointerEventData eventData, UnityEngine.Camera cam) : System.Void`  

```csharp
private System.Void UpdateDrag(UnityEngine.EventSystems.PointerEventData eventData, UnityEngine.Camera cam);
```

- `private UpdateVisuals() : System.Void`  

```csharp
private System.Void UpdateVisuals();
```


## Nested types

- `Game.ArtPipeline.Preview.BoxSlider+Direction`  
- `Game.ArtPipeline.Preview.BoxSlider+BoxSliderEvent`  
- `Game.ArtPipeline.Preview.BoxSlider+Axis`  

