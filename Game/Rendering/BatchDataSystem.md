# Game.Rendering.BatchDataSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class BatchDataSystem : Game.GameSystemBase, Game.Serialization.IPostDeserialize
{
    private Game.Rendering.RenderingSystem m_RenderingSystem;
    private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
    private Game.Rendering.BatchManagerSystem m_BatchManagerSystem;
    private Game.Rendering.BatchMeshSystem m_BatchMeshSystem;
    private Game.Rendering.ManagedBatchSystem m_ManagedBatchSystem;
    private Game.Rendering.PreCullingSystem m_PreCullingSystem;
    private Game.Rendering.LightingSystem m_LightingSystem;
    private Game.Rendering.MeshColorSystem m_MeshColorSystem;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.CitizenPresenceSystem m_CitizenPresenceSystem;
    private Game.Simulation.TreeGrowthSystem m_TreeGrowthSystem;
    private Game.Simulation.WetnessSystem m_WetnessSystem;
    private Game.Simulation.WindSystem m_WindSystem;
    private Game.Simulation.DirtynessSystem m_DirtynessSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Unity.Entities.EntityQuery m_RenderingSettingsQuery;
    private Colossal.Collections.NativeAccumulator<Game.Rendering.BatchDataSystem+SmoothingNeeded> m_SmoothingNeeded;
    private System.Int32 m_SHCoefficients;
    private System.Int32 m_LodParameters;
    private System.Boolean m_UpdateAll;
    private System.Single m_LastLightFactor;
    private System.Single m_LodFadeTimer;
    private Unity.Mathematics.float4 m_LastBuildingStateOverride;
    private System.UInt32 m_LastCitizenPresenceVersion;
    private System.UInt32 m_LastTreeGrowthVersion;
    private System.UInt32 m_LastWetnessVersion;
    private System.UInt32 m_LastDirtynessVersion;
    private System.UInt32 m_LastFireDamageVersion;
    private System.UInt32 m_LastWaterDamageVersion;
    private System.UInt32 m_LastWeatherDamageVersion;
    private System.UInt32 m_LastLaneConditionFrame;
    private System.UInt32 m_LastDamagedFrame;
    private Game.Rendering.BatchDataSystem+TypeHandle __TypeHandle;
    public static const System.Single LOD_FADE_DURATION;
    public static const System.Single DEBUG_FADE_DURATION;

    public BatchDataSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Single CalculateLightFactor();
    private System.Void GetDataQuery(Game.Rendering.PreCullingFlags& cullingFlags, Game.Rendering.BatchDataSystem+UpdateMasks& updateMasks);
    public System.Single GetLevelOfDetail(System.Single levelOfDetail, Game.Rendering.IGameCameraController cameraController);
    public System.Void InstancePropertiesUpdated();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
    private System.Void UpdateGlobalValues(Colossal.Rendering.NativeBatchInstances<Game.Rendering.CullingData, Game.Rendering.GroupData, Game.Rendering.BatchData, Game.Rendering.InstanceData> nativeBatchInstances);
}
```


## Fields

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  

```csharp
private Game.Rendering.RenderingSystem m_RenderingSystem;
```

- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  

```csharp
private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
```

- `private Game.Rendering.BatchManagerSystem m_BatchManagerSystem`  

```csharp
private Game.Rendering.BatchManagerSystem m_BatchManagerSystem;
```

- `private Game.Rendering.BatchMeshSystem m_BatchMeshSystem`  

```csharp
private Game.Rendering.BatchMeshSystem m_BatchMeshSystem;
```

- `private Game.Rendering.ManagedBatchSystem m_ManagedBatchSystem`  

```csharp
private Game.Rendering.ManagedBatchSystem m_ManagedBatchSystem;
```

- `private Game.Rendering.PreCullingSystem m_PreCullingSystem`  

```csharp
private Game.Rendering.PreCullingSystem m_PreCullingSystem;
```

- `private Game.Rendering.LightingSystem m_LightingSystem`  

```csharp
private Game.Rendering.LightingSystem m_LightingSystem;
```

- `private Game.Rendering.MeshColorSystem m_MeshColorSystem`  

```csharp
private Game.Rendering.MeshColorSystem m_MeshColorSystem;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.CitizenPresenceSystem m_CitizenPresenceSystem`  

```csharp
private Game.Simulation.CitizenPresenceSystem m_CitizenPresenceSystem;
```

- `private Game.Simulation.TreeGrowthSystem m_TreeGrowthSystem`  

```csharp
private Game.Simulation.TreeGrowthSystem m_TreeGrowthSystem;
```

- `private Game.Simulation.WetnessSystem m_WetnessSystem`  

```csharp
private Game.Simulation.WetnessSystem m_WetnessSystem;
```

- `private Game.Simulation.WindSystem m_WindSystem`  

```csharp
private Game.Simulation.WindSystem m_WindSystem;
```

- `private Game.Simulation.DirtynessSystem m_DirtynessSystem`  

```csharp
private Game.Simulation.DirtynessSystem m_DirtynessSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Unity.Entities.EntityQuery m_RenderingSettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_RenderingSettingsQuery;
```

- `private Colossal.Collections.NativeAccumulator<Game.Rendering.BatchDataSystem+SmoothingNeeded> m_SmoothingNeeded`  

```csharp
private Colossal.Collections.NativeAccumulator<Game.Rendering.BatchDataSystem+SmoothingNeeded> m_SmoothingNeeded;
```

- `private System.Int32 m_SHCoefficients`  

```csharp
private System.Int32 m_SHCoefficients;
```

- `private System.Int32 m_LodParameters`  

```csharp
private System.Int32 m_LodParameters;
```

- `private System.Boolean m_UpdateAll`  

```csharp
private System.Boolean m_UpdateAll;
```

- `private System.Single m_LastLightFactor`  

```csharp
private System.Single m_LastLightFactor;
```

- `private System.Single m_LodFadeTimer`  

```csharp
private System.Single m_LodFadeTimer;
```

- `private Unity.Mathematics.float4 m_LastBuildingStateOverride`  

```csharp
private Unity.Mathematics.float4 m_LastBuildingStateOverride;
```

- `private System.UInt32 m_LastCitizenPresenceVersion`  

```csharp
private System.UInt32 m_LastCitizenPresenceVersion;
```

- `private System.UInt32 m_LastTreeGrowthVersion`  

```csharp
private System.UInt32 m_LastTreeGrowthVersion;
```

- `private System.UInt32 m_LastWetnessVersion`  

```csharp
private System.UInt32 m_LastWetnessVersion;
```

- `private System.UInt32 m_LastDirtynessVersion`  

```csharp
private System.UInt32 m_LastDirtynessVersion;
```

- `private System.UInt32 m_LastFireDamageVersion`  

```csharp
private System.UInt32 m_LastFireDamageVersion;
```

- `private System.UInt32 m_LastWaterDamageVersion`  

```csharp
private System.UInt32 m_LastWaterDamageVersion;
```

- `private System.UInt32 m_LastWeatherDamageVersion`  

```csharp
private System.UInt32 m_LastWeatherDamageVersion;
```

- `private System.UInt32 m_LastLaneConditionFrame`  

```csharp
private System.UInt32 m_LastLaneConditionFrame;
```

- `private System.UInt32 m_LastDamagedFrame`  

```csharp
private System.UInt32 m_LastDamagedFrame;
```

- `private Game.Rendering.BatchDataSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.BatchDataSystem+TypeHandle __TypeHandle;
```

- `public static const System.Single LOD_FADE_DURATION`  

```csharp
public static const System.Single LOD_FADE_DURATION;
```

- `public static const System.Single DEBUG_FADE_DURATION`  

```csharp
public static const System.Single DEBUG_FADE_DURATION;
```


## Constructors

- `public BatchDataSystem()`  

```csharp
public BatchDataSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private CalculateLightFactor() : System.Single`  

```csharp
private System.Single CalculateLightFactor();
```

- `private GetDataQuery(Game.Rendering.PreCullingFlags& cullingFlags, Game.Rendering.BatchDataSystem+UpdateMasks& updateMasks) : System.Void`  

```csharp
private System.Void GetDataQuery(Game.Rendering.PreCullingFlags& cullingFlags, Game.Rendering.BatchDataSystem+UpdateMasks& updateMasks);
```

- `public GetLevelOfDetail(System.Single levelOfDetail, Game.Rendering.IGameCameraController cameraController) : System.Single`  

```csharp
public System.Single GetLevelOfDetail(System.Single levelOfDetail, Game.Rendering.IGameCameraController cameraController);
```

- `public InstancePropertiesUpdated() : System.Void`  

```csharp
public System.Void InstancePropertiesUpdated();
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

- `private UpdateGlobalValues(Colossal.Rendering.NativeBatchInstances<Game.Rendering.CullingData, Game.Rendering.GroupData, Game.Rendering.BatchData, Game.Rendering.InstanceData> nativeBatchInstances) : System.Void`  

```csharp
private System.Void UpdateGlobalValues(Colossal.Rendering.NativeBatchInstances<Game.Rendering.CullingData, Game.Rendering.GroupData, Game.Rendering.BatchData, Game.Rendering.InstanceData> nativeBatchInstances);
```


## Nested types

- `Game.Rendering.BatchDataSystem+UpdateMask`  
- `Game.Rendering.BatchDataSystem+UpdateMasks`  
- `Game.Rendering.BatchDataSystem+SmoothingType`  
- `Game.Rendering.BatchDataSystem+SmoothingNeeded`  
- `Game.Rendering.BatchDataSystem+CellTypes`  
- `Game.Rendering.BatchDataSystem+BatchDataJob`  
- `Game.Rendering.BatchDataSystem+BatchLodJob`  
- `Game.Rendering.BatchDataSystem+TypeHandle`  

