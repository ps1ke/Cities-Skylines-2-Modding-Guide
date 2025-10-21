# Game.Rendering.WindControl

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class WindControl
{
    private Game.Rendering.ShaderVariablesWind m_ShaderVariablesWindCB;
    private Game.Rendering.WindControl+SampledParameter<System.Single> _WindBaseStrengthPhase;
    private Game.Rendering.WindControl+SampledParameter<System.Single> _WindBaseStrengthPhase2;
    private Game.Rendering.WindControl+SampledParameter<System.Single> _WindTreeBaseStrengthPhase;
    private Game.Rendering.WindControl+SampledParameter<System.Single> _WindTreeBaseStrengthPhase2;
    private Game.Rendering.WindControl+SampledParameter<System.Single> _WindBaseStrengthVariancePeriod;
    private Game.Rendering.WindControl+SampledParameter<System.Single> _WindTreeBaseStrengthVariancePeriod;
    private Game.Rendering.WindControl+SampledParameter<System.Single> _WindGustStrengthPhase;
    private Game.Rendering.WindControl+SampledParameter<System.Single> _WindGustStrengthPhase2;
    private Game.Rendering.WindControl+SampledParameter<System.Single> _WindTreeGustStrengthPhase;
    private Game.Rendering.WindControl+SampledParameter<System.Single> _WindTreeGustStrengthPhase2;
    private Game.Rendering.WindControl+SampledParameter<System.Single> _WindGustStrengthVariancePeriod;
    private Game.Rendering.WindControl+SampledParameter<System.Single> _WindTreeGustStrengthVariancePeriod;
    private Game.Rendering.WindControl+SampledParameter<System.Single> _WindFlutterGustVariancePeriod;
    private Game.Rendering.WindControl+SampledParameter<System.Single> _WindTreeFlutterGustVariancePeriod;
    private System.Single _LastParametersSamplingTime;
    private static Game.Rendering.WindControl s_Instance;
    private static readonly System.Int32 m_ShaderVariablesWind;
    private static readonly Unity.Mathematics.float3 kForward;

    public static Game.Rendering.WindControl instance { get; }

    private WindControl();

    public System.Void Dispose();
    private System.Boolean GetWindComponent(UnityEngine.Camera camera, Game.Rendering.WindVolumeComponent& component);
    private System.Void SetGlobalProperties(UnityEngine.Rendering.CommandBuffer cmd, Game.Rendering.WindVolumeComponent wind);
    private System.Void SetupGPUData(UnityEngine.Rendering.ScriptableRenderContext context, UnityEngine.Camera camera);
    private System.Void UpdateCPUData(Game.Rendering.WindVolumeComponent wind);
}
```


## Fields

- `private Game.Rendering.ShaderVariablesWind m_ShaderVariablesWindCB`  

```csharp
private Game.Rendering.ShaderVariablesWind m_ShaderVariablesWindCB;
```

- `private Game.Rendering.WindControl+SampledParameter<System.Single> _WindBaseStrengthPhase`  

```csharp
private Game.Rendering.WindControl+SampledParameter<System.Single> _WindBaseStrengthPhase;
```

- `private Game.Rendering.WindControl+SampledParameter<System.Single> _WindBaseStrengthPhase2`  

```csharp
private Game.Rendering.WindControl+SampledParameter<System.Single> _WindBaseStrengthPhase2;
```

- `private Game.Rendering.WindControl+SampledParameter<System.Single> _WindTreeBaseStrengthPhase`  

```csharp
private Game.Rendering.WindControl+SampledParameter<System.Single> _WindTreeBaseStrengthPhase;
```

- `private Game.Rendering.WindControl+SampledParameter<System.Single> _WindTreeBaseStrengthPhase2`  

```csharp
private Game.Rendering.WindControl+SampledParameter<System.Single> _WindTreeBaseStrengthPhase2;
```

- `private Game.Rendering.WindControl+SampledParameter<System.Single> _WindBaseStrengthVariancePeriod`  

```csharp
private Game.Rendering.WindControl+SampledParameter<System.Single> _WindBaseStrengthVariancePeriod;
```

- `private Game.Rendering.WindControl+SampledParameter<System.Single> _WindTreeBaseStrengthVariancePeriod`  

```csharp
private Game.Rendering.WindControl+SampledParameter<System.Single> _WindTreeBaseStrengthVariancePeriod;
```

- `private Game.Rendering.WindControl+SampledParameter<System.Single> _WindGustStrengthPhase`  

```csharp
private Game.Rendering.WindControl+SampledParameter<System.Single> _WindGustStrengthPhase;
```

- `private Game.Rendering.WindControl+SampledParameter<System.Single> _WindGustStrengthPhase2`  

```csharp
private Game.Rendering.WindControl+SampledParameter<System.Single> _WindGustStrengthPhase2;
```

- `private Game.Rendering.WindControl+SampledParameter<System.Single> _WindTreeGustStrengthPhase`  

```csharp
private Game.Rendering.WindControl+SampledParameter<System.Single> _WindTreeGustStrengthPhase;
```

- `private Game.Rendering.WindControl+SampledParameter<System.Single> _WindTreeGustStrengthPhase2`  

```csharp
private Game.Rendering.WindControl+SampledParameter<System.Single> _WindTreeGustStrengthPhase2;
```

- `private Game.Rendering.WindControl+SampledParameter<System.Single> _WindGustStrengthVariancePeriod`  

```csharp
private Game.Rendering.WindControl+SampledParameter<System.Single> _WindGustStrengthVariancePeriod;
```

- `private Game.Rendering.WindControl+SampledParameter<System.Single> _WindTreeGustStrengthVariancePeriod`  

```csharp
private Game.Rendering.WindControl+SampledParameter<System.Single> _WindTreeGustStrengthVariancePeriod;
```

- `private Game.Rendering.WindControl+SampledParameter<System.Single> _WindFlutterGustVariancePeriod`  

```csharp
private Game.Rendering.WindControl+SampledParameter<System.Single> _WindFlutterGustVariancePeriod;
```

- `private Game.Rendering.WindControl+SampledParameter<System.Single> _WindTreeFlutterGustVariancePeriod`  

```csharp
private Game.Rendering.WindControl+SampledParameter<System.Single> _WindTreeFlutterGustVariancePeriod;
```

- `private System.Single _LastParametersSamplingTime`  

```csharp
private System.Single _LastParametersSamplingTime;
```

- `private static Game.Rendering.WindControl s_Instance`  

```csharp
private static Game.Rendering.WindControl s_Instance;
```

- `private static readonly System.Int32 m_ShaderVariablesWind`  

```csharp
private static readonly System.Int32 m_ShaderVariablesWind;
```

- `private static readonly Unity.Mathematics.float3 kForward`  

```csharp
private static readonly Unity.Mathematics.float3 kForward;
```


## Properties

- `public static Game.Rendering.WindControl instance { get }`  

```csharp
public static Game.Rendering.WindControl instance { get; }
```


## Constructors

- `private WindControl()`  

```csharp
private WindControl();
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `private GetWindComponent(UnityEngine.Camera camera, Game.Rendering.WindVolumeComponent& component) : System.Boolean`  

```csharp
private System.Boolean GetWindComponent(UnityEngine.Camera camera, Game.Rendering.WindVolumeComponent& component);
```

- `private SetGlobalProperties(UnityEngine.Rendering.CommandBuffer cmd, Game.Rendering.WindVolumeComponent wind) : System.Void`  

```csharp
private System.Void SetGlobalProperties(UnityEngine.Rendering.CommandBuffer cmd, Game.Rendering.WindVolumeComponent wind);
```

- `private SetupGPUData(UnityEngine.Rendering.ScriptableRenderContext context, UnityEngine.Camera camera) : System.Void`  

```csharp
private System.Void SetupGPUData(UnityEngine.Rendering.ScriptableRenderContext context, UnityEngine.Camera camera);
```

- `private UpdateCPUData(Game.Rendering.WindVolumeComponent wind) : System.Void`  

```csharp
private System.Void UpdateCPUData(Game.Rendering.WindVolumeComponent wind);
```


## Nested types

- `Game.Rendering.WindControl+SampledParameter<T>`  

