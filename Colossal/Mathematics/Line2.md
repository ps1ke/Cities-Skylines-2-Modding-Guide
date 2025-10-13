# Colossal.Mathematics.Line2

**Assembly:** `Colossal.Mathematics`  
**Namespace:** `Colossal.Mathematics`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

**Attributes:** `Serializable`  

## Code

```csharp
public sealed struct Line2
{
    public Unity.Mathematics.float2 a;
    public Unity.Mathematics.float2 b;

    public Colossal.Mathematics.Line1 x { get; set; }
    public Colossal.Mathematics.Line1 y { get; set; }
    public Unity.Mathematics.float4 ab { get; set; }

    public Line2(Unity.Mathematics.float2 _a, Unity.Mathematics.float2 _b);

}
```


## Fields

- `public Unity.Mathematics.float2 a`  

```csharp
public Unity.Mathematics.float2 a;
```

- `public Unity.Mathematics.float2 b`  

```csharp
public Unity.Mathematics.float2 b;
```


## Properties

- `public Colossal.Mathematics.Line1 x { get; set }`  

```csharp
public Colossal.Mathematics.Line1 x { get; set; }
```

- `public Colossal.Mathematics.Line1 y { get; set }`  

```csharp
public Colossal.Mathematics.Line1 y { get; set; }
```

- `public Unity.Mathematics.float4 ab { get; set }`  

```csharp
public Unity.Mathematics.float4 ab { get; set; }
```


## Constructors

- `public Line2(Unity.Mathematics.float2 _a, Unity.Mathematics.float2 _b)`  

```csharp
public Line2(Unity.Mathematics.float2 _a, Unity.Mathematics.float2 _b);
```


## Nested types

- `Colossal.Mathematics.Line2+Segment`  

