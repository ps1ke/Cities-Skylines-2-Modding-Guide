# Game.Effects.LightCullingSystem

**Assembly:** `Game`  
**Namespace:** `Game.Effects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.Rendering.RenderingSystem m_RenderingSystem`  
- `private Game.Effects.EffectControlSystem m_EffectControlSystem`  
- `private Unity.Entities.EntityQuery m_LightEffectPrefabQuery`  
- `private Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, Game.Effects.LightCullingSystem+LightEffectCullData> m_LightEffectCullData`  
- `private Unity.Collections.NativeQueue<Game.Effects.LightCullingSystem+VisibleLightData> m_VisibleLights`  
- `private Unity.Collections.NativeReference<System.Single> m_LastFrameMaxPunctualLightDistance`  
- `private Game.Effects.LightCullingSystem+TypeHandle __TypeHandle`  
- `private static Game.Effects.LightCullingSystem+DefaultLightParams s_DefaultLightParams`  
- `public static System.Boolean s_enableMinMaxLightCullingOptim`  
- `public static System.Single s_maxLightDistanceScale`  
- `public static System.Single s_minLightDistanceScale`  

## Constructors

- `public LightCullingSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private ComputeLightEffectCullData(Unity.Mathematics.float4 lodParameters) : System.Void`  
- `private static GetGPULightType(Game.Prefabs.Effects.LightEffect lightEffect) : UnityEngine.Rendering.HighDefinition.GPULightType`  
- `private GetRenderDataFromLigthEffet(UnityEngine.Rendering.HighDefinition.HDLightRenderData& hdLightRenderData, Game.Prefabs.LightEffectData lightEffectData, Game.Prefabs.Effects.LightEffect lightEffect, Unity.Mathematics.float4 lodParameters) : System.Void`  
- `private GetUnityAreaShape(Game.Rendering.AreaLightShape arealightShape) : UnityEngine.Rendering.HighDefinition.AreaLightShape`  
- `private GetUnitySpotShape(Game.Rendering.SpotLightShape spotlightShape) : UnityEngine.Rendering.HighDefinition.SpotLightShape`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private ReadDefaultLightParams() : System.Void`  

## Nested types

- `Game.Effects.LightCullingSystem+DefaultLightParams`  
- `Game.Effects.LightCullingSystem+LightEffectCullData`  
- `Game.Effects.LightCullingSystem+LightCullingJob`  
- `Game.Effects.LightCullingSystem+VisibleLightData`  
- `Game.Effects.LightCullingSystem+SortAndBuildPunctualLightsJob`  
- `Game.Effects.LightCullingSystem+TypeHandle`  

