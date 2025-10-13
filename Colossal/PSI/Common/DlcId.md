# Colossal.PSI.Common.DlcId

**Assembly:** `Colossal.PSI.Common`  
**Namespace:** `Colossal.PSI.Common`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Colossal.PSI.Common.DlcId>`  

**Attributes:** `Serializable`  

## Code

```csharp
public sealed struct DlcId : System.IEquatable<Colossal.PSI.Common.DlcId>
{
    public System.Int32 id;
    public static readonly Colossal.PSI.Common.DlcId Invalid;
    public static readonly Colossal.PSI.Common.DlcId Virtual;
    public static readonly Colossal.PSI.Common.DlcId BaseGame;

    public DlcId(System.Int32 id);

    public System.Boolean Equals(Colossal.PSI.Common.DlcId other);
    public virtual System.Boolean Equals(System.Object obj);
    public virtual System.Int32 GetHashCode();
    public virtual System.String ToString();
}
```


## Fields

- `public System.Int32 id`  

```csharp
public System.Int32 id;
```

- `public static readonly Colossal.PSI.Common.DlcId Invalid`  

```csharp
public static readonly Colossal.PSI.Common.DlcId Invalid;
```

- `public static readonly Colossal.PSI.Common.DlcId Virtual`  

```csharp
public static readonly Colossal.PSI.Common.DlcId Virtual;
```

- `public static readonly Colossal.PSI.Common.DlcId BaseGame`  

```csharp
public static readonly Colossal.PSI.Common.DlcId BaseGame;
```


## Constructors

- `public DlcId(System.Int32 id)`  

```csharp
public DlcId(System.Int32 id);
```


## Methods

- `public Equals(Colossal.PSI.Common.DlcId other) : System.Boolean`  

```csharp
public System.Boolean Equals(Colossal.PSI.Common.DlcId other);
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


