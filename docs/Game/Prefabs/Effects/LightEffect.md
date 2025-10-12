# Game.Prefabs.Effects.LightEffect

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs.Effects`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Fields

- `public Game.Rendering.LightType m_Type`  
- `public Game.Rendering.SpotLightShape m_SpotShape`  
- `public Game.Rendering.AreaLightShape m_AreaShape`  
- `public System.Single m_Range`  
- `public System.Single m_Intensity`  
- `public Game.Prefabs.Effects.LightIntensity m_LightIntensity`  
- `public System.Single m_LuxAtDistance`  
- `public Game.Rendering.LightUnit m_LightUnit`  
- `public System.Boolean m_EnableSpotReflector`  
- `public System.Single m_SpotAngle`  
- `public System.Single m_InnerSpotPercentage`  
- `public System.Single m_ShapeRadius`  
- `public System.Single m_AspectRatio`  
- `public System.Single m_ShapeWidth`  
- `public System.Single m_ShapeHeight`  
- `public System.Boolean m_UseColorTemperature`  
- `public UnityEngine.Color m_Color`  
- `public System.Single m_ColorTemperature`  
- `public UnityEngine.Texture m_Cookie`  
- `public System.Boolean m_AffectDiffuse`  
- `public System.Boolean m_AffectSpecular`  
- `public System.Boolean m_ApplyRangeAttenuation`  
- `public System.Single m_LightDimmer`  
- `public System.Single m_LodBias`  
- `public System.Single m_BarnDoorAngle`  
- `public System.Single m_BarnDoorLength`  
- `public System.Boolean m_UseVolumetric`  
- `public System.Single m_VolumetricDimmer`  
- `public System.Single m_VolumetricFadeDistance`  

## Constructors

- `public LightEffect()`  

## Methods

- `private CalculateLightIntensityPunctual(System.Single intensity) : System.Single`  
- `public ComputeLightFinalColor() : UnityEngine.Color`  
- `private ComputeLightIntensity() : System.Single`  
- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public GetEmissionColor() : UnityEngine.Color`  
- `public GetLightTypeAndShape() : UnityEngine.Rendering.HighDefinition.HDLightTypeAndShape`  
- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  
- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  
- `public RecalculateIntensity(Game.Rendering.LightUnit oldUnit, Game.Rendering.LightUnit newUnit) : System.Void`  

## Nested types

- `Game.Prefabs.Effects.LightEffect+ColorTemperatureSliderFieldFactory`  

