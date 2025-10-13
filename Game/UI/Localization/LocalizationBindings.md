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
public LocalizationBindings(LocalizationManager localizationManager)
	{
		m_LocalizationManager = localizationManager;
		AddBinding(m_LocalesBinding = new GetterValueBinding<string[]>("l10n", "locales", () => m_LocalizationManager.GetSupportedLocales(), new ArrayWriter<string>(new StringWriter())));
		AddBinding(m_DebugModeBinding = new ValueBinding<int>("l10n", "debugMode", 0));
		AddBinding(m_ActiveDictionaryChangedBinding = new EventBinding("l10n", "activeDictionaryChanged"));
		AddBinding(m_IndexCountsBinding = new RawMapBinding<string>("l10n", "indexCounts", BindIndexCounts));
		AddBinding(new TriggerBinding<string>("l10n", "selectLocale", SelectLocale));
		m_LocalizationManager.onSupportedLocalesChanged += OnSupportedLocalesChanged;
		m_LocalizationManager.onActiveDictionaryChanged += OnActiveDictionaryChanged;
	}
```


## Methods

- `private <.ctor>b__9_0() : System.String[]`  

```csharp
private System.String[] <.ctor>b__9_0();
```

- `private BindIndexCounts(Colossal.UI.Binding.IJsonWriter binder, System.String key) : System.Void`  

```csharp
private void BindIndexCounts(IJsonWriter binder, string key)
	{
		binder.Write(m_LocalizationManager.activeDictionary.indexCounts.TryGetValue(key, out var value) ? value : 0);
	}
```

- `public Dispose() : System.Void`  

```csharp
public void Dispose()
	{
		m_LocalizationManager.onSupportedLocalesChanged -= OnSupportedLocalesChanged;
		m_LocalizationManager.onActiveDictionaryChanged -= OnActiveDictionaryChanged;
	}
```

- `private OnActiveDictionaryChanged() : System.Void`  

```csharp
private void OnActiveDictionaryChanged()
	{
		m_ActiveDictionaryChangedBinding.Trigger();
		m_IndexCountsBinding.UpdateAll();
	}
```

- `private OnSupportedLocalesChanged() : System.Void`  

```csharp
private void OnSupportedLocalesChanged()
	{
		m_LocalesBinding.Update();
	}
```

- `private SelectLocale(System.String localeID) : System.Void`  

```csharp
private void SelectLocale(string localeID)
	{
		m_LocalizationManager?.SetActiveLocale(localeID);
		InterfaceSettings interfaceSettings = SharedSettings.instance?.userInterface;
		if (interfaceSettings != null)
		{
			interfaceSettings.locale = localeID;
		}
	}
```


## Nested types

- `Game.UI.Localization.LocalizationBindings+DebugMode`  

