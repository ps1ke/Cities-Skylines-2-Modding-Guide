# Game.Notifications.IconClusterSystem+IconCluster

**Assembly:** `Game`  
**Namespace:** `Game.Notifications`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Game.Notifications.IconClusterSystem+IconCluster>`  

## Code

```csharp
public sealed struct IconCluster : System.IEquatable<Game.Notifications.IconClusterSystem+IconCluster>
{
    private Unity.Mathematics.float3 m_Center;
    private Unity.Mathematics.float3 m_Size;
    private Unity.Mathematics.int2 m_SubClusters;
    private System.Single m_DistanceFactor;
    private System.Single m_Radius;
    private System.Int32 m_ParentCluster;
    private Colossal.Collections.NativeHeapBlock m_IconAllocation;
    private System.Int32 m_IconCount;
    private System.Int32 m_Level;
    private System.Int32 m_PrefabIndex;
    private Game.Notifications.IconClusterLayer m_Layer;
    private Game.Notifications.IconFlags m_Flags;
    private System.Boolean m_IsMoving;
    private System.Boolean m_IsTemp;

    public Unity.Mathematics.float3 center { get; }
    public Unity.Mathematics.float3 size { get; }
    public System.Single distanceFactor { get; }
    public Game.Notifications.IconClusterLayer layer { get; }
    public Game.Notifications.IconFlags flags { get; }
    public System.Boolean isMoving { get; }
    public System.Boolean isTemp { get; }
    public System.Int32 parentCluster { get; }
    public System.Int32 level { get; }
    public System.Int32 prefabIndex { get; }

    public IconCluster(Unity.Mathematics.float3 center, Unity.Mathematics.float3 size, System.Int32 parentCluster, Unity.Mathematics.int2 subClusters, System.Single radius, System.Single distanceFactor, Colossal.Collections.NativeHeapBlock iconAllocation, Game.Notifications.IconClusterLayer layer, Game.Notifications.IconFlags flags, System.Int32 iconCount, System.Int32 level, System.Int32 prefabIndex, System.Boolean isMoving, System.Boolean isTemp);
    public IconCluster(Game.Notifications.IconClusterSystem+IconCluster cluster1, Game.Notifications.IconClusterSystem+IconCluster cluster2, System.Int32 index1, System.Int32 index2, Colossal.Collections.NativeHeapBlock iconAllocation, System.Int32 iconCount, System.Int32 level);

    public static System.Single CalculateRadius(System.Single radius, System.Single distance);
    public System.Boolean Equals(Game.Notifications.IconClusterSystem+IconCluster other);
    public Colossal.Mathematics.Bounds3 GetBounds(System.Single distance, Unity.Mathematics.float3 cameraUp);
    public Unity.Collections.NativeArray<Game.Notifications.IconClusterSystem+ClusterIcon> GetIcons(Game.Notifications.IconClusterSystem+ClusterData clusterData);
    public Colossal.Collections.NativeHeapBlock GetIcons(System.Int32& firstIcon, System.Int32& iconCount);
    public System.Single GetRadius(System.Single distance);
    public System.Boolean GetSubClusters(Unity.Mathematics.int2& subClusters);
    public System.Boolean KeepCluster(System.Single distance);
    public static System.Void SetParent(Game.Notifications.IconClusterSystem+IconCluster& cluster, System.Int32 parent);
}
```


## Fields

- `private Unity.Mathematics.float3 m_Center`  

```csharp
private Unity.Mathematics.float3 m_Center;
```

- `private Unity.Mathematics.float3 m_Size`  

```csharp
private Unity.Mathematics.float3 m_Size;
```

- `private Unity.Mathematics.int2 m_SubClusters`  

```csharp
private Unity.Mathematics.int2 m_SubClusters;
```

- `private System.Single m_DistanceFactor`  

```csharp
private System.Single m_DistanceFactor;
```

- `private System.Single m_Radius`  

```csharp
private System.Single m_Radius;
```

- `private System.Int32 m_ParentCluster`  

```csharp
private System.Int32 m_ParentCluster;
```

- `private Colossal.Collections.NativeHeapBlock m_IconAllocation`  

```csharp
private Colossal.Collections.NativeHeapBlock m_IconAllocation;
```

- `private System.Int32 m_IconCount`  

```csharp
private System.Int32 m_IconCount;
```

- `private System.Int32 m_Level`  

```csharp
private System.Int32 m_Level;
```

- `private System.Int32 m_PrefabIndex`  

```csharp
private System.Int32 m_PrefabIndex;
```

- `private Game.Notifications.IconClusterLayer m_Layer`  

```csharp
private Game.Notifications.IconClusterLayer m_Layer;
```

- `private Game.Notifications.IconFlags m_Flags`  

```csharp
private Game.Notifications.IconFlags m_Flags;
```

- `private System.Boolean m_IsMoving`  

```csharp
private System.Boolean m_IsMoving;
```

- `private System.Boolean m_IsTemp`  

```csharp
private System.Boolean m_IsTemp;
```


## Properties

- `public Unity.Mathematics.float3 center { get }`  

```csharp
public Unity.Mathematics.float3 center { get; }
```

- `public Unity.Mathematics.float3 size { get }`  

```csharp
public Unity.Mathematics.float3 size { get; }
```

- `public System.Single distanceFactor { get }`  

```csharp
public System.Single distanceFactor { get; }
```

- `public Game.Notifications.IconClusterLayer layer { get }`  

```csharp
public Game.Notifications.IconClusterLayer layer { get; }
```

- `public Game.Notifications.IconFlags flags { get }`  

```csharp
public Game.Notifications.IconFlags flags { get; }
```

- `public System.Boolean isMoving { get }`  

```csharp
public System.Boolean isMoving { get; }
```

- `public System.Boolean isTemp { get }`  

```csharp
public System.Boolean isTemp { get; }
```

- `public System.Int32 parentCluster { get }`  

```csharp
public System.Int32 parentCluster { get; }
```

- `public System.Int32 level { get }`  

```csharp
public System.Int32 level { get; }
```

- `public System.Int32 prefabIndex { get }`  

```csharp
public System.Int32 prefabIndex { get; }
```


## Constructors

- `public IconCluster(Unity.Mathematics.float3 center, Unity.Mathematics.float3 size, System.Int32 parentCluster, Unity.Mathematics.int2 subClusters, System.Single radius, System.Single distanceFactor, Colossal.Collections.NativeHeapBlock iconAllocation, Game.Notifications.IconClusterLayer layer, Game.Notifications.IconFlags flags, System.Int32 iconCount, System.Int32 level, System.Int32 prefabIndex, System.Boolean isMoving, System.Boolean isTemp)`  

```csharp
public IconCluster(Unity.Mathematics.float3 center, Unity.Mathematics.float3 size, System.Int32 parentCluster, Unity.Mathematics.int2 subClusters, System.Single radius, System.Single distanceFactor, Colossal.Collections.NativeHeapBlock iconAllocation, Game.Notifications.IconClusterLayer layer, Game.Notifications.IconFlags flags, System.Int32 iconCount, System.Int32 level, System.Int32 prefabIndex, System.Boolean isMoving, System.Boolean isTemp);
```

- `public IconCluster(Game.Notifications.IconClusterSystem+IconCluster cluster1, Game.Notifications.IconClusterSystem+IconCluster cluster2, System.Int32 index1, System.Int32 index2, Colossal.Collections.NativeHeapBlock iconAllocation, System.Int32 iconCount, System.Int32 level)`  

```csharp
public IconCluster(Game.Notifications.IconClusterSystem+IconCluster cluster1, Game.Notifications.IconClusterSystem+IconCluster cluster2, System.Int32 index1, System.Int32 index2, Colossal.Collections.NativeHeapBlock iconAllocation, System.Int32 iconCount, System.Int32 level);
```


## Methods

- `public static CalculateRadius(System.Single radius, System.Single distance) : System.Single`  

```csharp
public static System.Single CalculateRadius(System.Single radius, System.Single distance);
```

- `public Equals(Game.Notifications.IconClusterSystem+IconCluster other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Notifications.IconClusterSystem+IconCluster other);
```

- `public GetBounds(System.Single distance, Unity.Mathematics.float3 cameraUp) : Colossal.Mathematics.Bounds3`  

```csharp
public Colossal.Mathematics.Bounds3 GetBounds(System.Single distance, Unity.Mathematics.float3 cameraUp);
```

- `public GetIcons(Game.Notifications.IconClusterSystem+ClusterData clusterData) : Unity.Collections.NativeArray<Game.Notifications.IconClusterSystem+ClusterIcon>`  

```csharp
public Unity.Collections.NativeArray<Game.Notifications.IconClusterSystem+ClusterIcon> GetIcons(Game.Notifications.IconClusterSystem+ClusterData clusterData);
```

- `public GetIcons(System.Int32& firstIcon, System.Int32& iconCount) : Colossal.Collections.NativeHeapBlock`  

```csharp
public Colossal.Collections.NativeHeapBlock GetIcons(System.Int32& firstIcon, System.Int32& iconCount);
```

- `public GetRadius(System.Single distance) : System.Single`  

```csharp
public System.Single GetRadius(System.Single distance);
```

- `public GetSubClusters(Unity.Mathematics.int2& subClusters) : System.Boolean`  

```csharp
public System.Boolean GetSubClusters(Unity.Mathematics.int2& subClusters);
```

- `public KeepCluster(System.Single distance) : System.Boolean`  

```csharp
public System.Boolean KeepCluster(System.Single distance);
```

- `public static SetParent(Game.Notifications.IconClusterSystem+IconCluster& cluster, System.Int32 parent) : System.Void`  

```csharp
public static System.Void SetParent(Game.Notifications.IconClusterSystem+IconCluster& cluster, System.Int32 parent);
```


