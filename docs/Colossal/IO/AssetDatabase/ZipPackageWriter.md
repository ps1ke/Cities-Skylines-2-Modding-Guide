# Colossal.IO.AssetDatabase.ZipPackageWriter

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.IO.AssetDatabase.IPackageWriter`, `System.IDisposable`  

## Fields

- `private System.Boolean m_IsDirty`  
- `private ICSharpCode.SharpZipLib.Zip.ZipFile m_ZipFile`  

## Constructors

- `public ZipPackageWriter(System.IO.Stream stream)`  

## Methods

- `public Add(Colossal.IO.AssetDatabase.IAssetData asset, System.Boolean preserveTimestamp = False) : System.Void`  
- `public Commit() : System.Boolean`  
- `public Dispose() : System.Void`  

## Nested types

- `Colossal.IO.AssetDatabase.ZipPackageWriter+FileDataSource`  
- `Colossal.IO.AssetDatabase.ZipPackageWriter+GuidDataSource`  

