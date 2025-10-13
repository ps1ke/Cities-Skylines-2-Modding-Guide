# Game.UI.Editor.LocalizationField+LocalizationFieldEntry

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public sealed struct LocalizationFieldEntry : Colossal.UI.Binding.IJsonWritable
{
    private System.String <localeId>k__BackingField;
    private System.String <text>k__BackingField;

    public System.String localeId { get; set; }
    public System.String text { get; set; }

    public LocalizationFieldEntry(System.String localeId, System.String text);

    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private System.String <localeId>k__BackingField`  

```csharp
private System.String <localeId>k__BackingField;
```

- `private System.String <text>k__BackingField`  

```csharp
private System.String <text>k__BackingField;
```


## Properties

- `public System.String localeId { get; set }`  

```csharp
public System.String localeId { get; set; }
```

- `public System.String text { get; set }`  

```csharp
public System.String text { get; set; }
```


## Constructors

- `public LocalizationFieldEntry(System.String localeId, System.String text)`  

```csharp
public LocalizationFieldEntry(System.String localeId, System.String text);
```


## Methods

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
```


