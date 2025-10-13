# Colossal.IO.AssetDatabase.AssetReference

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IComparable`, `System.IComparable<Colossal.Hash128>`, `System.IEquatable<Colossal.Hash128>`, `System.IEquatable<Colossal.IO.AssetDatabase.AssetReference>`  

**Attributes:** `Serializable`  

## Code

```csharp
public class AssetReference : System.IComparable, System.IComparable<Colossal.Hash128>, System.IEquatable<Colossal.Hash128>, System.IEquatable<Colossal.IO.AssetDatabase.AssetReference>
{
    private Colossal.Hash128 m_Guid;
    private System.Int32 m_GuidPart1;
    private System.Int32 m_GuidPart2;
    private System.Int32 m_GuidPart3;
    private System.Int32 m_GuidPart4;

    public Colossal.Hash128 guid { get; set; }

    public AssetReference(Colossal.Hash128 guid);

    public System.Int32 CompareTo(System.Object obj);
    public System.Int32 CompareTo(Colossal.Hash128 other);
    public System.Boolean Equals(Colossal.Hash128 other);
    public System.Boolean Equals(Colossal.IO.AssetDatabase.AssetReference other);
    public virtual System.Boolean Equals(System.Object obj);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `private Colossal.Hash128 m_Guid`  

```csharp
private Colossal.Hash128 m_Guid;
```

- `private System.Int32 m_GuidPart1`  

```csharp
private System.Int32 m_GuidPart1;
```

- `private System.Int32 m_GuidPart2`  

```csharp
private System.Int32 m_GuidPart2;
```

- `private System.Int32 m_GuidPart3`  

```csharp
private System.Int32 m_GuidPart3;
```

- `private System.Int32 m_GuidPart4`  

```csharp
private System.Int32 m_GuidPart4;
```


## Properties

- `public Colossal.Hash128 guid { get; set }`  

```csharp
public Colossal.Hash128 guid { get; set; }
```


## Constructors

- `public AssetReference(Colossal.Hash128 guid)`  

```csharp
public AssetReference(Colossal.Hash128 guid);
```


## Methods

- `public CompareTo(System.Object obj) : System.Int32`  

```csharp
public System.Int32 CompareTo(System.Object obj);
```

- `public CompareTo(Colossal.Hash128 other) : System.Int32`  

```csharp
public System.Int32 CompareTo(Colossal.Hash128 other);
```

- `public Equals(Colossal.Hash128 other) : System.Boolean`  

```csharp
public System.Boolean Equals(Colossal.Hash128 other);
```

- `public Equals(Colossal.IO.AssetDatabase.AssetReference other) : System.Boolean`  

```csharp
public System.Boolean Equals(Colossal.IO.AssetDatabase.AssetReference other);
```

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public virtual System.Boolean Equals(System.Object obj);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```


