# Game.UI.Editor.LocalizationField

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Widgets.Widget`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`  

## Code

```csharp
public class LocalizationField : Game.UI.Widgets.Widget, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback
{
    private System.Collections.Generic.List<Game.UI.Editor.LocalizationField+LocalizationFieldEntry> m_Localization;
    private Game.UI.Localization.LocalizedString <placeholder>k__BackingField;

    public System.Collections.Generic.IReadOnlyList<Game.UI.Editor.LocalizationField+LocalizationFieldEntry> localization { get; }
    public Game.UI.Localization.LocalizedString placeholder { get; set; }

    public LocalizationField(Game.UI.Localization.LocalizedString placeholder);

    public System.Void Add(Colossal.IO.AssetDatabase.LocaleAsset asset, System.String localeFormat);
    public System.Void Add(Game.UI.Editor.LocalizationField+LocalizationFieldEntry entry);
    public System.Void AddLanguage();
    public System.Void BuildLocaleData(System.String format, System.Collections.Generic.Dictionary<System.String, Colossal.IO.AssetDatabase.LocaleData> localeDatas, System.String fallback);
    public System.Void Clear();
    public System.Void Initialize();
    public System.Void Initialize(System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.LocaleAsset> assets, System.String localeFormat);
    public System.Void Initialize(System.Collections.Generic.IEnumerable<Game.UI.Editor.LocalizationField+LocalizationFieldEntry> entries);
    private System.Void InitializeMandatory();
    public static System.Boolean IsMandatory(System.String localeId);
    public System.Boolean IsValid();
    private System.Boolean IsValid(Game.UI.Editor.LocalizationField+LocalizationFieldEntry entry);
    public System.Void RemoveLanguage(System.Int32 index);
    public System.Void SetEntry(System.Int32 index, System.String localeId, System.String text);
    private System.Boolean TryGetUnusedLanguage(System.String& localeID);
    public System.Collections.Generic.IEnumerable<Game.UI.Editor.LocalizationField+LocalizationFieldEntry> ValidEntries();
    protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private System.Collections.Generic.List<Game.UI.Editor.LocalizationField+LocalizationFieldEntry> m_Localization`  

```csharp
private System.Collections.Generic.List<Game.UI.Editor.LocalizationField+LocalizationFieldEntry> m_Localization;
```

- `private Game.UI.Localization.LocalizedString <placeholder>k__BackingField`  

```csharp
private Game.UI.Localization.LocalizedString <placeholder>k__BackingField;
```


## Properties

- `public System.Collections.Generic.IReadOnlyList<Game.UI.Editor.LocalizationField+LocalizationFieldEntry> localization { get }`  

```csharp
public System.Collections.Generic.IReadOnlyList<Game.UI.Editor.LocalizationField+LocalizationFieldEntry> localization { get; }
```

- `public Game.UI.Localization.LocalizedString placeholder { get; set }`  

```csharp
public Game.UI.Localization.LocalizedString placeholder { get; set; }
```


## Constructors

- `public LocalizationField(Game.UI.Localization.LocalizedString placeholder)`  

```csharp
public LocalizationField(Game.UI.Localization.LocalizedString placeholder);
```


## Methods

- `public Add(Colossal.IO.AssetDatabase.LocaleAsset asset, System.String localeFormat) : System.Void`  

```csharp
public System.Void Add(Colossal.IO.AssetDatabase.LocaleAsset asset, System.String localeFormat);
```

- `public Add(Game.UI.Editor.LocalizationField+LocalizationFieldEntry entry) : System.Void`  

```csharp
public System.Void Add(Game.UI.Editor.LocalizationField+LocalizationFieldEntry entry);
```

- `public AddLanguage() : System.Void`  

```csharp
public System.Void AddLanguage();
```

- `public BuildLocaleData(System.String format, System.Collections.Generic.Dictionary<System.String, Colossal.IO.AssetDatabase.LocaleData> localeDatas, System.String fallback = null) : System.Void`  

```csharp
public System.Void BuildLocaleData(System.String format, System.Collections.Generic.Dictionary<System.String, Colossal.IO.AssetDatabase.LocaleData> localeDatas, System.String fallback);
```

- `public Clear() : System.Void`  

```csharp
public System.Void Clear();
```

- `public Initialize() : System.Void`  

```csharp
public System.Void Initialize();
```

- `public Initialize(System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.LocaleAsset> assets, System.String localeFormat) : System.Void`  

```csharp
public System.Void Initialize(System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.LocaleAsset> assets, System.String localeFormat);
```

- `public Initialize(System.Collections.Generic.IEnumerable<Game.UI.Editor.LocalizationField+LocalizationFieldEntry> entries) : System.Void`  

```csharp
public System.Void Initialize(System.Collections.Generic.IEnumerable<Game.UI.Editor.LocalizationField+LocalizationFieldEntry> entries);
```

- `private InitializeMandatory() : System.Void`  

```csharp
private System.Void InitializeMandatory();
```

- `public static IsMandatory(System.String localeId) : System.Boolean`  

```csharp
public static System.Boolean IsMandatory(System.String localeId);
```

- `public IsValid() : System.Boolean`  

```csharp
public System.Boolean IsValid();
```

- `private IsValid(Game.UI.Editor.LocalizationField+LocalizationFieldEntry entry) : System.Boolean`  

```csharp
private System.Boolean IsValid(Game.UI.Editor.LocalizationField+LocalizationFieldEntry entry);
```

- `public RemoveLanguage(System.Int32 index) : System.Void`  

```csharp
public System.Void RemoveLanguage(System.Int32 index);
```

- `public SetEntry(System.Int32 index, System.String localeId, System.String text) : System.Void`  

```csharp
public System.Void SetEntry(System.Int32 index, System.String localeId, System.String text);
```

- `private TryGetUnusedLanguage(System.String& localeID) : System.Boolean`  

```csharp
private System.Boolean TryGetUnusedLanguage(System.String& localeID);
```

- `public ValidEntries() : System.Collections.Generic.IEnumerable<Game.UI.Editor.LocalizationField+LocalizationFieldEntry>`  

```csharp
public System.Collections.Generic.IEnumerable<Game.UI.Editor.LocalizationField+LocalizationFieldEntry> ValidEntries();
```

- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
```


## Nested types

- `Game.UI.Editor.LocalizationField+LocalizationFieldEntry`  
- `Game.UI.Editor.LocalizationField+Bindings`  
- `Game.UI.Editor.LocalizationField+<>c`  
- `Game.UI.Editor.LocalizationField+<>c__DisplayClass14_0`  
- `Game.UI.Editor.LocalizationField+<>c__DisplayClass15_0`  
- `Game.UI.Editor.LocalizationField+<>c__DisplayClass22_0`  
- `Game.UI.Editor.LocalizationField+<ValidEntries>d__20`  

