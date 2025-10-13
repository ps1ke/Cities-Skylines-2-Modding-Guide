# Colossal.Mathematics.Quad3

**Assembly:** `Colossal.Mathematics`  
**Namespace:** `Colossal.Mathematics`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

**Attributes:** `Serializable`  

## Code

```csharp
public sealed struct Quad3
{
    public Unity.Mathematics.float3 a;
    public Unity.Mathematics.float3 b;
    public Unity.Mathematics.float3 c;
    public Unity.Mathematics.float3 d;

    public Colossal.Mathematics.Quad2 xy { get; set; }
    public Colossal.Mathematics.Quad2 xz { get; set; }
    public Colossal.Mathematics.Quad2 yx { get; set; }
    public Colossal.Mathematics.Quad2 yz { get; set; }
    public Colossal.Mathematics.Quad2 zx { get; set; }
    public Colossal.Mathematics.Quad2 zy { get; set; }
    public Colossal.Mathematics.Line3+Segment ab { get; }
    public Colossal.Mathematics.Line3+Segment ba { get; }
    public Colossal.Mathematics.Line3+Segment bc { get; }
    public Colossal.Mathematics.Line3+Segment cb { get; }
    public Colossal.Mathematics.Line3+Segment cd { get; }
    public Colossal.Mathematics.Line3+Segment dc { get; }
    public Colossal.Mathematics.Line3+Segment da { get; }
    public Colossal.Mathematics.Line3+Segment ad { get; }

    public Quad3(Unity.Mathematics.float3 _a, Unity.Mathematics.float3 _b, Unity.Mathematics.float3 _c, Unity.Mathematics.float3 _d);

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

- `public Unity.Mathematics.float3 d`  

```csharp
public Unity.Mathematics.float3 d;
```


## Properties

- `public Colossal.Mathematics.Quad2 xy { get; set }`  

```csharp
public Colossal.Mathematics.Quad2 xy { get; set; }
```

- `public Colossal.Mathematics.Quad2 xz { get; set }`  

```csharp
public Colossal.Mathematics.Quad2 xz { get; set; }
```

- `public Colossal.Mathematics.Quad2 yx { get; set }`  

```csharp
public Colossal.Mathematics.Quad2 yx { get; set; }
```

- `public Colossal.Mathematics.Quad2 yz { get; set }`  

```csharp
public Colossal.Mathematics.Quad2 yz { get; set; }
```

- `public Colossal.Mathematics.Quad2 zx { get; set }`  

```csharp
public Colossal.Mathematics.Quad2 zx { get; set; }
```

- `public Colossal.Mathematics.Quad2 zy { get; set }`  

```csharp
public Colossal.Mathematics.Quad2 zy { get; set; }
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

- `public Colossal.Mathematics.Line3+Segment cd { get }`  

```csharp
public Colossal.Mathematics.Line3+Segment cd { get; }
```

- `public Colossal.Mathematics.Line3+Segment dc { get }`  

```csharp
public Colossal.Mathematics.Line3+Segment dc { get; }
```

- `public Colossal.Mathematics.Line3+Segment da { get }`  

```csharp
public Colossal.Mathematics.Line3+Segment da { get; }
```

- `public Colossal.Mathematics.Line3+Segment ad { get }`  

```csharp
public Colossal.Mathematics.Line3+Segment ad { get; }
```


## Constructors

- `public Quad3(Unity.Mathematics.float3 _a, Unity.Mathematics.float3 _b, Unity.Mathematics.float3 _c, Unity.Mathematics.float3 _d)`  

```csharp
public Quad3(Unity.Mathematics.float3 _a, Unity.Mathematics.float3 _b, Unity.Mathematics.float3 _c, Unity.Mathematics.float3 _d);
```


