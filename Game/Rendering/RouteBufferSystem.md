# Game.Rendering.RouteBufferSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class RouteBufferSystem : Game.GameSystemBase, Game.Serialization.IPreDeserialize
{
    private Game.Rendering.RenderingSystem m_RenderingSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Unity.Entities.EntityQuery m_UpdatedRoutesQuery;
    private Unity.Entities.EntityQuery m_AllRoutesQuery;
    private Unity.Entities.EntityQuery m_RouteConfigQuery;
    private System.Collections.Generic.List<Game.Rendering.RouteBufferSystem+ManagedData> m_ManagedData;
    private Unity.Collections.NativeList<Game.Rendering.RouteBufferSystem+NativeData> m_NativeData;
    private System.Collections.Generic.Stack<System.Int32> m_FreeBufferIndices;
    private Unity.Jobs.JobHandle m_BufferDependencies;
    private System.Boolean m_Loaded;
    private Game.Rendering.RouteBufferSystem+TypeHandle __TypeHandle;

    public RouteBufferSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void Clear();
    public System.Void GetBuffer(System.Int32 index, UnityEngine.Material& material, UnityEngine.ComputeBuffer& segmentBuffer, System.Int32& originalRenderQueue, UnityEngine.Bounds& bounds, UnityEngine.Vector4& size);
    private System.Boolean GetLoaded();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  

```csharp
private Game.Rendering.RenderingSystem m_RenderingSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Unity.Entities.EntityQuery m_UpdatedRoutesQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedRoutesQuery;
```

- `private Unity.Entities.EntityQuery m_AllRoutesQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllRoutesQuery;
```

- `private Unity.Entities.EntityQuery m_RouteConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_RouteConfigQuery;
```

- `private System.Collections.Generic.List<Game.Rendering.RouteBufferSystem+ManagedData> m_ManagedData`  

```csharp
private System.Collections.Generic.List<Game.Rendering.RouteBufferSystem+ManagedData> m_ManagedData;
```

- `private Unity.Collections.NativeList<Game.Rendering.RouteBufferSystem+NativeData> m_NativeData`  

```csharp
private Unity.Collections.NativeList<Game.Rendering.RouteBufferSystem+NativeData> m_NativeData;
```

- `private System.Collections.Generic.Stack<System.Int32> m_FreeBufferIndices`  

```csharp
private System.Collections.Generic.Stack<System.Int32> m_FreeBufferIndices;
```

- `private Unity.Jobs.JobHandle m_BufferDependencies`  

```csharp
private Unity.Jobs.JobHandle m_BufferDependencies;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Rendering.RouteBufferSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.RouteBufferSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public RouteBufferSystem()`  

```csharp
public RouteBufferSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private Clear() : System.Void`  

```csharp
private System.Void Clear();
```

- `public GetBuffer(System.Int32 index, UnityEngine.Material& material, UnityEngine.ComputeBuffer& segmentBuffer, System.Int32& originalRenderQueue, UnityEngine.Bounds& bounds, UnityEngine.Vector4& size) : System.Void`  

```csharp
public System.Void GetBuffer(System.Int32 index, UnityEngine.Material& material, UnityEngine.ComputeBuffer& segmentBuffer, System.Int32& originalRenderQueue, UnityEngine.Bounds& bounds, UnityEngine.Vector4& size);
```

- `private GetLoaded() : System.Boolean`  

```csharp
private System.Boolean GetLoaded();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
```


## Nested types

- `Game.Rendering.RouteBufferSystem+ManagedData`  
- `Game.Rendering.RouteBufferSystem+NativeData`  
- `Game.Rendering.RouteBufferSystem+SegmentData`  
- `Game.Rendering.RouteBufferSystem+CurveKey`  
- `Game.Rendering.RouteBufferSystem+CurveValue`  
- `Game.Rendering.RouteBufferSystem+SourceKey`  
- `Game.Rendering.RouteBufferSystem+UpdateBufferJob`  
- `Game.Rendering.RouteBufferSystem+TypeHandle`  

