# PDX.SDK.Util.TrustLevelHelper

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Util`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class TrustLevelHelper
{
    private static System.Collections.Generic.Dictionary<System.String, PDX.SDK.Contracts.Enums.TrustLevel> levelKVs;

    public static PDX.SDK.Contracts.Enums.TrustLevel GetTrustLevel(System.String level);
    public static System.String GetTrustLevel(PDX.SDK.Contracts.Enums.TrustLevel level);
}
```


## Fields

- `private static System.Collections.Generic.Dictionary<System.String, PDX.SDK.Contracts.Enums.TrustLevel> levelKVs`  

```csharp
private static System.Collections.Generic.Dictionary<System.String, PDX.SDK.Contracts.Enums.TrustLevel> levelKVs;
```


## Methods

- `public static GetTrustLevel(System.String level) : PDX.SDK.Contracts.Enums.TrustLevel`  

```csharp
public static PDX.SDK.Contracts.Enums.TrustLevel GetTrustLevel(System.String level);
```

- `public static GetTrustLevel(PDX.SDK.Contracts.Enums.TrustLevel level) : System.String`  

```csharp
public static System.String GetTrustLevel(PDX.SDK.Contracts.Enums.TrustLevel level);
```


