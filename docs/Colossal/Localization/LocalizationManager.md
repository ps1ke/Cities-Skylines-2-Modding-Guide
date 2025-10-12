# Colossal.Localization.LocalizationManager

**Assembly:** `Colossal.Localization`  
**Namespace:** `Colossal.Localization`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `private Colossal.Localization.LocalizationDictionary <activeDictionary>k__BackingField`  
- `private System.String <fallbackLocaleId>k__BackingField`  
- `private System.Action onActiveDictionaryChanged`  
- `private System.Action onSupportedLocalesChanged`  
- `private System.Boolean m_SuppressEvents`  
- `private readonly System.Collections.Generic.Dictionary<System.String, Colossal.Localization.LocalizationManager+LocaleInfo> m_LocaleInfos`  
- `private readonly System.Collections.Generic.Dictionary<System.String, System.String> m_LocaleIdToLocalizedName`  
- `private readonly System.Collections.Generic.Dictionary<UnityEngine.SystemLanguage, System.String> m_SystemLanguageToLocaleId`  
- `private readonly Colossal.Localization.LocalizationDictionary m_FallbackDictionary`  
- `private readonly Colossal.Logging.ILog m_Log`  
- `public static const System.String kOsLanguage`  

## Properties

- `public Colossal.Localization.LocalizationDictionary activeDictionary { get; private set }`  
- `public System.String fallbackLocaleId { get; private set }`  
- `public System.String activeLocaleId { get }`  

## Constructors

- `public LocalizationManager(System.String fallbackLocaleId, UnityEngine.SystemLanguage fallbackSystemLanguage, System.String fallbackLocalizedName)`  

## Methods

- `private <LoadAvailableLocales>b__27_0(Colossal.IO.AssetDatabase.LocaleAsset e) : System.Boolean`  
- `public AddLocale(Colossal.IO.AssetDatabase.LocaleAsset asset) : System.Void`  
- `public AddLocale(System.String localeId, UnityEngine.SystemLanguage systemLanguage, System.String localizedName) : System.Void`  
- `private AddMissingEntriesFromFallback(Colossal.Localization.LocalizationDictionary target) : System.Void`  
- `public AddSource(System.String localeId, Colossal.IDictionarySource source) : System.Void`  
- `private Clear() : System.Void`  
- `public GetLocalizedName(System.String localeId) : System.String`  
- `public GetSupportedLocales() : System.String[]`  
- `private GetSystemLocaleId() : System.String`  
- `public LoadAvailableLocales() : System.Void`  
- `private LoadLocale(Colossal.Localization.LocalizationManager+LocaleInfo info, Colossal.Localization.LocalizationDictionary target) : System.Void`  
- `private LoadLocaleSource(Colossal.IDictionarySource source, Colossal.Localization.LocalizationDictionary target) : System.Void`  
- `public LocaleIdToSystemLanguage(System.String localeId) : UnityEngine.SystemLanguage`  
- `private NotifyActiveDictionaryChanged() : System.Void`  
- `private NotifySupportedLocalesChanged() : System.Void`  
- `private PerformBulkOperation(System.Action operation) : System.Void`  
- `public ReloadActiveLocale() : System.Void`  
- `private ReloadAvailableLocales() : System.Void`  
- `public RemoveLocale(System.String localeId) : System.Void`  
- `public RemoveSource(System.String localeId, Colossal.IDictionarySource source) : System.Void`  
- `public SetActiveLocale(System.String localeId) : System.Void`  
- `public SupportsLocale(System.String localeId) : System.Boolean`  
- `private UpdateSource(Colossal.IO.AssetDatabase.AssetChangedEventArgs args) : System.Void`  

## Events

- `onActiveDictionaryChanged` : `System.Action`  
- `onSupportedLocalesChanged` : `System.Action`  

## Nested types

- `Colossal.Localization.LocalizationManager+LocaleInfo`  
- `Colossal.Localization.LocalizationManager+<>c`  

