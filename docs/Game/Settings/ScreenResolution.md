# Game.Settings.ScreenResolution

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Game.Settings.ScreenResolution>`, `System.IComparable<Game.Settings.ScreenResolution>`, `Colossal.UI.Binding.IJsonReadable`, `Colossal.UI.Binding.IJsonWritable`  

## Fields

- `public System.Int32 width`  
- `public System.Int32 height`  
- `public UnityEngine.RefreshRate refreshRate`  

## Properties

- `public System.Double refreshRateDelta { get }`  
- `public System.Boolean isValid { get }`  

## Constructors

- `public ScreenResolution(UnityEngine.Resolution resolution)`  

## Methods

- `public CompareTo(Game.Settings.ScreenResolution other) : System.Int32`  
- `public Equals(Game.Settings.ScreenResolution other) : System.Boolean`  
- `public virtual Equals(System.Object obj) : System.Boolean`  
- `public virtual GetHashCode() : System.Int32`  
- `public Read(Colossal.UI.Binding.IJsonReader reader) : System.Void`  
- `public Sanitize() : System.Void`  
- `private static SupportValueTypesForAOT() : System.Void`  
- `public virtual ToString() : System.String`  
- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

