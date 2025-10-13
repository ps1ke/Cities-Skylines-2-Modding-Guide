# Game.Simulation.PlanetarySystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PlanetarySystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private Colossal.Atmosphere.SunMoonData m_SunMoonData;
    private Game.Simulation.TimeSystem m_TimeSystem;
    private Game.Simulation.PlanetarySystem+LightData m_SunLight;
    private Game.Simulation.PlanetarySystem+LightData m_MoonLight;
    private Game.Simulation.PlanetarySystem+LightData m_NightLight;
    private Game.Rendering.RenderingSystem m_RenderingSystem;
    private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private System.Int32 m_Year;
    private System.Int32 m_Day;
    private System.Int32 m_Hour;
    private System.Int32 m_Minute;
    private System.Single m_Second;
    private System.Single m_Latitude;
    private System.Single m_Longitude;
    private System.Boolean <overrideTime>k__BackingField;
    private System.Single <debugTimeMultiplier>k__BackingField;
    private System.Int32 m_NumberOfLunarCyclesPerYear;
    private UnityEngine.RenderTexture m_MoonTexture;
    private UnityEngine.Material m_MoonMaterial;
    private System.Int32 m_ClearPass;
    private System.Int32 m_LitPass;
    private UnityEngine.Vector2 m_OrenNayarCoefficients;
    private System.Single m_SurfaceRoughness;
    private Game.Simulation.PlanetarySystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_1383560598_0;
    private Unity.Entities.EntityQuery __query_1383560598_1;
    private Unity.Entities.EntityQuery __query_1383560598_2;
    private static readonly System.Single kDefaultLatitude;
    private static readonly System.Single kDefaultLongitude;
    private static const System.Single kDaysInYear;
    private static const System.Single kInvDaysInYear;
    private static const System.Single kHoursInDay;
    private static const System.Single kInvHoursInDay;
    private static const System.Single kSecsInMin;
    private static const System.Single kInvSecsInMin;
    private static const System.Single kSecsInHour;
    private static const System.Single kInvSecsInHour;
    private static const System.Single kLunarCyclesPerYear;
    private static const System.Single kInvLunarCyclesPerYear;

    public Game.Simulation.PlanetarySystem+LightData SunLight { get; }
    public Game.Simulation.PlanetarySystem+LightData MoonLight { get; }
    public Game.Simulation.PlanetarySystem+LightData NightLight { get; }
    public System.Boolean overrideTime { get; set; }
    public System.Single latitude { get; set; }
    public System.Single longitude { get; set; }
    public System.Single debugTimeMultiplier { get; set; }
    public System.Int32 year { get; set; }
    public System.Int32 day { get; set; }
    public System.Int32 hour { get; set; }
    public System.Int32 minute { get; set; }
    public System.Single second { get; set; }
    public System.Single time { get; set; }
    public System.Single dayOfYear { get; set; }
    public System.Single normalizedDayOfYear { get; set; }
    public System.Single normalizedTime { get; set; }
    public System.Int32 numberOfLunarCyclesPerYear { get; set; }
    public System.Int32 moonDay { get; }
    public System.Single moonSurfaceRoughness { get; set; }

    public PlanetarySystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private static System.DateTime CreateDateTime(System.Int32 year, System.Int32 day, System.Int32 hour, System.Int32 minute, System.Single second, System.Single longitude);
    public System.Void Deserialize<TReader>(TReader reader);
    public Colossal.Atmosphere.MoonCoordinate GetMoonPosition(System.DateTime date, System.Double latitude, System.Double longitude);
    public Colossal.Atmosphere.TopocentricCoordinates GetSunPosition(System.DateTime date, System.Double latitude, System.Double longitude);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    private System.Void RenderMoon();
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
    private System.Void UpdateTime(System.Single date, System.Single time, System.Int32 year);
}
```


## Fields

- `private Colossal.Atmosphere.SunMoonData m_SunMoonData`  

```csharp
private Colossal.Atmosphere.SunMoonData m_SunMoonData;
```

- `private Game.Simulation.TimeSystem m_TimeSystem`  

```csharp
private Game.Simulation.TimeSystem m_TimeSystem;
```

- `private Game.Simulation.PlanetarySystem+LightData m_SunLight`  

```csharp
private Game.Simulation.PlanetarySystem+LightData m_SunLight;
```

- `private Game.Simulation.PlanetarySystem+LightData m_MoonLight`  

```csharp
private Game.Simulation.PlanetarySystem+LightData m_MoonLight;
```

- `private Game.Simulation.PlanetarySystem+LightData m_NightLight`  

```csharp
private Game.Simulation.PlanetarySystem+LightData m_NightLight;
```

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  

```csharp
private Game.Rendering.RenderingSystem m_RenderingSystem;
```

- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  

```csharp
private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private System.Int32 m_Year`  

```csharp
private System.Int32 m_Year;
```

- `private System.Int32 m_Day`  

```csharp
private System.Int32 m_Day;
```

- `private System.Int32 m_Hour`  

```csharp
private System.Int32 m_Hour;
```

- `private System.Int32 m_Minute`  

```csharp
private System.Int32 m_Minute;
```

- `private System.Single m_Second`  

```csharp
private System.Single m_Second;
```

- `private System.Single m_Latitude`  

```csharp
private System.Single m_Latitude;
```

- `private System.Single m_Longitude`  

```csharp
private System.Single m_Longitude;
```

- `private System.Boolean <overrideTime>k__BackingField`  

```csharp
private System.Boolean <overrideTime>k__BackingField;
```

- `private System.Single <debugTimeMultiplier>k__BackingField`  

```csharp
private System.Single <debugTimeMultiplier>k__BackingField;
```

- `private System.Int32 m_NumberOfLunarCyclesPerYear`  

```csharp
private System.Int32 m_NumberOfLunarCyclesPerYear;
```

- `private UnityEngine.RenderTexture m_MoonTexture`  

```csharp
private UnityEngine.RenderTexture m_MoonTexture;
```

- `private UnityEngine.Material m_MoonMaterial`  

```csharp
private UnityEngine.Material m_MoonMaterial;
```

- `private System.Int32 m_ClearPass`  

```csharp
private System.Int32 m_ClearPass;
```

- `private System.Int32 m_LitPass`  

```csharp
private System.Int32 m_LitPass;
```

- `private UnityEngine.Vector2 m_OrenNayarCoefficients`  

```csharp
private UnityEngine.Vector2 m_OrenNayarCoefficients;
```

- `private System.Single m_SurfaceRoughness`  

```csharp
private System.Single m_SurfaceRoughness;
```

- `private Game.Simulation.PlanetarySystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.PlanetarySystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_1383560598_0`  

```csharp
private Unity.Entities.EntityQuery __query_1383560598_0;
```

- `private Unity.Entities.EntityQuery __query_1383560598_1`  

```csharp
private Unity.Entities.EntityQuery __query_1383560598_1;
```

- `private Unity.Entities.EntityQuery __query_1383560598_2`  

```csharp
private Unity.Entities.EntityQuery __query_1383560598_2;
```

- `private static readonly System.Single kDefaultLatitude`  

```csharp
private static readonly System.Single kDefaultLatitude;
```

- `private static readonly System.Single kDefaultLongitude`  

```csharp
private static readonly System.Single kDefaultLongitude;
```

- `private static const System.Single kDaysInYear`  

```csharp
private static const System.Single kDaysInYear;
```

- `private static const System.Single kInvDaysInYear`  

```csharp
private static const System.Single kInvDaysInYear;
```

- `private static const System.Single kHoursInDay`  

```csharp
private static const System.Single kHoursInDay;
```

- `private static const System.Single kInvHoursInDay`  

```csharp
private static const System.Single kInvHoursInDay;
```

- `private static const System.Single kSecsInMin`  

```csharp
private static const System.Single kSecsInMin;
```

- `private static const System.Single kInvSecsInMin`  

```csharp
private static const System.Single kInvSecsInMin;
```

- `private static const System.Single kSecsInHour`  

```csharp
private static const System.Single kSecsInHour;
```

- `private static const System.Single kInvSecsInHour`  

```csharp
private static const System.Single kInvSecsInHour;
```

- `private static const System.Single kLunarCyclesPerYear`  

```csharp
private static const System.Single kLunarCyclesPerYear;
```

- `private static const System.Single kInvLunarCyclesPerYear`  

```csharp
private static const System.Single kInvLunarCyclesPerYear;
```


## Properties

- `public Game.Simulation.PlanetarySystem+LightData SunLight { get }`  

```csharp
public Game.Simulation.PlanetarySystem+LightData SunLight { get; }
```

- `public Game.Simulation.PlanetarySystem+LightData MoonLight { get }`  

```csharp
public Game.Simulation.PlanetarySystem+LightData MoonLight { get; }
```

- `public Game.Simulation.PlanetarySystem+LightData NightLight { get }`  

```csharp
public Game.Simulation.PlanetarySystem+LightData NightLight { get; }
```

- `public System.Boolean overrideTime { get; set }`  

```csharp
public System.Boolean overrideTime { get; set; }
```

- `public System.Single latitude { get; set }`  

```csharp
public System.Single latitude { get; set; }
```

- `public System.Single longitude { get; set }`  

```csharp
public System.Single longitude { get; set; }
```

- `public System.Single debugTimeMultiplier { get; set }`  

```csharp
public System.Single debugTimeMultiplier { get; set; }
```

- `public System.Int32 year { get; set }`  

```csharp
public System.Int32 year { get; set; }
```

- `public System.Int32 day { get; set }`  

```csharp
public System.Int32 day { get; set; }
```

- `public System.Int32 hour { get; set }`  

```csharp
public System.Int32 hour { get; set; }
```

- `public System.Int32 minute { get; set }`  

```csharp
public System.Int32 minute { get; set; }
```

- `public System.Single second { get; set }`  

```csharp
public System.Single second { get; set; }
```

- `public System.Single time { get; set }`  

```csharp
public System.Single time { get; set; }
```

- `public System.Single dayOfYear { get; set }`  

```csharp
public System.Single dayOfYear { get; set; }
```

- `public System.Single normalizedDayOfYear { get; set }`  

```csharp
public System.Single normalizedDayOfYear { get; set; }
```

- `public System.Single normalizedTime { get; set }`  

```csharp
public System.Single normalizedTime { get; set; }
```

- `public System.Int32 numberOfLunarCyclesPerYear { get; set }`  

```csharp
public System.Int32 numberOfLunarCyclesPerYear { get; set; }
```

- `public System.Int32 moonDay { get }`  

```csharp
public System.Int32 moonDay { get; }
```

- `public System.Single moonSurfaceRoughness { get; set }`  

```csharp
public System.Single moonSurfaceRoughness { get; set; }
```


## Constructors

- `public PlanetarySystem()`  

```csharp
[Preserve]
	public PlanetarySystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		EntityQueryBuilder entityQueryBuilder = new EntityQueryBuilder(Allocator.Temp);
		EntityQueryBuilder entityQueryBuilder2 = entityQueryBuilder.WithAll<TimeSettingsData>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_1383560598_0 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder2 = entityQueryBuilder.WithAll<TimeData>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_1383560598_1 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder2 = entityQueryBuilder.WithAll<AtmosphereData>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_1383560598_2 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder.Dispose();
	}
```

- `private static CreateDateTime(System.Int32 year, System.Int32 day, System.Int32 hour, System.Int32 minute, System.Single second, System.Single longitude) : System.DateTime`  

```csharp
private static DateTime CreateDateTime(int year, int day, int hour, int minute, float second, float longitude)
	{
		return new DateTime(0L, DateTimeKind.Utc).AddYears(year - 1).AddDays(day - 1).AddHours(hour)
			.AddMinutes(minute)
			.AddSeconds(second)
			.AddSeconds(-43200f * longitude / 180f);
	}
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public GetMoonPosition(System.DateTime date, System.Double latitude, System.Double longitude) : Colossal.Atmosphere.MoonCoordinate`  

```csharp
public MoonCoordinate GetMoonPosition(DateTime date, double latitude, double longitude)
	{
		return m_SunMoonData.GetMoonPosition(date, latitude, longitude);
	}
```

- `public GetSunPosition(System.DateTime date, System.Double latitude, System.Double longitude) : Colossal.Atmosphere.TopocentricCoordinates`  

```csharp
public TopocentricCoordinates GetSunPosition(DateTime date, double latitude, double longitude)
	{
		return m_SunMoonData.GetSunPosition(date, latitude, longitude);
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_CameraUpdateSystem = base.World.GetOrCreateSystemManaged<CameraUpdateSystem>();
		m_MoonTexture = new RenderTexture(512, 512, 0, RenderTextureFormat.ARGB32)
		{
			name = "MoonTexture",
			hideFlags = HideFlags.DontSave
		};
		m_MoonMaterial = CoreUtils.CreateEngineMaterial(Shader.Find("Hidden/Satellites"));
		m_ClearPass = m_MoonMaterial.FindPass("Clear");
		m_LitPass = m_MoonMaterial.FindPass("LitSatellite");
		m_TimeSystem = base.World.GetOrCreateSystemManaged<TimeSystem>();
		m_RenderingSystem = base.World.GetOrCreateSystemManaged<RenderingSystem>();
		m_SunLight = new LightData("SunLight");
		m_MoonLight = new LightData("MoonLight");
		m_NightLight = new LightData("NightLight");
		m_SunMoonData = default(SunMoonData);
	}
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected override void OnCreateForCompiler()
	{
		base.OnCreateForCompiler();
		__AssignQueries(ref base.CheckedStateRef);
		__TypeHandle.__AssignHandles(ref base.CheckedStateRef);
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		base.OnDestroy();
		CoreUtils.Destroy(m_MoonTexture);
		CoreUtils.Destroy(m_MoonMaterial);
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		float num = latitude;
		float num2 = longitude;
		TimeSettingsData value3;
		TimeData value4;
		if (GameManager.instance.gameMode == GameMode.Game)
		{
			bool flag = overrideTime;
			GameplaySettings gameplaySettings = SharedSettings.instance?.gameplay;
			if (gameplaySettings != null && !overrideTime && !gameplaySettings.dayNightVisual)
			{
				num = 51.2277f;
				num2 = 6.7735f;
				time = 14.5f;
				day = 177;
				year = 2020;
				flag = true;
			}
			if (!flag && __query_1383560598_0.TryGetSingleton<TimeSettingsData>(out var value) && __query_1383560598_1.TryGetSingleton<TimeData>(out var value2))
			{
				double renderingFrame = (float)(m_RenderingSystem.frameIndex - value2.m_FirstFrame) + m_RenderingSystem.frameTime;
				float timeOfYear = m_TimeSystem.GetTimeOfYear(value, value2, renderingFrame);
				float num3 = m_TimeSystem.GetTimeOfDay(value, value2, renderingFrame) * debugTimeMultiplier;
				int num4 = m_TimeSystem.GetYear(value, value2);
				UpdateTime(timeOfYear, num3, num4);
			}
		}
		else if (GameManager.instance.gameMode == GameMode.Editor && !overrideTime && __query_1383560598_0.TryGetSingleton<TimeSettingsData>(out value3) && __query_1383560598_1.TryGetSingleton<TimeData>(out value4))
		{
			double renderingFrame2 = (float)(m_RenderingSystem.frameIndex - value4.m_FirstFrame) + m_RenderingSystem.frameTime;
			float timeOfYear2 = m_TimeSystem.GetTimeOfYear(value3, value4, renderingFrame2);
			float num5 = m_TimeSystem.GetTimeOfDay(value3, value4, renderingFrame2) * debugTimeMultiplier;
			int num6 = m_TimeSystem.GetYear(value3, value4);
			UpdateTime(timeOfYear2, num5, num6);
		}
		if (m_SunLight.isValid)
		{
			JulianDateTime date = CreateDateTime(year, day, hour, minute, second, num2);
			float planetTime;
			float3 @float = m_SunMoonData.GetSunPosition(date, num, num2).ToLocalCoordinates(out planetTime);
			float4x4 float4x = float4x4.LookAt(@float, float3.zero, new float3(0f, 1f, 0f));
			float3 float2 = math.rotate(float4x, new float3(0f, 0f, 1f));
			m_SunLight.transform.position = @float;
			m_SunLight.transform.rotation = new quaternion(float4x);
			m_SunLight.additionalData.intensity = m_SunLight.initialIntensity * math.smoothstep(0f, 0.3f, math.abs(math.min(0f, float2.y)));
		}
		if (m_MoonLight.isValid)
		{
			JulianDateTime date2 = CreateDateTime(year, moonDay, hour, minute, second, num2);
			MoonCoordinate moonPosition = m_SunMoonData.GetMoonPosition(date2, num, num2);
			float planetTime2;
			float3 float3 = moonPosition.topoCoords.ToLocalCoordinates(out planetTime2);
			float4x4 float4x2 = float4x4.LookAt(float3, float3.zero, new float3(0f, 1f, 0f));
			math.rotate(float4x2, new float3(0f, 0f, 1f));
			m_MoonLight.transform.position = float3;
			m_MoonLight.transform.rotation = new quaternion(float4x2);
			m_MoonLight.additionalData.distance = (float)moonPosition.distance;
			if (m_SunLight.isValid)
			{
				RenderMoon();
			}
		}
		if (m_NightLight.isValid && m_MoonLight.isValid)
		{
			float3 float4 = m_MoonLight.transform.position;
			float4.y = math.max(float4.y, 0.3f);
			float4x4 m = float4x4.LookAt(float4, float3.zero, new float3(0f, 1f, 0f));
			m_NightLight.transform.position = float4;
			m_NightLight.transform.rotation = new quaternion(m);
		}
	}
```

- `private RenderMoon() : System.Void`  

```csharp
private void RenderMoon()
	{
		if (m_MoonTexture != null && m_MoonMaterial != null && m_CameraUpdateSystem.activeCamera != null)
		{
			moonSurfaceRoughness = 0.8f;
			Camera activeCamera = m_CameraUpdateSystem.activeCamera;
			float num = Mathf.Tan(0.5f * activeCamera.fieldOfView * MathF.PI / 180f);
			Vector4 value = new Vector4(activeCamera.aspect * num, num, activeCamera.nearClipPlane, activeCamera.farClipPlane);
			m_MoonMaterial.SetMatrix(ShaderIDs._Camera2World, activeCamera.cameraToWorldMatrix);
			m_MoonMaterial.SetVector(ShaderIDs._CameraData, value);
			m_MoonMaterial.SetVector(ShaderIDs._SunDirection, m_SunLight.transform.forward);
			m_MoonMaterial.SetVector(ShaderIDs._Direction, m_MoonLight.transform.forward);
			m_MoonMaterial.SetVector(ShaderIDs._Tangent, m_MoonLight.transform.right);
			m_MoonMaterial.SetVector(ShaderIDs._BiTangent, m_MoonLight.transform.up);
			m_MoonMaterial.SetColor(ShaderIDs._Albedo, new Color(1f, 1f, 1f, 1f));
			m_MoonMaterial.SetVector(ShaderIDs._Corners, new Vector4(0f, 0f, 1f, 1f));
			m_MoonMaterial.SetVector(ShaderIDs._OrenNayarCoefficients, m_OrenNayarCoefficients);
			m_MoonMaterial.SetFloat(ShaderIDs._Luminance, 10f);
			if (__query_1383560598_2.TryGetSingleton<AtmosphereData>(out var value2) && m_PrefabSystem.TryGetPrefab<AtmospherePrefab>(value2.m_AtmospherePrefab, out var prefab))
			{
				m_MoonMaterial.SetTexture(ShaderIDs._TexDiffuse, prefab.m_MoonAlbedo);
				m_MoonMaterial.SetTexture(ShaderIDs._TexNormal, prefab.m_MoonNormal);
			}
			Graphics.Blit(null, m_MoonTexture, m_MoonMaterial, m_ClearPass);
			Graphics.Blit(null, m_MoonTexture, m_MoonMaterial, m_LitPass);
			m_MoonTexture.IncrementUpdateCount();
			m_MoonLight.additionalData.surfaceTexture = m_MoonTexture;
		}
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void SetDefaults(Context context)
	{
		m_Latitude = kDefaultLatitude;
		m_Longitude = kDefaultLongitude;
	}
```

- `private UpdateTime(System.Single date, System.Single time, System.Int32 year) : System.Void`  

```csharp
private void UpdateTime(float date, float time, int year)
	{
		normalizedDayOfYear = date;
		normalizedTime = time;
		m_Year = year;
	}
```


## Nested types

- `Game.Simulation.PlanetarySystem+LightData`  
- `Game.Simulation.PlanetarySystem+ShaderIDs`  
- `Game.Simulation.PlanetarySystem+TypeHandle`  

