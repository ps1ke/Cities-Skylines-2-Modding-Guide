# Game.Simulation.CityModifierUpdateSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_CityQuery`  
- `private Unity.Entities.EntityQuery m_EffectProviderQuery`  
- `private Game.Simulation.CityModifierUpdateSystem+CityModifierRefreshData m_CityModifierRefreshData`  
- `private Game.Simulation.CityModifierUpdateSystem+TypeHandle __TypeHandle`  

## Constructors

- `public CityModifierUpdateSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public static AddToTempList(Unity.Collections.NativeList<Game.Prefabs.CityModifierData> tempModifierList, Unity.Entities.DynamicBuffer<Game.Prefabs.CityModifierData> cityModifiers) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `public static InitializeTempList(Unity.Collections.NativeList<Game.Prefabs.CityModifierData> tempModifierList) : System.Void`  
- `public static InitializeTempList(Unity.Collections.NativeList<Game.Prefabs.CityModifierData> tempModifierList, Unity.Entities.DynamicBuffer<Game.Prefabs.CityModifierData> cityModifiers) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.CityModifierUpdateSystem+UpdateCityModifiersJob`  
- `Game.Simulation.CityModifierUpdateSystem+CityModifierRefreshData`  
- `Game.Simulation.CityModifierUpdateSystem+TypeHandle`  

