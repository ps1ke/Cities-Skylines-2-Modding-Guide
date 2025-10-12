# Game.UI.InGame.RoadSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private System.Single <length>k__BackingField`  
- `private System.Single <bestCondition>k__BackingField`  
- `private System.Single <worstCondition>k__BackingField`  
- `private System.Single <condition>k__BackingField`  
- `private System.Single <upkeep>k__BackingField`  
- `private System.Single[] m_Volume`  
- `private System.Single[] m_Flow`  

## Properties

- `protected System.String group { protected get }`  
- `private System.Single length { private get; private set }`  
- `private System.Single bestCondition { private get; private set }`  
- `private System.Single worstCondition { private get; private set }`  
- `private System.Single condition { private get; private set }`  
- `private System.Single upkeep { private get; private set }`  

## Constructors

- `public RoadSection()`  

## Methods

- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnProcess() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `protected virtual Reset() : System.Void`  

