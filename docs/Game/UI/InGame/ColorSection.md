# Game.UI.InGame.ColorSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private UnityEngine.Color32 <color>k__BackingField`  
- `private Unity.Entities.EntityArchetype m_ColorUpdateArchetype`  

## Properties

- `protected System.String group { protected get }`  
- `private UnityEngine.Color32 color { private get; private set }`  

## Constructors

- `public ColorSection()`  

## Methods

- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnProcess() : System.Void`  
- `private OnSetColor(UnityEngine.Color uiColor) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `protected virtual Reset() : System.Void`  
- `private Visible() : System.Boolean`  

