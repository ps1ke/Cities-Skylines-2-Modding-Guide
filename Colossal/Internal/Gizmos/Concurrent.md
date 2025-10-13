# Colossal.Internal.Gizmos.GizmoObjects+Concurrent

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Internal.Gizmos`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct Concurrent
{
    internal Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoBezier4x3> m_GizmoBezier4x3;
    internal Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoArrowHead> m_GizmoArrowHead;
    internal Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoLine> m_GizmoLine;
    internal Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoSphere> m_GizmoSphere;
    internal Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoCube> m_GizmoCube;
    internal Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoCylinder> m_GizmoCylinder;
    internal Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoArc> m_GizmoArc;
    internal Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoCapsule> m_GizmoCapsule;
    internal Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoCone> m_GizmoCone;
    internal Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoCapsuleConic> m_GizmoCapsuleConic;
    internal Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoFrustum> m_GizmoFrustum;

    public System.Void Enqueue(Colossal.Internal.Gizmos.GizmoBezier4x3 bezier);
    public System.Void Enqueue(Colossal.Internal.Gizmos.GizmoArrowHead arrowHead);
    public System.Void Enqueue(Colossal.Internal.Gizmos.GizmoLine line);
    public System.Void Enqueue(Colossal.Internal.Gizmos.GizmoSphere sphere);
    public System.Void Enqueue(Colossal.Internal.Gizmos.GizmoCube cube);
    public System.Void Enqueue(Colossal.Internal.Gizmos.GizmoCylinder cylinder);
    public System.Void Enqueue(Colossal.Internal.Gizmos.GizmoArc arc);
    public System.Void Enqueue(Colossal.Internal.Gizmos.GizmoCapsule capsule);
    public System.Void Enqueue(Colossal.Internal.Gizmos.GizmoCone cone);
    public System.Void Enqueue(Colossal.Internal.Gizmos.GizmoCapsuleConic capsuleConic);
    public System.Void Enqueue(Colossal.Internal.Gizmos.GizmoFrustum frustum);
}
```


## Fields

- `internal Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoBezier4x3> m_GizmoBezier4x3`  

```csharp
internal Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoBezier4x3> m_GizmoBezier4x3;
```

- `internal Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoArrowHead> m_GizmoArrowHead`  

```csharp
internal Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoArrowHead> m_GizmoArrowHead;
```

- `internal Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoLine> m_GizmoLine`  

```csharp
internal Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoLine> m_GizmoLine;
```

- `internal Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoSphere> m_GizmoSphere`  

```csharp
internal Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoSphere> m_GizmoSphere;
```

- `internal Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoCube> m_GizmoCube`  

```csharp
internal Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoCube> m_GizmoCube;
```

- `internal Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoCylinder> m_GizmoCylinder`  

```csharp
internal Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoCylinder> m_GizmoCylinder;
```

- `internal Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoArc> m_GizmoArc`  

```csharp
internal Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoArc> m_GizmoArc;
```

- `internal Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoCapsule> m_GizmoCapsule`  

```csharp
internal Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoCapsule> m_GizmoCapsule;
```

- `internal Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoCone> m_GizmoCone`  

```csharp
internal Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoCone> m_GizmoCone;
```

- `internal Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoCapsuleConic> m_GizmoCapsuleConic`  

```csharp
internal Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoCapsuleConic> m_GizmoCapsuleConic;
```

- `internal Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoFrustum> m_GizmoFrustum`  

```csharp
internal Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoFrustum> m_GizmoFrustum;
```


## Methods

- `public Enqueue(Colossal.Internal.Gizmos.GizmoBezier4x3 bezier) : System.Void`  

```csharp
public System.Void Enqueue(Colossal.Internal.Gizmos.GizmoBezier4x3 bezier);
```

- `public Enqueue(Colossal.Internal.Gizmos.GizmoArrowHead arrowHead) : System.Void`  

```csharp
public System.Void Enqueue(Colossal.Internal.Gizmos.GizmoArrowHead arrowHead);
```

- `public Enqueue(Colossal.Internal.Gizmos.GizmoLine line) : System.Void`  

```csharp
public System.Void Enqueue(Colossal.Internal.Gizmos.GizmoLine line);
```

- `public Enqueue(Colossal.Internal.Gizmos.GizmoSphere sphere) : System.Void`  

```csharp
public System.Void Enqueue(Colossal.Internal.Gizmos.GizmoSphere sphere);
```

- `public Enqueue(Colossal.Internal.Gizmos.GizmoCube cube) : System.Void`  

```csharp
public System.Void Enqueue(Colossal.Internal.Gizmos.GizmoCube cube);
```

- `public Enqueue(Colossal.Internal.Gizmos.GizmoCylinder cylinder) : System.Void`  

```csharp
public System.Void Enqueue(Colossal.Internal.Gizmos.GizmoCylinder cylinder);
```

- `public Enqueue(Colossal.Internal.Gizmos.GizmoArc arc) : System.Void`  

```csharp
public System.Void Enqueue(Colossal.Internal.Gizmos.GizmoArc arc);
```

- `public Enqueue(Colossal.Internal.Gizmos.GizmoCapsule capsule) : System.Void`  

```csharp
public System.Void Enqueue(Colossal.Internal.Gizmos.GizmoCapsule capsule);
```

- `public Enqueue(Colossal.Internal.Gizmos.GizmoCone cone) : System.Void`  

```csharp
public System.Void Enqueue(Colossal.Internal.Gizmos.GizmoCone cone);
```

- `public Enqueue(Colossal.Internal.Gizmos.GizmoCapsuleConic capsuleConic) : System.Void`  

```csharp
public System.Void Enqueue(Colossal.Internal.Gizmos.GizmoCapsuleConic capsuleConic);
```

- `public Enqueue(Colossal.Internal.Gizmos.GizmoFrustum frustum) : System.Void`  

```csharp
public System.Void Enqueue(Colossal.Internal.Gizmos.GizmoFrustum frustum);
```


