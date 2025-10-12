# Game.UI.InGame.BatterySection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private System.Int32 <batteryCharge>k__BackingField`  
- `private System.Int32 <batteryCapacity>k__BackingField`  
- `private System.Int32 <flow>k__BackingField`  
- `private System.Single <remainingTime>k__BackingField`  

## Properties

- `protected System.String group { protected get }`  
- `private System.Int32 batteryCharge { private get; private set }`  
- `private System.Int32 batteryCapacity { private get; private set }`  
- `private System.Int32 flow { private get; private set }`  
- `private System.Single remainingTime { private get; private set }`  

## Constructors

- `public BatterySection()`  

## Methods

- `protected virtual OnProcess() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `protected virtual Reset() : System.Void`  
- `private Visible() : System.Boolean`  

