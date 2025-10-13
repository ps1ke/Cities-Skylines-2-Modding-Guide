# Game.Notifications.RaycastJobs+RaycastIconsJob

**Assembly:** `Game`  
**Namespace:** `Game.Notifications`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJobParallelFor`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct RaycastIconsJob : Unity.Jobs.IJobParallelFor
{
    public Unity.Collections.NativeArray<Game.Common.RaycastInput> m_Input;
    public Unity.Mathematics.float3 m_CameraUp;
    public Unity.Mathematics.float3 m_CameraRight;
    public Game.Notifications.IconClusterSystem+ClusterData m_ClusterData;
    public Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> m_IconChunks;
    public Unity.Entities.EntityTypeHandle m_EntityType;
    public Unity.Entities.ComponentTypeHandle<Game.Notifications.Icon> m_IconType;
    public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefType;
    public Unity.Entities.ComponentLookup<Game.Common.Owner> m_OwnerData;
    public Unity.Entities.ComponentLookup<Game.Tools.Temp> m_TempData;
    public Unity.Entities.ComponentLookup<Game.Objects.Static> m_StaticData;
    public Unity.Entities.ComponentLookup<Game.Objects.Object> m_ObjectData;
    public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_TransformData;
    public Unity.Entities.ComponentLookup<Game.Objects.Placeholder> m_PlaceholderData;
    public Unity.Entities.ComponentLookup<Game.Objects.Attachment> m_AttachmentData;
    public Unity.Entities.ComponentLookup<Game.Rendering.CullingInfo> m_CullingInfoData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.NotificationIconDisplayData> m_IconDisplayData;
    public Colossal.Collections.NativeAccumulator<Game.Common.RaycastResult> m_Results;

    private System.Void CheckChunks(System.Int32 raycastIndex, Game.Common.RaycastInput input);
    private System.Void CheckClusters(System.Int32 raycastIndex, Game.Common.RaycastInput input);
    private System.Boolean CheckPlaceholder(Game.Common.RaycastInput input, Unity.Entities.Entity& entity);
    public System.Void Execute(System.Int32 index);
    private System.Void ValidateResult(System.Int32 raycastIndex, Game.Common.RaycastInput input, Game.Common.RaycastResult result, Game.Notifications.IconClusterLayer layer);
}
```


## Fields

- `public Unity.Collections.NativeArray<Game.Common.RaycastInput> m_Input`  

```csharp
public Unity.Collections.NativeArray<Game.Common.RaycastInput> m_Input;
```

- `public Unity.Mathematics.float3 m_CameraUp`  

```csharp
public Unity.Mathematics.float3 m_CameraUp;
```

- `public Unity.Mathematics.float3 m_CameraRight`  

```csharp
public Unity.Mathematics.float3 m_CameraRight;
```

- `public Game.Notifications.IconClusterSystem+ClusterData m_ClusterData`  

```csharp
public Game.Notifications.IconClusterSystem+ClusterData m_ClusterData;
```

- `public Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> m_IconChunks`  

```csharp
public Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> m_IconChunks;
```

- `public Unity.Entities.EntityTypeHandle m_EntityType`  

```csharp
public Unity.Entities.EntityTypeHandle m_EntityType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Notifications.Icon> m_IconType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Notifications.Icon> m_IconType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefType;
```

- `public Unity.Entities.ComponentLookup<Game.Common.Owner> m_OwnerData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Common.Owner> m_OwnerData;
```

- `public Unity.Entities.ComponentLookup<Game.Tools.Temp> m_TempData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Tools.Temp> m_TempData;
```

- `public Unity.Entities.ComponentLookup<Game.Objects.Static> m_StaticData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Objects.Static> m_StaticData;
```

- `public Unity.Entities.ComponentLookup<Game.Objects.Object> m_ObjectData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Objects.Object> m_ObjectData;
```

- `public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_TransformData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_TransformData;
```

- `public Unity.Entities.ComponentLookup<Game.Objects.Placeholder> m_PlaceholderData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Objects.Placeholder> m_PlaceholderData;
```

- `public Unity.Entities.ComponentLookup<Game.Objects.Attachment> m_AttachmentData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Objects.Attachment> m_AttachmentData;
```

- `public Unity.Entities.ComponentLookup<Game.Rendering.CullingInfo> m_CullingInfoData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Rendering.CullingInfo> m_CullingInfoData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.NotificationIconDisplayData> m_IconDisplayData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.NotificationIconDisplayData> m_IconDisplayData;
```

- `public Colossal.Collections.NativeAccumulator<Game.Common.RaycastResult> m_Results`  

```csharp
public Colossal.Collections.NativeAccumulator<Game.Common.RaycastResult> m_Results;
```


## Methods

- `private CheckChunks(System.Int32 raycastIndex, Game.Common.RaycastInput input) : System.Void`  

```csharp
private System.Void CheckChunks(System.Int32 raycastIndex, Game.Common.RaycastInput input);
```

- `private CheckClusters(System.Int32 raycastIndex, Game.Common.RaycastInput input) : System.Void`  

```csharp
private System.Void CheckClusters(System.Int32 raycastIndex, Game.Common.RaycastInput input);
```

- `private CheckPlaceholder(Game.Common.RaycastInput input, Unity.Entities.Entity& entity) : System.Boolean`  

```csharp
private System.Boolean CheckPlaceholder(Game.Common.RaycastInput input, Unity.Entities.Entity& entity);
```

- `public Execute(System.Int32 index) : System.Void`  

```csharp
public System.Void Execute(System.Int32 index);
```

- `private ValidateResult(System.Int32 raycastIndex, Game.Common.RaycastInput input, Game.Common.RaycastResult result, Game.Notifications.IconClusterLayer layer) : System.Void`  

```csharp
private System.Void ValidateResult(System.Int32 raycastIndex, Game.Common.RaycastInput input, Game.Common.RaycastResult result, Game.Notifications.IconClusterLayer layer);
```


