# Colossal.Mathematics.Bounds2

**Assembly:** `Colossal.Mathematics`  
**Namespace:** `Colossal.Mathematics`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Colossal.Mathematics.Bounds2>`, `Colossal.Mathematics.IBounds2<Colossal.Mathematics.Bounds2>`  

**Attributes:** `Serializable`  

## Code

```csharp
public sealed struct Bounds2 : System.IEquatable<Colossal.Mathematics.Bounds2>, Colossal.Mathematics.IBounds2<Colossal.Mathematics.Bounds2>
{
    public Unity.Mathematics.float2 min;
    public Unity.Mathematics.float2 max;

    public Colossal.Mathematics.Bounds1 x { get; set; }
    public Colossal.Mathematics.Bounds1 y { get; set; }

    public Bounds2(Unity.Mathematics.float2 _min, Unity.Mathematics.float2 _max);

    public Unity.Mathematics.float2 Center();
    public System.Boolean Equals(Colossal.Mathematics.Bounds2 other);
    public System.Boolean Intersect(Colossal.Mathematics.Bounds2 other);
    public Colossal.Mathematics.Bounds2 Merge(Colossal.Mathematics.Bounds2 other);
    public System.Void Reset();
    public Unity.Mathematics.float2 Size();
}
```


## Fields

- `public Unity.Mathematics.float2 min`  

```csharp
public Unity.Mathematics.float2 min;
```

- `public Unity.Mathematics.float2 max`  

```csharp
public Unity.Mathematics.float2 max;
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


## Constructors

- `public Bounds2(Unity.Mathematics.float2 _min, Unity.Mathematics.float2 _max)`  

```csharp
public Bounds2(Unity.Mathematics.float2 _min, Unity.Mathematics.float2 _max);
```


## Methods

- `public Center() : Unity.Mathematics.float2`  

```csharp
public Unity.Mathematics.float2 Center();
```

- `public Equals(Colossal.Mathematics.Bounds2 other) : System.Boolean`  

```csharp
public System.Boolean Equals(Colossal.Mathematics.Bounds2 other);
```

- `public Intersect(Colossal.Mathematics.Bounds2 other) : System.Boolean`  

```csharp
public System.Boolean Intersect(Colossal.Mathematics.Bounds2 other);
```

- `public Merge(Colossal.Mathematics.Bounds2 other) : Colossal.Mathematics.Bounds2`  

```csharp
public Colossal.Mathematics.Bounds2 Merge(Colossal.Mathematics.Bounds2 other);
```

- `public Reset() : System.Void`  

```csharp
public System.Void Reset();
```

- `public Size() : Unity.Mathematics.float2`  

```csharp
public Unity.Mathematics.float2 Size();
```


