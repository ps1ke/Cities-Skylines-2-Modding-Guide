# Colossal.IndentedStringBuilder

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class IndentedStringBuilder
{
    private System.Text.StringBuilder m_Builder;
    private System.Boolean m_IndentApplied;
    private Colossal.Indent <indent>k__BackingField;

    public Colossal.Indent indent { get; set; }

    public IndentedStringBuilder();

    public System.Void Append(System.String str);
    public System.Void AppendLine();
    public System.Void AppendLine(System.String str);
    public virtual System.String ToString();
}
```


## Fields

- `private System.Text.StringBuilder m_Builder`  

```csharp
private System.Text.StringBuilder m_Builder;
```

- `private System.Boolean m_IndentApplied`  

```csharp
private System.Boolean m_IndentApplied;
```

- `private Colossal.Indent <indent>k__BackingField`  

```csharp
private Colossal.Indent <indent>k__BackingField;
```


## Properties

- `public Colossal.Indent indent { get; set }`  

```csharp
public Colossal.Indent indent { get; set; }
```


## Constructors

- `public IndentedStringBuilder()`  

```csharp
public IndentedStringBuilder();
```


## Methods

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

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```


