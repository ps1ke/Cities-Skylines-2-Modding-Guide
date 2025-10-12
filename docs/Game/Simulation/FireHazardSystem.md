# Game.Simulation.FireHazardSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Buildings.LocalEffectSystem m_LocalEffectSystem`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.Simulation.ClimateSystem m_ClimateSystem`  
- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Unity.Entities.EntityQuery m_FlammableQuery`  
- `private Unity.Entities.EntityQuery m_FirePrefabQuery`  
- `private Unity.Entities.EntityQuery m_FireConfigQuery`  
- `private Game.Simulation.EventHelpers+FireHazardData m_FireHazardData`  
- `private System.Single <noRainDays>k__BackingField`  
- `private Game.Simulation.FireHazardSystem+TypeHandle __TypeHandle`  
- `private static const System.Int32 UPDATES_PER_DAY`  

## Properties

- `public System.Single noRainDays { get; private set }`  

## Constructors

- `public FireHazardSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  
- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

## Nested types

- `Game.Simulation.FireHazardSystem+FireHazardJob`  
- `Game.Simulation.FireHazardSystem+TypeHandle`  

