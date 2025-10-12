# Game.Rendering.PreCullingSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Common.BoundsMask <visibleMask>k__BackingField`  
- `private Game.Common.BoundsMask <becameVisible>k__BackingField`  
- `private Game.Common.BoundsMask <becameHidden>k__BackingField`  
- `private Game.Rendering.RenderingSystem m_RenderingSystem`  
- `private Game.Rendering.UndergroundViewSystem m_UndergroundViewSystem`  
- `private Game.Rendering.BatchMeshSystem m_BatchMeshSystem`  
- `private Game.Rendering.BatchDataSystem m_BatchDataSystem`  
- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  
- `private Game.Net.SearchSystem m_NetSearchSystem`  
- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  
- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Unity.Entities.EntityQuery m_InitializeQuery`  
- `private Unity.Entities.EntityQuery m_EventQuery`  
- `private Unity.Entities.EntityQuery m_CullingInfoQuery`  
- `private Unity.Entities.EntityQuery m_TempQuery`  
- `private Unity.Mathematics.float3 m_PrevCameraPosition`  
- `private Unity.Mathematics.float3 m_PrevCameraDirection`  
- `private Unity.Mathematics.float4 m_PrevLodParameters`  
- `private Game.Common.BoundsMask m_PrevVisibleMask`  
- `private Game.Rendering.PreCullingSystem+QueryFlags m_PrevQueryFlags`  
- `private System.Collections.Generic.Dictionary<Game.Rendering.PreCullingSystem+QueryFlags, Unity.Entities.EntityQuery> m_CullingQueries`  
- `private System.Collections.Generic.Dictionary<Game.Rendering.PreCullingSystem+QueryFlags, Unity.Entities.EntityQuery> m_RelativeQueries`  
- `private System.Collections.Generic.Dictionary<Game.Rendering.PreCullingSystem+QueryFlags, Unity.Entities.EntityQuery> m_RemoveQueries`  
- `private Unity.Collections.NativeList<Game.Rendering.PreCullingData> m_CullingData`  
- `private Unity.Collections.NativeList<Game.Rendering.PreCullingData> m_UpdatedData`  
- `private Unity.Entities.Entity m_FadeContainer`  
- `private Unity.Jobs.JobHandle m_WriteDependencies`  
- `private Unity.Jobs.JobHandle m_ReadDependencies`  
- `private System.Boolean m_ResetPrevious`  
- `private System.Boolean m_Loaded`  
- `private Game.Rendering.PreCullingSystem+TypeHandle __TypeHandle`  

## Properties

- `public Game.Common.BoundsMask visibleMask { get; private set }`  
- `public Game.Common.BoundsMask becameVisible { get; private set }`  
- `public Game.Common.BoundsMask becameHidden { get; private set }`  

## Constructors

- `public PreCullingSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public AddCullingDataReader(Unity.Jobs.JobHandle dependencies) : System.Void`  
- `public AddCullingDataWriter(Unity.Jobs.JobHandle dependencies) : System.Void`  
- `public GetCullingData(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Game.Rendering.PreCullingData>`  
- `private GetCullingQuery(Game.Rendering.PreCullingSystem+QueryFlags flags) : Unity.Entities.EntityQuery`  
- `public GetFadeContainer() : Unity.Entities.Entity`  
- `private GetLoaded() : System.Boolean`  
- `private GetQueryFlags() : Game.Rendering.PreCullingSystem+QueryFlags`  
- `private GetRelativeQuery(Game.Rendering.PreCullingSystem+QueryFlags flags) : Unity.Entities.EntityQuery`  
- `private GetRemoveQuery(Game.Rendering.PreCullingSystem+QueryFlags flags) : Unity.Entities.EntityQuery`  
- `public GetUpdatedData(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Game.Rendering.PreCullingData>`  
- `private InitializeCullingData() : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  
- `public ResetCulling() : System.Void`  

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

