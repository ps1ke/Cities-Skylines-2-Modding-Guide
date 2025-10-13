# Colossal.Mathematics.Triangle2

**Assembly:** `Colossal.Mathematics`  
**Namespace:** `Colossal.Mathematics`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

**Attributes:** `Serializable`  

## Code

```csharp
public sealed struct Triangle2
{
    public Unity.Mathematics.float2 a;
    public Unity.Mathematics.float2 b;
    public Unity.Mathematics.float2 c;

    public Colossal.Mathematics.Triangle1 x { get; set; }
    public Colossal.Mathematics.Triangle1 y { get; set; }
    public Colossal.Mathematics.Line2+Segment ab { get; }
    public Colossal.Mathematics.Line2+Segment ba { get; }
    public Colossal.Mathematics.Line2+Segment bc { get; }
    public Colossal.Mathematics.Line2+Segment cb { get; }
    public Colossal.Mathematics.Line2+Segment ca { get; }
    public Colossal.Mathematics.Line2+Segment ac { get; }

    public Triangle2(Unity.Mathematics.float2 _a, Unity.Mathematics.float2 _b, Unity.Mathematics.float2 _c);

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

- `public Unity.Mathematics.float2 c`  

```csharp
public Unity.Mathematics.float2 c;
```


## Properties

- `public Colossal.Mathematics.Triangle1 x { get; set }`  

```csharp
public Colossal.Mathematics.Triangle1 x { get; set; }
```

- `public Colossal.Mathematics.Triangle1 y { get; set }`  

```csharp
public Colossal.Mathematics.Triangle1 y { get; set; }
```

- `public Colossal.Mathematics.Line2+Segment ab { get }`  

```csharp
public Colossal.Mathematics.Line2+Segment ab { get; }
```

- `public Colossal.Mathematics.Line2+Segment ba { get }`  

```csharp
public Colossal.Mathematics.Line2+Segment ba { get; }
```

- `public Colossal.Mathematics.Line2+Segment bc { get }`  

```csharp
public Colossal.Mathematics.Line2+Segment bc { get; }
```

- `public Colossal.Mathematics.Line2+Segment cb { get }`  

```csharp
public Colossal.Mathematics.Line2+Segment cb { get; }
```

- `public Colossal.Mathematics.Line2+Segment ca { get }`  

```csharp
public Colossal.Mathematics.Line2+Segment ca { get; }
```

- `public Colossal.Mathematics.Line2+Segment ac { get }`  

```csharp
public Colossal.Mathematics.Line2+Segment ac { get; }
```


## Constructors

- `public Triangle2(Unity.Mathematics.float2 _a, Unity.Mathematics.float2 _b, Unity.Mathematics.float2 _c)`  

```csharp
public Triangle2(Unity.Mathematics.float2 _a, Unity.Mathematics.float2 _b, Unity.Mathematics.float2 _c);
```


