# Game.ArtPipeline.Preview.SVBoxSlider

**Assembly:** `Game.ArtPipeline`  
**Namespace:** `Game.ArtPipeline.Preview`  

**Type:** class public  

**Base:** `UnityEngine.MonoBehaviour`  

**Attributes:** `RequireComponent`, `ExecuteInEditMode`  

## Fields

- `public Game.ArtPipeline.Preview.ColorPicker picker`  
- `private Game.ArtPipeline.Preview.BoxSlider slider`  
- `private UnityEngine.UI.RawImage image`  
- `private UnityEngine.ComputeShader compute`  
- `private System.Int32 kernelID`  
- `private UnityEngine.RenderTexture renderTexture`  
- `private System.Int32 textureWidth`  
- `private System.Int32 textureHeight`  
- `private System.Single lastH`  
- `private System.Boolean listen`  
- `private System.Boolean overrideComputeShader`  
- `private System.Boolean supportsComputeShaders`  

## Properties

- `public UnityEngine.RectTransform rectTransform { get }`  

## Constructors

- `public SVBoxSlider()`  

## Methods

- `private Awake() : System.Void`  
- `private HSVChanged(System.Single h, System.Single s, System.Single v) : System.Void`  
- `private InitializeCompute() : System.Void`  
- `private OnDestroy() : System.Void`  
- `private OnDisable() : System.Void`  
- `private OnEnable() : System.Void`  
- `private RegenerateSVTexture() : System.Void`  
- `private SliderChanged(System.Single saturation, System.Single value) : System.Void`  

