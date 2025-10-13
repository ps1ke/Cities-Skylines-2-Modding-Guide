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
[Preserve]
	public LightingSystem()
	{
	}
```


## Methods

- `private BlendLUT(UnityEngine.Texture3D source, UnityEngine.Texture3D destination, System.Single delta, System.Single lutContribution) : System.Void`  

```csharp
private void BlendLUT(Texture3D source, Texture3D destination, float delta, float lutContribution)
	{
		if (source != null && destination != null)
		{
			if (m_LUTBlend != null)
			{
				m_LUTBlend.SetTexture(m_KernalBlend, ShaderID._TargetLUT, m_BlendResult);
				m_LUTBlend.SetTexture(m_KernalBlend, ShaderID._SourceLUT, source);
				m_LUTBlend.SetTexture(m_KernalBlend, ShaderID._DestinationLUT, destination);
				m_LUTBlend.SetFloat(ShaderID._BlendLUT, math.clamp(delta, 0f, 1f));
				m_LUTBlend.Dispatch(m_KernalBlend, 32, 32, 32);
				m_Tonemap.lutTexture.value = m_BlendResult;
				m_Tonemap.lutContribution.value = lutContribution;
			}
			else
			{
				m_Tonemap.lutTexture.value = ((delta < 0.5f) ? source : destination);
				m_Tonemap.lutContribution.value = lutContribution;
			}
		}
		else if (source != null && destination == null)
		{
			m_Tonemap.lutTexture.value = source;
			m_Tonemap.lutContribution.value = math.lerp(lutContribution, 0f, delta);
		}
		else if (destination != null && source == null)
		{
			m_Tonemap.lutTexture.value = destination;
			m_Tonemap.lutContribution.value = math.lerp(0f, lutContribution, delta);
		}
		else
		{
			m_Tonemap.lutTexture.value = null;
			m_Tonemap.lutContribution.value = lutContribution;
		}
	}
```

- `private CalcObscured(Game.Simulation.PlanetarySystem+LightData moon, Game.Simulation.PlanetarySystem+LightData night, System.Single range = 0,3) : System.Single`  

```csharp
private float CalcObscured(PlanetarySystem.LightData moon, PlanetarySystem.LightData night, float range = 0.3f)
	{
		float y = moon.transform.position.y;
		float y2 = night.transform.position.y;
		if (y != y2)
		{
			return math.clamp((y2 - y) / range, 0f, 1f);
		}
		return 0f;
	}
```

- `private CalculateState(Unity.Mathematics.float3 sunPosition, Unity.Mathematics.float3 sunDirection, System.Single& delta) : Game.Rendering.LightingSystem+State`  

```csharp
private State CalculateState(float3 sunPosition, float3 sunDirection, out float delta)
	{
		if (m_NightDayCycleData == null)
		{
			delta = 1f;
			return State.Day;
		}
		float3 @float = new float3(sunPosition.x, 0f, sunPosition.z);
		@float = ((!(math.dot(@float, @float) < 0.0001f)) ? math.normalize(@float) : new float3(-1f, 0f, 0f));
		float num = math.acos(math.dot(-sunDirection, @float)) * (180f / MathF.PI);
		bool num2 = @float.x > 0f;
		if (sunDirection.y > 0f)
		{
			num = 0f - num;
		}
		if (num2)
		{
			delta = 1f;
			if (num < m_NightDayCycleData.DawnStartAngle)
			{
				return State.Night;
			}
			if (num >= m_NightDayCycleData.DawnStartAngle && num < m_NightDayCycleData.SunriseMidpointAngle)
			{
				delta = (num - m_NightDayCycleData.DawnStartAngle) / (m_NightDayCycleData.SunriseMidpointAngle - m_NightDayCycleData.DawnStartAngle);
				return State.Dawn;
			}
			if (num >= m_NightDayCycleData.SunriseMidpointAngle && num < m_NightDayCycleData.SunriseEndAngle)
			{
				delta = (num - m_NightDayCycleData.SunriseMidpointAngle) / (m_NightDayCycleData.SunriseEndAngle - m_NightDayCycleData.SunriseMidpointAngle);
				return State.Sunrise;
			}
			return State.Day;
		}
		delta = 1f;
		if (num > m_NightDayCycleData.SunsetStartAngle)
		{
			return State.Day;
		}
		if (num <= m_NightDayCycleData.SunsetStartAngle && num > m_NightDayCycleData.SunsetMidpointAngle)
		{
			delta = 1f - (num - m_NightDayCycleData.SunsetMidpointAngle) / (m_NightDayCycleData.SunsetStartAngle - m_NightDayCycleData.SunsetMidpointAngle);
			return State.Sunset;
		}
		if (num <= m_NightDayCycleData.SunsetMidpointAngle && num > m_NightDayCycleData.DuskEndAngle)
		{
			delta = 1f - (num - m_NightDayCycleData.DuskEndAngle) / (m_NightDayCycleData.SunsetMidpointAngle - m_NightDayCycleData.DuskEndAngle);
			return State.Dusk;
		}
		return State.Night;
	}
```

- `private EnableShadows(Game.Simulation.PlanetarySystem+LightData lightData, System.Boolean enabled) : System.Void`  

```csharp
private void EnableShadows(PlanetarySystem.LightData lightData, bool enabled)
	{
		lightData.additionalData.EnableShadows(enabled && !shadowDisabled);
	}
```

- `private NextState(Game.Rendering.LightingSystem+State value) : Game.Rendering.LightingSystem+State`  

```csharp
private State NextState(State value)
	{
		return value switch
		{
			State.Dawn => State.Sunrise, 
			State.Sunrise => State.Day, 
			State.Day => State.Sunset, 
			State.Sunset => State.Dusk, 
			State.Dusk => State.Night, 
			State.Night => State.Dawn, 
			_ => State.Invalid, 
		};
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_PlanetarySystem = base.World.GetOrCreateSystemManaged<PlanetarySystem>();
		m_NightDayCycleData = Resources.Load<DayNightCycleData>("DayNight/Default");
		SetupPostprocessing();
		m_LUTBlend = Resources.Load<ComputeShader>("DayNight/LUTBlend");
		if ((bool)m_LUTBlend)
		{
			m_KernalBlend = m_LUTBlend.FindKernel("CSBlend");
			RenderTextureDescriptor desc = new RenderTextureDescriptor
			{
				autoGenerateMips = false,
				bindMS = false,
				depthBufferBits = 0,
				dimension = TextureDimension.Tex3D,
				enableRandomWrite = true,
				graphicsFormat = GraphicsFormat.R16G16B16A16_SFloat,
				memoryless = RenderTextureMemoryless.None,
				height = 32,
				width = 32,
				volumeDepth = 32,
				mipCount = 1,
				msaaSamples = 1,
				sRGB = false,
				useDynamicScale = false,
				useMipMap = false
			};
			m_BlendResult = new RenderTexture(desc);
			m_BlendResult.Create();
		}
		m_TimeSettingGroup = GetEntityQuery(ComponentType.ReadOnly<TimeSettingsData>());
		RequireForUpdate(m_TimeSettingGroup);
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		base.OnDestroy();
		if (m_Volume != null)
		{
			UnityEngine.Object.Destroy(m_Volume.gameObject);
		}
		if (m_BlendResult != null)
		{
			UnityEngine.Object.Destroy(m_BlendResult);
		}
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		ShadowsQualitySettings shadowsQualitySettings = SharedSettings.instance?.graphics?.GetQualitySetting<ShadowsQualitySettings>();
		if (shadowsQualitySettings != null)
		{
			shadowDisabled = !shadowsQualitySettings.enabled;
		}
		PlanetarySystem.LightData moonLight = m_PlanetarySystem.MoonLight;
		PlanetarySystem.LightData sunLight = m_PlanetarySystem.SunLight;
		PlanetarySystem.LightData nightLight = m_PlanetarySystem.NightLight;
		if (!sunLight.isValid || !moonLight.isValid || !nightLight.isValid || m_NightDayCycleData == null)
		{
			return;
		}
		dayLightBrightness = math.saturate(sunLight.additionalData.intensity / 110000f);
		float delta;
		State state = CalculateState(sunLight.transform.position, sunLight.transform.forward, out delta);
		if (m_PlanetarySystem.overrideTime)
		{
			m_LastState = State.Invalid;
		}
		else
		{
			if ((state == m_LastState && delta < m_LastDelta) || NextState(state) == m_LastState)
			{
				state = m_LastState;
				delta = m_LastDelta;
			}
			m_LastState = state;
			m_LastDelta = delta;
		}
		float t = CalcObscured(moonLight, nightLight, m_NightDayCycleData.NightLightObscuredRange);
		float num = math.lerp(m_NightDayCycleData.NightLightIntensity, m_NightDayCycleData.NightLightObscuredIntensity, t);
		float num2 = m_NightDayCycleData.MoonIntensity - (num - m_NightDayCycleData.NightLightIntensity);
		float num3 = math.lerp(m_NightDayCycleData.NightIndirectReflectiveMultiplier, m_NightDayCycleData.NightObscuredIndirectReflectiveMultiplier, t);
		float num4 = math.lerp(m_NightDayCycleData.NightIndirectDiffuseMultiplier, m_NightDayCycleData.NightObscuredIndirectDiffuseMultiplier, t);
		if (!m_NightDayCycleData.UseLUT)
		{
			m_Tonemap.lutTexture.value = null;
			m_Tonemap.lutContribution.value = m_NightDayCycleData.LutContribution;
		}
		m_Tonemap.mode.overrideState = m_NightDayCycleData.UseLUT;
		m_ColorAdjustments.colorFilter.overrideState = m_NightDayCycleData.UseFilters;
		switch (state)
		{
		case State.Dawn:
		{
			m_Exposure.limitMax.value = m_NightDayCycleData.NightExposureMax;
			m_Exposure.limitMin.value = math.lerp(m_NightDayCycleData.NightExposureLowMin, m_NightDayCycleData.DayExposureMin, delta);
			moonLight.additionalData.intensity = num2;
			moonLight.additionalData.color = m_NightDayCycleData.MoonLightColor;
			bool flag2 = sunLight.additionalData.intensity > num2;
			EnableShadows(moonLight, !flag2);
			EnableShadows(sunLight, flag2);
			nightLight.additionalData.intensity = num;
			nightLight.additionalData.color = m_NightDayCycleData.MoonLightColor;
			EnableShadows(nightLight, enabled: false);
			m_PhysicallyBasedSky.exposure.value = math.lerp(m_NightDayCycleData.NightSkyExposure, m_NightDayCycleData.DaySkyExposure, delta);
			m_PhysicallyBasedSky.zenithTint.value = Color.Lerp(m_NightDayCycleData.NightZenithTint, m_NightDayCycleData.DayZenithTint, delta);
			m_PhysicallyBasedSky.horizonTint.value = Color.Lerp(m_NightDayCycleData.NightHorizonTint, m_NightDayCycleData.DayHorizonTint, delta);
			m_ColorAdjustments.colorFilter.value = Color.Lerp(m_NightDayCycleData.NightColorFilter, m_NightDayCycleData.SunriseColorFilter, delta);
			m_ColorAdjustments.contrast.value = math.lerp(m_NightDayCycleData.NightContrast, m_NightDayCycleData.SunriseAndSunsetContrast, delta);
			m_Indirect.reflectionLightingMultiplier.value = math.lerp(num3, 1f, delta);
			m_Indirect.indirectDiffuseLightingMultiplier.value = math.lerp(num4, 1f, delta);
			if (m_NightDayCycleData.UseLUT)
			{
				BlendLUT(m_NightDayCycleData.NightLUT, m_NightDayCycleData.SunriseAndSunsetLUT, delta, m_NightDayCycleData.LutContribution);
			}
			break;
		}
		case State.Sunrise:
			m_Exposure.limitMax.value = m_NightDayCycleData.DayExposureMax;
			m_Exposure.limitMin.value = m_NightDayCycleData.DayExposureMin;
			moonLight.additionalData.intensity = math.lerp(num2, 0.5f, delta);
			moonLight.additionalData.color = m_NightDayCycleData.MoonLightColor;
			EnableShadows(moonLight, enabled: false);
			nightLight.additionalData.intensity = math.lerp(num, 0.5f, delta);
			nightLight.additionalData.color = m_NightDayCycleData.MoonLightColor;
			EnableShadows(nightLight, enabled: false);
			EnableShadows(sunLight, enabled: true);
			m_PhysicallyBasedSky.exposure.value = m_NightDayCycleData.DaySkyExposure;
			m_PhysicallyBasedSky.zenithTint.value = m_NightDayCycleData.DayZenithTint;
			m_PhysicallyBasedSky.horizonTint.value = m_NightDayCycleData.DayHorizonTint;
			m_ColorAdjustments.colorFilter.value = Color.Lerp(m_NightDayCycleData.SunriseColorFilter, m_NightDayCycleData.DayColorFilter, delta);
			m_ColorAdjustments.contrast.value = math.lerp(m_NightDayCycleData.SunriseAndSunsetContrast, m_NightDayCycleData.DayContrast, delta);
			m_Indirect.reflectionLightingMultiplier.value = 1f;
			m_Indirect.indirectDiffuseLightingMultiplier.value = 1f;
			if (m_NightDayCycleData.UseLUT)
			{
				BlendLUT(m_NightDayCycleData.SunriseAndSunsetLUT, m_NightDayCycleData.DayLUT, delta, m_NightDayCycleData.LutContribution);
			}
			break;
		case State.Day:
			m_Exposure.limitMax.value = m_NightDayCycleData.DayExposureMax;
			m_Exposure.limitMin.value = m_NightDayCycleData.DayExposureMin;
			m_PhysicallyBasedSky.exposure.value = m_NightDayCycleData.DaySkyExposure;
			m_PhysicallyBasedSky.zenithTint.value = m_NightDayCycleData.DayZenithTint;
			m_PhysicallyBasedSky.horizonTint.value = m_NightDayCycleData.DayHorizonTint;
			moonLight.additionalData.intensity = 0f;
			moonLight.additionalData.color = m_NightDayCycleData.MoonLightColor;
			EnableShadows(moonLight, enabled: false);
			nightLight.additionalData.intensity = 0f;
			nightLight.additionalData.color = m_NightDayCycleData.MoonLightColor;
			EnableShadows(nightLight, enabled: false);
			EnableShadows(sunLight, enabled: true);
			m_ColorAdjustments.colorFilter.value = m_NightDayCycleData.DayColorFilter;
			m_ColorAdjustments.contrast.value = m_NightDayCycleData.DayContrast;
			m_Indirect.reflectionLightingMultiplier.value = 1f;
			m_Indirect.indirectDiffuseLightingMultiplier.value = 1f;
			if (m_NightDayCycleData.UseLUT)
			{
				m_Tonemap.lutTexture.value = m_NightDayCycleData.DayLUT;
				m_Tonemap.lutContribution.value = m_NightDayCycleData.LutContribution;
			}
			break;
		case State.Sunset:
			m_Exposure.limitMax.value = m_NightDayCycleData.DayExposureMax;
			m_Exposure.limitMin.value = m_NightDayCycleData.DayExposureMin;
			moonLight.additionalData.intensity = math.lerp(0.5f, num2, delta);
			moonLight.additionalData.color = m_NightDayCycleData.MoonLightColor;
			EnableShadows(moonLight, enabled: false);
			nightLight.additionalData.intensity = math.lerp(0f, num, delta);
			nightLight.additionalData.color = m_NightDayCycleData.MoonLightColor;
			EnableShadows(nightLight, enabled: false);
			EnableShadows(sunLight, enabled: true);
			m_PhysicallyBasedSky.exposure.value = m_NightDayCycleData.DaySkyExposure;
			m_PhysicallyBasedSky.zenithTint.value = m_NightDayCycleData.DayZenithTint;
			m_PhysicallyBasedSky.horizonTint.value = m_NightDayCycleData.DayHorizonTint;
			m_ColorAdjustments.colorFilter.value = Color.Lerp(m_NightDayCycleData.DayColorFilter, m_NightDayCycleData.SunsetColorFilter, delta);
			m_ColorAdjustments.contrast.value = math.lerp(m_NightDayCycleData.DayContrast, m_NightDayCycleData.SunriseAndSunsetContrast, delta);
			m_Indirect.reflectionLightingMultiplier.value = 1f;
			m_Indirect.indirectDiffuseLightingMultiplier.value = 1f;
			if (m_NightDayCycleData.UseLUT)
			{
				BlendLUT(m_NightDayCycleData.DayLUT, m_NightDayCycleData.SunriseAndSunsetLUT, delta, m_NightDayCycleData.LutContribution);
			}
			break;
		case State.Dusk:
		{
			m_Exposure.limitMax.value = m_NightDayCycleData.NightExposureMax;
			m_Exposure.limitMin.value = m_NightDayCycleData.NightExposureLowMin;
			moonLight.additionalData.intensity = num2;
			moonLight.additionalData.color = m_NightDayCycleData.MoonLightColor;
			bool flag = sunLight.additionalData.intensity > num2;
			EnableShadows(moonLight, !flag);
			EnableShadows(sunLight, flag);
			nightLight.additionalData.intensity = num;
			nightLight.additionalData.color = m_NightDayCycleData.MoonLightColor;
			EnableShadows(nightLight, enabled: false);
			m_PhysicallyBasedSky.exposure.value = math.lerp(m_NightDayCycleData.DaySkyExposure, m_NightDayCycleData.NightSkyExposure, delta);
			m_PhysicallyBasedSky.zenithTint.value = Color.Lerp(m_NightDayCycleData.DayZenithTint, m_NightDayCycleData.NightZenithTint, delta);
			m_PhysicallyBasedSky.horizonTint.value = Color.Lerp(m_NightDayCycleData.DayHorizonTint, m_NightDayCycleData.NightHorizonTint, delta);
			m_ColorAdjustments.colorFilter.value = Color.Lerp(m_NightDayCycleData.SunsetColorFilter, m_NightDayCycleData.NightColorFilter, delta);
			m_ColorAdjustments.contrast.value = math.lerp(m_NightDayCycleData.SunriseAndSunsetContrast, m_NightDayCycleData.NightContrast, delta);
			m_Indirect.reflectionLightingMultiplier.value = math.lerp(1f, num3, delta);
			m_Indirect.indirectDiffuseLightingMultiplier.value = math.lerp(1f, num4, delta);
			if (m_NightDayCycleData.UseLUT)
			{
				BlendLUT(m_NightDayCycleData.SunriseAndSunsetLUT, m_NightDayCycleData.NightLUT, delta, m_NightDayCycleData.LutContribution);
			}
			break;
		}
		case State.Night:
			m_Exposure.limitMax.value = m_NightDayCycleData.NightExposureMax;
			m_Exposure.limitMin.value = m_NightDayCycleData.NightExposureLowMin;
			m_PhysicallyBasedSky.exposure.value = m_NightDayCycleData.NightSkyExposure;
			m_PhysicallyBasedSky.zenithTint.value = m_NightDayCycleData.NightZenithTint;
			m_PhysicallyBasedSky.horizonTint.value = m_NightDayCycleData.NightHorizonTint;
			moonLight.additionalData.intensity = num2;
			moonLight.additionalData.color = m_NightDayCycleData.MoonLightColor;
			EnableShadows(moonLight, enabled: true);
			EnableShadows(sunLight, enabled: false);
			moonLight.additionalData.shadowTint = m_NightDayCycleData.MoonShadowTint;
			nightLight.additionalData.intensity = num;
			nightLight.additionalData.color = m_NightDayCycleData.MoonLightColor;
			EnableShadows(nightLight, enabled: false);
			m_ColorAdjustments.colorFilter.value = m_NightDayCycleData.NightColorFilter;
			m_ColorAdjustments.contrast.value = m_NightDayCycleData.NightContrast;
			m_Indirect.reflectionLightingMultiplier.value = num3;
			m_Indirect.indirectDiffuseLightingMultiplier.value = num4;
			if (m_NightDayCycleData.UseLUT)
			{
				m_Tonemap.lutTexture.value = m_NightDayCycleData.NightLUT;
				m_Tonemap.lutContribution.value = m_NightDayCycleData.LutContribution;
			}
			break;
		}
		m_Profile.Reset();
	}
```

- `private SetupPostprocessing() : System.Void`  

```csharp
private void SetupPostprocessing()
	{
		if (!m_PostProcessingSetup)
		{
			GameObject gameObject = new GameObject("LightingPostProcessVolume");
			UnityEngine.Object.DontDestroyOnLoad(gameObject);
			m_Volume = gameObject.AddComponent<Volume>();
			m_Volume.priority = 1000f;
			m_Profile = m_Volume.profile;
			m_Exposure = m_Profile.Add<Exposure>();
			m_Exposure.active = true;
			m_Exposure.mode.value = ExposureMode.Automatic;
			m_Exposure.limitMin.overrideState = true;
			m_Exposure.limitMin.value = -5f;
			m_Exposure.limitMax.overrideState = true;
			m_Exposure.limitMax.value = 14f;
			m_PhysicallyBasedSky = m_Profile.Add<PhysicallyBasedSky>();
			m_PhysicallyBasedSky.zenithTint.overrideState = true;
			m_PhysicallyBasedSky.horizonTint.overrideState = true;
			m_PhysicallyBasedSky.exposure.overrideState = true;
			m_PhysicallyBasedSky.exposure.value = 0f;
			m_ColorAdjustments = m_Profile.Add<ColorAdjustments>();
			m_ColorAdjustments.colorFilter.overrideState = true;
			m_ColorAdjustments.colorFilter.value = new Color(1f, 1f, 1f);
			m_ColorAdjustments.contrast.overrideState = true;
			m_ColorAdjustments.contrast.value = 0f;
			m_Indirect = m_Profile.Add<IndirectLightingController>();
			m_Indirect.reflectionLightingMultiplier.overrideState = true;
			m_Indirect.indirectDiffuseLightingMultiplier.overrideState = true;
			m_Indirect.reflectionLightingMultiplier.value = 1f;
			m_Indirect.indirectDiffuseLightingMultiplier.value = 1f;
			m_Tonemap = m_Profile.Add<Tonemapping>();
			m_Tonemap.mode.overrideState = true;
			m_Tonemap.mode.value = TonemappingMode.External;
			m_Tonemap.lutContribution.overrideState = true;
			m_Tonemap.lutContribution.value = 0.5f;
			m_Tonemap.lutTexture.overrideState = true;
			m_Tonemap.lutTexture.value = null;
			m_PostProcessingSetup = true;
		}
	}
```


## Nested types

- `Game.Rendering.LightingSystem+ShaderID`  
- `Game.Rendering.LightingSystem+State`  

