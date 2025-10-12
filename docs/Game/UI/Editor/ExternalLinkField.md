# Game.UI.Editor.ExternalLinkField

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Widgets.Widget`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`  

## Fields

- `private System.Collections.Generic.List<Colossal.PSI.Common.IModsUploadSupport+ExternalLinkData> <links>k__BackingField`  
- `private System.Int32 <maxLinks>k__BackingField`  
- `private static readonly Colossal.PSI.Common.IModsUploadSupport+ExternalLinkData kDefaultLink`  
- `private static readonly System.String[] kAcceptedTypes`  

## Properties

- `public System.Collections.Generic.List<Colossal.PSI.Common.IModsUploadSupport+ExternalLinkData> links { get; set }`  
- `public System.Int32 maxLinks { get; set }`  

## Constructors

- `public ExternalLinkField()`  

## Methods

- `private Add() : System.Void`  
- `private Remove(System.Int32 index) : System.Void`  
- `private SetValue(System.Int32 index, System.String type, System.String url) : System.Void`  
- `private WriteExternalLink(Colossal.UI.Binding.IJsonWriter writer, Colossal.PSI.Common.IModsUploadSupport+ExternalLinkData link) : System.Void`  
- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

## Nested types

- `Game.UI.Editor.ExternalLinkField+Bindings`  
- `Game.UI.Editor.ExternalLinkField+<>c`  

