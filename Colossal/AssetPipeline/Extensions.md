# Colossal.AssetPipeline.Extensions

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class Extensions
{
    public static System.Collections.Generic.IEnumerable<T> FilterBy<T>(Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.IAsset> assetGroup, System.Func<T, System.Boolean> predicate);
    public static T Find<T>(Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.IAsset> assetGroup, System.Func<T, System.Boolean> predicate);
    internal static System.Int32 GetExtensionId(Colossal.AssetPipeline.Module module);
    internal static System.Int32 GetSubId(Colossal.AssetPipeline.Module module);
    public static System.Boolean Has(Colossal.AssetPipeline.ImportMode mode, Colossal.AssetPipeline.ImportMode flag);
    internal static System.Boolean IsBase(Colossal.AssetPipeline.Module module);
    internal static System.Boolean IsExtension(Colossal.AssetPipeline.Module module);
    internal static System.Boolean IsSub(Colossal.AssetPipeline.Module module);
    internal static Colossal.AssetPipeline.Module SetExtensionId(Colossal.AssetPipeline.Module module, System.Int32 id);
    internal static Colossal.AssetPipeline.Module SetSubId(Colossal.AssetPipeline.Module module, System.Int32 id);
}
```


## Methods

- `public static FilterBy<T>(Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.IAsset> assetGroup, System.Func<T, System.Boolean> predicate = null) : System.Collections.Generic.IEnumerable<T>`  

```csharp
public static System.Collections.Generic.IEnumerable<T> FilterBy<T>(Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.IAsset> assetGroup, System.Func<T, System.Boolean> predicate);
```

- `public static Find<T>(Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.IAsset> assetGroup, System.Func<T, System.Boolean> predicate) : T`  

```csharp
public static T Find<T>(Colossal.AssetPipeline.Collectors.SourceAssetCollector+AssetGroup<Colossal.AssetPipeline.IAsset> assetGroup, System.Func<T, System.Boolean> predicate);
```

- `internal static GetExtensionId(Colossal.AssetPipeline.Module module) : System.Int32`  

```csharp
internal static System.Int32 GetExtensionId(Colossal.AssetPipeline.Module module);
```

- `internal static GetSubId(Colossal.AssetPipeline.Module module) : System.Int32`  

```csharp
internal static System.Int32 GetSubId(Colossal.AssetPipeline.Module module);
```

- `public static Has(Colossal.AssetPipeline.ImportMode mode, Colossal.AssetPipeline.ImportMode flag) : System.Boolean`  

```csharp
public static System.Boolean Has(Colossal.AssetPipeline.ImportMode mode, Colossal.AssetPipeline.ImportMode flag);
```

- `internal static IsBase(Colossal.AssetPipeline.Module module) : System.Boolean`  

```csharp
internal static System.Boolean IsBase(Colossal.AssetPipeline.Module module);
```

- `internal static IsExtension(Colossal.AssetPipeline.Module module) : System.Boolean`  

```csharp
internal static System.Boolean IsExtension(Colossal.AssetPipeline.Module module);
```

- `internal static IsSub(Colossal.AssetPipeline.Module module) : System.Boolean`  

```csharp
internal static System.Boolean IsSub(Colossal.AssetPipeline.Module module);
```

- `internal static SetExtensionId(Colossal.AssetPipeline.Module module, System.Int32 id) : Colossal.AssetPipeline.Module`  

```csharp
internal static Colossal.AssetPipeline.Module SetExtensionId(Colossal.AssetPipeline.Module module, System.Int32 id);
```

- `internal static SetSubId(Colossal.AssetPipeline.Module module, System.Int32 id) : Colossal.AssetPipeline.Module`  

```csharp
internal static Colossal.AssetPipeline.Module SetSubId(Colossal.AssetPipeline.Module module, System.Int32 id);
```


## Nested types

- `Colossal.AssetPipeline.Extensions+<FilterBy>d__0<T>`  

