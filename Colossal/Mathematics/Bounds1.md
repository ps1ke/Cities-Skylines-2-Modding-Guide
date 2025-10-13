# Colossal.Mathematics.Bounds1

**Assembly:** `Colossal.Mathematics`  
**Namespace:** `Colossal.Mathematics`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Colossal.Mathematics.Bounds1>`  

**Attributes:** `Serializable`  

## Code

```csharp
public sealed struct Bounds1 : System.IEquatable<Colossal.Mathematics.Bounds1>
{
    public System.Single min;
    public System.Single max;

    public Bounds1(System.Single _min, System.Single _max);
    public Bounds1(Unity.Mathematics.float2 minmax);

    public System.Boolean Equals(Colossal.Mathematics.Bounds1 other);
    public virtual System.Boolean Equals(System.Object obj);
    public virtual System.Int32 GetHashCode();
    public virtual System.String ToString();
}
```


## Fields

- `public System.Single min`  

```csharp
public System.Single min;
```

- `public System.Single max`  

```csharp
public System.Single max;
```


## Constructors

- `public Bounds1(System.Single _min, System.Single _max)`  

```csharp
public Bounds1(System.Single _min, System.Single _max);
```

- `public Bounds1(Unity.Mathematics.float2 minmax)`  

```csharp
public Bounds1(Unity.Mathematics.float2 minmax);
```


## Methods

- `public Equals(Colossal.Mathematics.Bounds1 other) : System.Boolean`  

```csharp
public System.Boolean Equals(Colossal.Mathematics.Bounds1 other);
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


