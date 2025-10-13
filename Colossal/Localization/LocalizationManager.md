# Colossal.Localization.LocalizationManager

**Assembly:** `Colossal.Localization`  
**Namespace:** `Colossal.Localization`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class LocalizationManager
{
    private Colossal.Localization.LocalizationDictionary <activeDictionary>k__BackingField;
    private System.String <fallbackLocaleId>k__BackingField;
    private System.Action onActiveDictionaryChanged;
    private System.Action onSupportedLocalesChanged;
    private System.Boolean m_SuppressEvents;
    private readonly System.Collections.Generic.Dictionary<System.String, Colossal.Localization.LocalizationManager+LocaleInfo> m_LocaleInfos;
    private readonly System.Collections.Generic.Dictionary<System.String, System.String> m_LocaleIdToLocalizedName;
    private readonly System.Collections.Generic.Dictionary<UnityEngine.SystemLanguage, System.String> m_SystemLanguageToLocaleId;
    private readonly Colossal.Localization.LocalizationDictionary m_FallbackDictionary;
    private readonly Colossal.Logging.ILog m_Log;
    public static const System.String kOsLanguage;

    public Colossal.Localization.LocalizationDictionary activeDictionary { get; private set; }
    public System.String fallbackLocaleId { get; private set; }
    public System.String activeLocaleId { get; }

    public LocalizationManager(System.String fallbackLocaleId, UnityEngine.SystemLanguage fallbackSystemLanguage, System.String fallbackLocalizedName);

    private System.Boolean <LoadAvailableLocales>b__27_0(Colossal.IO.AssetDatabase.LocaleAsset e);
    public System.Void AddLocale(Colossal.IO.AssetDatabase.LocaleAsset asset);
    public System.Void AddLocale(System.String localeId, UnityEngine.SystemLanguage systemLanguage, System.String localizedName);
    private System.Void AddMissingEntriesFromFallback(Colossal.Localization.LocalizationDictionary target);
    public System.Void AddSource(System.String localeId, Colossal.IDictionarySource source);
    private System.Void Clear();
    public System.String GetLocalizedName(System.String localeId);
    public System.String[] GetSupportedLocales();
    private System.String GetSystemLocaleId();
    public System.Void LoadAvailableLocales();
    private System.Void LoadLocale(Colossal.Localization.LocalizationManager+LocaleInfo info, Colossal.Localization.LocalizationDictionary target);
    private System.Void LoadLocaleSource(Colossal.IDictionarySource source, Colossal.Localization.LocalizationDictionary target);
    public UnityEngine.SystemLanguage LocaleIdToSystemLanguage(System.String localeId);
    private System.Void NotifyActiveDictionaryChanged();
    private System.Void NotifySupportedLocalesChanged();
    private System.Void PerformBulkOperation(System.Action operation);
    public System.Void ReloadActiveLocale();
    private System.Void ReloadAvailableLocales();
    public System.Void RemoveLocale(System.String localeId);
    public System.Void RemoveSource(System.String localeId, Colossal.IDictionarySource source);
    public System.Void SetActiveLocale(System.String localeId);
    public System.Boolean SupportsLocale(System.String localeId);
    private System.Void UpdateSource(Colossal.IO.AssetDatabase.AssetChangedEventArgs args);
}
```


## Fields

- `private Colossal.Localization.LocalizationDictionary <activeDictionary>k__BackingField`  

```csharp
private Colossal.Localization.LocalizationDictionary <activeDictionary>k__BackingField;
```

- `private System.String <fallbackLocaleId>k__BackingField`  

```csharp
private System.String <fallbackLocaleId>k__BackingField;
```

- `private System.Action onActiveDictionaryChanged`  

```csharp
private System.Action onActiveDictionaryChanged;
```

- `private System.Action onSupportedLocalesChanged`  

```csharp
private System.Action onSupportedLocalesChanged;
```

- `private System.Boolean m_SuppressEvents`  

```csharp
private System.Boolean m_SuppressEvents;
```

- `private readonly System.Collections.Generic.Dictionary<System.String, Colossal.Localization.LocalizationManager+LocaleInfo> m_LocaleInfos`  

```csharp
private readonly System.Collections.Generic.Dictionary<System.String, Colossal.Localization.LocalizationManager+LocaleInfo> m_LocaleInfos;
```

- `private readonly System.Collections.Generic.Dictionary<System.String, System.String> m_LocaleIdToLocalizedName`  

```csharp
private readonly System.Collections.Generic.Dictionary<System.String, System.String> m_LocaleIdToLocalizedName;
```

- `private readonly System.Collections.Generic.Dictionary<UnityEngine.SystemLanguage, System.String> m_SystemLanguageToLocaleId`  

```csharp
private readonly System.Collections.Generic.Dictionary<UnityEngine.SystemLanguage, System.String> m_SystemLanguageToLocaleId;
```

- `private readonly Colossal.Localization.LocalizationDictionary m_FallbackDictionary`  

```csharp
private readonly Colossal.Localization.LocalizationDictionary m_FallbackDictionary;
```

- `private readonly Colossal.Logging.ILog m_Log`  

```csharp
private readonly Colossal.Logging.ILog m_Log;
```

- `public static const System.String kOsLanguage`  

```csharp
public static const System.String kOsLanguage;
```


## Properties

- `public Colossal.Localization.LocalizationDictionary activeDictionary { get; private set }`  

```csharp
public Colossal.Localization.LocalizationDictionary activeDictionary { get; private set; }
```

- `public System.String fallbackLocaleId { get; private set }`  

```csharp
public System.String fallbackLocaleId { get; private set; }
```

- `public System.String activeLocaleId { get }`  

```csharp
public System.String activeLocaleId { get; }
```


## Constructors

- `public LocalizationManager(System.String fallbackLocaleId, UnityEngine.SystemLanguage fallbackSystemLanguage, System.String fallbackLocalizedName)`  

```csharp
public LocalizationManager(System.String fallbackLocaleId, UnityEngine.SystemLanguage fallbackSystemLanguage, System.String fallbackLocalizedName);
```


## Methods

- `private <LoadAvailableLocales>b__27_0(Colossal.IO.AssetDatabase.LocaleAsset e) : System.Boolean`  

```csharp
private System.Boolean <LoadAvailableLocales>b__27_0(Colossal.IO.AssetDatabase.LocaleAsset e);
```

- `public AddLocale(Colossal.IO.AssetDatabase.LocaleAsset asset) : System.Void`  

```csharp
public System.Void AddLocale(Colossal.IO.AssetDatabase.LocaleAsset asset);
```

- `public AddLocale(System.String localeId, UnityEngine.SystemLanguage systemLanguage, System.String localizedName) : System.Void`  

```csharp
public System.Void AddLocale(System.String localeId, UnityEngine.SystemLanguage systemLanguage, System.String localizedName);
```

- `private AddMissingEntriesFromFallback(Colossal.Localization.LocalizationDictionary target) : System.Void`  

```csharp
private System.Void AddMissingEntriesFromFallback(Colossal.Localization.LocalizationDictionary target);
```

- `public AddSource(System.String localeId, Colossal.IDictionarySource source) : System.Void`  

```csharp
public System.Void AddSource(System.String localeId, Colossal.IDictionarySource source);
```

- `private Clear() : System.Void`  

```csharp
private System.Void Clear();
```

- `public GetLocalizedName(System.String localeId) : System.String`  

```csharp
public System.String GetLocalizedName(System.String localeId);
```

- `public GetSupportedLocales() : System.String[]`  

```csharp
public System.String[] GetSupportedLocales();
```

- `private GetSystemLocaleId() : System.String`  

```csharp
private System.String GetSystemLocaleId();
```

- `public LoadAvailableLocales() : System.Void`  

```csharp
public System.Void LoadAvailableLocales();
```

- `private LoadLocale(Colossal.Localization.LocalizationManager+LocaleInfo info, Colossal.Localization.LocalizationDictionary target) : System.Void`  

```csharp
private System.Void LoadLocale(Colossal.Localization.LocalizationManager+LocaleInfo info, Colossal.Localization.LocalizationDictionary target);
```

- `private LoadLocaleSource(Colossal.IDictionarySource source, Colossal.Localization.LocalizationDictionary target) : System.Void`  

```csharp
private System.Void LoadLocaleSource(Colossal.IDictionarySource source, Colossal.Localization.LocalizationDictionary target);
```

- `public LocaleIdToSystemLanguage(System.String localeId) : UnityEngine.SystemLanguage`  

```csharp
public UnityEngine.SystemLanguage LocaleIdToSystemLanguage(System.String localeId);
```

- `private NotifyActiveDictionaryChanged() : System.Void`  

```csharp
private System.Void NotifyActiveDictionaryChanged();
```

- `private NotifySupportedLocalesChanged() : System.Void`  

```csharp
private System.Void NotifySupportedLocalesChanged();
```

- `private PerformBulkOperation(System.Action operation) : System.Void`  

```csharp
private System.Void PerformBulkOperation(System.Action operation);
```

- `public ReloadActiveLocale() : System.Void`  

```csharp
public System.Void ReloadActiveLocale();
```

- `private ReloadAvailableLocales() : System.Void`  

```csharp
private System.Void ReloadAvailableLocales();
```

- `public RemoveLocale(System.String localeId) : System.Void`  

```csharp
public System.Void RemoveLocale(System.String localeId);
```

- `public RemoveSource(System.String localeId, Colossal.IDictionarySource source) : System.Void`  

```csharp
public System.Void RemoveSource(System.String localeId, Colossal.IDictionarySource source);
```

- `public SetActiveLocale(System.String localeId) : System.Void`  

```csharp
public System.Void SetActiveLocale(System.String localeId);
```

- `public SupportsLocale(System.String localeId) : System.Boolean`  

```csharp
public System.Boolean SupportsLocale(System.String localeId);
```

- `private UpdateSource(Colossal.IO.AssetDatabase.AssetChangedEventArgs args) : System.Void`  

```csharp
private System.Void UpdateSource(Colossal.IO.AssetDatabase.AssetChangedEventArgs args);
```


## Events

- `onActiveDictionaryChanged` : `System.Action`  

```csharp
public event System.Action onActiveDictionaryChanged;
```

- `onSupportedLocalesChanged` : `System.Action`  

```csharp
public event System.Action onSupportedLocalesChanged;
```


## Nested types

- `Colossal.Localization.LocalizationManager+LocaleInfo`  
- `Colossal.Localization.LocalizationManager+<>c`  

