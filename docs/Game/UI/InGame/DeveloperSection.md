# Game.UI.InGame.DeveloperSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.InGame.ISubsectionProvider`  

## Fields

- `private System.Collections.Generic.List<Game.UI.InGame.ISubsectionSource> <subsections>k__BackingField`  

## Properties

- `protected System.String group { protected get }`  
- `public System.Collections.Generic.List<Game.UI.InGame.ISubsectionSource> subsections { get; private set }`  
- `protected System.Boolean displayForDestroyedObjects { protected get }`  
- `protected System.Boolean displayForOutsideConnections { protected get }`  
- `protected System.Boolean displayForUnderConstruction { protected get }`  
- `protected System.Boolean displayForUpgrades { protected get }`  

## Constructors

- `public DeveloperSection()`  

## Methods

- `public AddSubsection(Game.UI.InGame.ISubsectionSource subsection) : System.Void`  
- `private GetSubsectionCount() : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnProcess() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `protected virtual Reset() : System.Void`  
- `private Visible() : System.Boolean`  

