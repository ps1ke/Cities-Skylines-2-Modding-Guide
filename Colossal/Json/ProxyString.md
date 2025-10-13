# Colossal.Json.ProxyString

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Json`  

**Type:** class sealed public  

**Base:** `Colossal.Json.Variant`  
**Implements:** `System.IConvertible`, `System.IEquatable<Colossal.Json.Variant>`  

## Code

```csharp
public sealed class ProxyString : Colossal.Json.Variant, System.IConvertible, System.IEquatable<Colossal.Json.Variant>
{
    private readonly System.String value;

    public ProxyString(System.String value);
    public ProxyString(System.Char[] value);
    public ProxyString(System.Type value);
    public ProxyString(System.Guid value);
    public ProxyString(System.Enum value);
    public ProxyString(System.Net.IPAddress value);
    public ProxyString(System.DateTime value);
    public ProxyString(System.TimeSpan value);
    public ProxyString(Colossal.Logging.Level value);

    public virtual System.Boolean Equals(Colossal.Json.Variant other);
    public virtual System.Char ToChar(System.IFormatProvider provider);
    public virtual System.String ToString(System.IFormatProvider provider);
}
```


## Fields

- `private readonly System.String value`  

```csharp
private readonly System.String value;
```


## Constructors

- `public ProxyString(System.String value)`  

```csharp
public ProxyString(System.String value);
```

- `public ProxyString(System.Char[] value)`  

```csharp
public ProxyString(System.Char[] value);
```

- `public ProxyString(System.Type value)`  

```csharp
public ProxyString(System.Type value);
```

- `public ProxyString(System.Guid value)`  

```csharp
public ProxyString(System.Guid value);
```

- `public ProxyString(System.Enum value)`  

```csharp
public ProxyString(System.Enum value);
```

- `public ProxyString(System.Net.IPAddress value)`  

```csharp
public ProxyString(System.Net.IPAddress value);
```

- `public ProxyString(System.DateTime value)`  

```csharp
public ProxyString(System.DateTime value);
```

- `public ProxyString(System.TimeSpan value)`  

```csharp
public ProxyString(System.TimeSpan value);
```

- `public ProxyString(Colossal.Logging.Level value)`  

```csharp
public ProxyString(Colossal.Logging.Level value);
```


## Methods

- `public virtual Equals(Colossal.Json.Variant other) : System.Boolean`  

```csharp
public virtual System.Boolean Equals(Colossal.Json.Variant other);
```

- `public virtual ToChar(System.IFormatProvider provider) : System.Char`  

```csharp
public virtual System.Char ToChar(System.IFormatProvider provider);
```

- `public virtual ToString(System.IFormatProvider provider) : System.String`  

```csharp
public virtual System.String ToString(System.IFormatProvider provider);
```


