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
public Plane(float3 a, float3 b, float3 c)
	{
		m_Normal = math.normalize(math.cross(b - a, c - a));
		m_Distance = 0f - math.dot(m_Normal, a);
	}
```

- `public Plane(Unity.Mathematics.float3 inNormal, System.Single d)`  

```csharp
public Plane(float3 a, float3 b, float3 c)
	{
		m_Normal = math.normalize(math.cross(b - a, c - a));
		m_Distance = 0f - math.dot(m_Normal, a);
	}
```

- `public Plane(Unity.Mathematics.float3 a, Unity.Mathematics.float3 b, Unity.Mathematics.float3 c)`  

```csharp
public Plane(float3 a, float3 b, float3 c)
	{
		m_Normal = math.normalize(math.cross(b - a, c - a));
		m_Distance = 0f - math.dot(m_Normal, a);
	}
```


## Methods

- `public ClosestPointOnPlane(Unity.Mathematics.float3 point) : Unity.Mathematics.float3`  

```csharp
public float3 ClosestPointOnPlane(float3 point)
	{
		float num = math.dot(m_Normal, point) + m_Distance;
		return point - m_Normal * num;
	}
```

- `public Flip() : System.Void`  

```csharp
public void Flip()
	{
		m_Normal = -m_Normal;
		m_Distance = 0f - m_Distance;
	}
```

- `public GetDistanceToPoint(Unity.Mathematics.float3 point) : System.Single`  

```csharp
public float GetDistanceToPoint(float3 point)
	{
		return math.dot(m_Normal, point) + m_Distance;
	}
```

- `public GetSide(Unity.Mathematics.float3 point) : System.Boolean`  

```csharp
public bool GetSide(float3 point)
	{
		return math.dot(m_Normal, point) + m_Distance > 0f;
	}
```

- `public SameSide(Unity.Mathematics.float3 inPt0, Unity.Mathematics.float3 inPt1) : System.Boolean`  

```csharp
public bool SameSide(float3 inPt0, float3 inPt1)
	{
		float distanceToPoint = GetDistanceToPoint(inPt0);
		float distanceToPoint2 = GetDistanceToPoint(inPt1);
		if (!(distanceToPoint > 0f) || !(distanceToPoint2 > 0f))
		{
			if (distanceToPoint <= 0f)
			{
				return distanceToPoint2 <= 0f;
			}
			return false;
		}
		return true;
	}
```

- `public Set3Points(Unity.Mathematics.float3 a, Unity.Mathematics.float3 b, Unity.Mathematics.float3 c) : System.Void`  

```csharp
public void Set3Points(float3 a, float3 b, float3 c)
	{
		m_Normal = math.normalize(math.cross(b - a, c - a));
		m_Distance = 0f - math.dot(m_Normal, a);
	}
```

- `public SetNormalAndPosition(Unity.Mathematics.float3 inNormal, Unity.Mathematics.float3 inPoint) : System.Void`  

```csharp
public void SetNormalAndPosition(float3 inNormal, float3 inPoint)
	{
		m_Normal = math.normalize(inNormal);
		m_Distance = 0f - math.dot(inNormal, inPoint);
	}
```

- `public virtual ToString() : System.String`  

```csharp
public override string ToString()
	{
		return $"(normal:({m_Normal.x:F1}, {m_Normal.y:F1}, {m_Normal.z:F1}), distance:{m_Distance:F1})";
	}
```

- `public Translate(Unity.Mathematics.float3 translation) : System.Void`  

```csharp
public static Plane Translate(Plane plane, float3 translation)
	{
		return new Plane(plane.m_Normal, plane.m_Distance += math.dot(plane.m_Normal, translation));
	}
```

- `public static Translate(Game.Rendering.Legacy.Plane plane, Unity.Mathematics.float3 translation) : Game.Rendering.Legacy.Plane`  

```csharp
public static Plane Translate(Plane plane, float3 translation)
	{
		return new Plane(plane.m_Normal, plane.m_Distance += math.dot(plane.m_Normal, translation));
	}
```


