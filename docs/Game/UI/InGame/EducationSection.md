# Game.UI.InGame.EducationSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private System.Int32 <studentCount>k__BackingField`  
- `private System.Int32 <studentCapacity>k__BackingField`  
- `private System.Single <graduationTime>k__BackingField`  
- `private System.Single <failProbability>k__BackingField`  

## Properties

- `protected System.String group { protected get }`  
- `private System.Int32 studentCount { private get; private set }`  
- `private System.Int32 studentCapacity { private get; private set }`  
- `private System.Single graduationTime { private get; private set }`  
- `private System.Single failProbability { private get; private set }`  

## Constructors

- `public EducationSection()`  

## Methods

- `protected virtual OnProcess() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `protected virtual Reset() : System.Void`  
- `private Visible() : System.Boolean`  

