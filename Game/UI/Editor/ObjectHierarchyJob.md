# Game.UI.Editor.EditorHierarchyUISystem+ObjectHierarchyJob

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IJobChunk`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct ObjectHierarchyJob : Unity.Entities.IJobChunk
{
    public Unity.Entities.EntityTypeHandle m_EntityType;
    public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefType;
    public Unity.Entities.BufferLookup<Game.Prefabs.SubMesh> m_SubMeshes;
    public Unity.Collections.NativeParallelHashSet<Game.UI.Editor.EditorHierarchyUISystem+ItemId> m_ExpandedIds;
    public Unity.Collections.NativeList<Game.UI.Editor.EditorHierarchyUISystem+HierarchyItem> m_Hierarchy;

    public System.Void Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
    private System.Void Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
}
```


## Fields

- `public Unity.Entities.EntityTypeHandle m_EntityType`  

```csharp
public Unity.Entities.EntityTypeHandle m_EntityType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefType;
```

- `public Unity.Entities.BufferLookup<Game.Prefabs.SubMesh> m_SubMeshes`  

```csharp
public Unity.Entities.BufferLookup<Game.Prefabs.SubMesh> m_SubMeshes;
```

- `public Unity.Collections.NativeParallelHashSet<Game.UI.Editor.EditorHierarchyUISystem+ItemId> m_ExpandedIds`  

```csharp
public Unity.Collections.NativeParallelHashSet<Game.UI.Editor.EditorHierarchyUISystem+ItemId> m_ExpandedIds;
```

- `public Unity.Collections.NativeList<Game.UI.Editor.EditorHierarchyUISystem+HierarchyItem> m_Hierarchy`  

```csharp
public Unity.Collections.NativeList<Game.UI.Editor.EditorHierarchyUISystem+HierarchyItem> m_Hierarchy;
```


## Methods

- `public Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  

```csharp
public System.Void Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
```

- `private Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask) : System.Void`  

```csharp
private System.Void Unity.Entities.IJobChunk.Execute(Unity.Entities.ArchetypeChunk& chunk, System.Int32 unfilteredChunkIndex, System.Boolean useEnabledMask, Unity.Burst.Intrinsics.v128& chunkEnabledMask);
```


