# Colossal.IO.AssetDatabase.AsyncReadDescriptor

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Colossal.IO.AssetDatabase.AsyncReadDescriptor>`  

**Attributes:** `IsReadOnly`  

## Code

```csharp
public sealed struct AsyncReadDescriptor : System.IEquatable<Colossal.IO.AssetDatabase.AsyncReadDescriptor>
{
    public readonly System.String name;
    public readonly System.String path;
    public readonly System.Int64 offset;
    public readonly System.Int64 size;
    public readonly System.Boolean packaged;

    public static Colossal.IO.AssetDatabase.AsyncReadDescriptor Invalid { get; }

    public AsyncReadDescriptor(System.String name, System.String path);
    public AsyncReadDescriptor(System.String name, System.String path, System.Int64 offset, System.Int64 size, System.Boolean packaged);

    public System.Boolean Equals(Colossal.IO.AssetDatabase.AsyncReadDescriptor other);
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

- `public readonly System.Int64 offset`  

```csharp
public readonly System.Int64 offset;
```

- `public readonly System.Int64 size`  

```csharp
public readonly System.Int64 size;
```

- `public readonly System.Boolean packaged`  

```csharp
public readonly System.Boolean packaged;
```


## Properties

- `public static Colossal.IO.AssetDatabase.AsyncReadDescriptor Invalid { get }`  

```csharp
public static Colossal.IO.AssetDatabase.AsyncReadDescriptor Invalid { get; }
```


## Constructors

- `public AsyncReadDescriptor(System.String name, System.String path)`  

```csharp
public AsyncReadDescriptor(System.String name, System.String path);
```

- `public AsyncReadDescriptor(System.String name, System.String path, System.Int64 offset, System.Int64 size, System.Boolean packaged)`  

```csharp
public AsyncReadDescriptor(System.String name, System.String path, System.Int64 offset, System.Int64 size, System.Boolean packaged);
```


## Methods

- `public Equals(Colossal.IO.AssetDatabase.AsyncReadDescriptor other) : System.Boolean`  

```csharp
public System.Boolean Equals(Colossal.IO.AssetDatabase.AsyncReadDescriptor other);
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


