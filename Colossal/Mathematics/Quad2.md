# Colossal.Mathematics.Quad2

**Assembly:** `Colossal.Mathematics`  
**Namespace:** `Colossal.Mathematics`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

**Attributes:** `Serializable`  

## Code

```csharp
public sealed struct Quad2
{
    public Unity.Mathematics.float2 a;
    public Unity.Mathematics.float2 b;
    public Unity.Mathematics.float2 c;
    public Unity.Mathematics.float2 d;

    public Colossal.Mathematics.Line2+Segment ab { get; }
    public Colossal.Mathematics.Line2+Segment ba { get; }
    public Colossal.Mathematics.Line2+Segment bc { get; }
    public Colossal.Mathematics.Line2+Segment cb { get; }
    public Colossal.Mathematics.Line2+Segment cd { get; }
    public Colossal.Mathematics.Line2+Segment dc { get; }
    public Colossal.Mathematics.Line2+Segment da { get; }
    public Colossal.Mathematics.Line2+Segment ad { get; }

    public Quad2(Unity.Mathematics.float2 _a, Unity.Mathematics.float2 _b, Unity.Mathematics.float2 _c, Unity.Mathematics.float2 _d);

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

- `public Unity.Mathematics.float2 d`  

```csharp
public Unity.Mathematics.float2 d;
```


## Properties

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

- `public Colossal.Mathematics.Line2+Segment cd { get }`  

```csharp
public Colossal.Mathematics.Line2+Segment cd { get; }
```

- `public Colossal.Mathematics.Line2+Segment dc { get }`  

```csharp
public Colossal.Mathematics.Line2+Segment dc { get; }
```

- `public Colossal.Mathematics.Line2+Segment da { get }`  

```csharp
public Colossal.Mathematics.Line2+Segment da { get; }
```

- `public Colossal.Mathematics.Line2+Segment ad { get }`  

```csharp
public Colossal.Mathematics.Line2+Segment ad { get; }
```


## Constructors

- `public Quad2(Unity.Mathematics.float2 _a, Unity.Mathematics.float2 _b, Unity.Mathematics.float2 _c, Unity.Mathematics.float2 _d)`  

```csharp
public Quad2(Unity.Mathematics.float2 _a, Unity.Mathematics.float2 _b, Unity.Mathematics.float2 _c, Unity.Mathematics.float2 _d);
```


