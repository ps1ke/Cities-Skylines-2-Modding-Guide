# Game.ArtPipeline.Preview.ColorPicker

**Assembly:** `Game.ArtPipeline`  
**Namespace:** `Game.ArtPipeline.Preview`  

**Type:** class public  

**Base:** `UnityEngine.MonoBehaviour`  

## Fields

- `private System.Single _hue`  
- `private System.Single _saturation`  
- `private System.Single _brightness`  
- `private System.Single _red`  
- `private System.Single _green`  
- `private System.Single _blue`  
- `private System.Single _alpha`  
- `public Game.ArtPipeline.Preview.ColorPickerSetup Setup`  
- `public Game.ArtPipeline.Preview.ColorChangedEvent onValueChanged`  
- `public Game.ArtPipeline.Preview.HSVChangedEvent onHSVChanged`  
- `private System.Collections.Generic.List<UnityEngine.UI.ToggleGroup> toggleGroups`  

## Properties

- `public UnityEngine.Color CurrentColor { get; set }`  
- `public System.Single H { get; set }`  
- `public System.Single S { get; set }`  
- `public System.Single V { get; set }`  
- `public System.Single R { get; set }`  
- `public System.Single G { get; set }`  
- `public System.Single B { get; set }`  
- `private System.Single A { private get; private set }`  

## Constructors

- `public ColorPicker()`  

## Methods

- `public AssignColor(Game.ArtPipeline.Preview.ColorValues type, System.Single value) : System.Void`  
- `public GetValue(Game.ArtPipeline.Preview.ColorValues type) : System.Single`  
- `private HandleHeaderSetting(Game.ArtPipeline.Preview.ColorPickerSetup+ColorHeaderShowing setupShowHeader) : System.Void`  
- `private HSVChanged() : System.Void`  
- `private LateUpdate() : System.Void`  
- `public RegisterToggle(UnityEngine.UI.ToggleGroup tg) : System.Void`  
- `private RGBChanged() : System.Void`  
- `private SendChangedEvent() : System.Void`  
- `private Start() : System.Void`  
- `public ToggleColorSliders() : System.Void`  
- `private UpdateColorToggleText() : System.Void`  

