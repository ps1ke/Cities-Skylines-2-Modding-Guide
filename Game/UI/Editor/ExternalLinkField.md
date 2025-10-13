# Game.UI.Editor.ExternalLinkField

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Widgets.Widget`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`  

## Code

```csharp
public class ExternalLinkField : Game.UI.Widgets.Widget, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback
{
    private System.Collections.Generic.List<Colossal.PSI.Common.IModsUploadSupport+ExternalLinkData> <links>k__BackingField;
    private System.Int32 <maxLinks>k__BackingField;
    private static readonly Colossal.PSI.Common.IModsUploadSupport+ExternalLinkData kDefaultLink;
    private static readonly System.String[] kAcceptedTypes;

    public System.Collections.Generic.List<Colossal.PSI.Common.IModsUploadSupport+ExternalLinkData> links { get; set; }
    public System.Int32 maxLinks { get; set; }

    public ExternalLinkField();

    private System.Void Add();
    private System.Void Remove(System.Int32 index);
    private System.Void SetValue(System.Int32 index, System.String type, System.String url);
    private System.Void WriteExternalLink(Colossal.UI.Binding.IJsonWriter writer, Colossal.PSI.Common.IModsUploadSupport+ExternalLinkData link);
    protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private System.Collections.Generic.List<Colossal.PSI.Common.IModsUploadSupport+ExternalLinkData> <links>k__BackingField`  

```csharp
private System.Collections.Generic.List<Colossal.PSI.Common.IModsUploadSupport+ExternalLinkData> <links>k__BackingField;
```

- `private System.Int32 <maxLinks>k__BackingField`  

```csharp
private System.Int32 <maxLinks>k__BackingField;
```

- `private static readonly Colossal.PSI.Common.IModsUploadSupport+ExternalLinkData kDefaultLink`  

```csharp
private static readonly Colossal.PSI.Common.IModsUploadSupport+ExternalLinkData kDefaultLink;
```

- `private static readonly System.String[] kAcceptedTypes`  

```csharp
private static readonly System.String[] kAcceptedTypes;
```


## Properties

- `public System.Collections.Generic.List<Colossal.PSI.Common.IModsUploadSupport+ExternalLinkData> links { get; set }`  

```csharp
public System.Collections.Generic.List<Colossal.PSI.Common.IModsUploadSupport+ExternalLinkData> links { get; set; }
```

- `public System.Int32 maxLinks { get; set }`  

```csharp
public System.Int32 maxLinks { get; set; }
```


## Constructors

- `public ExternalLinkField()`  

```csharp
public ExternalLinkField();
```


## Methods

- `private Add() : System.Void`  

```csharp
private System.Void Add();
```

- `private Remove(System.Int32 index) : System.Void`  

```csharp
private System.Void Remove(System.Int32 index);
```

- `private SetValue(System.Int32 index, System.String type, System.String url) : System.Void`  

```csharp
private System.Void SetValue(System.Int32 index, System.String type, System.String url);
```

- `private WriteExternalLink(Colossal.UI.Binding.IJsonWriter writer, Colossal.PSI.Common.IModsUploadSupport+ExternalLinkData link) : System.Void`  

```csharp
private System.Void WriteExternalLink(Colossal.UI.Binding.IJsonWriter writer, Colossal.PSI.Common.IModsUploadSupport+ExternalLinkData link);
```

- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
```


## Nested types

- `Game.UI.Editor.ExternalLinkField+Bindings`  
- `Game.UI.Editor.ExternalLinkField+<>c`  

