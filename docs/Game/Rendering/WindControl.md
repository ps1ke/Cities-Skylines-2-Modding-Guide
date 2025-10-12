# Game.Rendering.WindControl

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `private Game.Rendering.ShaderVariablesWind m_ShaderVariablesWindCB`  
- `private Game.Rendering.WindControl+SampledParameter<System.Single> _WindBaseStrengthPhase`  
- `private Game.Rendering.WindControl+SampledParameter<System.Single> _WindBaseStrengthPhase2`  
- `private Game.Rendering.WindControl+SampledParameter<System.Single> _WindTreeBaseStrengthPhase`  
- `private Game.Rendering.WindControl+SampledParameter<System.Single> _WindTreeBaseStrengthPhase2`  
- `private Game.Rendering.WindControl+SampledParameter<System.Single> _WindBaseStrengthVariancePeriod`  
- `private Game.Rendering.WindControl+SampledParameter<System.Single> _WindTreeBaseStrengthVariancePeriod`  
- `private Game.Rendering.WindControl+SampledParameter<System.Single> _WindGustStrengthPhase`  
- `private Game.Rendering.WindControl+SampledParameter<System.Single> _WindGustStrengthPhase2`  
- `private Game.Rendering.WindControl+SampledParameter<System.Single> _WindTreeGustStrengthPhase`  
- `private Game.Rendering.WindControl+SampledParameter<System.Single> _WindTreeGustStrengthPhase2`  
- `private Game.Rendering.WindControl+SampledParameter<System.Single> _WindGustStrengthVariancePeriod`  
- `private Game.Rendering.WindControl+SampledParameter<System.Single> _WindTreeGustStrengthVariancePeriod`  
- `private Game.Rendering.WindControl+SampledParameter<System.Single> _WindFlutterGustVariancePeriod`  
- `private Game.Rendering.WindControl+SampledParameter<System.Single> _WindTreeFlutterGustVariancePeriod`  
- `private System.Single _LastParametersSamplingTime`  
- `private static Game.Rendering.WindControl s_Instance`  
- `private static readonly System.Int32 m_ShaderVariablesWind`  
- `private static readonly Unity.Mathematics.float3 kForward`  

## Properties

- `public static Game.Rendering.WindControl instance { get }`  

## Constructors

- `private WindControl()`  

## Methods

- `public Dispose() : System.Void`  
- `private GetWindComponent(UnityEngine.Camera camera, Game.Rendering.WindVolumeComponent& component) : System.Boolean`  
- `private SetGlobalProperties(UnityEngine.Rendering.CommandBuffer cmd, Game.Rendering.WindVolumeComponent wind) : System.Void`  
- `private SetupGPUData(UnityEngine.Rendering.ScriptableRenderContext context, UnityEngine.Camera camera) : System.Void`  
- `private UpdateCPUData(Game.Rendering.WindVolumeComponent wind) : System.Void`  

## Nested types

- `Game.Rendering.WindControl+SampledParameter<T>`  

