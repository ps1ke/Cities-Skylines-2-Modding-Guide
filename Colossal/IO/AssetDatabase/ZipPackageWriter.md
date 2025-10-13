# Colossal.IO.AssetDatabase.ZipPackageWriter

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.IO.AssetDatabase.IPackageWriter`, `System.IDisposable`  

## Code

```csharp
public class ZipPackageWriter : Colossal.IO.AssetDatabase.IPackageWriter, System.IDisposable
{
    private System.Boolean m_IsDirty;
    private ICSharpCode.SharpZipLib.Zip.ZipFile m_ZipFile;

    public ZipPackageWriter(System.IO.Stream stream);

    public System.Void Add(Colossal.IO.AssetDatabase.IAssetData asset, System.Boolean preserveTimestamp);
    public System.Boolean Commit();
    public System.Void Dispose();
}
```


## Fields

- `private System.Boolean m_IsDirty`  

```csharp
private System.Boolean m_IsDirty;
```

- `private ICSharpCode.SharpZipLib.Zip.ZipFile m_ZipFile`  

```csharp
private ICSharpCode.SharpZipLib.Zip.ZipFile m_ZipFile;
```


## Constructors

- `public ZipPackageWriter(System.IO.Stream stream)`  

```csharp
public ZipPackageWriter(System.IO.Stream stream);
```


## Methods

- `public Add(Colossal.IO.AssetDatabase.IAssetData asset, System.Boolean preserveTimestamp = False) : System.Void`  

```csharp
public System.Void Add(Colossal.IO.AssetDatabase.IAssetData asset, System.Boolean preserveTimestamp);
```

- `public Commit() : System.Boolean`  

```csharp
public System.Boolean Commit();
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```


## Nested types

- `Colossal.IO.AssetDatabase.ZipPackageWriter+FileDataSource`  
- `Colossal.IO.AssetDatabase.ZipPackageWriter+GuidDataSource`  

