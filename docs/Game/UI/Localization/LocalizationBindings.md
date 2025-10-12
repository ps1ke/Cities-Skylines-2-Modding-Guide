# Game.UI.Localization.LocalizationBindings

**Assembly:** `Game`  
**Namespace:** `Game.UI.Localization`  

**Type:** class public  

**Base:** `Colossal.UI.Binding.CompositeBinding`  
**Implements:** `Colossal.UI.Binding.IUpdateBinding`, `Colossal.UI.Binding.IBinding`, `Colossal.UI.Binding.IBindingRegistry`, `Colossal.UI.Binding.IBindingGroup`, `System.IDisposable`  

## Fields

- `private readonly Colossal.Localization.LocalizationManager m_LocalizationManager`  
- `private readonly Colossal.UI.Binding.GetterValueBinding<System.String[]> m_LocalesBinding`  
- `private readonly Colossal.UI.Binding.ValueBinding<System.Int32> m_DebugModeBinding`  
- `private readonly Colossal.UI.Binding.EventBinding m_ActiveDictionaryChangedBinding`  
- `private readonly Colossal.UI.Binding.RawMapBinding<System.String> m_IndexCountsBinding`  
- `private static const System.String kGroup`  

## Properties

- `public Game.UI.Localization.LocalizationBindings+DebugMode debugMode { get; set }`  

## Constructors

- `public LocalizationBindings(Colossal.Localization.LocalizationManager localizationManager)`  

## Methods

- `private <.ctor>b__9_0() : System.String[]`  
- `private BindIndexCounts(Colossal.UI.Binding.IJsonWriter binder, System.String key) : System.Void`  
- `public Dispose() : System.Void`  
- `private OnActiveDictionaryChanged() : System.Void`  
- `private OnSupportedLocalesChanged() : System.Void`  
- `private SelectLocale(System.String localeID) : System.Void`  

## Nested types

- `Game.UI.Localization.LocalizationBindings+DebugMode`  

