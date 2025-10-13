# Game.Rendering.Legacy.Plane

**Assembly:** `Game`  
**Namespace:** `Game.Rendering.Legacy`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct Plane
{
    private Unity.Mathematics.float3 m_Normal;
    private System.Single m_Distance;

    public Unity.Mathematics.float3 normal { get; set; }
    public System.Single distance { get; set; }
    public Game.Rendering.Legacy.Plane flipped { get; }

    public Plane(Unity.Mathematics.float3 inNormal, Unity.Mathematics.float3 inPoint);
    public Plane(Unity.Mathematics.float3 inNormal, System.Single d);
    public Plane(Unity.Mathematics.float3 a, Unity.Mathematics.float3 b, Unity.Mathematics.float3 c);

    public Unity.Mathematics.float3 ClosestPointOnPlane(Unity.Mathematics.float3 point);
    public System.Void Flip();
    public System.Single GetDistanceToPoint(Unity.Mathematics.float3 point);
    public System.Boolean GetSide(Unity.Mathematics.float3 point);
    public System.Boolean SameSide(Unity.Mathematics.float3 inPt0, Unity.Mathematics.float3 inPt1);
    public System.Void Set3Points(Unity.Mathematics.float3 a, Unity.Mathematics.float3 b, Unity.Mathematics.float3 c);
    public System.Void SetNormalAndPosition(Unity.Mathematics.float3 inNormal, Unity.Mathematics.float3 inPoint);
    public virtual System.String ToString();
    public System.Void Translate(Unity.Mathematics.float3 translation);
    public static Game.Rendering.Legacy.Plane Translate(Game.Rendering.Legacy.Plane plane, Unity.Mathematics.float3 translation);
}
```


## Fields

- `private Unity.Mathematics.float3 m_Normal`  

```csharp
private Unity.Mathematics.float3 m_Normal;
```

- `private System.Single m_Distance`  

```csharp
private System.Single m_Distance;
```


## Properties

- `public Unity.Mathematics.float3 normal { get; set }`  

```csharp
public Unity.Mathematics.float3 normal { get; set; }
```

- `public System.Single distance { get; set }`  

```csharp
public System.Single distance { get; set; }
```

- `public Game.Rendering.Legacy.Plane flipped { get }`  

```csharp
public Game.Rendering.Legacy.Plane flipped { get; }
```


## Constructors

- `public Plane(Unity.Mathematics.float3 inNormal, Unity.Mathematics.float3 inPoint)`  

```csharp
public Plane(Unity.Mathematics.float3 inNormal, Unity.Mathematics.float3 inPoint);
```

- `public Plane(Unity.Mathematics.float3 inNormal, System.Single d)`  

```csharp
public Plane(Unity.Mathematics.float3 inNormal, System.Single d);
```

- `public Plane(Unity.Mathematics.float3 a, Unity.Mathematics.float3 b, Unity.Mathematics.float3 c)`  

```csharp
public Plane(Unity.Mathematics.float3 a, Unity.Mathematics.float3 b, Unity.Mathematics.float3 c);
```


## Methods

- `public ClosestPointOnPlane(Unity.Mathematics.float3 point) : Unity.Mathematics.float3`  

```csharp
public Unity.Mathematics.float3 ClosestPointOnPlane(Unity.Mathematics.float3 point);
```

- `public Flip() : System.Void`  

```csharp
public System.Void Flip();
```

- `public GetDistanceToPoint(Unity.Mathematics.float3 point) : System.Single`  

```csharp
public System.Single GetDistanceToPoint(Unity.Mathematics.float3 point);
```

- `public GetSide(Unity.Mathematics.float3 point) : System.Boolean`  

```csharp
public System.Boolean GetSide(Unity.Mathematics.float3 point);
```

- `public SameSide(Unity.Mathematics.float3 inPt0, Unity.Mathematics.float3 inPt1) : System.Boolean`  

```csharp
public System.Boolean SameSide(Unity.Mathematics.float3 inPt0, Unity.Mathematics.float3 inPt1);
```

- `public Set3Points(Unity.Mathematics.float3 a, Unity.Mathematics.float3 b, Unity.Mathematics.float3 c) : System.Void`  

```csharp
public System.Void Set3Points(Unity.Mathematics.float3 a, Unity.Mathematics.float3 b, Unity.Mathematics.float3 c);
```

- `public SetNormalAndPosition(Unity.Mathematics.float3 inNormal, Unity.Mathematics.float3 inPoint) : System.Void`  

```csharp
public System.Void SetNormalAndPosition(Unity.Mathematics.float3 inNormal, Unity.Mathematics.float3 inPoint);
```

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```

- `public Translate(Unity.Mathematics.float3 translation) : System.Void`  

```csharp
public System.Void Translate(Unity.Mathematics.float3 translation);
```

- `public static Translate(Game.Rendering.Legacy.Plane plane, Unity.Mathematics.float3 translation) : Game.Rendering.Legacy.Plane`  

```csharp
public static Game.Rendering.Legacy.Plane Translate(Game.Rendering.Legacy.Plane plane, Unity.Mathematics.float3 translation);
```


