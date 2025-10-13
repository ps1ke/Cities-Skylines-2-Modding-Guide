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
public PlanetarySystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private static CreateDateTime(System.Int32 year, System.Int32 day, System.Int32 hour, System.Int32 minute, System.Single second, System.Single longitude) : System.DateTime`  

```csharp
private static System.DateTime CreateDateTime(System.Int32 year, System.Int32 day, System.Int32 hour, System.Int32 minute, System.Single second, System.Single longitude);
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public GetMoonPosition(System.DateTime date, System.Double latitude, System.Double longitude) : Colossal.Atmosphere.MoonCoordinate`  

```csharp
public Colossal.Atmosphere.MoonCoordinate GetMoonPosition(System.DateTime date, System.Double latitude, System.Double longitude);
```

- `public GetSunPosition(System.DateTime date, System.Double latitude, System.Double longitude) : Colossal.Atmosphere.TopocentricCoordinates`  

```csharp
public Colossal.Atmosphere.TopocentricCoordinates GetSunPosition(System.DateTime date, System.Double latitude, System.Double longitude);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private RenderMoon() : System.Void`  

```csharp
private System.Void RenderMoon();
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
```

- `private UpdateTime(System.Single date, System.Single time, System.Int32 year) : System.Void`  

```csharp
private System.Void UpdateTime(System.Single date, System.Single time, System.Int32 year);
```


## Nested types

- `Game.Simulation.PlanetarySystem+LightData`  
- `Game.Simulation.PlanetarySystem+ShaderIDs`  
- `Game.Simulation.PlanetarySystem+TypeHandle`  

