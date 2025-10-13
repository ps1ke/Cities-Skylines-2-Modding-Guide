# Colossal.Mathematics.Bezier4x2

**Assembly:** `Colossal.Mathematics`  
**Namespace:** `Colossal.Mathematics`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

**Attributes:** `Serializable`  

## Code

```csharp
public sealed struct Bezier4x2
{
    public Unity.Mathematics.float2 a;
    public Unity.Mathematics.float2 b;
    public Unity.Mathematics.float2 c;
    public Unity.Mathematics.float2 d;

    public Colossal.Mathematics.Bezier4x1 x { get; set; }
    public Colossal.Mathematics.Bezier4x1 y { get; set; }
    public Unity.Mathematics.float4 ab { get; set; }
    public Unity.Mathematics.float4 cd { get; set; }

    public Bezier4x2(Unity.Mathematics.float2 _a, Unity.Mathematics.float2 _b, Unity.Mathematics.float2 _c, Unity.Mathematics.float2 _d);

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

- `public Colossal.Mathematics.Bezier4x1 x { get; set }`  

```csharp
public Colossal.Mathematics.Bezier4x1 x { get; set; }
```

- `public Colossal.Mathematics.Bezier4x1 y { get; set }`  

```csharp
public Colossal.Mathematics.Bezier4x1 y { get; set; }
```

- `public Unity.Mathematics.float4 ab { get; set }`  

```csharp
public Unity.Mathematics.float4 ab { get; set; }
```

- `public Unity.Mathematics.float4 cd { get; set }`  

```csharp
public Unity.Mathematics.float4 cd { get; set; }
```


## Constructors

- `public Bezier4x2(Unity.Mathematics.float2 _a, Unity.Mathematics.float2 _b, Unity.Mathematics.float2 _c, Unity.Mathematics.float2 _d)`  

```csharp
public Bezier4x2(Unity.Mathematics.float2 _a, Unity.Mathematics.float2 _b, Unity.Mathematics.float2 _c, Unity.Mathematics.float2 _d);
```


