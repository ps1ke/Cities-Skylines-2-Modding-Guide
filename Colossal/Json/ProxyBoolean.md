# Colossal.Json.ProxyBoolean

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Json`  

**Type:** class sealed public  

**Base:** `Colossal.Json.Variant`  
**Implements:** `System.IConvertible`, `System.IEquatable<Colossal.Json.Variant>`  

## Code

```csharp
public sealed class ProxyBoolean : Colossal.Json.Variant, System.IConvertible, System.IEquatable<Colossal.Json.Variant>
{
    private readonly System.Boolean value;

    public ProxyBoolean(System.Boolean value);

    public virtual System.Boolean Equals(Colossal.Json.Variant other);
    public virtual System.Boolean ToBoolean(System.IFormatProvider provider);
    public virtual System.String ToString(System.IFormatProvider provider);
}
```


## Fields

- `private readonly System.Boolean value`  

```csharp
private readonly System.Boolean value;
```


## Constructors

- `public ProxyBoolean(System.Boolean value)`  

```csharp
public ProxyBoolean(System.Boolean value);
```


## Methods

- `public virtual Equals(Colossal.Json.Variant other) : System.Boolean`  

```csharp
public virtual System.Boolean Equals(Colossal.Json.Variant other);
```

- `public virtual ToBoolean(System.IFormatProvider provider) : System.Boolean`  

```csharp
public virtual System.Boolean ToBoolean(System.IFormatProvider provider);
```

- `public virtual ToString(System.IFormatProvider provider) : System.String`  

```csharp
public virtual System.String ToString(System.IFormatProvider provider);
```


