# Colossal.IO.AssetDatabase.IPackageWriter

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** interface abstract public  

**Implements:** `System.IDisposable`  

## Code

```csharp
public abstract interface IPackageWriter : System.IDisposable
{
    public abstract System.Void Add(Colossal.IO.AssetDatabase.IAssetData data, System.Boolean preserveTimestamp);
    public abstract System.Boolean Commit();
}
```


## Methods

- `public abstract Add(Colossal.IO.AssetDatabase.IAssetData data, System.Boolean preserveTimestamp = False) : System.Void`  

```csharp
public abstract System.Void Add(Colossal.IO.AssetDatabase.IAssetData data, System.Boolean preserveTimestamp);
```

- `public abstract Commit() : System.Boolean`  

```csharp
public abstract System.Boolean Commit();
```


