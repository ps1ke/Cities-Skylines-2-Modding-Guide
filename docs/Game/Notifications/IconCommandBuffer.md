# Game.Notifications.IconCommandBuffer

**Assembly:** `Game`  
**Namespace:** `Game.Notifications`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `private Unity.Collections.NativeQueue<Game.Notifications.IconCommandBuffer+Command> m_Commands`  
- `private System.Int32 m_BufferIndex`  

## Constructors

- `public IconCommandBuffer(Unity.Collections.NativeQueue<Game.Notifications.IconCommandBuffer+Command> commands, System.Int32 bufferIndex)`  

## Methods

- `public Add(Unity.Entities.Entity owner, Unity.Entities.Entity prefab, Game.Notifications.IconPriority priority = Info, Game.Notifications.IconClusterLayer clusterLayer = Default, Game.Notifications.IconFlags flags = 0, Unity.Entities.Entity target = null, System.Boolean isTemp = False, System.Boolean isHidden = False, System.Boolean disallowCluster = False, System.Single delay = 0) : System.Void`  
- `public Add(Unity.Entities.Entity owner, Unity.Entities.Entity prefab, Unity.Mathematics.float3 location, Game.Notifications.IconPriority priority = Info, Game.Notifications.IconClusterLayer clusterLayer = Default, Game.Notifications.IconFlags flags = IgnoreTarget, Unity.Entities.Entity target = null, System.Boolean isTemp = False, System.Boolean isHidden = False, System.Boolean disallowCluster = False, System.Single delay = 0) : System.Void`  
- `public Remove(Unity.Entities.Entity owner, Unity.Entities.Entity prefab, Unity.Entities.Entity target = null, Game.Notifications.IconFlags flags = 0) : System.Void`  
- `public Remove(Unity.Entities.Entity owner, Game.Notifications.IconPriority priority) : System.Void`  
- `public Update(Unity.Entities.Entity owner) : System.Void`  

## Nested types

- `Game.Notifications.IconCommandBuffer+CommandFlags`  
- `Game.Notifications.IconCommandBuffer+Command`  

