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
private float CalculateLightIntensityPunctual(float intensity)
	{
		switch (m_Type)
		{
		case Game.Rendering.LightType.Point:
			if (m_LightUnit == Game.Rendering.LightUnit.Candela)
			{
				return intensity;
			}
			return Game.Rendering.LightUtils.ConvertPointLightLumenToCandela(intensity);
		case Game.Rendering.LightType.Spot:
			if (m_LightUnit == Game.Rendering.LightUnit.Candela)
			{
				return intensity;
			}
			if (m_EnableSpotReflector)
			{
				if (m_SpotShape == Game.Rendering.SpotLightShape.Cone)
				{
					return Game.Rendering.LightUtils.ConvertSpotLightLumenToCandela(intensity, m_SpotAngle * (MathF.PI / 180f), exact: true);
				}
				if (m_SpotShape == Game.Rendering.SpotLightShape.Pyramid)
				{
					Game.Rendering.LightUtils.CalculateAnglesForPyramid(m_AspectRatio, m_SpotAngle * (MathF.PI / 180f), out var angleA, out var angleB);
					return Game.Rendering.LightUtils.ConvertFrustrumLightLumenToCandela(intensity, angleA, angleB);
				}
				return Game.Rendering.LightUtils.ConvertPointLightLumenToCandela(intensity);
			}
			return Game.Rendering.LightUtils.ConvertPointLightLumenToCandela(intensity);
		default:
			return intensity;
		}
	}
```

- `public ComputeLightFinalColor() : UnityEngine.Color`  

```csharp
public Color ComputeLightFinalColor()
	{
		Color color = m_Color.linear * ComputeLightIntensity();
		if (m_UseColorTemperature)
		{
			color *= Mathf.CorrelatedColorTemperatureToRGB(m_ColorTemperature);
		}
		return color * m_LightDimmer;
	}
```

- `private ComputeLightIntensity() : System.Single`  

```csharp
private float ComputeLightIntensity()
	{
		if (m_LightUnit == Game.Rendering.LightUnit.Lumen)
		{
			if (m_Type == Game.Rendering.LightType.Spot || m_Type == Game.Rendering.LightType.Point)
			{
				return CalculateLightIntensityPunctual(m_LightIntensity.m_Intensity);
			}
			return Game.Rendering.LightUtils.ConvertAreaLightLumenToLuminance(m_AreaShape, m_LightIntensity.m_Intensity, m_ShapeWidth, m_ShapeHeight);
		}
		if (m_LightUnit == Game.Rendering.LightUnit.Ev100)
		{
			return Game.Rendering.LightUtils.ConvertEvToLuminance(m_LightIntensity.m_Intensity);
		}
		if ((m_Type == Game.Rendering.LightType.Spot || m_Type == Game.Rendering.LightType.Point) && m_LightUnit == Game.Rendering.LightUnit.Lux)
		{
			if (m_Type == Game.Rendering.LightType.Spot && m_SpotShape == Game.Rendering.SpotLightShape.Box)
			{
				return m_LightIntensity.m_Intensity;
			}
			return Game.Rendering.LightUtils.ConvertLuxToCandela(m_LightIntensity.m_Intensity, m_LuxAtDistance);
		}
		return m_LightIntensity.m_Intensity;
	}
```

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
	}
```

- `public GetEmissionColor() : UnityEngine.Color`  

```csharp
public Color GetEmissionColor()
	{
		Color color = m_Color.linear * m_LightIntensity.m_Intensity;
		if (m_UseColorTemperature)
		{
			color *= Mathf.CorrelatedColorTemperatureToRGB(m_ColorTemperature);
		}
		return color * m_LightDimmer;
	}
```

- `public GetLightTypeAndShape() : UnityEngine.Rendering.HighDefinition.HDLightTypeAndShape`  

```csharp
public HDLightTypeAndShape GetLightTypeAndShape()
	{
		return m_Type switch
		{
			Game.Rendering.LightType.Spot => m_SpotShape switch
			{
				Game.Rendering.SpotLightShape.Cone => HDLightTypeAndShape.ConeSpot, 
				Game.Rendering.SpotLightShape.Box => HDLightTypeAndShape.BoxSpot, 
				Game.Rendering.SpotLightShape.Pyramid => HDLightTypeAndShape.PyramidSpot, 
				_ => throw new NotImplementedException($"Spot shape not implemented {m_SpotShape}"), 
			}, 
			Game.Rendering.LightType.Point => HDLightTypeAndShape.Point, 
			Game.Rendering.LightType.Area => m_AreaShape switch
			{
				Game.Rendering.AreaLightShape.Rectangle => HDLightTypeAndShape.RectangleArea, 
				Game.Rendering.AreaLightShape.Tube => HDLightTypeAndShape.TubeArea, 
				_ => throw new NotImplementedException($"Area shape not implemented {m_AreaShape}"), 
			}, 
			_ => throw new NotImplementedException($"Light type not implemented {m_Type}"), 
		};
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<LightEffectData>());
		components.Add(ComponentType.ReadWrite<EffectColorData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		int num = RenderingUtils.CalculateLodLimit(RenderingUtils.GetRenderingSize(new float3(m_Range)), m_LodBias);
		float num2 = RenderingUtils.CalculateDistanceFactor(num);
		float invDistanceFactor = 1f / num2;
		if (m_LightIntensity != null)
		{
			if (m_LightUnit != m_LightIntensity.m_LightUnit)
			{
				RecalculateIntensity(m_LightUnit, m_LightIntensity.m_LightUnit);
			}
			m_Intensity = m_LightIntensity.m_Intensity;
			m_LightUnit = m_LightIntensity.m_LightUnit;
		}
		else
		{
			m_LightIntensity = new LightIntensity
			{
				m_Intensity = m_Intensity,
				m_LightUnit = m_LightUnit
			};
		}
		LightEffectData componentData = new LightEffectData
		{
			m_Range = m_Range,
			m_DistanceFactor = num2,
			m_InvDistanceFactor = invDistanceFactor,
			m_MinLod = num
		};
		entityManager.SetComponentData(entity, componentData);
		EffectColorData componentData2 = entityManager.GetComponentData<EffectColorData>(entity);
		componentData2.m_Color = ComputeLightFinalColor();
		entityManager.SetComponentData(entity, componentData2);
	}
```

- `public RecalculateIntensity(Game.Rendering.LightUnit oldUnit, Game.Rendering.LightUnit newUnit) : System.Void`  

```csharp
public void RecalculateIntensity(Game.Rendering.LightUnit oldUnit, Game.Rendering.LightUnit newUnit)
	{
		m_Intensity = Game.Rendering.LightUtils.ConvertLightIntensity(oldUnit, newUnit, this, m_Intensity);
		m_LightIntensity.m_Intensity = m_Intensity;
	}
```


## Nested types

- `Game.Prefabs.Effects.LightEffect+ColorTemperatureSliderFieldFactory`  

