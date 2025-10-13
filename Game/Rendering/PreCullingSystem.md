# Game.Rendering.PreCullingSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PreCullingSystem : Game.GameSystemBase, Game.Serialization.IPostDeserialize
{
    private Game.Common.BoundsMask <visibleMask>k__BackingField;
    private Game.Common.BoundsMask <becameVisible>k__BackingField;
    private Game.Common.BoundsMask <becameHidden>k__BackingField;
    private Game.Rendering.RenderingSystem m_RenderingSystem;
    private Game.Rendering.UndergroundViewSystem m_UndergroundViewSystem;
    private Game.Rendering.BatchMeshSystem m_BatchMeshSystem;
    private Game.Rendering.BatchDataSystem m_BatchDataSystem;
    private Game.Objects.SearchSystem m_ObjectSearchSystem;
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Unity.Entities.EntityQuery m_InitializeQuery;
    private Unity.Entities.EntityQuery m_EventQuery;
    private Unity.Entities.EntityQuery m_CullingInfoQuery;
    private Unity.Entities.EntityQuery m_TempQuery;
    private Unity.Mathematics.float3 m_PrevCameraPosition;
    private Unity.Mathematics.float3 m_PrevCameraDirection;
    private Unity.Mathematics.float4 m_PrevLodParameters;
    private Game.Common.BoundsMask m_PrevVisibleMask;
    private Game.Rendering.PreCullingSystem+QueryFlags m_PrevQueryFlags;
    private System.Collections.Generic.Dictionary<Game.Rendering.PreCullingSystem+QueryFlags, Unity.Entities.EntityQuery> m_CullingQueries;
    private System.Collections.Generic.Dictionary<Game.Rendering.PreCullingSystem+QueryFlags, Unity.Entities.EntityQuery> m_RelativeQueries;
    private System.Collections.Generic.Dictionary<Game.Rendering.PreCullingSystem+QueryFlags, Unity.Entities.EntityQuery> m_RemoveQueries;
    private Unity.Collections.NativeList<Game.Rendering.PreCullingData> m_CullingData;
    private Unity.Collections.NativeList<Game.Rendering.PreCullingData> m_UpdatedData;
    private Unity.Entities.Entity m_FadeContainer;
    private Unity.Jobs.JobHandle m_WriteDependencies;
    private Unity.Jobs.JobHandle m_ReadDependencies;
    private System.Boolean m_ResetPrevious;
    private System.Boolean m_Loaded;
    private Game.Rendering.PreCullingSystem+TypeHandle __TypeHandle;

    public Game.Common.BoundsMask visibleMask { get; private set; }
    public Game.Common.BoundsMask becameVisible { get; private set; }
    public Game.Common.BoundsMask becameHidden { get; private set; }

    public PreCullingSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddCullingDataReader(Unity.Jobs.JobHandle dependencies);
    public System.Void AddCullingDataWriter(Unity.Jobs.JobHandle dependencies);
    public Unity.Collections.NativeList<Game.Rendering.PreCullingData> GetCullingData(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies);
    private Unity.Entities.EntityQuery GetCullingQuery(Game.Rendering.PreCullingSystem+QueryFlags flags);
    public Unity.Entities.Entity GetFadeContainer();
    private System.Boolean GetLoaded();
    private Game.Rendering.PreCullingSystem+QueryFlags GetQueryFlags();
    private Unity.Entities.EntityQuery GetRelativeQuery(Game.Rendering.PreCullingSystem+QueryFlags flags);
    private Unity.Entities.EntityQuery GetRemoveQuery(Game.Rendering.PreCullingSystem+QueryFlags flags);
    public Unity.Collections.NativeList<Game.Rendering.PreCullingData> GetUpdatedData(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies);
    private System.Void InitializeCullingData();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
    public System.Void ResetCulling();
}
```


## Fields

- `private Game.Common.BoundsMask <visibleMask>k__BackingField`  

```csharp
private Game.Common.BoundsMask <visibleMask>k__BackingField;
```

- `private Game.Common.BoundsMask <becameVisible>k__BackingField`  

```csharp
private Game.Common.BoundsMask <becameVisible>k__BackingField;
```

- `private Game.Common.BoundsMask <becameHidden>k__BackingField`  

```csharp
private Game.Common.BoundsMask <becameHidden>k__BackingField;
```

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  

```csharp
private Game.Rendering.RenderingSystem m_RenderingSystem;
```

- `private Game.Rendering.UndergroundViewSystem m_UndergroundViewSystem`  

```csharp
private Game.Rendering.UndergroundViewSystem m_UndergroundViewSystem;
```

- `private Game.Rendering.BatchMeshSystem m_BatchMeshSystem`  

```csharp
private Game.Rendering.BatchMeshSystem m_BatchMeshSystem;
```

- `private Game.Rendering.BatchDataSystem m_BatchDataSystem`  

```csharp
private Game.Rendering.BatchDataSystem m_BatchDataSystem;
```

- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  

```csharp
private Game.Objects.SearchSystem m_ObjectSearchSystem;
```

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  

```csharp
private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Unity.Entities.EntityQuery m_InitializeQuery`  

```csharp
private Unity.Entities.EntityQuery m_InitializeQuery;
```

- `private Unity.Entities.EntityQuery m_EventQuery`  

```csharp
private Unity.Entities.EntityQuery m_EventQuery;
```

- `private Unity.Entities.EntityQuery m_CullingInfoQuery`  

```csharp
private Unity.Entities.EntityQuery m_CullingInfoQuery;
```

- `private Unity.Entities.EntityQuery m_TempQuery`  

```csharp
private Unity.Entities.EntityQuery m_TempQuery;
```

- `private Unity.Mathematics.float3 m_PrevCameraPosition`  

```csharp
private Unity.Mathematics.float3 m_PrevCameraPosition;
```

- `private Unity.Mathematics.float3 m_PrevCameraDirection`  

```csharp
private Unity.Mathematics.float3 m_PrevCameraDirection;
```

- `private Unity.Mathematics.float4 m_PrevLodParameters`  

```csharp
private Unity.Mathematics.float4 m_PrevLodParameters;
```

- `private Game.Common.BoundsMask m_PrevVisibleMask`  

```csharp
private Game.Common.BoundsMask m_PrevVisibleMask;
```

- `private Game.Rendering.PreCullingSystem+QueryFlags m_PrevQueryFlags`  

```csharp
private Game.Rendering.PreCullingSystem+QueryFlags m_PrevQueryFlags;
```

- `private System.Collections.Generic.Dictionary<Game.Rendering.PreCullingSystem+QueryFlags, Unity.Entities.EntityQuery> m_CullingQueries`  

```csharp
private System.Collections.Generic.Dictionary<Game.Rendering.PreCullingSystem+QueryFlags, Unity.Entities.EntityQuery> m_CullingQueries;
```

- `private System.Collections.Generic.Dictionary<Game.Rendering.PreCullingSystem+QueryFlags, Unity.Entities.EntityQuery> m_RelativeQueries`  

```csharp
private System.Collections.Generic.Dictionary<Game.Rendering.PreCullingSystem+QueryFlags, Unity.Entities.EntityQuery> m_RelativeQueries;
```

- `private System.Collections.Generic.Dictionary<Game.Rendering.PreCullingSystem+QueryFlags, Unity.Entities.EntityQuery> m_RemoveQueries`  

```csharp
private System.Collections.Generic.Dictionary<Game.Rendering.PreCullingSystem+QueryFlags, Unity.Entities.EntityQuery> m_RemoveQueries;
```

- `private Unity.Collections.NativeList<Game.Rendering.PreCullingData> m_CullingData`  

```csharp
private Unity.Collections.NativeList<Game.Rendering.PreCullingData> m_CullingData;
```

- `private Unity.Collections.NativeList<Game.Rendering.PreCullingData> m_UpdatedData`  

```csharp
private Unity.Collections.NativeList<Game.Rendering.PreCullingData> m_UpdatedData;
```

- `private Unity.Entities.Entity m_FadeContainer`  

```csharp
private Unity.Entities.Entity m_FadeContainer;
```

- `private Unity.Jobs.JobHandle m_WriteDependencies`  

```csharp
private Unity.Jobs.JobHandle m_WriteDependencies;
```

- `private Unity.Jobs.JobHandle m_ReadDependencies`  

```csharp
private Unity.Jobs.JobHandle m_ReadDependencies;
```

- `private System.Boolean m_ResetPrevious`  

```csharp
private System.Boolean m_ResetPrevious;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Rendering.PreCullingSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.PreCullingSystem+TypeHandle __TypeHandle;
```


## Properties

- `public Game.Common.BoundsMask visibleMask { get; private set }`  

```csharp
public Game.Common.BoundsMask visibleMask { get; private set; }
```

- `public Game.Common.BoundsMask becameVisible { get; private set }`  

```csharp
public Game.Common.BoundsMask becameVisible { get; private set; }
```

- `public Game.Common.BoundsMask becameHidden { get; private set }`  

```csharp
public Game.Common.BoundsMask becameHidden { get; private set; }
```


## Constructors

- `public PreCullingSystem()`  

```csharp
public PreCullingSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public AddCullingDataReader(Unity.Jobs.JobHandle dependencies) : System.Void`  

```csharp
public System.Void AddCullingDataReader(Unity.Jobs.JobHandle dependencies);
```

- `public AddCullingDataWriter(Unity.Jobs.JobHandle dependencies) : System.Void`  

```csharp
public System.Void AddCullingDataWriter(Unity.Jobs.JobHandle dependencies);
```

- `public GetCullingData(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Game.Rendering.PreCullingData>`  

```csharp
public Unity.Collections.NativeList<Game.Rendering.PreCullingData> GetCullingData(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies);
```

- `private GetCullingQuery(Game.Rendering.PreCullingSystem+QueryFlags flags) : Unity.Entities.EntityQuery`  

```csharp
private Unity.Entities.EntityQuery GetCullingQuery(Game.Rendering.PreCullingSystem+QueryFlags flags);
```

- `public GetFadeContainer() : Unity.Entities.Entity`  

```csharp
public Unity.Entities.Entity GetFadeContainer();
```

- `private GetLoaded() : System.Boolean`  

```csharp
private System.Boolean GetLoaded();
```

- `private GetQueryFlags() : Game.Rendering.PreCullingSystem+QueryFlags`  

```csharp
private Game.Rendering.PreCullingSystem+QueryFlags GetQueryFlags();
```

- `private GetRelativeQuery(Game.Rendering.PreCullingSystem+QueryFlags flags) : Unity.Entities.EntityQuery`  

```csharp
private Unity.Entities.EntityQuery GetRelativeQuery(Game.Rendering.PreCullingSystem+QueryFlags flags);
```

- `private GetRemoveQuery(Game.Rendering.PreCullingSystem+QueryFlags flags) : Unity.Entities.EntityQuery`  

```csharp
private Unity.Entities.EntityQuery GetRemoveQuery(Game.Rendering.PreCullingSystem+QueryFlags flags);
```

- `public GetUpdatedData(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Game.Rendering.PreCullingData>`  

```csharp
public Unity.Collections.NativeList<Game.Rendering.PreCullingData> GetUpdatedData(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies);
```

- `private InitializeCullingData() : System.Void`  

```csharp
private System.Void InitializeCullingData();
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

- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
```

- `public ResetCulling() : System.Void`  

```csharp
public System.Void ResetCulling();
```


## Nested types

- `Game.Rendering.PreCullingSystem+QueryFlags`  
- `Game.Rendering.PreCullingSystem+TreeCullingJob1`  
- `Game.Rendering.PreCullingSystem+TreeCullingJob2`  
- `Game.Rendering.PreCullingSystem+TreeCullingIterator`  
- `Game.Rendering.PreCullingSystem+InitializeCullingJob`  
- `Game.Rendering.PreCullingSystem+EventCullingJob`  
- `Game.Rendering.PreCullingSystem+QueryCullingJob`  
- `Game.Rendering.PreCullingSystem+QueryRemoveJob`  
- `Game.Rendering.PreCullingSystem+RelativeCullingJob`  
- `Game.Rendering.PreCullingSystem+TempCullingJob`  
- `Game.Rendering.PreCullingSystem+VerifyVisibleJob`  
- `Game.Rendering.PreCullingSystem+ActionFlags`  
- `Game.Rendering.PreCullingSystem+CullingAction`  
- `Game.Rendering.PreCullingSystem+OverflowAction`  
- `Game.Rendering.PreCullingSystem+CullingActionJob`  
- `Game.Rendering.PreCullingSystem+ResizeCullingDataJob`  
- `Game.Rendering.PreCullingSystem+FilterUpdatesJob`  
- `Game.Rendering.PreCullingSystem+TypeHandle`  

