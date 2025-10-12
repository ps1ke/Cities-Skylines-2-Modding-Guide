# Game.UI.InGame.UIPolicySlider

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Game.UI.InGame.UIPolicySlider>`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `IsReadOnly`  

## Fields

- `private readonly System.Single m_Value`  
- `private readonly System.Single m_Default`  
- `private readonly System.Single m_Step`  
- `private readonly Game.Prefabs.PolicySliderUnit m_Unit`  
- `private readonly Colossal.Mathematics.Bounds1 <range>k__BackingField`  

## Properties

- `public Colossal.Mathematics.Bounds1 range { get }`  

## Constructors

- `public UIPolicySlider(System.Single value, Game.Prefabs.PolicySliderData sliderData)`  
- `public UIPolicySlider(Game.Prefabs.PolicySliderData sliderData)`  

## Methods

- `public virtual Equals(System.Object obj) : System.Boolean`  
- `public Equals(Game.UI.InGame.UIPolicySlider other) : System.Boolean`  
- `public virtual GetHashCode() : System.Int32`  
- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

