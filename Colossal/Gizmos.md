# Colossal.Gizmos

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class Gizmos
{
    private static Colossal.Internal.Gizmos.GizmoObjects m_GizmoObjects;
    private static Colossal.NativeCounter m_EstimatedVertexCount;
    private static Colossal.NativeCounter m_EstimatedIndexCount;
    private static Colossal.GizmoBatcher m_Batcher;
    private static System.Boolean m_IsCreated;

    public static Colossal.GizmoBatcher& batcher { get; }
    public static System.Int32 estimatedVertexCount { get; }
    public static System.Int32 estimatedIndexCount { get; }
    public static Colossal.Internal.Gizmos.GizmoObjects& objects { get; }

    public static System.Void CreateResources();
    public static System.Void ReleaseResources();
    public static System.Void ResetCounters();
}
```


## Fields

- `private static Colossal.Internal.Gizmos.GizmoObjects m_GizmoObjects`  

```csharp
private static Colossal.Internal.Gizmos.GizmoObjects m_GizmoObjects;
```

- `private static Colossal.NativeCounter m_EstimatedVertexCount`  

```csharp
private static Colossal.NativeCounter m_EstimatedVertexCount;
```

- `private static Colossal.NativeCounter m_EstimatedIndexCount`  

```csharp
private static Colossal.NativeCounter m_EstimatedIndexCount;
```

- `private static Colossal.GizmoBatcher m_Batcher`  

```csharp
private static Colossal.GizmoBatcher m_Batcher;
```

- `private static System.Boolean m_IsCreated`  

```csharp
private static System.Boolean m_IsCreated;
```


## Properties

- `public static Colossal.GizmoBatcher& batcher { get }`  

```csharp
public static Colossal.GizmoBatcher& batcher { get; }
```

- `public static System.Int32 estimatedVertexCount { get }`  

```csharp
public static System.Int32 estimatedVertexCount { get; }
```

- `public static System.Int32 estimatedIndexCount { get }`  

```csharp
public static System.Int32 estimatedIndexCount { get; }
```

- `public static Colossal.Internal.Gizmos.GizmoObjects& objects { get }`  

```csharp
public static Colossal.Internal.Gizmos.GizmoObjects& objects { get; }
```


## Methods

- `public static CreateResources() : System.Void`  

```csharp
public static System.Void CreateResources();
```

- `public static ReleaseResources() : System.Void`  

```csharp
public static System.Void ReleaseResources();
```

- `public static ResetCounters() : System.Void`  

```csharp
public static System.Void ResetCounters();
```


