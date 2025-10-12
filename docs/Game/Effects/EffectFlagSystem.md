# Game.Effects.EffectFlagSystem

**Assembly:** `Game`  
**Namespace:** `Game.Effects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

## Fields

- `private Unity.Entities.Entity m_CurrentSeason`  
- `private System.UInt32 m_LastSeasonChange`  
- `private System.Boolean m_IsColdSeason`  
- `private System.Boolean m_IsNightTime`  
- `private System.UInt32 m_LastTimeChange`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Simulation.TimeSystem m_TimeSystem`  
- `private Game.Simulation.ClimateSystem m_ClimateSystem`  
- `public static readonly System.UInt32 kNightRandomTicks`  
- `public static readonly System.UInt32 kDayRandomTicks`  
- `public static readonly System.Single kNightBegin`  
- `public static readonly System.Single kDayBegin`  
- `public static readonly System.UInt32 kSpringRandomTicks`  
- `public static readonly System.UInt32 kAutumnRandomTicks`  
- `public static readonly System.Single kSpringTemperature`  
- `public static readonly System.Single kAutumnTemperature`  

## Constructors

- `public EffectFlagSystem()`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public GetData() : Game.Effects.EffectFlagSystem+EffectFlagData`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `public static IsEnabled(Game.Prefabs.EffectConditionFlags flag, Unity.Mathematics.Random random, Game.Effects.EffectFlagSystem+EffectFlagData data, System.UInt32 frame) : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  
- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

## Nested types

- `Game.Effects.EffectFlagSystem+EffectFlagData`  

