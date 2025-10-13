# Colossal.Indent

**Assembly:** `Colossal.Logging`  
**Namespace:** `Colossal`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public class Indent : System.IDisposable
{
    private System.String <indentString>k__BackingField;
    private System.Int32 m_Indent;
    public System.String indentFormat;

    public Colossal.Indent scoped { get; }
    public System.String indentString { get; private set; }
    public System.Int32 indent { get; set; }

    public Indent();

    public System.Void Dispose();
    public virtual System.Boolean Equals(System.Object obj);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `private System.String <indentString>k__BackingField`  

```csharp
private System.String <indentString>k__BackingField;
```

- `private System.Int32 m_Indent`  

```csharp
private System.Int32 m_Indent;
```

- `public System.String indentFormat`  

```csharp
public System.String indentFormat;
```


## Properties

- `public Colossal.Indent scoped { get }`  

```csharp
public Colossal.Indent scoped { get; }
```

- `public System.String indentString { get; private set }`  

```csharp
public System.String indentString { get; private set; }
```

- `public System.Int32 indent { get; set }`  

```csharp
public System.Int32 indent { get; set; }
```


## Constructors

- `public Indent()`  

```csharp
public Indent();
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public virtual System.Boolean Equals(System.Object obj);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```


