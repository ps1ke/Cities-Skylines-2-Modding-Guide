# Game.Rendering.LightingSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class LightingSystem : Game.GameSystemBase
{
    private Game.Simulation.PlanetarySystem m_PlanetarySystem;
    protected Unity.Entities.EntityQuery m_TimeSettingGroup;
    private UnityEngine.Rendering.HighDefinition.Exposure m_Exposure;
    private UnityEngine.Rendering.HighDefinition.PhysicallyBasedSky m_PhysicallyBasedSky;
    private UnityEngine.Rendering.HighDefinition.ColorAdjustments m_ColorAdjustments;
    private UnityEngine.Rendering.HighDefinition.IndirectLightingController m_Indirect;
    private UnityEngine.Rendering.HighDefinition.Tonemapping m_Tonemap;
    private System.Boolean m_PostProcessingSetup;
    private DayNightCycleData m_NightDayCycleData;
    private UnityEngine.Rendering.Volume m_Volume;
    private UnityEngine.Rendering.VolumeProfile m_Profile;
    private UnityEngine.RenderTexture m_BlendResult;
    private UnityEngine.ComputeShader m_LUTBlend;
    private System.Int32 m_KernalBlend;
    private Game.Rendering.LightingSystem+State m_LastState;
    private System.Single m_LastDelta;
    private System.Boolean <shadowDisabled>k__BackingField;
    private System.Single <dayLightBrightness>k__BackingField;

    private System.Boolean shadowDisabled { private get; private set; }
    public System.Single dayLightBrightness { get; private set; }
    public Game.Rendering.LightingSystem+State state { get; }

    public LightingSystem();

    private System.Void BlendLUT(UnityEngine.Texture3D source, UnityEngine.Texture3D destination, System.Single delta, System.Single lutContribution);
    private System.Single CalcObscured(Game.Simulation.PlanetarySystem+LightData moon, Game.Simulation.PlanetarySystem+LightData night, System.Single range);
    private Game.Rendering.LightingSystem+State CalculateState(Unity.Mathematics.float3 sunPosition, Unity.Mathematics.float3 sunDirection, System.Single& delta);
    private System.Void EnableShadows(Game.Simulation.PlanetarySystem+LightData lightData, System.Boolean enabled);
    private Game.Rendering.LightingSystem+State NextState(Game.Rendering.LightingSystem+State value);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    private System.Void SetupPostprocessing();
}
```


## Fields

- `private Game.Simulation.PlanetarySystem m_PlanetarySystem`  

```csharp
private Game.Simulation.PlanetarySystem m_PlanetarySystem;
```

- `protected Unity.Entities.EntityQuery m_TimeSettingGroup`  

```csharp
protected Unity.Entities.EntityQuery m_TimeSettingGroup;
```

- `private UnityEngine.Rendering.HighDefinition.Exposure m_Exposure`  

```csharp
private UnityEngine.Rendering.HighDefinition.Exposure m_Exposure;
```

- `private UnityEngine.Rendering.HighDefinition.PhysicallyBasedSky m_PhysicallyBasedSky`  

```csharp
private UnityEngine.Rendering.HighDefinition.PhysicallyBasedSky m_PhysicallyBasedSky;
```

- `private UnityEngine.Rendering.HighDefinition.ColorAdjustments m_ColorAdjustments`  

```csharp
private UnityEngine.Rendering.HighDefinition.ColorAdjustments m_ColorAdjustments;
```

- `private UnityEngine.Rendering.HighDefinition.IndirectLightingController m_Indirect`  

```csharp
private UnityEngine.Rendering.HighDefinition.IndirectLightingController m_Indirect;
```

- `private UnityEngine.Rendering.HighDefinition.Tonemapping m_Tonemap`  

```csharp
private UnityEngine.Rendering.HighDefinition.Tonemapping m_Tonemap;
```

- `private System.Boolean m_PostProcessingSetup`  

```csharp
private System.Boolean m_PostProcessingSetup;
```

- `private DayNightCycleData m_NightDayCycleData`  

```csharp
private DayNightCycleData m_NightDayCycleData;
```

- `private UnityEngine.Rendering.Volume m_Volume`  

```csharp
private UnityEngine.Rendering.Volume m_Volume;
```

- `private UnityEngine.Rendering.VolumeProfile m_Profile`  

```csharp
private UnityEngine.Rendering.VolumeProfile m_Profile;
```

- `private UnityEngine.RenderTexture m_BlendResult`  

```csharp
private UnityEngine.RenderTexture m_BlendResult;
```

- `private UnityEngine.ComputeShader m_LUTBlend`  

```csharp
private UnityEngine.ComputeShader m_LUTBlend;
```

- `private System.Int32 m_KernalBlend`  

```csharp
private System.Int32 m_KernalBlend;
```

- `private Game.Rendering.LightingSystem+State m_LastState`  

```csharp
private Game.Rendering.LightingSystem+State m_LastState;
```

- `private System.Single m_LastDelta`  

```csharp
private System.Single m_LastDelta;
```

- `private System.Boolean <shadowDisabled>k__BackingField`  

```csharp
private System.Boolean <shadowDisabled>k__BackingField;
```

- `private System.Single <dayLightBrightness>k__BackingField`  

```csharp
private System.Single <dayLightBrightness>k__BackingField;
```


## Properties

- `private System.Boolean shadowDisabled { private get; private set }`  

```csharp
private System.Boolean shadowDisabled { private get; private set; }
```

- `public System.Single dayLightBrightness { get; private set }`  

```csharp
public System.Single dayLightBrightness { get; private set; }
```

- `public Game.Rendering.LightingSystem+State state { get }`  

```csharp
public Game.Rendering.LightingSystem+State state { get; }
```


## Constructors

- `public LightingSystem()`  

```csharp
public LightingSystem();
```


## Methods

- `private BlendLUT(UnityEngine.Texture3D source, UnityEngine.Texture3D destination, System.Single delta, System.Single lutContribution) : System.Void`  

```csharp
private System.Void BlendLUT(UnityEngine.Texture3D source, UnityEngine.Texture3D destination, System.Single delta, System.Single lutContribution);
```

- `private CalcObscured(Game.Simulation.PlanetarySystem+LightData moon, Game.Simulation.PlanetarySystem+LightData night, System.Single range = 0,3) : System.Single`  

```csharp
private System.Single CalcObscured(Game.Simulation.PlanetarySystem+LightData moon, Game.Simulation.PlanetarySystem+LightData night, System.Single range);
```

- `private CalculateState(Unity.Mathematics.float3 sunPosition, Unity.Mathematics.float3 sunDirection, System.Single& delta) : Game.Rendering.LightingSystem+State`  

```csharp
private Game.Rendering.LightingSystem+State CalculateState(Unity.Mathematics.float3 sunPosition, Unity.Mathematics.float3 sunDirection, System.Single& delta);
```

- `private EnableShadows(Game.Simulation.PlanetarySystem+LightData lightData, System.Boolean enabled) : System.Void`  

```csharp
private System.Void EnableShadows(Game.Simulation.PlanetarySystem+LightData lightData, System.Boolean enabled);
```

- `private NextState(Game.Rendering.LightingSystem+State value) : Game.Rendering.LightingSystem+State`  

```csharp
private Game.Rendering.LightingSystem+State NextState(Game.Rendering.LightingSystem+State value);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private SetupPostprocessing() : System.Void`  

```csharp
private System.Void SetupPostprocessing();
```


## Nested types

- `Game.Rendering.LightingSystem+ShaderID`  
- `Game.Rendering.LightingSystem+State`  

