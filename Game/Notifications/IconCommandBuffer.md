# Game.Notifications.IconCommandBuffer

**Assembly:** `Game`  
**Namespace:** `Game.Notifications`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct IconCommandBuffer
{
    private Unity.Collections.NativeQueue<Game.Notifications.IconCommandBuffer+Command> m_Commands;
    private System.Int32 m_BufferIndex;

    public IconCommandBuffer(Unity.Collections.NativeQueue<Game.Notifications.IconCommandBuffer+Command> commands, System.Int32 bufferIndex);

    public System.Void Add(Unity.Entities.Entity owner, Unity.Entities.Entity prefab, Game.Notifications.IconPriority priority, Game.Notifications.IconClusterLayer clusterLayer, Game.Notifications.IconFlags flags, Unity.Entities.Entity target, System.Boolean isTemp, System.Boolean isHidden, System.Boolean disallowCluster, System.Single delay);
    public System.Void Add(Unity.Entities.Entity owner, Unity.Entities.Entity prefab, Unity.Mathematics.float3 location, Game.Notifications.IconPriority priority, Game.Notifications.IconClusterLayer clusterLayer, Game.Notifications.IconFlags flags, Unity.Entities.Entity target, System.Boolean isTemp, System.Boolean isHidden, System.Boolean disallowCluster, System.Single delay);
    public System.Void Remove(Unity.Entities.Entity owner, Unity.Entities.Entity prefab, Unity.Entities.Entity target, Game.Notifications.IconFlags flags);
    public System.Void Remove(Unity.Entities.Entity owner, Game.Notifications.IconPriority priority);
    public System.Void Update(Unity.Entities.Entity owner);
}
```


## Fields

- `private Unity.Collections.NativeQueue<Game.Notifications.IconCommandBuffer+Command> m_Commands`  

```csharp
private Unity.Collections.NativeQueue<Game.Notifications.IconCommandBuffer+Command> m_Commands;
```

- `private System.Int32 m_BufferIndex`  

```csharp
private System.Int32 m_BufferIndex;
```


## Constructors

- `public IconCommandBuffer(Unity.Collections.NativeQueue<Game.Notifications.IconCommandBuffer+Command> commands, System.Int32 bufferIndex)`  

```csharp
public IconCommandBuffer(NativeQueue<Command>.ParallelWriter commands, int bufferIndex)
	{
		m_Commands = commands;
		m_BufferIndex = bufferIndex;
	}
```


## Methods

- `public Add(Unity.Entities.Entity owner, Unity.Entities.Entity prefab, Game.Notifications.IconPriority priority = Info, Game.Notifications.IconClusterLayer clusterLayer = Default, Game.Notifications.IconFlags flags = 0, Unity.Entities.Entity target = null, System.Boolean isTemp = False, System.Boolean isHidden = False, System.Boolean disallowCluster = False, System.Single delay = 0) : System.Void`  

```csharp
public System.Void Add(Unity.Entities.Entity owner, Unity.Entities.Entity prefab, Game.Notifications.IconPriority priority, Game.Notifications.IconClusterLayer clusterLayer, Game.Notifications.IconFlags flags, Unity.Entities.Entity target, System.Boolean isTemp, System.Boolean isHidden, System.Boolean disallowCluster, System.Single delay);
```

- `public Add(Unity.Entities.Entity owner, Unity.Entities.Entity prefab, Unity.Mathematics.float3 location, Game.Notifications.IconPriority priority = Info, Game.Notifications.IconClusterLayer clusterLayer = Default, Game.Notifications.IconFlags flags = IgnoreTarget, Unity.Entities.Entity target = null, System.Boolean isTemp = False, System.Boolean isHidden = False, System.Boolean disallowCluster = False, System.Single delay = 0) : System.Void`  

```csharp
public System.Void Add(Unity.Entities.Entity owner, Unity.Entities.Entity prefab, Unity.Mathematics.float3 location, Game.Notifications.IconPriority priority, Game.Notifications.IconClusterLayer clusterLayer, Game.Notifications.IconFlags flags, Unity.Entities.Entity target, System.Boolean isTemp, System.Boolean isHidden, System.Boolean disallowCluster, System.Single delay);
```

- `public Remove(Unity.Entities.Entity owner, Unity.Entities.Entity prefab, Unity.Entities.Entity target = null, Game.Notifications.IconFlags flags = 0) : System.Void`  

```csharp
public void Remove(Entity owner, IconPriority priority)
	{
		m_Commands.Enqueue(new Command
		{
			m_Owner = owner,
			m_CommandFlags = (CommandFlags)66,
			m_Priority = priority,
			m_BufferIndex = m_BufferIndex
		});
	}
```

- `public Remove(Unity.Entities.Entity owner, Game.Notifications.IconPriority priority) : System.Void`  

```csharp
public void Remove(Entity owner, IconPriority priority)
	{
		m_Commands.Enqueue(new Command
		{
			m_Owner = owner,
			m_CommandFlags = (CommandFlags)66,
			m_Priority = priority,
			m_BufferIndex = m_BufferIndex
		});
	}
```

- `public Update(Unity.Entities.Entity owner) : System.Void`  

```csharp
public void Update(Entity owner)
	{
		m_Commands.Enqueue(new Command
		{
			m_Owner = owner,
			m_CommandFlags = CommandFlags.Update,
			m_BufferIndex = m_BufferIndex
		});
	}
```


## Nested types

- `Game.Notifications.IconCommandBuffer+CommandFlags`  
- `Game.Notifications.IconCommandBuffer+Command`  

