# Colossal.AssetPipeline.AssetUtils

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline`  

**Type:** class static public  

**Base:** `System.Object`  

## Fields

- `private static System.Collections.Generic.HashSet<System.String> s_SupportedThemes`  

## Methods

- `public static AddSupportedThemes(System.Collections.Generic.IEnumerable<System.String> themes) : System.Void`  
- `public static ParseName(System.String name, System.String& theme, System.String& assetName, System.Int32& level, Unity.Mathematics.int2& lotSize, Colossal.AssetPipeline.Module& module, System.Int32& lod, System.String& material, System.String& suffix) : System.Void`  
- `private static ParseNameWithSuffixes(System.String name, System.String[] entries, System.String& theme, System.String& assetName, System.Int32& level, Unity.Mathematics.int2& lotSize, Colossal.AssetPipeline.Module& module, System.Int32& lod, System.String& material, System.String& suffix, System.String& extra) : System.Void`  
- `public static ReadFileIntoNativeArray(System.String path) : Unity.Collections.NativeArray<System.Byte>`  
- `private static ValidateFileName(System.String name, System.String theme, System.String assetName, System.Int32 level, Unity.Mathematics.int2 lotSize, Colossal.AssetPipeline.Module module, System.Int32 lod, System.String material, System.String suffix, System.String extra, System.String& reconstructedName) : System.Boolean`  

## Nested types

- `Colossal.AssetPipeline.AssetUtils+ParseMethod`  
- `Colossal.AssetPipeline.AssetUtils+<>c__DisplayClass3_0`  

