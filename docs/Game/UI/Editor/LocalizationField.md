# Game.UI.Editor.LocalizationField

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Widgets.Widget`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`  

## Fields

- `private System.Collections.Generic.List<Game.UI.Editor.LocalizationField+LocalizationFieldEntry> m_Localization`  
- `private Game.UI.Localization.LocalizedString <placeholder>k__BackingField`  

## Properties

- `public System.Collections.Generic.IReadOnlyList<Game.UI.Editor.LocalizationField+LocalizationFieldEntry> localization { get }`  
- `public Game.UI.Localization.LocalizedString placeholder { get; set }`  

## Constructors

- `public LocalizationField(Game.UI.Localization.LocalizedString placeholder)`  

## Methods

- `public Add(Colossal.IO.AssetDatabase.LocaleAsset asset, System.String localeFormat) : System.Void`  
- `public Add(Game.UI.Editor.LocalizationField+LocalizationFieldEntry entry) : System.Void`  
- `public AddLanguage() : System.Void`  
- `public BuildLocaleData(System.String format, System.Collections.Generic.Dictionary<System.String, Colossal.IO.AssetDatabase.LocaleData> localeDatas, System.String fallback = null) : System.Void`  
- `public Clear() : System.Void`  
- `public Initialize() : System.Void`  
- `public Initialize(System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.LocaleAsset> assets, System.String localeFormat) : System.Void`  
- `public Initialize(System.Collections.Generic.IEnumerable<Game.UI.Editor.LocalizationField+LocalizationFieldEntry> entries) : System.Void`  
- `private InitializeMandatory() : System.Void`  
- `public static IsMandatory(System.String localeId) : System.Boolean`  
- `public IsValid() : System.Boolean`  
- `private IsValid(Game.UI.Editor.LocalizationField+LocalizationFieldEntry entry) : System.Boolean`  
- `public RemoveLanguage(System.Int32 index) : System.Void`  
- `public SetEntry(System.Int32 index, System.String localeId, System.String text) : System.Void`  
- `private TryGetUnusedLanguage(System.String& localeID) : System.Boolean`  
- `public ValidEntries() : System.Collections.Generic.IEnumerable<Game.UI.Editor.LocalizationField+LocalizationFieldEntry>`  
- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

## Nested types

- `Game.UI.Editor.LocalizationField+LocalizationFieldEntry`  
- `Game.UI.Editor.LocalizationField+Bindings`  
- `Game.UI.Editor.LocalizationField+<>c`  
- `Game.UI.Editor.LocalizationField+<>c__DisplayClass14_0`  
- `Game.UI.Editor.LocalizationField+<>c__DisplayClass15_0`  
- `Game.UI.Editor.LocalizationField+<>c__DisplayClass22_0`  
- `Game.UI.Editor.LocalizationField+<ValidEntries>d__20`  

