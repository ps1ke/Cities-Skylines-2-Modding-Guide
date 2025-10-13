# Colossal.IO.AssetDatabase.Identifier

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Colossal.IO.AssetDatabase.Identifier>`, `System.IComparable<Colossal.IO.AssetDatabase.Identifier>`  

## Code

```csharp
public sealed struct Identifier : System.IEquatable<Colossal.IO.AssetDatabase.Identifier>, System.IComparable<Colossal.IO.AssetDatabase.Identifier>
{
    public readonly Colossal.Hash128 guid;
    public System.String uri;
    public static Colossal.IO.AssetDatabase.Identifier None;

    public Identifier(Colossal.Hash128 guid);
    public Identifier(Colossal.Hash128 guid, System.String uri);

    public System.Int32 CompareTo(Colossal.IO.AssetDatabase.Identifier other);
    public System.Boolean Equals(Colossal.IO.AssetDatabase.Identifier other);
    public virtual System.Boolean Equals(System.Object obj);
    public virtual System.Int32 GetHashCode();
    internal System.Void ReplaceUri(System.String uri);
    public virtual System.String ToString();
}
```


## Fields

- `public readonly Colossal.Hash128 guid`  

```csharp
public readonly Colossal.Hash128 guid;
```

- `public System.String uri`  

```csharp
public System.String uri;
```

- `public static Colossal.IO.AssetDatabase.Identifier None`  

```csharp
public static Colossal.IO.AssetDatabase.Identifier None;
```


## Constructors

- `public Identifier(Colossal.Hash128 guid)`  

```csharp
public Identifier(Colossal.Hash128 guid);
```

- `public Identifier(Colossal.Hash128 guid, System.String uri)`  

```csharp
public Identifier(Colossal.Hash128 guid, System.String uri);
```


## Methods

- `public CompareTo(Colossal.IO.AssetDatabase.Identifier other) : System.Int32`  

```csharp
public System.Int32 CompareTo(Colossal.IO.AssetDatabase.Identifier other);
```

- `public Equals(Colossal.IO.AssetDatabase.Identifier other) : System.Boolean`  

```csharp
public System.Boolean Equals(Colossal.IO.AssetDatabase.Identifier other);
```

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public virtual System.Boolean Equals(System.Object obj);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```

- `internal ReplaceUri(System.String uri) : System.Void`  

```csharp
internal System.Void ReplaceUri(System.String uri);
```

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```


