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
private void Add()
	{
		links.Add(kDefaultLink);
		SetPropertiesChanged();
	}
```

- `private Remove(System.Int32 index) : System.Void`  

```csharp
private void Remove(int index)
	{
		links.RemoveAt(index);
		SetPropertiesChanged();
	}
```

- `private SetValue(System.Int32 index, System.String type, System.String url) : System.Void`  

```csharp
private void SetValue(int index, string type, string url)
	{
		IModsUploadSupport.ExternalLinkData value = new IModsUploadSupport.ExternalLinkData
		{
			m_Type = type,
			m_URL = url
		};
		if (AssetUploadUtils.LockLinkType(value.m_URL, out var type2))
		{
			value.m_Type = type2;
		}
		links[index] = value;
		SetPropertiesChanged();
	}
```

- `private WriteExternalLink(Colossal.UI.Binding.IJsonWriter writer, Colossal.PSI.Common.IModsUploadSupport+ExternalLinkData link) : System.Void`  

```csharp
private void WriteExternalLink(IJsonWriter writer, IModsUploadSupport.ExternalLinkData link)
	{
		writer.TypeBegin("ExternalLinkData");
		writer.PropertyName("type");
		writer.Write(link.m_Type);
		writer.PropertyName("url");
		writer.Write(link.m_URL);
		writer.PropertyName("error");
		writer.Write(!AssetUploadUtils.ValidateExternalLink(link));
		writer.PropertyName("lockType");
		writer.Write(AssetUploadUtils.LockLinkType(link.m_URL, out var _));
		writer.TypeEnd();
	}
```

- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
protected override void WriteProperties(IJsonWriter writer)
	{
		base.WriteProperties(writer);
		writer.PropertyName("links");
		writer.ArrayBegin(links.Count);
		foreach (IModsUploadSupport.ExternalLinkData link in links)
		{
			WriteExternalLink(writer, link);
		}
		writer.ArrayEnd();
		writer.PropertyName("acceptedTypes");
		writer.Write(kAcceptedTypes);
		writer.PropertyName("maxLinks");
		writer.Write(maxLinks);
	}
```


## Nested types

- `Game.UI.Editor.ExternalLinkField+Bindings`  
- `Game.UI.Editor.ExternalLinkField+<>c`  

