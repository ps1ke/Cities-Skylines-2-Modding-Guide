# Game.Rendering.NotificationIconBufferSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_IconQuery`  
- `private Unity.Entities.EntityQuery m_ConfigurationQuery`  
- `private Game.Notifications.IconClusterSystem m_IconClusterSystem`  
- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Unity.Collections.NativeList<Game.Rendering.NotificationIconBufferSystem+InstanceData> m_InstanceData`  
- `private Colossal.Collections.NativeValue<Colossal.Mathematics.Bounds3> m_IconBounds`  
- `private Unity.Jobs.JobHandle m_InstanceDataDeps`  
- `private Game.Rendering.NotificationIconBufferSystem+TypeHandle __TypeHandle`  

## Constructors

- `public NotificationIconBufferSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public GetIconData() : Game.Rendering.NotificationIconBufferSystem+IconData`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Rendering.NotificationIconBufferSystem+IconData`  
- `Game.Rendering.NotificationIconBufferSystem+InstanceData`  
- `Game.Rendering.NotificationIconBufferSystem+HiddenPositionData`  
- `Game.Rendering.NotificationIconBufferSystem+NotificationIconBufferJob`  
- `Game.Rendering.NotificationIconBufferSystem+NotificationIconSortJob`  
- `Game.Rendering.NotificationIconBufferSystem+TypeHandle`  

