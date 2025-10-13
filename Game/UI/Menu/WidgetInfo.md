# Game.UI.Menu.OptionsUISystem+WidgetInfo

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public sealed struct WidgetInfo : Colossal.UI.Binding.IJsonWritable
{
    private System.Int32 <id>k__BackingField;
    private Game.UI.Localization.LocalizedString <displayName>k__BackingField;
    private System.Boolean <isVisible>k__BackingField;
    private System.Boolean <isAdvanced>k__BackingField;
    private System.Boolean <searchHidden>k__BackingField;

    public System.Int32 id { get; set; }
    public Game.UI.Localization.LocalizedString displayName { get; set; }
    public System.Boolean isVisible { get; set; }
    public System.Boolean isAdvanced { get; set; }
    public System.Boolean searchHidden { get; set; }

    public static System.Int32 GetId(System.Int32 page, System.Int32 section, System.Int32 widget);
    public static System.Void GetIndices(System.Int32 id, System.Int32& page, System.Int32& section, System.Int32& widget);
    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private System.Int32 <id>k__BackingField`  

```csharp
private System.Int32 <id>k__BackingField;
```

- `private Game.UI.Localization.LocalizedString <displayName>k__BackingField`  

```csharp
private Game.UI.Localization.LocalizedString <displayName>k__BackingField;
```

- `private System.Boolean <isVisible>k__BackingField`  

```csharp
private System.Boolean <isVisible>k__BackingField;
```

- `private System.Boolean <isAdvanced>k__BackingField`  

```csharp
private System.Boolean <isAdvanced>k__BackingField;
```

- `private System.Boolean <searchHidden>k__BackingField`  

```csharp
private System.Boolean <searchHidden>k__BackingField;
```


## Properties

- `public System.Int32 id { get; set }`  

```csharp
public System.Int32 id { get; set; }
```

- `public Game.UI.Localization.LocalizedString displayName { get; set }`  

```csharp
public Game.UI.Localization.LocalizedString displayName { get; set; }
```

- `public System.Boolean isVisible { get; set }`  

```csharp
public System.Boolean isVisible { get; set; }
```

- `public System.Boolean isAdvanced { get; set }`  

```csharp
public System.Boolean isAdvanced { get; set; }
```

- `public System.Boolean searchHidden { get; set }`  

```csharp
public System.Boolean searchHidden { get; set; }
```


## Methods

- `public static GetId(System.Int32 page, System.Int32 section, System.Int32 widget) : System.Int32`  

```csharp
public static System.Int32 GetId(System.Int32 page, System.Int32 section, System.Int32 widget);
```

- `public static GetIndices(System.Int32 id, System.Int32& page, System.Int32& section, System.Int32& widget) : System.Void`  

```csharp
public static System.Void GetIndices(System.Int32 id, System.Int32& page, System.Int32& section, System.Int32& widget);
```

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
```


