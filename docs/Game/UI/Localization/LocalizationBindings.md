# Game.UI.Localization.LocalizationBindings

**Assembly:** `Game`  
**Namespace:** `Game.UI.Localization`  

**Type:** class public  

**Base:** `Colossal.UI.Binding.CompositeBinding`  
**Implements:** `Colossal.UI.Binding.IUpdateBinding`, `Colossal.UI.Binding.IBinding`, `Colossal.UI.Binding.IBindingRegistry`, `Colossal.UI.Binding.IBindingGroup`, `System.IDisposable`  

## Code

```csharp
public class LocalizationBindings : Colossal.UI.Binding.CompositeBinding, Colossal.UI.Binding.IUpdateBinding, Colossal.UI.Binding.IBinding, Colossal.UI.Binding.IBindingRegistry, Colossal.UI.Binding.IBindingGroup, System.IDisposable
{
    private readonly Colossal.Localization.LocalizationManager m_LocalizationManager;
    private readonly Colossal.UI.Binding.GetterValueBinding<System.String[]> m_LocalesBinding;
    private readonly Colossal.UI.Binding.ValueBinding<System.Int32> m_DebugModeBinding;
    private readonly Colossal.UI.Binding.EventBinding m_ActiveDictionaryChangedBinding;
    private readonly Colossal.UI.Binding.RawMapBinding<System.String> m_IndexCountsBinding;
    private static const System.String kGroup;

    public Game.UI.Localization.LocalizationBindings+DebugMode debugMode { get; set; }

    public LocalizationBindings(Colossal.Localization.LocalizationManager localizationManager);

    private System.String[] <.ctor>b__9_0();
    private System.Void BindIndexCounts(Colossal.UI.Binding.IJsonWriter binder, System.String key);
    public System.Void Dispose();
    private System.Void OnActiveDictionaryChanged();
    private System.Void OnSupportedLocalesChanged();
    private System.Void SelectLocale(System.String localeID);
}
```


## Fields

- `private readonly Colossal.Localization.LocalizationManager m_LocalizationManager`  

```csharp
private readonly Colossal.Localization.LocalizationManager m_LocalizationManager;
```

- `private readonly Colossal.UI.Binding.GetterValueBinding<System.String[]> m_LocalesBinding`  

```csharp
private readonly Colossal.UI.Binding.GetterValueBinding<System.String[]> m_LocalesBinding;
```

- `private readonly Colossal.UI.Binding.ValueBinding<System.Int32> m_DebugModeBinding`  

```csharp
private readonly Colossal.UI.Binding.ValueBinding<System.Int32> m_DebugModeBinding;
```

- `private readonly Colossal.UI.Binding.EventBinding m_ActiveDictionaryChangedBinding`  

```csharp
private readonly Colossal.UI.Binding.EventBinding m_ActiveDictionaryChangedBinding;
```

- `private readonly Colossal.UI.Binding.RawMapBinding<System.String> m_IndexCountsBinding`  

```csharp
private readonly Colossal.UI.Binding.RawMapBinding<System.String> m_IndexCountsBinding;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Properties

- `public Game.UI.Localization.LocalizationBindings+DebugMode debugMode { get; set }`  

```csharp
public Game.UI.Localization.LocalizationBindings+DebugMode debugMode { get; set; }
```


## Constructors

- `public LocalizationBindings(Colossal.Localization.LocalizationManager localizationManager)`  

```csharp
public LocalizationBindings(Colossal.Localization.LocalizationManager localizationManager);
```


## Methods

- `private <.ctor>b__9_0() : System.String[]`  

```csharp
private System.String[] <.ctor>b__9_0();
```

- `private BindIndexCounts(Colossal.UI.Binding.IJsonWriter binder, System.String key) : System.Void`  

```csharp
private System.Void BindIndexCounts(Colossal.UI.Binding.IJsonWriter binder, System.String key);
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `private OnActiveDictionaryChanged() : System.Void`  

```csharp
private System.Void OnActiveDictionaryChanged();
```

- `private OnSupportedLocalesChanged() : System.Void`  

```csharp
private System.Void OnSupportedLocalesChanged();
```

- `private SelectLocale(System.String localeID) : System.Void`  

```csharp
private System.Void SelectLocale(System.String localeID);
```


## Nested types

- `Game.UI.Localization.LocalizationBindings+DebugMode`  

