# Colossal.Atmosphere.JulianDateTime

**Assembly:** `Game`  
**Namespace:** `Colossal.Atmosphere`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct JulianDateTime
{
    private System.Int64 m_Day;
    private System.Double m_Fraction;
    private static readonly Colossal.Atmosphere.JulianDateTime J2000;
    private static const System.Double kSecPerDay;
    private static const System.Double kOmegaE;

    public JulianDateTime(System.Double j);
    public JulianDateTime(Colossal.Atmosphere.JulianDateTime j);
    public JulianDateTime(System.DateTime utc);

    public System.Void AddSeconds(System.Double seconds);
    public System.Double Subtract(Colossal.Atmosphere.JulianDateTime j);
    public System.Double Subtract(System.Double j);
    public System.DateTime ToDateTime();
    public System.Double ToDouble();
    public System.Double ToGMST();
    public System.Double ToLMST(System.Double longitude);
    public virtual System.String ToString();
}
```


## Fields

- `private System.Int64 m_Day`  

```csharp
private System.Int64 m_Day;
```

- `private System.Double m_Fraction`  

```csharp
private System.Double m_Fraction;
```

- `private static readonly Colossal.Atmosphere.JulianDateTime J2000`  

```csharp
private static readonly Colossal.Atmosphere.JulianDateTime J2000;
```

- `private static const System.Double kSecPerDay`  

```csharp
private static const System.Double kSecPerDay;
```

- `private static const System.Double kOmegaE`  

```csharp
private static const System.Double kOmegaE;
```


## Constructors

- `public JulianDateTime(System.Double j)`  

```csharp
public JulianDateTime(System.Double j);
```

- `public JulianDateTime(Colossal.Atmosphere.JulianDateTime j)`  

```csharp
public JulianDateTime(Colossal.Atmosphere.JulianDateTime j);
```

- `public JulianDateTime(System.DateTime utc)`  

```csharp
public JulianDateTime(System.DateTime utc);
```


## Methods

- `public AddSeconds(System.Double seconds) : System.Void`  

```csharp
public System.Void AddSeconds(System.Double seconds);
```

- `public Subtract(Colossal.Atmosphere.JulianDateTime j) : System.Double`  

```csharp
public System.Double Subtract(Colossal.Atmosphere.JulianDateTime j);
```

- `public Subtract(System.Double j) : System.Double`  

```csharp
public System.Double Subtract(System.Double j);
```

- `public ToDateTime() : System.DateTime`  

```csharp
public System.DateTime ToDateTime();
```

- `public ToDouble() : System.Double`  

```csharp
public System.Double ToDouble();
```

- `public ToGMST() : System.Double`  

```csharp
public System.Double ToGMST();
```

- `public ToLMST(System.Double longitude) : System.Double`  

```csharp
public System.Double ToLMST(System.Double longitude);
```

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```


