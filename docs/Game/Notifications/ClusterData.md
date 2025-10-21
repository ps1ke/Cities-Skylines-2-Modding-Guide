# Game.Notifications.IconClusterSystem+ClusterData

**Assembly:** `Game`  
**Namespace:** `Game.Notifications`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct ClusterData
{
    private Unity.Collections.NativeList<Game.Notifications.IconClusterSystem+IconCluster> m_Clusters;
    private Unity.Collections.NativeList<Game.Notifications.IconClusterSystem+ClusterIcon> m_Icons;
    private Unity.Collections.NativeList<System.Int32> m_Roots;

    public System.Boolean isEmpty { get; }

    public ClusterData(Unity.Collections.NativeList<Game.Notifications.IconClusterSystem+IconCluster> clusters, Unity.Collections.NativeList<Game.Notifications.IconClusterSystem+ClusterIcon> icons, Unity.Collections.NativeList<System.Int32> roots);

    public Game.Notifications.IconClusterSystem+IconCluster GetCluster(System.Int32 index);
    public Unity.Collections.NativeArray<Game.Notifications.IconClusterSystem+ClusterIcon> GetIcons(System.Int32 firstIcon, System.Int32 iconCount);
    public System.Boolean GetRoot(System.Int32& index, Game.Notifications.IconClusterSystem+IconCluster& cluster);
}
```


## Fields

- `private Unity.Collections.NativeList<Game.Notifications.IconClusterSystem+IconCluster> m_Clusters`  

```csharp
private Unity.Collections.NativeList<Game.Notifications.IconClusterSystem+IconCluster> m_Clusters;
```

- `private Unity.Collections.NativeList<Game.Notifications.IconClusterSystem+ClusterIcon> m_Icons`  

```csharp
private Unity.Collections.NativeList<Game.Notifications.IconClusterSystem+ClusterIcon> m_Icons;
```

- `private Unity.Collections.NativeList<System.Int32> m_Roots`  

```csharp
private Unity.Collections.NativeList<System.Int32> m_Roots;
```


## Properties

- `public System.Boolean isEmpty { get }`  

```csharp
public System.Boolean isEmpty { get; }
```


## Constructors

- `public ClusterData(Unity.Collections.NativeList<Game.Notifications.IconClusterSystem+IconCluster> clusters, Unity.Collections.NativeList<Game.Notifications.IconClusterSystem+ClusterIcon> icons, Unity.Collections.NativeList<System.Int32> roots)`  

```csharp
public ClusterData(Unity.Collections.NativeList<Game.Notifications.IconClusterSystem+IconCluster> clusters, Unity.Collections.NativeList<Game.Notifications.IconClusterSystem+ClusterIcon> icons, Unity.Collections.NativeList<System.Int32> roots);
```


## Methods

- `public GetCluster(System.Int32 index) : Game.Notifications.IconClusterSystem+IconCluster`  

```csharp
public Game.Notifications.IconClusterSystem+IconCluster GetCluster(System.Int32 index);
```

- `public GetIcons(System.Int32 firstIcon, System.Int32 iconCount) : Unity.Collections.NativeArray<Game.Notifications.IconClusterSystem+ClusterIcon>`  

```csharp
public Unity.Collections.NativeArray<Game.Notifications.IconClusterSystem+ClusterIcon> GetIcons(System.Int32 firstIcon, System.Int32 iconCount);
```

- `public GetRoot(System.Int32& index, Game.Notifications.IconClusterSystem+IconCluster& cluster) : System.Boolean`  

```csharp
public System.Boolean GetRoot(System.Int32& index, Game.Notifications.IconClusterSystem+IconCluster& cluster);
```


