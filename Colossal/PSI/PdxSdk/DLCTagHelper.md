# Colossal.PSI.PdxSdk.PdxSdkPlatform+DLCTagHelper

**Assembly:** `Colossal.PSI.PdxSdk`  
**Namespace:** `Colossal.PSI.PdxSdk`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class DLCTagHelper
{
    private static readonly System.Text.RegularExpressions.Regex kSplitRegex;
    private static readonly System.Text.RegularExpressions.Regex kWhitespaceRegex;
    private static System.Collections.Generic.HashSet<System.String> sHasBackend;
    private static System.Collections.Generic.HashSet<System.String> sPdxTags;

    public static System.Boolean HasBackend(System.String internalName);
    public static System.Void Initialize(System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.ModGameAddon> addons);
    public static System.Boolean IsValidTag(System.String pdxName);
    public static System.String ToInternalName(System.String pdxName);
    public static System.String ToPdxName(System.String internalName);
}
```


## Fields

- `private static readonly System.Text.RegularExpressions.Regex kSplitRegex`  

```csharp
private static readonly System.Text.RegularExpressions.Regex kSplitRegex;
```

- `private static readonly System.Text.RegularExpressions.Regex kWhitespaceRegex`  

```csharp
private static readonly System.Text.RegularExpressions.Regex kWhitespaceRegex;
```

- `private static System.Collections.Generic.HashSet<System.String> sHasBackend`  

```csharp
private static System.Collections.Generic.HashSet<System.String> sHasBackend;
```

- `private static System.Collections.Generic.HashSet<System.String> sPdxTags`  

```csharp
private static System.Collections.Generic.HashSet<System.String> sPdxTags;
```


## Methods

- `public static HasBackend(System.String internalName) : System.Boolean`  

```csharp
public static System.Boolean HasBackend(System.String internalName);
```

- `public static Initialize(System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.ModGameAddon> addons) : System.Void`  

```csharp
public static System.Void Initialize(System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.ModGameAddon> addons);
```

- `public static IsValidTag(System.String pdxName) : System.Boolean`  

```csharp
public static System.Boolean IsValidTag(System.String pdxName);
```

- `public static ToInternalName(System.String pdxName) : System.String`  

```csharp
public static System.String ToInternalName(System.String pdxName);
```

- `public static ToPdxName(System.String internalName) : System.String`  

```csharp
public static System.String ToPdxName(System.String internalName);
```


