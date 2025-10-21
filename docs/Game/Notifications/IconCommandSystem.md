# Game.Notifications.IconCommandSystem

**Assembly:** `Game`  
**Namespace:** `Game.Notifications`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class IconCommandSystem : Game.GameSystemBase
{
    private Game.Common.ModificationEndBarrier m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_ConfigurationQuery;
    private System.Collections.Generic.List<Unity.Collections.NativeQueue<Game.Notifications.IconCommandBuffer+Command>> m_Queues;
    private Unity.Jobs.JobHandle m_Dependencies;
    private System.Int32 m_BufferIndex;
    private Game.Notifications.IconCommandSystem+TypeHandle __TypeHandle;

    public IconCommandSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddCommandBufferWriter(Unity.Jobs.JobHandle handle);
    public Game.Notifications.IconCommandBuffer CreateCommandBuffer();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnStopRunning();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationEndBarrier m_ModificationBarrier`  

```csharp
private Game.Common.ModificationEndBarrier m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_ConfigurationQuery`  

```csharp
private Unity.Entities.EntityQuery m_ConfigurationQuery;
```

- `private System.Collections.Generic.List<Unity.Collections.NativeQueue<Game.Notifications.IconCommandBuffer+Command>> m_Queues`  

```csharp
private System.Collections.Generic.List<Unity.Collections.NativeQueue<Game.Notifications.IconCommandBuffer+Command>> m_Queues;
```

- `private Unity.Jobs.JobHandle m_Dependencies`  

```csharp
private Unity.Jobs.JobHandle m_Dependencies;
```

- `private System.Int32 m_BufferIndex`  

```csharp
private System.Int32 m_BufferIndex;
```

- `private Game.Notifications.IconCommandSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Notifications.IconCommandSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public IconCommandSystem()`  

```csharp
public IconCommandSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public AddCommandBufferWriter(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public System.Void AddCommandBufferWriter(Unity.Jobs.JobHandle handle);
```

- `public CreateCommandBuffer() : Game.Notifications.IconCommandBuffer`  

```csharp
public Game.Notifications.IconCommandBuffer CreateCommandBuffer();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnStopRunning() : System.Void`  

```csharp
protected virtual System.Void OnStopRunning();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Notifications.IconCommandSystem+IconCommandPlaybackJob`  
- `Game.Notifications.IconCommandSystem+TypeHandle`  

