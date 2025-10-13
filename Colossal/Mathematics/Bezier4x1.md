# Colossal.Mathematics.Bezier4x1

**Assembly:** `Colossal.Mathematics`  
**Namespace:** `Colossal.Mathematics`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

**Attributes:** `Serializable`  

## Code

```csharp
public sealed struct Bezier4x1
{
    public System.Single a;
    public System.Single b;
    public System.Single c;
    public System.Single d;

    public Unity.Mathematics.float4 abcd { get; set; }

    public Bezier4x1(System.Single _a, System.Single _b, System.Single _c, System.Single _d);
    public Bezier4x1(Unity.Mathematics.float4 _abcd);

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

- `public System.Single d`  

```csharp
public System.Single d;
```


## Properties

- `public Unity.Mathematics.float4 abcd { get; set }`  

```csharp
public Unity.Mathematics.float4 abcd { get; set; }
```


## Constructors

- `public Bezier4x1(System.Single _a, System.Single _b, System.Single _c, System.Single _d)`  

```csharp
public Bezier4x1(System.Single _a, System.Single _b, System.Single _c, System.Single _d);
```

- `public Bezier4x1(Unity.Mathematics.float4 _abcd)`  

```csharp
public Bezier4x1(Unity.Mathematics.float4 _abcd);
```


