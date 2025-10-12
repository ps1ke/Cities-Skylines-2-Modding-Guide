# Game.Net.CompositionSelectSystem

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Prefabs.NetCompositionSystem m_NetCompositionSystem`  
- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Game.Common.ModificationBarrier3 m_ModificationBarrier`  
- `private Unity.Entities.EntityQuery m_UpdatedQuery`  
- `private Unity.Entities.EntityQuery m_AllQuery`  
- `private System.Boolean m_Loaded`  
- `private Game.Net.CompositionSelectSystem+TypeHandle __TypeHandle`  

## Constructors

- `public CompositionSelectSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private GetLoaded() : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Net.CompositionSelectSystem+CompositionCreateInfo`  
- `Game.Net.CompositionSelectSystem+SelectCompositionJob`  
- `Game.Net.CompositionSelectSystem+CreatedCompositionKey`  
- `Game.Net.CompositionSelectSystem+CreateCompositionJob`  
- `Game.Net.CompositionSelectSystem+TypeHandle`  

