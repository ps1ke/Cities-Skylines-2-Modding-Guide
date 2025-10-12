# Colossal.IO.AssetDatabase.Transient

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.IO.AssetDatabase.IAssetDatabaseDescriptor<Colossal.IO.AssetDatabase.Transient>`, `System.IEquatable<Colossal.IO.AssetDatabase.Transient>`  

**Attributes:** `IsReadOnly`  

## Fields

- `private readonly System.Int64 m_MaxChunkSize`  
- `private readonly System.String m_Name`  
- `private readonly System.String m_RootPath`  

## Properties

- `public System.Boolean canWriteSettings { get }`  
- `public System.String name { get }`  
- `public Colossal.IO.AssetDatabase.IAssetFactory assetFactory { get }`  
- `public Colossal.IO.AssetDatabase.IDataSourceProvider dataSourceProvider { get }`  

## Constructors

- `public Transient(System.Int64 maxChunkSize, System.String rootPath = null)`  

## Methods

- `public Equals(Colossal.IO.AssetDatabase.Transient other) : System.Boolean`  
- `public virtual Equals(System.Object obj) : System.Boolean`  
- `public virtual GetHashCode() : System.Int32`  

