# Game.Rendering.LightingSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Fields

- `private Game.Simulation.PlanetarySystem m_PlanetarySystem`  
- `protected Unity.Entities.EntityQuery m_TimeSettingGroup`  
- `private UnityEngine.Rendering.HighDefinition.Exposure m_Exposure`  
- `private UnityEngine.Rendering.HighDefinition.PhysicallyBasedSky m_PhysicallyBasedSky`  
- `private UnityEngine.Rendering.HighDefinition.ColorAdjustments m_ColorAdjustments`  
- `private UnityEngine.Rendering.HighDefinition.IndirectLightingController m_Indirect`  
- `private UnityEngine.Rendering.HighDefinition.Tonemapping m_Tonemap`  
- `private System.Boolean m_PostProcessingSetup`  
- `private DayNightCycleData m_NightDayCycleData`  
- `private UnityEngine.Rendering.Volume m_Volume`  
- `private UnityEngine.Rendering.VolumeProfile m_Profile`  
- `private UnityEngine.RenderTexture m_BlendResult`  
- `private UnityEngine.ComputeShader m_LUTBlend`  
- `private System.Int32 m_KernalBlend`  
- `private Game.Rendering.LightingSystem+State m_LastState`  
- `private System.Single m_LastDelta`  
- `private System.Boolean <shadowDisabled>k__BackingField`  
- `private System.Single <dayLightBrightness>k__BackingField`  

## Properties

- `private System.Boolean shadowDisabled { private get; private set }`  
- `public System.Single dayLightBrightness { get; private set }`  
- `public Game.Rendering.LightingSystem+State state { get }`  

## Constructors

- `public LightingSystem()`  

## Methods

- `private BlendLUT(UnityEngine.Texture3D source, UnityEngine.Texture3D destination, System.Single delta, System.Single lutContribution) : System.Void`  
- `private CalcObscured(Game.Simulation.PlanetarySystem+LightData moon, Game.Simulation.PlanetarySystem+LightData night, System.Single range = 0,3) : System.Single`  
- `private CalculateState(Unity.Mathematics.float3 sunPosition, Unity.Mathematics.float3 sunDirection, System.Single& delta) : Game.Rendering.LightingSystem+State`  
- `private EnableShadows(Game.Simulation.PlanetarySystem+LightData lightData, System.Boolean enabled) : System.Void`  
- `private NextState(Game.Rendering.LightingSystem+State value) : Game.Rendering.LightingSystem+State`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private SetupPostprocessing() : System.Void`  

## Nested types

- `Game.Rendering.LightingSystem+ShaderID`  
- `Game.Rendering.LightingSystem+State`  

