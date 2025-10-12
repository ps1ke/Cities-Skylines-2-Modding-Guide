# Game.UI.InGame.LevelInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Colossal.UI.Binding.RawValueBinding m_ResidentialLevels`  
- `private Colossal.UI.Binding.RawValueBinding m_CommercialLevels`  
- `private Colossal.UI.Binding.RawValueBinding m_IndustrialLevels`  
- `private Colossal.UI.Binding.RawValueBinding m_OfficeLevels`  
- `private Unity.Entities.EntityQuery m_SpawnableQuery`  
- `private Unity.Collections.NativeArray<Game.UI.InGame.LevelInfoviewUISystem+Levels> m_Results`  
- `private Game.UI.InGame.LevelInfoviewUISystem+TypeHandle __TypeHandle`  
- `private static const System.String kGroup`  

## Properties

- `protected System.Boolean Active { protected get }`  

## Constructors

- `public LevelInfoviewUISystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual PerformUpdate() : System.Void`  
- `private UpdateBindings() : System.Void`  
- `private UpdateCommercialLevels(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `private UpdateIndustrialLevels(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `private UpdateOfficeLevels(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `private UpdateResidentialLevels(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `private WriteLevels(Colossal.UI.Binding.IJsonWriter writer, Game.UI.InGame.LevelInfoviewUISystem+Levels levels) : System.Void`  

## Nested types

- `Game.UI.InGame.LevelInfoviewUISystem+Result`  
- `Game.UI.InGame.LevelInfoviewUISystem+UpdateLevelsJob`  
- `Game.UI.InGame.LevelInfoviewUISystem+Levels`  
- `Game.UI.InGame.LevelInfoviewUISystem+TypeHandle`  

