# Colossal.Mathematics.Triangle1

**Assembly:** `Colossal.Mathematics`  
**Namespace:** `Colossal.Mathematics`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

**Attributes:** `Serializable`  

## Code

```csharp
public sealed struct Triangle1
{
    public System.Single a;
    public System.Single b;
    public System.Single c;

    public Unity.Mathematics.float3 abc { get; set; }
    public Colossal.Mathematics.Line1+Segment ab { get; }
    public Colossal.Mathematics.Line1+Segment ba { get; }
    public Colossal.Mathematics.Line1+Segment bc { get; }
    public Colossal.Mathematics.Line1+Segment cb { get; }
    public Colossal.Mathematics.Line1+Segment ca { get; }
    public Colossal.Mathematics.Line2+Segment ac { get; }

    public Triangle1(System.Single _a, System.Single _b, System.Single _c);

}
```


## Fields

- `public System.Single a`  

```csharp
public System.Single a;
```

- `public System.Single b`  

```csharp
public System.Single b;
```

- `public System.Single c`  

```csharp
public System.Single c;
```


## Properties

- `public Unity.Mathematics.float3 abc { get; set }`  

```csharp
public Unity.Mathematics.float3 abc { get; set; }
```

- `public Colossal.Mathematics.Line1+Segment ab { get }`  

```csharp
public Colossal.Mathematics.Line1+Segment ab { get; }
```

- `public Colossal.Mathematics.Line1+Segment ba { get }`  

```csharp
public Colossal.Mathematics.Line1+Segment ba { get; }
```

- `public Colossal.Mathematics.Line1+Segment bc { get }`  

```csharp
public Colossal.Mathematics.Line1+Segment bc { get; }
```

- `public Colossal.Mathematics.Line1+Segment cb { get }`  

```csharp
public Colossal.Mathematics.Line1+Segment cb { get; }
```

- `public Colossal.Mathematics.Line1+Segment ca { get }`  

```csharp
public Colossal.Mathematics.Line1+Segment ca { get; }
```

- `public Colossal.Mathematics.Line2+Segment ac { get }`  

```csharp
public Colossal.Mathematics.Line2+Segment ac { get; }
```


## Constructors

- `public Triangle1(System.Single _a, System.Single _b, System.Single _c)`  

```csharp
public Triangle1(System.Single _a, System.Single _b, System.Single _c);
```


