# Game.Effects.EffectControlSystem

**Assembly:** `Game`  
**Namespace:** `Game.Effects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Effects.VFXSystem m_VFXSystem`  
- `private Game.Effects.SearchSystem m_SearchSystem`  
- `private Game.Effects.EffectFlagSystem m_EffectFlagSystem`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Rendering.PreCullingSystem m_PreCullingSystem`  
- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Rendering.RenderingSystem m_RenderingSystem`  
- `private Game.Rendering.BatchDataSystem m_BatchDataSystem`  
- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  
- `private Game.Effects.EffectControlData m_EffectControlData`  
- `private Unity.Collections.NativeList<Game.Effects.EnabledEffectData> m_EnabledData`  
- `private Unity.Entities.EntityQuery m_UpdatedEffectsQuery`  
- `private Unity.Entities.EntityQuery m_AllEffectsQuery`  
- `private Unity.Jobs.JobHandle m_EnabledWriteDependencies`  
- `private Unity.Jobs.JobHandle m_EnabledReadDependencies`  
- `private Unity.Mathematics.float3 m_PrevCameraPosition`  
- `private Unity.Mathematics.float3 m_PrevCameraDirection`  
- `private Unity.Mathematics.float4 m_PrevLodParameters`  
- `private System.Boolean m_Loaded`  
- `private System.Boolean m_ResetPrevious`  
- `private Game.Effects.EffectControlSystem+TypeHandle __TypeHandle`  

## Constructors

- `public EffectControlSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public AddEnabledDataReader(Unity.Jobs.JobHandle dependencies) : System.Void`  
- `public AddEnabledDataWriter(Unity.Jobs.JobHandle dependencies) : System.Void`  
- `public GetEnabledData(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Game.Effects.EnabledEffectData>`  
- `private GetLoaded() : System.Boolean`  
- `public GetLodParameters(Unity.Mathematics.float4& lodParameters, Unity.Mathematics.float3& cameraPosition, Unity.Mathematics.float3& cameraDirection) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

## Nested types

- `Game.Effects.EffectControlSystem+EffectControlJob`  
- `Game.Effects.EffectControlSystem+EffectCullingJob`  
- `Game.Effects.EffectControlSystem+TreeCullingJob1`  
- `Game.Effects.EffectControlSystem+TreeCullingJob2`  
- `Game.Effects.EffectControlSystem+TreeCullingIterator`  
- `Game.Effects.EffectControlSystem+ActionFlags`  
- `Game.Effects.EffectControlSystem+EnabledAction`  
- `Game.Effects.EffectControlSystem+OverflowAction`  
- `Game.Effects.EffectControlSystem+EnabledActionJob`  
- `Game.Effects.EffectControlSystem+ResizeEnabledDataJob`  
- `Game.Effects.EffectControlSystem+TypeHandle`  

