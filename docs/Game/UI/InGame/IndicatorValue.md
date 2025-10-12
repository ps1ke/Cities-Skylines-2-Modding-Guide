# Game.UI.InGame.IndicatorValue

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Game.UI.InGame.IndicatorValue>`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `IsReadOnly`  

## Fields

- `private readonly System.Single <min>k__BackingField`  
- `private readonly System.Single <max>k__BackingField`  
- `private readonly System.Single <current>k__BackingField`  

## Properties

- `public System.Single min { get }`  
- `public System.Single max { get }`  
- `public System.Single current { get }`  

## Constructors

- `public IndicatorValue(System.Single min, System.Single max, System.Single current)`  

## Methods

- `public static Calculate(System.Single supply, System.Single demand, System.Single minRangeFactor = -1, System.Single maxRangeFactor = 1) : Game.UI.InGame.IndicatorValue`  
- `public Equals(Game.UI.InGame.IndicatorValue other) : System.Boolean`  
- `public virtual Equals(System.Object obj) : System.Boolean`  
- `public virtual GetHashCode() : System.Int32`  
- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

