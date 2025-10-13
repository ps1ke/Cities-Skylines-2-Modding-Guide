# PDX.SDK.Util.PlatformExtensions

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Util`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class PlatformExtensions
{
    private static System.Collections.Generic.Dictionary<PDX.SDK.Contracts.Service.Mods.Enums.ModPlatform, System.String> modsPlatformStrings;

    internal static PDX.SDK.Contracts.Service.Mods.Enums.ModPlatform GetModsPlatform(PDX.SDK.Contracts.Enums.Platform platform);
    internal static System.String GetPlatform(PDX.SDK.Contracts.Enums.Platform plat);
    internal static System.Boolean IsValidModsConsolePlatform(PDX.SDK.Contracts.Enums.Platform platform);
    public static PDX.SDK.Contracts.Enums.Platform RuntimePlatformToPdxPlatform(UnityEngine.RuntimePlatform platform);
    internal static System.String ToModsPlatformString(PDX.SDK.Contracts.Service.Mods.Enums.ModPlatform plat);
}
```


## Fields

- `private static System.Collections.Generic.Dictionary<PDX.SDK.Contracts.Service.Mods.Enums.ModPlatform, System.String> modsPlatformStrings`  

```csharp
private static System.Collections.Generic.Dictionary<PDX.SDK.Contracts.Service.Mods.Enums.ModPlatform, System.String> modsPlatformStrings;
```


## Methods

- `internal static GetModsPlatform(PDX.SDK.Contracts.Enums.Platform platform) : PDX.SDK.Contracts.Service.Mods.Enums.ModPlatform`  

```csharp
internal static PDX.SDK.Contracts.Service.Mods.Enums.ModPlatform GetModsPlatform(PDX.SDK.Contracts.Enums.Platform platform);
```

- `internal static GetPlatform(PDX.SDK.Contracts.Enums.Platform plat) : System.String`  

```csharp
internal static System.String GetPlatform(PDX.SDK.Contracts.Enums.Platform plat);
```

- `internal static IsValidModsConsolePlatform(PDX.SDK.Contracts.Enums.Platform platform) : System.Boolean`  

```csharp
internal static System.Boolean IsValidModsConsolePlatform(PDX.SDK.Contracts.Enums.Platform platform);
```

- `public static RuntimePlatformToPdxPlatform(UnityEngine.RuntimePlatform platform) : PDX.SDK.Contracts.Enums.Platform`  

```csharp
public static PDX.SDK.Contracts.Enums.Platform RuntimePlatformToPdxPlatform(UnityEngine.RuntimePlatform platform);
```

- `internal static ToModsPlatformString(PDX.SDK.Contracts.Service.Mods.Enums.ModPlatform plat) : System.String`  

```csharp
internal static System.String ToModsPlatformString(PDX.SDK.Contracts.Service.Mods.Enums.ModPlatform plat);
```


