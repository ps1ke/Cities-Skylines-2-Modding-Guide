# Colossal.IO.AssetDatabase.AssetExtensions

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class AssetExtensions
{
    private static readonly System.Random s_Random;

    public static TAssetData GetRandomAsset<TAssetData>(Colossal.IO.AssetDatabase.IAssetDatabase database, Colossal.IO.AssetDatabase.SearchFilter<TAssetData> filter);
    public static System.Int32 Range(System.Int32 min, System.Int32 max);
}
```


## Fields

- `private static readonly System.Random s_Random`  

```csharp
private static readonly System.Random s_Random;
```


## Methods

- `public static GetRandomAsset<TAssetData>(Colossal.IO.AssetDatabase.IAssetDatabase database, Colossal.IO.AssetDatabase.SearchFilter<TAssetData> filter = null) : TAssetData`  

```csharp
public static TAssetData GetRandomAsset<TAssetData>(Colossal.IO.AssetDatabase.IAssetDatabase database, Colossal.IO.AssetDatabase.SearchFilter<TAssetData> filter);
```

- `public static Range(System.Int32 min, System.Int32 max) : System.Int32`  

```csharp
public static System.Int32 Range(System.Int32 min, System.Int32 max);
```


