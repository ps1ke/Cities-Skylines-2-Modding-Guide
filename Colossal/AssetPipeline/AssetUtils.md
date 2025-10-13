# Colossal.AssetPipeline.AssetUtils

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class AssetUtils
{
    private static System.Collections.Generic.HashSet<System.String> s_SupportedThemes;

    public static System.Void AddSupportedThemes(System.Collections.Generic.IEnumerable<System.String> themes);
    public static System.Void ParseName(System.String name, System.String& theme, System.String& assetName, System.Int32& level, Unity.Mathematics.int2& lotSize, Colossal.AssetPipeline.Module& module, System.Int32& lod, System.String& material, System.String& suffix);
    private static System.Void ParseNameWithSuffixes(System.String name, System.String[] entries, System.String& theme, System.String& assetName, System.Int32& level, Unity.Mathematics.int2& lotSize, Colossal.AssetPipeline.Module& module, System.Int32& lod, System.String& material, System.String& suffix, System.String& extra);
    public static Unity.Collections.NativeArray<System.Byte> ReadFileIntoNativeArray(System.String path);
    private static System.Boolean ValidateFileName(System.String name, System.String theme, System.String assetName, System.Int32 level, Unity.Mathematics.int2 lotSize, Colossal.AssetPipeline.Module module, System.Int32 lod, System.String material, System.String suffix, System.String extra, System.String& reconstructedName);
}
```


## Fields

- `private static System.Collections.Generic.HashSet<System.String> s_SupportedThemes`  

```csharp
private static System.Collections.Generic.HashSet<System.String> s_SupportedThemes;
```


## Methods

- `public static AddSupportedThemes(System.Collections.Generic.IEnumerable<System.String> themes) : System.Void`  

```csharp
public static System.Void AddSupportedThemes(System.Collections.Generic.IEnumerable<System.String> themes);
```

- `public static ParseName(System.String name, System.String& theme, System.String& assetName, System.Int32& level, Unity.Mathematics.int2& lotSize, Colossal.AssetPipeline.Module& module, System.Int32& lod, System.String& material, System.String& suffix) : System.Void`  

```csharp
public static System.Void ParseName(System.String name, System.String& theme, System.String& assetName, System.Int32& level, Unity.Mathematics.int2& lotSize, Colossal.AssetPipeline.Module& module, System.Int32& lod, System.String& material, System.String& suffix);
```

- `private static ParseNameWithSuffixes(System.String name, System.String[] entries, System.String& theme, System.String& assetName, System.Int32& level, Unity.Mathematics.int2& lotSize, Colossal.AssetPipeline.Module& module, System.Int32& lod, System.String& material, System.String& suffix, System.String& extra) : System.Void`  

```csharp
private static System.Void ParseNameWithSuffixes(System.String name, System.String[] entries, System.String& theme, System.String& assetName, System.Int32& level, Unity.Mathematics.int2& lotSize, Colossal.AssetPipeline.Module& module, System.Int32& lod, System.String& material, System.String& suffix, System.String& extra);
```

- `public static ReadFileIntoNativeArray(System.String path) : Unity.Collections.NativeArray<System.Byte>`  

```csharp
public static Unity.Collections.NativeArray<System.Byte> ReadFileIntoNativeArray(System.String path);
```

- `private static ValidateFileName(System.String name, System.String theme, System.String assetName, System.Int32 level, Unity.Mathematics.int2 lotSize, Colossal.AssetPipeline.Module module, System.Int32 lod, System.String material, System.String suffix, System.String extra, System.String& reconstructedName) : System.Boolean`  

```csharp
private static System.Boolean ValidateFileName(System.String name, System.String theme, System.String assetName, System.Int32 level, Unity.Mathematics.int2 lotSize, Colossal.AssetPipeline.Module module, System.Int32 lod, System.String material, System.String suffix, System.String extra, System.String& reconstructedName);
```


## Nested types

- `Colossal.AssetPipeline.AssetUtils+ParseMethod`  
- `Colossal.AssetPipeline.AssetUtils+<>c__DisplayClass3_0`  

