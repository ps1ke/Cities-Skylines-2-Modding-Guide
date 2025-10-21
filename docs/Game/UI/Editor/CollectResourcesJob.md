# Game.UI.Editor.MapRequirementSystem+CollectResourcesJob

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJob`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct CollectResourcesJob : Unity.Jobs.IJob
{
    public Unity.Collections.NativeArray<Unity.Entities.ArchetypeChunk> m_AreaChunks;
    public Unity.Entities.BufferTypeHandle<Game.Areas.MapFeatureElement> m_MapFeatureElementType;
    public Unity.Collections.NativeArray<System.Boolean> m_Results;

    private System.Void Check(Unity.Entities.BufferAccessor<Game.Areas.MapFeatureElement> mapFeatureAccessor);
    public System.Void Execute();
}
```


## Fields

- `public Unity.Collections.NativeArray<Unity.Entities.ArchetypeChunk> m_AreaChunks`  

```csharp
public Unity.Collections.NativeArray<Unity.Entities.ArchetypeChunk> m_AreaChunks;
```

- `public Unity.Entities.BufferTypeHandle<Game.Areas.MapFeatureElement> m_MapFeatureElementType`  

```csharp
public Unity.Entities.BufferTypeHandle<Game.Areas.MapFeatureElement> m_MapFeatureElementType;
```

- `public Unity.Collections.NativeArray<System.Boolean> m_Results`  

```csharp
public Unity.Collections.NativeArray<System.Boolean> m_Results;
```


## Methods

- `private Check(Unity.Entities.BufferAccessor<Game.Areas.MapFeatureElement> mapFeatureAccessor) : System.Void`  

```csharp
private System.Void Check(Unity.Entities.BufferAccessor<Game.Areas.MapFeatureElement> mapFeatureAccessor);
```

- `public Execute() : System.Void`  

```csharp
public System.Void Execute();
```


