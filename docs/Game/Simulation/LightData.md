# Game.Simulation.PlanetarySystem+LightData

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct LightData
{
    private readonly System.String m_Tag;
    private UnityEngine.Transform <transform>k__BackingField;
    private UnityEngine.Light <light>k__BackingField;
    private UnityEngine.Rendering.HighDefinition.HDAdditionalLightData <additionalData>k__BackingField;
    private System.Single <initialIntensity>k__BackingField;

    public UnityEngine.Transform transform { get; private set; }
    public UnityEngine.Light light { get; private set; }
    public UnityEngine.Rendering.HighDefinition.HDAdditionalLightData additionalData { get; private set; }
    public System.Single initialIntensity { get; private set; }
    public System.Boolean isValid { get; }

    public LightData(System.String tag);

}
```


## Fields

- `private readonly System.String m_Tag`  

```csharp
private readonly System.String m_Tag;
```

- `private UnityEngine.Transform <transform>k__BackingField`  

```csharp
private UnityEngine.Transform <transform>k__BackingField;
```

- `private UnityEngine.Light <light>k__BackingField`  

```csharp
private UnityEngine.Light <light>k__BackingField;
```

- `private UnityEngine.Rendering.HighDefinition.HDAdditionalLightData <additionalData>k__BackingField`  

```csharp
private UnityEngine.Rendering.HighDefinition.HDAdditionalLightData <additionalData>k__BackingField;
```

- `private System.Single <initialIntensity>k__BackingField`  

```csharp
private System.Single <initialIntensity>k__BackingField;
```


## Properties

- `public UnityEngine.Transform transform { get; private set }`  

```csharp
public UnityEngine.Transform transform { get; private set; }
```

- `public UnityEngine.Light light { get; private set }`  

```csharp
public UnityEngine.Light light { get; private set; }
```

- `public UnityEngine.Rendering.HighDefinition.HDAdditionalLightData additionalData { get; private set }`  

```csharp
public UnityEngine.Rendering.HighDefinition.HDAdditionalLightData additionalData { get; private set; }
```

- `public System.Single initialIntensity { get; private set }`  

```csharp
public System.Single initialIntensity { get; private set; }
```

- `public System.Boolean isValid { get }`  

```csharp
public System.Boolean isValid { get; }
```


## Constructors

- `public LightData(System.String tag)`  

```csharp
public LightData(System.String tag);
```


