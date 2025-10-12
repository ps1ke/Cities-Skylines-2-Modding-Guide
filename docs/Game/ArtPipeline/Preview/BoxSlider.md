# Game.ArtPipeline.Preview.BoxSlider

**Assembly:** `Game.ArtPipeline`  
**Namespace:** `Game.ArtPipeline.Preview`  

**Type:** class public  

**Base:** `UnityEngine.UI.Selectable`  
**Implements:** `UnityEngine.EventSystems.IMoveHandler`, `UnityEngine.EventSystems.IEventSystemHandler`, `UnityEngine.EventSystems.IPointerDownHandler`, `UnityEngine.EventSystems.IPointerUpHandler`, `UnityEngine.EventSystems.IPointerEnterHandler`, `UnityEngine.EventSystems.IPointerExitHandler`, `UnityEngine.EventSystems.ISelectHandler`, `UnityEngine.EventSystems.IDeselectHandler`, `UnityEngine.EventSystems.IDragHandler`, `UnityEngine.EventSystems.IInitializePotentialDragHandler`, `UnityEngine.UI.ICanvasElement`  

**Attributes:** `AddComponentMenu`, `RequireComponent`  

## Fields

- `private UnityEngine.RectTransform m_HandleRect`  
- `private System.Single m_MinValue`  
- `private System.Single m_MaxValue`  
- `private System.Boolean m_WholeNumbers`  
- `private System.Single m_Value`  
- `private System.Single m_ValueY`  
- `private Game.ArtPipeline.Preview.BoxSlider+BoxSliderEvent m_OnValueChanged`  
- `private UnityEngine.Transform m_HandleTransform`  
- `private UnityEngine.RectTransform m_HandleContainerRect`  
- `private UnityEngine.Vector2 m_Offset`  
- `private UnityEngine.DrivenRectTransformTracker m_Tracker`  

## Properties

- `public UnityEngine.RectTransform handleRect { get; set }`  
- `public System.Single minValue { get; set }`  
- `public System.Single maxValue { get; set }`  
- `public System.Boolean wholeNumbers { get; set }`  
- `public System.Single value { get; set }`  
- `public System.Single normalizedValue { get; set }`  
- `public System.Single valueY { get; set }`  
- `public System.Single normalizedValueY { get; set }`  
- `public Game.ArtPipeline.Preview.BoxSlider+BoxSliderEvent onValueChanged { get; set }`  
- `private System.Single stepSize { private get }`  

## Constructors

- `protected BoxSlider()`  

## Methods

- `public GraphicUpdateComplete() : System.Void`  
- `public LayoutComplete() : System.Void`  
- `private MayDrag(UnityEngine.EventSystems.PointerEventData eventData) : System.Boolean`  
- `protected virtual OnDisable() : System.Void`  
- `public virtual OnDrag(UnityEngine.EventSystems.PointerEventData eventData) : System.Void`  
- `protected virtual OnEnable() : System.Void`  
- `public virtual OnInitializePotentialDrag(UnityEngine.EventSystems.PointerEventData eventData) : System.Void`  
- `public virtual OnPointerDown(UnityEngine.EventSystems.PointerEventData eventData) : System.Void`  
- `protected virtual OnRectTransformDimensionsChange() : System.Void`  
- `public virtual Rebuild(UnityEngine.UI.CanvasUpdate executing) : System.Void`  
- `private Set(System.Single input) : System.Void`  
- `private Set(System.Single input, System.Boolean sendCallback) : System.Void`  
- `public static SetClass<T>(T& currentValue, T newValue) : System.Boolean`  
- `public static SetStruct<T>(T& currentValue, T newValue) : System.Boolean`  
- `private SetY(System.Single input) : System.Void`  
- `private SetY(System.Single input, System.Boolean sendCallback) : System.Void`  
- `private UnityEngine.UI.ICanvasElement.get_transform() : UnityEngine.Transform`  
- `private UpdateCachedReferences() : System.Void`  
- `private UpdateDrag(UnityEngine.EventSystems.PointerEventData eventData, UnityEngine.Camera cam) : System.Void`  
- `private UpdateVisuals() : System.Void`  

## Nested types

- `Game.ArtPipeline.Preview.BoxSlider+Direction`  
- `Game.ArtPipeline.Preview.BoxSlider+BoxSliderEvent`  
- `Game.ArtPipeline.Preview.BoxSlider+Axis`  

