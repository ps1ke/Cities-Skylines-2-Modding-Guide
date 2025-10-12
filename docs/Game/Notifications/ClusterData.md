# Game.Notifications.IconClusterSystem+ClusterData

**Assembly:** `Game`  
**Namespace:** `Game.Notifications`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `private Unity.Collections.NativeList<Game.Notifications.IconClusterSystem+IconCluster> m_Clusters`  
- `private Unity.Collections.NativeList<Game.Notifications.IconClusterSystem+ClusterIcon> m_Icons`  
- `private Unity.Collections.NativeList<System.Int32> m_Roots`  

## Properties

- `public System.Boolean isEmpty { get }`  

## Constructors

- `public ClusterData(Unity.Collections.NativeList<Game.Notifications.IconClusterSystem+IconCluster> clusters, Unity.Collections.NativeList<Game.Notifications.IconClusterSystem+ClusterIcon> icons, Unity.Collections.NativeList<System.Int32> roots)`  

## Methods

- `public GetCluster(System.Int32 index) : Game.Notifications.IconClusterSystem+IconCluster`  
- `public GetIcons(System.Int32 firstIcon, System.Int32 iconCount) : Unity.Collections.NativeArray<Game.Notifications.IconClusterSystem+ClusterIcon>`  
- `public GetRoot(System.Int32& index, Game.Notifications.IconClusterSystem+IconCluster& cluster) : System.Boolean`  

