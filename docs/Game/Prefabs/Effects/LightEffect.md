# Game.Prefabs.Effects.LightEffect

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Effects`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class LightEffect : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Rendering.LightType m_Type;
    public Game.Rendering.SpotLightShape m_SpotShape;
    public Game.Rendering.AreaLightShape m_AreaShape;
    public System.Single m_Range;
    public System.Single m_Intensity;
    public Game.Prefabs.Effects.LightIntensity m_LightIntensity;
    public System.Single m_LuxAtDistance;
    public Game.Rendering.LightUnit m_LightUnit;
    public System.Boolean m_EnableSpotReflector;
    public System.Single m_SpotAngle;
    public System.Single m_InnerSpotPercentage;
    public System.Single m_ShapeRadius;
    public System.Single m_AspectRatio;
    public System.Single m_ShapeWidth;
    public System.Single m_ShapeHeight;
    public System.Boolean m_UseColorTemperature;
    public UnityEngine.Color m_Color;
    public System.Single m_ColorTemperature;
    public UnityEngine.Texture m_Cookie;
    public System.Boolean m_AffectDiffuse;
    public System.Boolean m_AffectSpecular;
    public System.Boolean m_ApplyRangeAttenuation;
    public System.Single m_LightDimmer;
    public System.Single m_LodBias;
    public System.Single m_BarnDoorAngle;
    public System.Single m_BarnDoorLength;
    public System.Boolean m_UseVolumetric;
    public System.Single m_VolumetricDimmer;
    public System.Single m_VolumetricFadeDistance;

    public LightEffect();

    private System.Single CalculateLightIntensityPunctual(System.Single intensity);
    public UnityEngine.Color ComputeLightFinalColor();
    private System.Single ComputeLightIntensity();
    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public UnityEngine.Color GetEmissionColor();
    public UnityEngine.Rendering.HighDefinition.HDLightTypeAndShape GetLightTypeAndShape();
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public System.Void RecalculateIntensity(Game.Rendering.LightUnit oldUnit, Game.Rendering.LightUnit newUnit);
}
```


## Fields

- `public Game.Rendering.LightType m_Type`  

```csharp
public Game.Rendering.LightType m_Type;
```

- `public Game.Rendering.SpotLightShape m_SpotShape`  

```csharp
public Game.Rendering.SpotLightShape m_SpotShape;
```

- `public Game.Rendering.AreaLightShape m_AreaShape`  

```csharp
public Game.Rendering.AreaLightShape m_AreaShape;
```

- `public System.Single m_Range`  

```csharp
public System.Single m_Range;
```

- `public System.Single m_Intensity`  

```csharp
public System.Single m_Intensity;
```

- `public Game.Prefabs.Effects.LightIntensity m_LightIntensity`  

```csharp
public Game.Prefabs.Effects.LightIntensity m_LightIntensity;
```

- `public System.Single m_LuxAtDistance`  

```csharp
public System.Single m_LuxAtDistance;
```

- `public Game.Rendering.LightUnit m_LightUnit`  

```csharp
public Game.Rendering.LightUnit m_LightUnit;
```

- `public System.Boolean m_EnableSpotReflector`  

```csharp
public System.Boolean m_EnableSpotReflector;
```

- `public System.Single m_SpotAngle`  

```csharp
public System.Single m_SpotAngle;
```

- `public System.Single m_InnerSpotPercentage`  

```csharp
public System.Single m_InnerSpotPercentage;
```

- `public System.Single m_ShapeRadius`  

```csharp
public System.Single m_ShapeRadius;
```

- `public System.Single m_AspectRatio`  

```csharp
public System.Single m_AspectRatio;
```

- `public System.Single m_ShapeWidth`  

```csharp
public System.Single m_ShapeWidth;
```

- `public System.Single m_ShapeHeight`  

```csharp
public System.Single m_ShapeHeight;
```

- `public System.Boolean m_UseColorTemperature`  

```csharp
public System.Boolean m_UseColorTemperature;
```

- `public UnityEngine.Color m_Color`  

```csharp
public UnityEngine.Color m_Color;
```

- `public System.Single m_ColorTemperature`  

```csharp
public System.Single m_ColorTemperature;
```

- `public UnityEngine.Texture m_Cookie`  

```csharp
public UnityEngine.Texture m_Cookie;
```

- `public System.Boolean m_AffectDiffuse`  

```csharp
public System.Boolean m_AffectDiffuse;
```

- `public System.Boolean m_AffectSpecular`  

```csharp
public System.Boolean m_AffectSpecular;
```

- `public System.Boolean m_ApplyRangeAttenuation`  

```csharp
public System.Boolean m_ApplyRangeAttenuation;
```

- `public System.Single m_LightDimmer`  

```csharp
public System.Single m_LightDimmer;
```

- `public System.Single m_LodBias`  

```csharp
public System.Single m_LodBias;
```

- `public System.Single m_BarnDoorAngle`  

```csharp
public System.Single m_BarnDoorAngle;
```

- `public System.Single m_BarnDoorLength`  

```csharp
public System.Single m_BarnDoorLength;
```

- `public System.Boolean m_UseVolumetric`  

```csharp
public System.Boolean m_UseVolumetric;
```

- `public System.Single m_VolumetricDimmer`  

```csharp
public System.Single m_VolumetricDimmer;
```

- `public System.Single m_VolumetricFadeDistance`  

```csharp
public System.Single m_VolumetricFadeDistance;
```


## Constructors

- `public LightEffect()`  

```csharp
public LightEffect();
```


## Methods

- `private CalculateLightIntensityPunctual(System.Single intensity) : System.Single`  

```csharp
private System.Single CalculateLightIntensityPunctual(System.Single intensity);
```

- `public ComputeLightFinalColor() : UnityEngine.Color`  

```csharp
public UnityEngine.Color ComputeLightFinalColor();
```

- `private ComputeLightIntensity() : System.Single`  

```csharp
private System.Single ComputeLightIntensity();
```

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public GetEmissionColor() : UnityEngine.Color`  

```csharp
public UnityEngine.Color GetEmissionColor();
```

- `public GetLightTypeAndShape() : UnityEngine.Rendering.HighDefinition.HDLightTypeAndShape`  

```csharp
public UnityEngine.Rendering.HighDefinition.HDLightTypeAndShape GetLightTypeAndShape();
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```

- `public RecalculateIntensity(Game.Rendering.LightUnit oldUnit, Game.Rendering.LightUnit newUnit) : System.Void`  

```csharp
public System.Void RecalculateIntensity(Game.Rendering.LightUnit oldUnit, Game.Rendering.LightUnit newUnit);
```


## Nested types

- `Game.Prefabs.Effects.LightEffect+ColorTemperatureSliderFieldFactory`  

