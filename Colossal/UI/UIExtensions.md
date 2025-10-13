# Colossal.UI.UIExtensions

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class UIExtensions
{
    public static System.String ToGlobalUri(Colossal.IO.AssetDatabase.AssetData asset);
    public static System.String ToUri(Colossal.IO.AssetDatabase.AssetData asset);
    public static System.String ToUri(Colossal.IO.AssetDatabase.TextureAsset asset, Colossal.IO.AssetDatabase.TextureAsset fallbackAsset, System.Int32 mipBias);
    public static System.Boolean TryGetImageAsset(System.String uri, Colossal.IO.AssetDatabase.ImageAsset& imageAsset);
}
```


## Methods

- `public static ToGlobalUri(Colossal.IO.AssetDatabase.AssetData asset) : System.String`  

```csharp
public static System.String ToGlobalUri(Colossal.IO.AssetDatabase.AssetData asset);
```

- `public static ToUri(Colossal.IO.AssetDatabase.AssetData asset) : System.String`  

```csharp
public static System.String ToUri(Colossal.IO.AssetDatabase.AssetData asset);
```

- `public static ToUri(Colossal.IO.AssetDatabase.TextureAsset asset, Colossal.IO.AssetDatabase.TextureAsset fallbackAsset = null, System.Int32 mipBias = 0) : System.String`  

```csharp
public static System.String ToUri(Colossal.IO.AssetDatabase.TextureAsset asset, Colossal.IO.AssetDatabase.TextureAsset fallbackAsset, System.Int32 mipBias);
```

- `public static TryGetImageAsset(System.String uri, Colossal.IO.AssetDatabase.ImageAsset& imageAsset) : System.Boolean`  

```csharp
public static System.Boolean TryGetImageAsset(System.String uri, Colossal.IO.AssetDatabase.ImageAsset& imageAsset);
```


