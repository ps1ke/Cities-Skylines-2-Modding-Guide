# Colossal.Mathematics.Line3+Segment

**Assembly:** `Colossal.Mathematics`  
**Namespace:** `Colossal.Mathematics`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

**Attributes:** `Serializable`  

## Code

```csharp
public sealed struct Segment
{
    public Unity.Mathematics.float3 a;
    public Unity.Mathematics.float3 b;

    public Unity.Mathematics.float3 ab { get; }
    public Unity.Mathematics.float3 ba { get; }
    public Colossal.Mathematics.Line1+Segment x { get; set; }
    public Colossal.Mathematics.Line1+Segment y { get; set; }
    public Colossal.Mathematics.Line1+Segment z { get; set; }
    public Colossal.Mathematics.Line2+Segment xy { get; set; }
    public Colossal.Mathematics.Line2+Segment xz { get; set; }
    public Colossal.Mathematics.Line2+Segment yx { get; set; }
    public Colossal.Mathematics.Line2+Segment yz { get; set; }
    public Colossal.Mathematics.Line2+Segment zx { get; set; }
    public Colossal.Mathematics.Line2+Segment zy { get; set; }

    public Segment(Unity.Mathematics.float3 _a, Unity.Mathematics.float3 _b);

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


## Properties

- `public Unity.Mathematics.float3 ab { get }`  

```csharp
public Unity.Mathematics.float3 ab { get; }
```

- `public Unity.Mathematics.float3 ba { get }`  

```csharp
public Unity.Mathematics.float3 ba { get; }
```

- `public Colossal.Mathematics.Line1+Segment x { get; set }`  

```csharp
public Colossal.Mathematics.Line1+Segment x { get; set; }
```

- `public Colossal.Mathematics.Line1+Segment y { get; set }`  

```csharp
public Colossal.Mathematics.Line1+Segment y { get; set; }
```

- `public Colossal.Mathematics.Line1+Segment z { get; set }`  

```csharp
public Colossal.Mathematics.Line1+Segment z { get; set; }
```

- `public Colossal.Mathematics.Line2+Segment xy { get; set }`  

```csharp
public Colossal.Mathematics.Line2+Segment xy { get; set; }
```

- `public Colossal.Mathematics.Line2+Segment xz { get; set }`  

```csharp
public Colossal.Mathematics.Line2+Segment xz { get; set; }
```

- `public Colossal.Mathematics.Line2+Segment yx { get; set }`  

```csharp
public Colossal.Mathematics.Line2+Segment yx { get; set; }
```

- `public Colossal.Mathematics.Line2+Segment yz { get; set }`  

```csharp
public Colossal.Mathematics.Line2+Segment yz { get; set; }
```

- `public Colossal.Mathematics.Line2+Segment zx { get; set }`  

```csharp
public Colossal.Mathematics.Line2+Segment zx { get; set; }
```

- `public Colossal.Mathematics.Line2+Segment zy { get; set }`  

```csharp
public Colossal.Mathematics.Line2+Segment zy { get; set; }
```


## Constructors

- `public Segment(Unity.Mathematics.float3 _a, Unity.Mathematics.float3 _b)`  

```csharp
public Segment(Unity.Mathematics.float3 _a, Unity.Mathematics.float3 _b);
```


