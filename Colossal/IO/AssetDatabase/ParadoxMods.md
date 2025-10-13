# Colossal.IO.AssetDatabase.ParadoxMods

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.IO.AssetDatabase.IAssetDatabaseDescriptor<Colossal.IO.AssetDatabase.ParadoxMods>`, `System.IEquatable<Colossal.IO.AssetDatabase.ParadoxMods>`  

## Code

```csharp
public sealed struct ParadoxMods : Colossal.IO.AssetDatabase.IAssetDatabaseDescriptor<Colossal.IO.AssetDatabase.ParadoxMods>, System.IEquatable<Colossal.IO.AssetDatabase.ParadoxMods>
{
    public System.Boolean canWriteSettings { get; }
    public System.String name { get; }
    public Colossal.IO.AssetDatabase.IAssetFactory assetFactory { get; }
    public Colossal.IO.AssetDatabase.IDataSourceProvider dataSourceProvider { get; }

    public System.Boolean Equals(Colossal.IO.AssetDatabase.ParadoxMods other);
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

- `public Equals(Colossal.IO.AssetDatabase.ParadoxMods other) : System.Boolean`  

```csharp
public System.Boolean Equals(Colossal.IO.AssetDatabase.ParadoxMods other);
```

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public virtual System.Boolean Equals(System.Object obj);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```


