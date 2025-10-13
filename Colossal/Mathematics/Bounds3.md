# Colossal.Mathematics.Bounds3

**Assembly:** `Colossal.Mathematics`  
**Namespace:** `Colossal.Mathematics`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Colossal.Mathematics.Bounds3>`  

**Attributes:** `Serializable`  

## Code

```csharp
public sealed struct Bounds3 : System.IEquatable<Colossal.Mathematics.Bounds3>
{
    public Unity.Mathematics.float3 min;
    public Unity.Mathematics.float3 max;

    public Colossal.Mathematics.Bounds1 x { get; set; }
    public Colossal.Mathematics.Bounds1 y { get; set; }
    public Colossal.Mathematics.Bounds1 z { get; set; }
    public Colossal.Mathematics.Bounds2 xy { get; set; }
    public Colossal.Mathematics.Bounds2 xz { get; set; }
    public Colossal.Mathematics.Bounds2 yx { get; set; }
    public Colossal.Mathematics.Bounds2 yz { get; set; }
    public Colossal.Mathematics.Bounds2 zx { get; set; }
    public Colossal.Mathematics.Bounds2 zy { get; set; }

    public Bounds3(Unity.Mathematics.float3 _min, Unity.Mathematics.float3 _max);
    public Bounds3(UnityEngine.Bounds bounds);

    public System.Boolean Equals(Colossal.Mathematics.Bounds3 other);
    public System.Void Reset();
}
```


## Fields

- `public Unity.Mathematics.float3 min`  

```csharp
public Unity.Mathematics.float3 min;
```

- `public Unity.Mathematics.float3 max`  

```csharp
public Unity.Mathematics.float3 max;
```


## Properties

- `public Colossal.Mathematics.Bounds1 x { get; set }`  

```csharp
public Colossal.Mathematics.Bounds1 x { get; set; }
```

- `public Colossal.Mathematics.Bounds1 y { get; set }`  

```csharp
public Colossal.Mathematics.Bounds1 y { get; set; }
```

- `public Colossal.Mathematics.Bounds1 z { get; set }`  

```csharp
public Colossal.Mathematics.Bounds1 z { get; set; }
```

- `public Colossal.Mathematics.Bounds2 xy { get; set }`  

```csharp
public Colossal.Mathematics.Bounds2 xy { get; set; }
```

- `public Colossal.Mathematics.Bounds2 xz { get; set }`  

```csharp
public Colossal.Mathematics.Bounds2 xz { get; set; }
```

- `public Colossal.Mathematics.Bounds2 yx { get; set }`  

```csharp
public Colossal.Mathematics.Bounds2 yx { get; set; }
```

- `public Colossal.Mathematics.Bounds2 yz { get; set }`  

```csharp
public Colossal.Mathematics.Bounds2 yz { get; set; }
```

- `public Colossal.Mathematics.Bounds2 zx { get; set }`  

```csharp
public Colossal.Mathematics.Bounds2 zx { get; set; }
```

- `public Colossal.Mathematics.Bounds2 zy { get; set }`  

```csharp
public Colossal.Mathematics.Bounds2 zy { get; set; }
```


## Constructors

- `public Bounds3(Unity.Mathematics.float3 _min, Unity.Mathematics.float3 _max)`  

```csharp
public Bounds3(Unity.Mathematics.float3 _min, Unity.Mathematics.float3 _max);
```

- `public Bounds3(UnityEngine.Bounds bounds)`  

```csharp
public Bounds3(UnityEngine.Bounds bounds);
```


## Methods

- `public Equals(Colossal.Mathematics.Bounds3 other) : System.Boolean`  

```csharp
public System.Boolean Equals(Colossal.Mathematics.Bounds3 other);
```

- `public Reset() : System.Void`  

```csharp
public System.Void Reset();
```


