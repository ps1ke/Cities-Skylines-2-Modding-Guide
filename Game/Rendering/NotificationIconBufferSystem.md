# Game.Rendering.NotificationIconBufferSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class NotificationIconBufferSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_IconQuery;
    private Unity.Entities.EntityQuery m_ConfigurationQuery;
    private Game.Notifications.IconClusterSystem m_IconClusterSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Unity.Collections.NativeList<Game.Rendering.NotificationIconBufferSystem+InstanceData> m_InstanceData;
    private Colossal.Collections.NativeValue<Colossal.Mathematics.Bounds3> m_IconBounds;
    private Unity.Jobs.JobHandle m_InstanceDataDeps;
    private Game.Rendering.NotificationIconBufferSystem+TypeHandle __TypeHandle;

    public NotificationIconBufferSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public Game.Rendering.NotificationIconBufferSystem+IconData GetIconData();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_IconQuery`  

```csharp
private Unity.Entities.EntityQuery m_IconQuery;
```

- `private Unity.Entities.EntityQuery m_ConfigurationQuery`  

```csharp
private Unity.Entities.EntityQuery m_ConfigurationQuery;
```

- `private Game.Notifications.IconClusterSystem m_IconClusterSystem`  

```csharp
private Game.Notifications.IconClusterSystem m_IconClusterSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Unity.Collections.NativeList<Game.Rendering.NotificationIconBufferSystem+InstanceData> m_InstanceData`  

```csharp
private Unity.Collections.NativeList<Game.Rendering.NotificationIconBufferSystem+InstanceData> m_InstanceData;
```

- `private Colossal.Collections.NativeValue<Colossal.Mathematics.Bounds3> m_IconBounds`  

```csharp
private Colossal.Collections.NativeValue<Colossal.Mathematics.Bounds3> m_IconBounds;
```

- `private Unity.Jobs.JobHandle m_InstanceDataDeps`  

```csharp
private Unity.Jobs.JobHandle m_InstanceDataDeps;
```

- `private Game.Rendering.NotificationIconBufferSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.NotificationIconBufferSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public NotificationIconBufferSystem()`  

```csharp
public NotificationIconBufferSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public GetIconData() : Game.Rendering.NotificationIconBufferSystem+IconData`  

```csharp
public Game.Rendering.NotificationIconBufferSystem+IconData GetIconData();
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


## Nested types

- `Game.Rendering.NotificationIconBufferSystem+IconData`  
- `Game.Rendering.NotificationIconBufferSystem+InstanceData`  
- `Game.Rendering.NotificationIconBufferSystem+HiddenPositionData`  
- `Game.Rendering.NotificationIconBufferSystem+NotificationIconBufferJob`  
- `Game.Rendering.NotificationIconBufferSystem+NotificationIconSortJob`  
- `Game.Rendering.NotificationIconBufferSystem+TypeHandle`  

