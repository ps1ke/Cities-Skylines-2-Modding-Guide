# Game.Tools.ControlPoint

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Game.Tools.ControlPoint>`  

## Code

```csharp
public sealed struct ControlPoint : System.IEquatable<Game.Tools.ControlPoint>
{
    public Unity.Mathematics.float3 m_Position;
    public Unity.Mathematics.float3 m_HitPosition;
    public Unity.Mathematics.float2 m_Direction;
    public Unity.Mathematics.float3 m_HitDirection;
    public Unity.Mathematics.quaternion m_Rotation;
    public Unity.Entities.Entity m_OriginalEntity;
    public Unity.Mathematics.float2 m_SnapPriority;
    public Unity.Mathematics.int2 m_ElementIndex;
    public System.Single m_CurvePosition;
    public System.Single m_Elevation;

    public ControlPoint(Unity.Entities.Entity raycastEntity, Game.Common.RaycastHit raycastHit);

    public System.Boolean Equals(Game.Tools.ControlPoint other);
    public System.Boolean EqualsIgnoreHit(Game.Tools.ControlPoint other);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `public Unity.Mathematics.float3 m_Position`  

```csharp
public Unity.Mathematics.float3 m_Position;
```

- `public Unity.Mathematics.float3 m_HitPosition`  

```csharp
public Unity.Mathematics.float3 m_HitPosition;
```

- `public Unity.Mathematics.float2 m_Direction`  

```csharp
public Unity.Mathematics.float2 m_Direction;
```

- `public Unity.Mathematics.float3 m_HitDirection`  

```csharp
public Unity.Mathematics.float3 m_HitDirection;
```

- `public Unity.Mathematics.quaternion m_Rotation`  

```csharp
public Unity.Mathematics.quaternion m_Rotation;
```

- `public Unity.Entities.Entity m_OriginalEntity`  

```csharp
public Unity.Entities.Entity m_OriginalEntity;
```

- `public Unity.Mathematics.float2 m_SnapPriority`  

```csharp
public Unity.Mathematics.float2 m_SnapPriority;
```

- `public Unity.Mathematics.int2 m_ElementIndex`  

```csharp
public Unity.Mathematics.int2 m_ElementIndex;
```

- `public System.Single m_CurvePosition`  

```csharp
public System.Single m_CurvePosition;
```

- `public System.Single m_Elevation`  

```csharp
public System.Single m_Elevation;
```


## Constructors

- `public ControlPoint(Unity.Entities.Entity raycastEntity, Game.Common.RaycastHit raycastHit)`  

```csharp
public ControlPoint(Unity.Entities.Entity raycastEntity, Game.Common.RaycastHit raycastHit);
```


## Methods

- `public Equals(Game.Tools.ControlPoint other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Tools.ControlPoint other);
```

- `public EqualsIgnoreHit(Game.Tools.ControlPoint other) : System.Boolean`  

```csharp
public System.Boolean EqualsIgnoreHit(Game.Tools.ControlPoint other);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```


