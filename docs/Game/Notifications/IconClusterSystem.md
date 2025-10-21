# Game.Notifications.IconClusterSystem

**Assembly:** `Game`  
**Namespace:** `Game.Notifications`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class IconClusterSystem : Game.GameSystemBase, Game.Serialization.IPreDeserialize
{
    private Unity.Entities.EntityQuery m_IconQuery;
    private Unity.Entities.EntityQuery m_ModifiedQuery;
    private Unity.Entities.EntityQuery m_ModifiedAndTempQuery;
    private Colossal.Collections.NativeQuadTree<System.Int32, Game.Notifications.IconClusterSystem+TreeBounds> m_ClusterTree;
    private Colossal.Collections.NativeHeapAllocator m_IconAllocator;
    private Unity.Collections.NativeList<Game.Notifications.IconClusterSystem+IconCluster> m_IconClusters;
    private Unity.Collections.NativeList<Game.Notifications.IconClusterSystem+ClusterIcon> m_ClusterIcons;
    private Unity.Collections.NativeList<System.Int32> m_RootClusters;
    private Unity.Collections.NativeList<System.Int32> m_FreeClusterIndices;
    private Unity.Jobs.JobHandle m_ClusterReadDeps;
    private Unity.Jobs.JobHandle m_ClusterWriteDeps;
    private System.Boolean m_Loaded;
    private Game.Notifications.IconClusterSystem+TypeHandle __TypeHandle;

    public IconClusterSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddIconClusterReader(Unity.Jobs.JobHandle jobHandle);
    public System.Void AddIconClusterWriter(Unity.Jobs.JobHandle jobHandle);
    private System.Void ClearData();
    public Game.Notifications.IconClusterSystem+ClusterData GetIconClusterData(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies);
    private System.Boolean GetLoaded();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
    public System.Void RecalculateClusters();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_IconQuery`  

```csharp
private Unity.Entities.EntityQuery m_IconQuery;
```

- `private Unity.Entities.EntityQuery m_ModifiedQuery`  

```csharp
private Unity.Entities.EntityQuery m_ModifiedQuery;
```

- `private Unity.Entities.EntityQuery m_ModifiedAndTempQuery`  

```csharp
private Unity.Entities.EntityQuery m_ModifiedAndTempQuery;
```

- `private Colossal.Collections.NativeQuadTree<System.Int32, Game.Notifications.IconClusterSystem+TreeBounds> m_ClusterTree`  

```csharp
private Colossal.Collections.NativeQuadTree<System.Int32, Game.Notifications.IconClusterSystem+TreeBounds> m_ClusterTree;
```

- `private Colossal.Collections.NativeHeapAllocator m_IconAllocator`  

```csharp
private Colossal.Collections.NativeHeapAllocator m_IconAllocator;
```

- `private Unity.Collections.NativeList<Game.Notifications.IconClusterSystem+IconCluster> m_IconClusters`  

```csharp
private Unity.Collections.NativeList<Game.Notifications.IconClusterSystem+IconCluster> m_IconClusters;
```

- `private Unity.Collections.NativeList<Game.Notifications.IconClusterSystem+ClusterIcon> m_ClusterIcons`  

```csharp
private Unity.Collections.NativeList<Game.Notifications.IconClusterSystem+ClusterIcon> m_ClusterIcons;
```

- `private Unity.Collections.NativeList<System.Int32> m_RootClusters`  

```csharp
private Unity.Collections.NativeList<System.Int32> m_RootClusters;
```

- `private Unity.Collections.NativeList<System.Int32> m_FreeClusterIndices`  

```csharp
private Unity.Collections.NativeList<System.Int32> m_FreeClusterIndices;
```

- `private Unity.Jobs.JobHandle m_ClusterReadDeps`  

```csharp
private Unity.Jobs.JobHandle m_ClusterReadDeps;
```

- `private Unity.Jobs.JobHandle m_ClusterWriteDeps`  

```csharp
private Unity.Jobs.JobHandle m_ClusterWriteDeps;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Notifications.IconClusterSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Notifications.IconClusterSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public IconClusterSystem()`  

```csharp
public IconClusterSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public AddIconClusterReader(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public System.Void AddIconClusterReader(Unity.Jobs.JobHandle jobHandle);
```

- `public AddIconClusterWriter(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public System.Void AddIconClusterWriter(Unity.Jobs.JobHandle jobHandle);
```

- `private ClearData() : System.Void`  

```csharp
private System.Void ClearData();
```

- `public GetIconClusterData(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies) : Game.Notifications.IconClusterSystem+ClusterData`  

```csharp
public Game.Notifications.IconClusterSystem+ClusterData GetIconClusterData(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies);
```

- `private GetLoaded() : System.Boolean`  

```csharp
private System.Boolean GetLoaded();
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

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
```

- `public RecalculateClusters() : System.Void`  

```csharp
public System.Void RecalculateClusters();
```


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

