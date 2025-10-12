# Game.UI.InGame.StatusSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Collections.NativeList<Game.UI.InGame.CitizenCondition> <conditions>k__BackingField`  
- `private Unity.Collections.NativeList<Game.UI.InGame.Notification> <notifications>k__BackingField`  
- `private Game.UI.InGame.CitizenHappiness <happiness>k__BackingField`  
- `private Game.UI.ImageSystem m_ImageSystem`  
- `private System.Boolean m_Dead`  

## Properties

- `protected System.String group { protected get }`  
- `private Unity.Collections.NativeList<Game.UI.InGame.CitizenCondition> conditions { private get; private set }`  
- `private Unity.Collections.NativeList<Game.UI.InGame.Notification> notifications { private get; private set }`  
- `private Game.UI.InGame.CitizenHappiness happiness { private get; private set }`  

## Constructors

- `public StatusSection()`  

## Methods

- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnProcess() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `protected virtual Reset() : System.Void`  
- `private Visible() : System.Boolean`  

