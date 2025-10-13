# Colossal.IO.AssetDatabase.GdkCloud

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.IO.AssetDatabase.IAssetDatabaseDescriptor<Colossal.IO.AssetDatabase.GdkCloud>`, `System.IEquatable<Colossal.IO.AssetDatabase.GdkCloud>`  

## Code

```csharp
public sealed struct GdkCloud : Colossal.IO.AssetDatabase.IAssetDatabaseDescriptor<Colossal.IO.AssetDatabase.GdkCloud>, System.IEquatable<Colossal.IO.AssetDatabase.GdkCloud>
{
    public System.Boolean canWriteSettings { get; }
    public System.String name { get; }
    public Colossal.IO.AssetDatabase.IAssetFactory assetFactory { get; }
    public Colossal.IO.AssetDatabase.IDataSourceProvider dataSourceProvider { get; }

    public System.Boolean Equals(Colossal.IO.AssetDatabase.GdkCloud other);
    public virtual System.Boolean Equals(System.Object obj);
    public virtual System.Int32 GetHashCode();
}
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

- `public Equals(Colossal.IO.AssetDatabase.GdkCloud other) : System.Boolean`  

```csharp
public System.Boolean Equals(Colossal.IO.AssetDatabase.GdkCloud other);
```

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public virtual System.Boolean Equals(System.Object obj);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```


