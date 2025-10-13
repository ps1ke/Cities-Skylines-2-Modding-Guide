# Colossal.IO.AssetDatabase.Transient

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.IO.AssetDatabase.IAssetDatabaseDescriptor<Colossal.IO.AssetDatabase.Transient>`, `System.IEquatable<Colossal.IO.AssetDatabase.Transient>`  

**Attributes:** `IsReadOnly`  

## Code

```csharp
public sealed struct Transient : Colossal.IO.AssetDatabase.IAssetDatabaseDescriptor<Colossal.IO.AssetDatabase.Transient>, System.IEquatable<Colossal.IO.AssetDatabase.Transient>
{
    private readonly System.Int64 m_MaxChunkSize;
    private readonly System.String m_Name;
    private readonly System.String m_RootPath;

    public System.Boolean canWriteSettings { get; }
    public System.String name { get; }
    public Colossal.IO.AssetDatabase.IAssetFactory assetFactory { get; }
    public Colossal.IO.AssetDatabase.IDataSourceProvider dataSourceProvider { get; }

    public Transient(System.Int64 maxChunkSize, System.String rootPath);

    public System.Boolean Equals(Colossal.IO.AssetDatabase.Transient other);
    public virtual System.Boolean Equals(System.Object obj);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `private readonly System.Int64 m_MaxChunkSize`  

```csharp
private readonly System.Int64 m_MaxChunkSize;
```

- `private readonly System.String m_Name`  

```csharp
private readonly System.String m_Name;
```

- `private readonly System.String m_RootPath`  

```csharp
private readonly System.String m_RootPath;
```


## Properties

- `public System.Boolean canWriteSettings { get }`  

```csharp
public System.Boolean canWriteSettings { get; }
```

- `public System.String name { get }`  

```csharp
public System.String name { get; }
```

- `public Colossal.IO.AssetDatabase.IAssetFactory assetFactory { get }`  

```csharp
public Colossal.IO.AssetDatabase.IAssetFactory assetFactory { get; }
```

- `public Colossal.IO.AssetDatabase.IDataSourceProvider dataSourceProvider { get }`  

```csharp
public Colossal.IO.AssetDatabase.IDataSourceProvider dataSourceProvider { get; }
```


## Constructors

- `public Transient(System.Int64 maxChunkSize, System.String rootPath = null)`  

```csharp
public Transient(System.Int64 maxChunkSize, System.String rootPath);
```


## Methods

- `public Equals(Colossal.IO.AssetDatabase.Transient other) : System.Boolean`  

```csharp
public System.Boolean Equals(Colossal.IO.AssetDatabase.Transient other);
```

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public virtual System.Boolean Equals(System.Object obj);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```


