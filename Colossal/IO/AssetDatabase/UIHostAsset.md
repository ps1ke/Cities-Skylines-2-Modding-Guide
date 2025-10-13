# Colossal.IO.AssetDatabase.UIHostAsset

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `Colossal.IO.AssetDatabase.Metadata<Colossal.IO.AssetDatabase.UIHostConfig>`  
**Implements:** `Colossal.IO.AssetDatabase.IAssetData`, `System.IDisposable`, `System.IComparable<Colossal.IO.AssetDatabase.IAssetData>`, `System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>`, `Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset`, `Colossal.AssetPipeline.Diagnostic.Report+IFile`  

## Code

```csharp
public class UIHostAsset : Colossal.IO.AssetDatabase.Metadata<Colossal.IO.AssetDatabase.UIHostConfig>, Colossal.IO.AssetDatabase.IAssetData, System.IDisposable, System.IComparable<Colossal.IO.AssetDatabase.IAssetData>, System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>, Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset, Colossal.AssetPipeline.Diagnostic.Report+IFile
{
    public static const System.String kExtension;

    public System.String hostname { get; }
    public System.String scheme { get; }
    public System.Int32 priority { get; }
    public System.Uri uiUri { get; }
    public System.String uiPath { get; }

    public UIHostAsset();

    private static System.String EnsureTrailingSlash(System.String input);
    private static System.String GetParentPath(System.String uri);
}
```


## Fields

- `public static const System.String kExtension`  

```csharp
public static const System.String kExtension;
```


## Properties

- `public System.String hostname { get }`  

```csharp
public System.String hostname { get; }
```

- `public System.String scheme { get }`  

```csharp
public System.String scheme { get; }
```

- `public System.Int32 priority { get }`  

```csharp
public System.Int32 priority { get; }
```

- `public System.Uri uiUri { get }`  

```csharp
public System.Uri uiUri { get; }
```

- `public System.String uiPath { get }`  

```csharp
public System.String uiPath { get; }
```


## Constructors

- `public UIHostAsset()`  

```csharp
public UIHostAsset();
```


## Methods

- `private static EnsureTrailingSlash(System.String input) : System.String`  

```csharp
private static System.String EnsureTrailingSlash(System.String input);
```

- `private static GetParentPath(System.String uri) : System.String`  

```csharp
private static System.String GetParentPath(System.String uri);
```


