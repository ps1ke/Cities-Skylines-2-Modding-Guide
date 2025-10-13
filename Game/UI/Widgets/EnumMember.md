# Game.UI.Widgets.EnumMember

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public class EnumMember : Colossal.UI.Binding.IJsonWritable
{
    private System.UInt64 <value>k__BackingField;
    private Game.UI.Localization.LocalizedString <displayName>k__BackingField;
    private System.Boolean <disabled>k__BackingField;

    public System.UInt64 value { get; set; }
    public Game.UI.Localization.LocalizedString displayName { get; set; }
    public System.Boolean disabled { get; set; }

    public EnumMember(System.UInt64 value, Game.UI.Localization.LocalizedString displayName, System.Boolean disabled);

    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private System.UInt64 <value>k__BackingField`  

```csharp
private System.UInt64 <value>k__BackingField;
```

- `private Game.UI.Localization.LocalizedString <displayName>k__BackingField`  

```csharp
private Game.UI.Localization.LocalizedString <displayName>k__BackingField;
```

- `private System.Boolean <disabled>k__BackingField`  

```csharp
private System.Boolean <disabled>k__BackingField;
```


## Properties

- `public System.UInt64 value { get; set }`  

```csharp
public System.UInt64 value { get; set; }
```

- `public Game.UI.Localization.LocalizedString displayName { get; set }`  

```csharp
public Game.UI.Localization.LocalizedString displayName { get; set; }
```

- `public System.Boolean disabled { get; set }`  

```csharp
public System.Boolean disabled { get; set; }
```


## Constructors

- `public EnumMember(System.UInt64 value, Game.UI.Localization.LocalizedString displayName, System.Boolean disabled = False)`  

```csharp
public EnumMember(ulong value, LocalizedString displayName, bool disabled = false)
	{
		this.value = value;
		this.displayName = displayName;
		this.disabled = disabled;
	}
```


## Methods

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public void Write(IJsonWriter writer)
	{
		writer.TypeBegin(GetType().FullName);
		writer.PropertyName("value");
		ULongWriter.WriteAsArray(writer, value);
		writer.PropertyName("displayName");
		writer.Write(displayName);
		writer.PropertyName("disabled");
		writer.Write(disabled);
		writer.TypeEnd();
	}
```


