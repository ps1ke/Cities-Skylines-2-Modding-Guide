# Game.UI.InGame.SewageSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private System.Single <capacity>k__BackingField`  
- `private System.Single <lastProcessed>k__BackingField`  
- `private System.Single <lastPurified>k__BackingField`  
- `private System.Single <purification>k__BackingField`  

## Properties

- `protected System.String group { protected get }`  
- `private System.Single capacity { private get; private set }`  
- `private System.Single lastProcessed { private get; private set }`  
- `private System.Single lastPurified { private get; private set }`  
- `private System.Single purification { private get; private set }`  

## Constructors

- `public SewageSection()`  

## Methods

- `private HasWaterSource() : System.Boolean`  
- `protected virtual OnProcess() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `protected virtual Reset() : System.Void`  
- `private Visible() : System.Boolean`  

