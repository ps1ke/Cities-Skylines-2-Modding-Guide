# Game.Notifications.IconClusterSystem

**Assembly:** `Game`  
**Namespace:** `Game.Notifications`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_IconQuery`  
- `private Unity.Entities.EntityQuery m_ModifiedQuery`  
- `private Unity.Entities.EntityQuery m_ModifiedAndTempQuery`  
- `private Colossal.Collections.NativeQuadTree<System.Int32, Game.Notifications.IconClusterSystem+TreeBounds> m_ClusterTree`  
- `private Colossal.Collections.NativeHeapAllocator m_IconAllocator`  
- `private Unity.Collections.NativeList<Game.Notifications.IconClusterSystem+IconCluster> m_IconClusters`  
- `private Unity.Collections.NativeList<Game.Notifications.IconClusterSystem+ClusterIcon> m_ClusterIcons`  
- `private Unity.Collections.NativeList<System.Int32> m_RootClusters`  
- `private Unity.Collections.NativeList<System.Int32> m_FreeClusterIndices`  
- `private Unity.Jobs.JobHandle m_ClusterReadDeps`  
- `private Unity.Jobs.JobHandle m_ClusterWriteDeps`  
- `private System.Boolean m_Loaded`  
- `private Game.Notifications.IconClusterSystem+TypeHandle __TypeHandle`  

## Constructors

- `public IconClusterSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public AddIconClusterReader(Unity.Jobs.JobHandle jobHandle) : System.Void`  
- `public AddIconClusterWriter(Unity.Jobs.JobHandle jobHandle) : System.Void`  
- `private ClearData() : System.Void`  
- `public GetIconClusterData(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies) : Game.Notifications.IconClusterSystem+ClusterData`  
- `private GetLoaded() : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  
- `public RecalculateClusters() : System.Void`  

## Nested types

- `Game.Notifications.IconClusterSystem+ClusterData`  
- `Game.Notifications.IconClusterSystem+IconCluster`  
- `Game.Notifications.IconClusterSystem+ClusterIcon`  
- `Game.Notifications.IconClusterSystem+TempIconCluster`  
- `Game.Notifications.IconClusterSystem+TreeBounds`  
- `Game.Notifications.IconClusterSystem+IconChunkJob`  
- `Game.Notifications.IconClusterSystem+IconClusterJob`  
- `Game.Notifications.IconClusterSystem+IconData`  
- `Game.Notifications.IconClusterSystem+TypeHandle`  

