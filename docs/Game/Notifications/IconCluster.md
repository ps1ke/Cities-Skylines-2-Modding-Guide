# Game.Notifications.IconClusterSystem+IconCluster

**Assembly:** `Game`  
**Namespace:** `Game.Notifications`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Game.Notifications.IconClusterSystem+IconCluster>`  

## Fields

- `private Unity.Mathematics.float3 m_Center`  
- `private Unity.Mathematics.float3 m_Size`  
- `private Unity.Mathematics.int2 m_SubClusters`  
- `private System.Single m_DistanceFactor`  
- `private System.Single m_Radius`  
- `private System.Int32 m_ParentCluster`  
- `private Colossal.Collections.NativeHeapBlock m_IconAllocation`  
- `private System.Int32 m_IconCount`  
- `private System.Int32 m_Level`  
- `private System.Int32 m_PrefabIndex`  
- `private Game.Notifications.IconClusterLayer m_Layer`  
- `private Game.Notifications.IconFlags m_Flags`  
- `private System.Boolean m_IsMoving`  
- `private System.Boolean m_IsTemp`  

## Properties

- `public Unity.Mathematics.float3 center { get }`  
- `public Unity.Mathematics.float3 size { get }`  
- `public System.Single distanceFactor { get }`  
- `public Game.Notifications.IconClusterLayer layer { get }`  
- `public Game.Notifications.IconFlags flags { get }`  
- `public System.Boolean isMoving { get }`  
- `public System.Boolean isTemp { get }`  
- `public System.Int32 parentCluster { get }`  
- `public System.Int32 level { get }`  
- `public System.Int32 prefabIndex { get }`  

## Constructors

- `public IconCluster(Unity.Mathematics.float3 center, Unity.Mathematics.float3 size, System.Int32 parentCluster, Unity.Mathematics.int2 subClusters, System.Single radius, System.Single distanceFactor, Colossal.Collections.NativeHeapBlock iconAllocation, Game.Notifications.IconClusterLayer layer, Game.Notifications.IconFlags flags, System.Int32 iconCount, System.Int32 level, System.Int32 prefabIndex, System.Boolean isMoving, System.Boolean isTemp)`  
- `public IconCluster(Game.Notifications.IconClusterSystem+IconCluster cluster1, Game.Notifications.IconClusterSystem+IconCluster cluster2, System.Int32 index1, System.Int32 index2, Colossal.Collections.NativeHeapBlock iconAllocation, System.Int32 iconCount, System.Int32 level)`  

## Methods

- `public static CalculateRadius(System.Single radius, System.Single distance) : System.Single`  
- `public Equals(Game.Notifications.IconClusterSystem+IconCluster other) : System.Boolean`  
- `public GetBounds(System.Single distance, Unity.Mathematics.float3 cameraUp) : Colossal.Mathematics.Bounds3`  
- `public GetIcons(Game.Notifications.IconClusterSystem+ClusterData clusterData) : Unity.Collections.NativeArray<Game.Notifications.IconClusterSystem+ClusterIcon>`  
- `public GetIcons(System.Int32& firstIcon, System.Int32& iconCount) : Colossal.Collections.NativeHeapBlock`  
- `public GetRadius(System.Single distance) : System.Single`  
- `public GetSubClusters(Unity.Mathematics.int2& subClusters) : System.Boolean`  
- `public KeepCluster(System.Single distance) : System.Boolean`  
- `public static SetParent(Game.Notifications.IconClusterSystem+IconCluster& cluster, System.Int32 parent) : System.Void`  

