# Colossal.PSI.Common.DlcHelper

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class DlcHelper
{
    private static Colossal.Logging.ILog log;
    private static System.Collections.Generic.Dictionary<Colossal.PSI.Common.DlcId, Colossal.PSI.Common.DlcAttribute> m_CachedAttributes;
    private static Colossal.Collections.Generic.BiDictionary<Colossal.PSI.Common.DlcId, System.String> m_CachedDlcNames;
    public static const System.String kEntitlementExtension;

    public static System.Collections.Generic.Dictionary<Colossal.PSI.Common.DlcId, Colossal.PSI.Common.DlcAttribute> GetDlcAttributes();
    private static System.Boolean GetDlcDescriptionType(System.Type& dlcDescriptionType);
    public static Colossal.Collections.Generic.BiDictionary<Colossal.PSI.Common.DlcId, System.String> GetDlcNames();
    public static System.Void ResetCachedData();
    public static System.Boolean TryGetManifest(System.String name, System.String& path);
}
```


## Fields

- `private static Colossal.Logging.ILog log`  

```csharp
private static Colossal.Logging.ILog log;
```

- `private static System.Collections.Generic.Dictionary<Colossal.PSI.Common.DlcId, Colossal.PSI.Common.DlcAttribute> m_CachedAttributes`  

```csharp
private static System.Collections.Generic.Dictionary<Colossal.PSI.Common.DlcId, Colossal.PSI.Common.DlcAttribute> m_CachedAttributes;
```

- `private static Colossal.Collections.Generic.BiDictionary<Colossal.PSI.Common.DlcId, System.String> m_CachedDlcNames`  

```csharp
private static Colossal.Collections.Generic.BiDictionary<Colossal.PSI.Common.DlcId, System.String> m_CachedDlcNames;
```

- `public static const System.String kEntitlementExtension`  

```csharp
public static const System.String kEntitlementExtension;
```


## Methods

- `public static GetDlcAttributes() : System.Collections.Generic.Dictionary<Colossal.PSI.Common.DlcId, Colossal.PSI.Common.DlcAttribute>`  

```csharp
public static System.Collections.Generic.Dictionary<Colossal.PSI.Common.DlcId, Colossal.PSI.Common.DlcAttribute> GetDlcAttributes();
```

- `private static GetDlcDescriptionType(System.Type& dlcDescriptionType) : System.Boolean`  

```csharp
private static System.Boolean GetDlcDescriptionType(System.Type& dlcDescriptionType);
```

- `public static GetDlcNames() : Colossal.Collections.Generic.BiDictionary<Colossal.PSI.Common.DlcId, System.String>`  

```csharp
public static Colossal.Collections.Generic.BiDictionary<Colossal.PSI.Common.DlcId, System.String> GetDlcNames();
```

- `public static ResetCachedData() : System.Void`  

```csharp
public static System.Void ResetCachedData();
```

- `public static TryGetManifest(System.String name, System.String& path) : System.Boolean`  

```csharp
public static System.Boolean TryGetManifest(System.String name, System.String& path);
```


## Nested types

- `Colossal.PSI.Common.DlcHelper+<>c`  

