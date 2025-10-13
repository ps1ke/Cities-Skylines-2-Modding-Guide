# Colossal.Internal.Gizmos.GizmoObjects

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Internal.Gizmos`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct GizmoObjects
{
    private Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoBezier4x3> m_GizmoBezier4x3;
    private Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoArrowHead> m_GizmoArrowHead;
    private Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoLine> m_GizmoLine;
    private Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoSphere> m_GizmoSphere;
    private Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoCube> m_GizmoCube;
    private Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoCylinder> m_GizmoCylinder;
    private Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoArc> m_GizmoArc;
    private Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoCapsule> m_GizmoCapsule;
    private Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoCone> m_GizmoCone;
    private Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoCapsuleConic> m_GizmoCapsuleConic;
    private Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoFrustum> m_GizmoFrustum;

    public System.Int32 Count { get; }

    public GizmoObjects(Unity.Collections.Allocator allocator);

    public System.Void Dispose();
    public Colossal.Internal.Gizmos.GizmoObjects+Concurrent ToConcurrent();
    public System.Boolean TryCreateRenderData(Colossal.Internal.Gizmos.RenderData& renderData);
}
```


## Fields

- `private Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoBezier4x3> m_GizmoBezier4x3`  

```csharp
private Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoBezier4x3> m_GizmoBezier4x3;
```

- `private Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoArrowHead> m_GizmoArrowHead`  

```csharp
private Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoArrowHead> m_GizmoArrowHead;
```

- `private Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoLine> m_GizmoLine`  

```csharp
private Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoLine> m_GizmoLine;
```

- `private Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoSphere> m_GizmoSphere`  

```csharp
private Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoSphere> m_GizmoSphere;
```

- `private Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoCube> m_GizmoCube`  

```csharp
private Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoCube> m_GizmoCube;
```

- `private Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoCylinder> m_GizmoCylinder`  

```csharp
private Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoCylinder> m_GizmoCylinder;
```

- `private Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoArc> m_GizmoArc`  

```csharp
private Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoArc> m_GizmoArc;
```

- `private Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoCapsule> m_GizmoCapsule`  

```csharp
private Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoCapsule> m_GizmoCapsule;
```

- `private Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoCone> m_GizmoCone`  

```csharp
private Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoCone> m_GizmoCone;
```

- `private Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoCapsuleConic> m_GizmoCapsuleConic`  

```csharp
private Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoCapsuleConic> m_GizmoCapsuleConic;
```

- `private Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoFrustum> m_GizmoFrustum`  

```csharp
private Unity.Collections.NativeQueue<Colossal.Internal.Gizmos.GizmoFrustum> m_GizmoFrustum;
```


## Properties

- `public System.Int32 Count { get }`  

```csharp
public System.Int32 Count { get; }
```


## Constructors

- `public GizmoObjects(Unity.Collections.Allocator allocator)`  

```csharp
public GizmoObjects(Unity.Collections.Allocator allocator);
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public ToConcurrent() : Colossal.Internal.Gizmos.GizmoObjects+Concurrent`  

```csharp
public Colossal.Internal.Gizmos.GizmoObjects+Concurrent ToConcurrent();
```

- `public TryCreateRenderData(Colossal.Internal.Gizmos.RenderData& renderData) : System.Boolean`  

```csharp
public System.Boolean TryCreateRenderData(Colossal.Internal.Gizmos.RenderData& renderData);
```


## Nested types

- `Colossal.Internal.Gizmos.GizmoObjects+Concurrent`  

