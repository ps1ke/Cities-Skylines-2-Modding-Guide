# Colossal.PSI.PdxSdk.PdxSdkExtensions

**Assembly:** `Colossal.PSI.PdxSdk`  
**Namespace:** `Colossal.PSI.PdxSdk`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class PdxSdkExtensions
{
    public static System.Boolean GetUserIdType(System.String& userType);
    public static PDX.SDK.Contracts.Enums.BackendEnvironment ToParadoxBackendEnvironment(Colossal.PSI.PdxSdk.ProductEnvironment environment);
    public static PDX.SDK.Contracts.Enums.Ecosystem ToPdxEcoSystem(PDX.SDK.Contracts.Enums.Platform platform);
    public static PDX.SDK.Contracts.Enums.Language ToPdxLanguage(System.String languageString);
    public static PDX.SDK.Contracts.Enums.Platform ToPdxPlatform(UnityEngine.RuntimePlatform platform);
}
```


## Methods

- `public static GetUserIdType(System.String& userType) : System.Boolean`  

```csharp
public static System.Boolean GetUserIdType(System.String& userType);
```

- `public static ToParadoxBackendEnvironment(Colossal.PSI.PdxSdk.ProductEnvironment environment) : PDX.SDK.Contracts.Enums.BackendEnvironment`  

```csharp
public static PDX.SDK.Contracts.Enums.BackendEnvironment ToParadoxBackendEnvironment(Colossal.PSI.PdxSdk.ProductEnvironment environment);
```

- `public static ToPdxEcoSystem(PDX.SDK.Contracts.Enums.Platform platform) : PDX.SDK.Contracts.Enums.Ecosystem`  

```csharp
public static PDX.SDK.Contracts.Enums.Ecosystem ToPdxEcoSystem(PDX.SDK.Contracts.Enums.Platform platform);
```

- `public static ToPdxLanguage(System.String languageString) : PDX.SDK.Contracts.Enums.Language`  

```csharp
public static PDX.SDK.Contracts.Enums.Language ToPdxLanguage(System.String languageString);
```

- `public static ToPdxPlatform(UnityEngine.RuntimePlatform platform) : PDX.SDK.Contracts.Enums.Platform`  

```csharp
public static PDX.SDK.Contracts.Enums.Platform ToPdxPlatform(UnityEngine.RuntimePlatform platform);
```


