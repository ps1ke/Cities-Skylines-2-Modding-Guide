# Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Collectors`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset>`  

**Attributes:** `IsReadOnly`  

## Code

```csharp
public sealed struct Asset : System.IEquatable<Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset>
{
    public readonly System.String name;
    public readonly System.String path;
    public readonly System.String hashPath;
    public readonly Colossal.Hash64 hash;

    public Asset(System.String path, System.String rootPath);
    public Asset(System.String name, System.String rootPath, System.String[] paths);

    public System.Boolean Equals(Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset other);
    public virtual System.Boolean Equals(System.Object obj);
    public virtual System.Int32 GetHashCode();
    public virtual System.String ToString();
}
```


## Fields

- `public readonly System.String name`  

```csharp
public readonly System.String name;
```

- `public readonly System.String path`  

```csharp
public readonly System.String path;
```

- `public readonly System.String hashPath`  

```csharp
public readonly System.String hashPath;
```

- `public readonly Colossal.Hash64 hash`  

```csharp
public readonly Colossal.Hash64 hash;
```


## Constructors

- `public Asset(System.String path, System.String rootPath)`  

```csharp
public Asset(System.String path, System.String rootPath);
```

- `public Asset(System.String name, System.String rootPath, System.String[] paths)`  

```csharp
public Asset(System.String name, System.String rootPath, System.String[] paths);
```


## Methods

- `public Equals(Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset other) : System.Boolean`  

```csharp
public System.Boolean Equals(Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset other);
```

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public virtual System.Boolean Equals(System.Object obj);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```


## Nested types

- `Colossal.AssetPipeline.Collectors.SourceAssetCollector+Asset+<>c__DisplayClass5_0`  

