# Game.Rendering.BatchDataSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  
- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  
- `private Game.Rendering.BatchManagerSystem m_BatchManagerSystem`  
- `private Game.Rendering.BatchMeshSystem m_BatchMeshSystem`  
- `private Game.Rendering.ManagedBatchSystem m_ManagedBatchSystem`  
- `private Game.Rendering.PreCullingSystem m_PreCullingSystem`  
- `private Game.Rendering.LightingSystem m_LightingSystem`  
- `private Game.Rendering.MeshColorSystem m_MeshColorSystem`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Simulation.CitizenPresenceSystem m_CitizenPresenceSystem`  
- `private Game.Simulation.TreeGrowthSystem m_TreeGrowthSystem`  
- `private Game.Simulation.WetnessSystem m_WetnessSystem`  
- `private Game.Simulation.WindSystem m_WindSystem`  
- `private Game.Simulation.DirtynessSystem m_DirtynessSystem`  
- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Unity.Entities.EntityQuery m_RenderingSettingsQuery`  
- `private Colossal.Collections.NativeAccumulator<Game.Rendering.BatchDataSystem+SmoothingNeeded> m_SmoothingNeeded`  
- `private System.Int32 m_SHCoefficients`  
- `private System.Int32 m_LodParameters`  
- `private System.Boolean m_UpdateAll`  
- `private System.Single m_LastLightFactor`  
- `private System.Single m_LodFadeTimer`  
- `private Unity.Mathematics.float4 m_LastBuildingStateOverride`  
- `private System.UInt32 m_LastCitizenPresenceVersion`  
- `private System.UInt32 m_LastTreeGrowthVersion`  
- `private System.UInt32 m_LastWetnessVersion`  
- `private System.UInt32 m_LastDirtynessVersion`  
- `private System.UInt32 m_LastFireDamageVersion`  
- `private System.UInt32 m_LastWaterDamageVersion`  
- `private System.UInt32 m_LastWeatherDamageVersion`  
- `private System.UInt32 m_LastLaneConditionFrame`  
- `private System.UInt32 m_LastDamagedFrame`  
- `private Game.Rendering.BatchDataSystem+TypeHandle __TypeHandle`  
- `public static const System.Single LOD_FADE_DURATION`  
- `public static const System.Single DEBUG_FADE_DURATION`  

## Constructors

- `public BatchDataSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private CalculateLightFactor() : System.Single`  
- `private GetDataQuery(Game.Rendering.PreCullingFlags& cullingFlags, Game.Rendering.BatchDataSystem+UpdateMasks& updateMasks) : System.Void`  
- `public GetLevelOfDetail(System.Single levelOfDetail, Game.Rendering.IGameCameraController cameraController) : System.Single`  
- `public InstancePropertiesUpdated() : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  
- `private UpdateGlobalValues(Colossal.Rendering.NativeBatchInstances<Game.Rendering.CullingData, Game.Rendering.GroupData, Game.Rendering.BatchData, Game.Rendering.InstanceData> nativeBatchInstances) : System.Void`  

## Nested types

- `Game.Rendering.BatchDataSystem+UpdateMask`  
- `Game.Rendering.BatchDataSystem+UpdateMasks`  
- `Game.Rendering.BatchDataSystem+SmoothingType`  
- `Game.Rendering.BatchDataSystem+SmoothingNeeded`  
- `Game.Rendering.BatchDataSystem+CellTypes`  
- `Game.Rendering.BatchDataSystem+BatchDataJob`  
- `Game.Rendering.BatchDataSystem+BatchLodJob`  
- `Game.Rendering.BatchDataSystem+TypeHandle`  

