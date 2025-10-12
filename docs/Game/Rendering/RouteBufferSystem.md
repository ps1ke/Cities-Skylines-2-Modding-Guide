# Game.Rendering.RouteBufferSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Unity.Entities.EntityQuery m_UpdatedRoutesQuery`  
- `private Unity.Entities.EntityQuery m_AllRoutesQuery`  
- `private Unity.Entities.EntityQuery m_RouteConfigQuery`  
- `private System.Collections.Generic.List<Game.Rendering.RouteBufferSystem+ManagedData> m_ManagedData`  
- `private Unity.Collections.NativeList<Game.Rendering.RouteBufferSystem+NativeData> m_NativeData`  
- `private System.Collections.Generic.Stack<System.Int32> m_FreeBufferIndices`  
- `private Unity.Jobs.JobHandle m_BufferDependencies`  
- `private System.Boolean m_Loaded`  
- `private Game.Rendering.RouteBufferSystem+TypeHandle __TypeHandle`  

## Constructors

- `public RouteBufferSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private Clear() : System.Void`  
- `public GetBuffer(System.Int32 index, UnityEngine.Material& material, UnityEngine.ComputeBuffer& segmentBuffer, System.Int32& originalRenderQueue, UnityEngine.Bounds& bounds, UnityEngine.Vector4& size) : System.Void`  
- `private GetLoaded() : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

## Nested types

- `Game.Rendering.RouteBufferSystem+ManagedData`  
- `Game.Rendering.RouteBufferSystem+NativeData`  
- `Game.Rendering.RouteBufferSystem+SegmentData`  
- `Game.Rendering.RouteBufferSystem+CurveKey`  
- `Game.Rendering.RouteBufferSystem+CurveValue`  
- `Game.Rendering.RouteBufferSystem+SourceKey`  
- `Game.Rendering.RouteBufferSystem+UpdateBufferJob`  
- `Game.Rendering.RouteBufferSystem+TypeHandle`  

