# Game.ArtPipeline.Preview.ColorLabel

**Assembly:** `Game.ArtPipeline`  
**Namespace:** `Game.ArtPipeline.Preview`  

**Type:** class public  

**Base:** `UnityEngine.MonoBehaviour`  

**Attributes:** `RequireComponent`  

## Fields

- `public Game.ArtPipeline.Preview.ColorPicker picker`  
- `public Game.ArtPipeline.Preview.ColorValues type`  
- `public System.String prefix`  
- `public System.Single minValue`  
- `public System.Single maxValue`  
- `public System.Int32 precision`  
- `private UnityEngine.UI.Text label`  

## Constructors

- `public ColorLabel()`  

## Methods

- `private Awake() : System.Void`  
- `private ColorChanged(UnityEngine.Color color) : System.Void`  
- `private ConvertToDisplayString(System.Single value) : System.String`  
- `private HSVChanged(System.Single hue, System.Single sateration, System.Single value) : System.Void`  
- `private OnDestroy() : System.Void`  
- `private OnEnable() : System.Void`  
- `private UpdateValue() : System.Void`  

