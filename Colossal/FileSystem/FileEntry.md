# Colossal.FileSystem.FileEntry

**Assembly:** `Colossal.IO`  
**Namespace:** `Colossal.FileSystem`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class FileEntry
{
    private System.String <path>k__BackingField;
    private System.Int64 <hash>k__BackingField;
    private System.Int32 <directory>k__BackingField;

    public System.String path { get; private set; }
    public System.Int64 hash { get; private set; }
    public System.Int32 directory { get; private set; }

    public FileEntry(System.String file, System.Int32 dir);

    private System.Int64 CalculateHash();
    public virtual System.Boolean Equals(System.Object obj);
    public virtual System.Int32 GetHashCode();
    public System.Void SetHash(System.Int64 newHash);
    public virtual System.String ToString();
}
```


## Fields

- `private System.String <path>k__BackingField`  

```csharp
private System.String <path>k__BackingField;
```

- `private System.Int64 <hash>k__BackingField`  

```csharp
private System.Int64 <hash>k__BackingField;
```

- `private System.Int32 <directory>k__BackingField`  

```csharp
private System.Int32 <directory>k__BackingField;
```


## Properties

- `public System.String path { get; private set }`  

```csharp
public System.String path { get; private set; }
```

- `public System.Int64 hash { get; private set }`  

```csharp
public System.Int64 hash { get; private set; }
```

- `public System.Int32 directory { get; private set }`  

```csharp
public System.Int32 directory { get; private set; }
```


## Constructors

- `public FileEntry(System.String file, System.Int32 dir)`  

```csharp
public FileEntry(System.String file, System.Int32 dir);
```


## Methods

- `private CalculateHash() : System.Int64`  

```csharp
private System.Int64 CalculateHash();
```

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public virtual System.Boolean Equals(System.Object obj);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```

- `public SetHash(System.Int64 newHash) : System.Void`  

```csharp
public System.Void SetHash(System.Int64 newHash);
```

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```


