# Colossal.AlignedStringBuilder

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class AlignedStringBuilder
{
    private System.Text.StringBuilder m_Builder;
    private System.Int32 m_CurrentLineLength;

    public AlignedStringBuilder();

    public System.Void Append(System.Char c);
    public System.Void Append(System.Byte b);
    public System.Void Append(System.SByte b);
    public System.Void Append(System.Int16 b);
    public System.Void Append(System.UInt16 b);
    public System.Void Append(System.Int32 b);
    public System.Void Append(System.UInt32 b);
    public System.Void Append(System.Int64 b);
    public System.Void Append(System.UInt64 b);
    public System.Void Append(System.Single b);
    public System.Void Append(System.Double b);
    public System.Void Append(System.Decimal b);
    public System.Void Append(System.String str);
    public System.Void AppendLine();
    public System.Void AppendLine(System.String str);
    public System.Void AppendPad(System.String str, System.Int32 count);
    public System.Void Clear();
    public virtual System.String ToString();
}
```


## Fields

- `private System.Text.StringBuilder m_Builder`  

```csharp
private System.Text.StringBuilder m_Builder;
```

- `private System.Int32 m_CurrentLineLength`  

```csharp
private System.Int32 m_CurrentLineLength;
```


## Constructors

- `public AlignedStringBuilder()`  

```csharp
public AlignedStringBuilder();
```


## Methods

- `public Append(System.Char c) : System.Void`  

```csharp
public System.Void Append(System.Char c);
```

- `public Append(System.Byte b) : System.Void`  

```csharp
public System.Void Append(System.Byte b);
```

- `public Append(System.SByte b) : System.Void`  

```csharp
public System.Void Append(System.SByte b);
```

- `public Append(System.Int16 b) : System.Void`  

```csharp
public System.Void Append(System.Int16 b);
```

- `public Append(System.UInt16 b) : System.Void`  

```csharp
public System.Void Append(System.UInt16 b);
```

- `public Append(System.Int32 b) : System.Void`  

```csharp
public System.Void Append(System.Int32 b);
```

- `public Append(System.UInt32 b) : System.Void`  

```csharp
public System.Void Append(System.UInt32 b);
```

- `public Append(System.Int64 b) : System.Void`  

```csharp
public System.Void Append(System.Int64 b);
```

- `public Append(System.UInt64 b) : System.Void`  

```csharp
public System.Void Append(System.UInt64 b);
```

- `public Append(System.Single b) : System.Void`  

```csharp
public System.Void Append(System.Single b);
```

- `public Append(System.Double b) : System.Void`  

```csharp
public System.Void Append(System.Double b);
```

- `public Append(System.Decimal b) : System.Void`  

```csharp
public System.Void Append(System.Decimal b);
```

- `public Append(System.String str) : System.Void`  

```csharp
public System.Void Append(System.String str);
```

- `public AppendLine() : System.Void`  

```csharp
public System.Void AppendLine();
```

- `public AppendLine(System.String str) : System.Void`  

```csharp
public System.Void AppendLine(System.String str);
```

- `public AppendPad(System.String str, System.Int32 count) : System.Void`  

```csharp
public System.Void AppendPad(System.String str, System.Int32 count);
```

- `public Clear() : System.Void`  

```csharp
public System.Void Clear();
```

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```


