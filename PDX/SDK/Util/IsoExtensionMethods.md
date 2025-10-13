# PDX.SDK.Util.IsoExtensionMethods

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Util`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class IsoExtensionMethods
{
    public static PDX.SDK.Contracts.Enums.Country GetCountry(System.String iso31661alpha2code);
    public static PDX.SDK.Contracts.Enums.Language GetLanguage(System.String IETFTag);
    public static System.String ToIetfTagLanguageString(System.Nullable<PDX.SDK.Contracts.Enums.Language> language);
    public static System.String ToIetfTagLanguageString(PDX.SDK.Contracts.Enums.Language language);
}
```


## Methods

- `public static GetCountry(System.String iso31661alpha2code) : PDX.SDK.Contracts.Enums.Country`  

```csharp
public static PDX.SDK.Contracts.Enums.Country GetCountry(System.String iso31661alpha2code);
```

- `public static GetLanguage(System.String IETFTag) : PDX.SDK.Contracts.Enums.Language`  

```csharp
public static PDX.SDK.Contracts.Enums.Language GetLanguage(System.String IETFTag);
```

- `public static ToIetfTagLanguageString(System.Nullable<PDX.SDK.Contracts.Enums.Language> language) : System.String`  

```csharp
public static System.String ToIetfTagLanguageString(System.Nullable<PDX.SDK.Contracts.Enums.Language> language);
```

- `public static ToIetfTagLanguageString(PDX.SDK.Contracts.Enums.Language language) : System.String`  

```csharp
public static System.String ToIetfTagLanguageString(PDX.SDK.Contracts.Enums.Language language);
```


