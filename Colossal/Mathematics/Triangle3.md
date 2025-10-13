# Colossal.Mathematics.Triangle3

**Assembly:** `Colossal.Mathematics`  
**Namespace:** `Colossal.Mathematics`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

**Attributes:** `Serializable`  

## Code

```csharp
public sealed struct Triangle3
{
    public Unity.Mathematics.float3 a;
    public Unity.Mathematics.float3 b;
    public Unity.Mathematics.float3 c;

    public Colossal.Mathematics.Triangle1 x { get; set; }
    public Colossal.Mathematics.Triangle1 y { get; set; }
    public Colossal.Mathematics.Triangle1 z { get; set; }
    public Colossal.Mathematics.Triangle2 xy { get; set; }
    public Colossal.Mathematics.Triangle2 xz { get; set; }
    public Colossal.Mathematics.Triangle2 yx { get; set; }
    public Colossal.Mathematics.Triangle2 yz { get; set; }
    public Colossal.Mathematics.Triangle2 zx { get; set; }
    public Colossal.Mathematics.Triangle2 zy { get; set; }
    public Colossal.Mathematics.Line3+Segment ab { get; }
    public Colossal.Mathematics.Line3+Segment ba { get; }
    public Colossal.Mathematics.Line3+Segment bc { get; }
    public Colossal.Mathematics.Line3+Segment cb { get; }
    public Colossal.Mathematics.Line3+Segment ca { get; }
    public Colossal.Mathematics.Line3+Segment ac { get; }

    public Triangle3(Unity.Mathematics.float3 _a, Unity.Mathematics.float3 _b, Unity.Mathematics.float3 _c);

}
```


## Fields

- `public Unity.Mathematics.float3 a`  

```csharp
public Unity.Mathematics.float3 a;
```

- `public Unity.Mathematics.float3 b`  

```csharp
public Unity.Mathematics.float3 b;
```

- `public Unity.Mathematics.float3 c`  

```csharp
public Unity.Mathematics.float3 c;
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

- `public Colossal.Mathematics.Triangle1 z { get; set }`  

```csharp
public Colossal.Mathematics.Triangle1 z { get; set; }
```

- `public Colossal.Mathematics.Triangle2 xy { get; set }`  

```csharp
public Colossal.Mathematics.Triangle2 xy { get; set; }
```

- `public Colossal.Mathematics.Triangle2 xz { get; set }`  

```csharp
public Colossal.Mathematics.Triangle2 xz { get; set; }
```

- `public Colossal.Mathematics.Triangle2 yx { get; set }`  

```csharp
public Colossal.Mathematics.Triangle2 yx { get; set; }
```

- `public Colossal.Mathematics.Triangle2 yz { get; set }`  

```csharp
public Colossal.Mathematics.Triangle2 yz { get; set; }
```

- `public Colossal.Mathematics.Triangle2 zx { get; set }`  

```csharp
public Colossal.Mathematics.Triangle2 zx { get; set; }
```

- `public Colossal.Mathematics.Triangle2 zy { get; set }`  

```csharp
public Colossal.Mathematics.Triangle2 zy { get; set; }
```

- `public Colossal.Mathematics.Line3+Segment ab { get }`  

```csharp
public Colossal.Mathematics.Line3+Segment ab { get; }
```

- `public Colossal.Mathematics.Line3+Segment ba { get }`  

```csharp
public Colossal.Mathematics.Line3+Segment ba { get; }
```

- `public Colossal.Mathematics.Line3+Segment bc { get }`  

```csharp
public Colossal.Mathematics.Line3+Segment bc { get; }
```

- `public Colossal.Mathematics.Line3+Segment cb { get }`  

```csharp
public Colossal.Mathematics.Line3+Segment cb { get; }
```

- `public Colossal.Mathematics.Line3+Segment ca { get }`  

```csharp
public Colossal.Mathematics.Line3+Segment ca { get; }
```

- `public Colossal.Mathematics.Line3+Segment ac { get }`  

```csharp
public Colossal.Mathematics.Line3+Segment ac { get; }
```


## Constructors

- `public Triangle3(Unity.Mathematics.float3 _a, Unity.Mathematics.float3 _b, Unity.Mathematics.float3 _c)`  

```csharp
public Triangle3(Unity.Mathematics.float3 _a, Unity.Mathematics.float3 _b, Unity.Mathematics.float3 _c);
```


