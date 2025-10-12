# Game.UI.InGame.CompanySection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.Entity companyEntity`  
- `private Game.Economy.Resource <input1>k__BackingField`  
- `private Game.Economy.Resource <input2>k__BackingField`  
- `private Game.Economy.Resource <output>k__BackingField`  
- `private Game.Economy.Resource <sells>k__BackingField`  
- `private Game.Economy.Resource <stores>k__BackingField`  
- `private Unity.Mathematics.int2 <customers>k__BackingField`  
- `private System.Single <price>k__BackingField`  
- `private System.Boolean <isRentable>k__BackingField`  

## Properties

- `protected System.String group { protected get }`  
- `private Game.Economy.Resource input1 { private get; private set }`  
- `private Game.Economy.Resource input2 { private get; private set }`  
- `private Game.Economy.Resource output { private get; private set }`  
- `private Game.Economy.Resource sells { private get; private set }`  
- `private Game.Economy.Resource stores { private get; private set }`  
- `private Unity.Mathematics.int2 customers { private get; private set }`  
- `private System.Single price { private get; private set }`  
- `private System.Boolean isRentable { private get; private set }`  

## Constructors

- `public CompanySection()`  

## Methods

- `protected virtual OnProcess() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `protected virtual Reset() : System.Void`  
- `private Visible() : System.Boolean`  

## Nested types

- `Game.UI.InGame.CompanySection+ExtractedKey`  

