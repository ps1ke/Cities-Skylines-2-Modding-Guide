# Game.Simulation.PlanetarySystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Colossal.Atmosphere.SunMoonData m_SunMoonData`  
- `private Game.Simulation.TimeSystem m_TimeSystem`  
- `private Game.Simulation.PlanetarySystem+LightData m_SunLight`  
- `private Game.Simulation.PlanetarySystem+LightData m_MoonLight`  
- `private Game.Simulation.PlanetarySystem+LightData m_NightLight`  
- `private Game.Rendering.RenderingSystem m_RenderingSystem`  
- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private System.Int32 m_Year`  
- `private System.Int32 m_Day`  
- `private System.Int32 m_Hour`  
- `private System.Int32 m_Minute`  
- `private System.Single m_Second`  
- `private System.Single m_Latitude`  
- `private System.Single m_Longitude`  
- `private System.Boolean <overrideTime>k__BackingField`  
- `private System.Single <debugTimeMultiplier>k__BackingField`  
- `private System.Int32 m_NumberOfLunarCyclesPerYear`  
- `private UnityEngine.RenderTexture m_MoonTexture`  
- `private UnityEngine.Material m_MoonMaterial`  
- `private System.Int32 m_ClearPass`  
- `private System.Int32 m_LitPass`  
- `private UnityEngine.Vector2 m_OrenNayarCoefficients`  
- `private System.Single m_SurfaceRoughness`  
- `private Game.Simulation.PlanetarySystem+TypeHandle __TypeHandle`  
- `private Unity.Entities.EntityQuery __query_1383560598_0`  
- `private Unity.Entities.EntityQuery __query_1383560598_1`  
- `private Unity.Entities.EntityQuery __query_1383560598_2`  
- `private static readonly System.Single kDefaultLatitude`  
- `private static readonly System.Single kDefaultLongitude`  
- `private static const System.Single kDaysInYear`  
- `private static const System.Single kInvDaysInYear`  
- `private static const System.Single kHoursInDay`  
- `private static const System.Single kInvHoursInDay`  
- `private static const System.Single kSecsInMin`  
- `private static const System.Single kInvSecsInMin`  
- `private static const System.Single kSecsInHour`  
- `private static const System.Single kInvSecsInHour`  
- `private static const System.Single kLunarCyclesPerYear`  
- `private static const System.Single kInvLunarCyclesPerYear`  

## Properties

- `public Game.Simulation.PlanetarySystem+LightData SunLight { get }`  
- `public Game.Simulation.PlanetarySystem+LightData MoonLight { get }`  
- `public Game.Simulation.PlanetarySystem+LightData NightLight { get }`  
- `public System.Boolean overrideTime { get; set }`  
- `public System.Single latitude { get; set }`  
- `public System.Single longitude { get; set }`  
- `public System.Single debugTimeMultiplier { get; set }`  
- `public System.Int32 year { get; set }`  
- `public System.Int32 day { get; set }`  
- `public System.Int32 hour { get; set }`  
- `public System.Int32 minute { get; set }`  
- `public System.Single second { get; set }`  
- `public System.Single time { get; set }`  
- `public System.Single dayOfYear { get; set }`  
- `public System.Single normalizedDayOfYear { get; set }`  
- `public System.Single normalizedTime { get; set }`  
- `public System.Int32 numberOfLunarCyclesPerYear { get; set }`  
- `public System.Int32 moonDay { get }`  
- `public System.Single moonSurfaceRoughness { get; set }`  

## Constructors

- `public PlanetarySystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private static CreateDateTime(System.Int32 year, System.Int32 day, System.Int32 hour, System.Int32 minute, System.Single second, System.Single longitude) : System.DateTime`  
- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public GetMoonPosition(System.DateTime date, System.Double latitude, System.Double longitude) : Colossal.Atmosphere.MoonCoordinate`  
- `public GetSunPosition(System.DateTime date, System.Double latitude, System.Double longitude) : Colossal.Atmosphere.TopocentricCoordinates`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private RenderMoon() : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  
- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  
- `private UpdateTime(System.Single date, System.Single time, System.Int32 year) : System.Void`  

## Nested types

- `Game.Simulation.PlanetarySystem+LightData`  
- `Game.Simulation.PlanetarySystem+ShaderIDs`  
- `Game.Simulation.PlanetarySystem+TypeHandle`  

