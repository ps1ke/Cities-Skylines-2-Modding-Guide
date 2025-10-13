# Colossal.IO.AssetDatabase.User

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.IO.AssetDatabase.IAssetDatabaseDescriptor<Colossal.IO.AssetDatabase.User>`, `System.IEquatable<Colossal.IO.AssetDatabase.User>`  

**Attributes:** `IsReadOnly`  

## Code

```csharp
public sealed struct User : Colossal.IO.AssetDatabase.IAssetDatabaseDescriptor<Colossal.IO.AssetDatabase.User>, System.IEquatable<Colossal.IO.AssetDatabase.User>
{
    private static readonly System.String kRootPath;

    public System.Boolean canWriteSettings { get; }
    public System.String name { get; }
    public Colossal.IO.AssetDatabase.IAssetFactory assetFactory { get; }
    public Colossal.IO.AssetDatabase.IDataSourceProvider dataSourceProvider { get; }

    public System.Boolean Equals(Colossal.IO.AssetDatabase.User other);
    public virtual System.Boolean Equals(System.Object obj);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `private static readonly System.String kRootPath`  

```csharp
private static readonly System.String kRootPath;
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


## Methods

- `public Equals(Colossal.IO.AssetDatabase.User other) : System.Boolean`  

```csharp
public System.Boolean Equals(Colossal.IO.AssetDatabase.User other);
```

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public virtual System.Boolean Equals(System.Object obj);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```


