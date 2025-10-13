# Colossal.IO.AssetDatabase.IAssetData

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** interface abstract public  

**Implements:** `System.IDisposable`, `System.IComparable<Colossal.IO.AssetDatabase.IAssetData>`, `System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>`  

**Attributes:** `JsonConverter`  

## Code

```csharp
public abstract interface IAssetData : System.IDisposable, System.IComparable<Colossal.IO.AssetDatabase.IAssetData>, System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>
{
    public Colossal.IO.AssetDatabase.LoadState state { get; }
    public System.String name { get; }
    public Colossal.IO.AssetDatabase.Identifier id { get; set; }
    public System.String uri { get; set; }
    public Colossal.IO.AssetDatabase.ILocalAssetDatabase database { get; set; }
    public System.Boolean isPersistent { get; }
    public System.Boolean isDirty { get; }

    public abstract System.Boolean MarkDirty();
    public abstract System.Void PostCreate();
    public abstract System.Void Save(System.Boolean force);
    public abstract System.Void Unload(System.Boolean force);
}
```


## Properties

- `public Colossal.IO.AssetDatabase.LoadState state { get }`  

```csharp
public Colossal.IO.AssetDatabase.LoadState state { get; }
```

- `public System.String name { get }`  

```csharp
public System.String name { get; }
```

- `public Colossal.IO.AssetDatabase.Identifier id { get; set }`  

```csharp
public Colossal.IO.AssetDatabase.Identifier id { get; set; }
```

- `public System.String uri { get; set }`  

```csharp
public System.String uri { get; set; }
```

- `public Colossal.IO.AssetDatabase.ILocalAssetDatabase database { get; set }`  

```csharp
public Colossal.IO.AssetDatabase.ILocalAssetDatabase database { get; set; }
```

- `public System.Boolean isPersistent { get }`  

```csharp
public System.Boolean isPersistent { get; }
```

- `public System.Boolean isDirty { get }`  

```csharp
public System.Boolean isDirty { get; }
```


## Methods

- `public abstract MarkDirty() : System.Boolean`  

```csharp
public abstract System.Boolean MarkDirty();
```

- `public abstract PostCreate() : System.Void`  

```csharp
public abstract System.Void PostCreate();
```

- `public abstract Save(System.Boolean force = False) : System.Void`  

```csharp
public abstract System.Void Save(System.Boolean force);
```

- `public abstract Unload(System.Boolean force = False) : System.Void`  

```csharp
public abstract System.Void Unload(System.Boolean force);
```


