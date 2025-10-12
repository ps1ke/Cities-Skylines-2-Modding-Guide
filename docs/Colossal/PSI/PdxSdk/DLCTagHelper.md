# Colossal.PSI.PdxSdk.PdxSdkPlatform+DLCTagHelper

**Assembly:** `Colossal.PSI.PdxSdk`  
**Namespace:** `Colossal.PSI.PdxSdk`  

**Type:** class static public  

**Base:** `System.Object`  

## Fields

- `private static readonly System.Text.RegularExpressions.Regex kSplitRegex`  
- `private static readonly System.Text.RegularExpressions.Regex kWhitespaceRegex`  
- `private static System.Collections.Generic.HashSet<System.String> sHasBackend`  
- `private static System.Collections.Generic.HashSet<System.String> sPdxTags`  

## Methods

- `public static HasBackend(System.String internalName) : System.Boolean`  
- `public static Initialize(System.Collections.Generic.List<PDX.SDK.Contracts.Service.Mods.Models.ModGameAddon> addons) : System.Void`  
- `public static IsValidTag(System.String pdxName) : System.Boolean`  
- `public static ToInternalName(System.String pdxName) : System.String`  
- `public static ToPdxName(System.String internalName) : System.String`  

