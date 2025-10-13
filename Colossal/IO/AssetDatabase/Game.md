# Colossal.IO.AssetDatabase.Game

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.IO.AssetDatabase.IAssetDatabaseDescriptor<Colossal.IO.AssetDatabase.Game>`, `System.IEquatable<Colossal.IO.AssetDatabase.Game>`  

**Attributes:** `IsReadOnly`  

## Code

```csharp
public sealed struct Game : Colossal.IO.AssetDatabase.IAssetDatabaseDescriptor<Colossal.IO.AssetDatabase.Game>, System.IEquatable<Colossal.IO.AssetDatabase.Game>
{
    private readonly System.String m_RootPath;
    private readonly System.String <name>k__BackingField;

    public System.Boolean canWriteSettings { get; }
    public System.String name { get; }
    public Colossal.IO.AssetDatabase.IAssetFactory assetFactory { get; }
    public Colossal.IO.AssetDatabase.IDataSourceProvider dataSourceProvider { get; }

    public Game(System.String rootPath);

    public System.Boolean Equals(Colossal.IO.AssetDatabase.Game other);
    public virtual System.Boolean Equals(System.Object obj);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `private readonly System.String m_RootPath`  

```csharp
private readonly System.String m_RootPath;
```

- `private readonly System.String <name>k__BackingField`  

```csharp
private readonly System.String <name>k__BackingField;
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

- `public Game(System.String rootPath)`  

```csharp
public Game(System.String rootPath);
```


## Methods

- `public Equals(Colossal.IO.AssetDatabase.Game other) : System.Boolean`  

```csharp
public System.Boolean Equals(Colossal.IO.AssetDatabase.Game other);
```

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public virtual System.Boolean Equals(System.Object obj);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```


