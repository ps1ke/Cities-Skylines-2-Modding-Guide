# Game.UI.InGame.DisasterInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_ShelteredCount`  
- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_ShelterCapacity`  
- `private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_ShelterAvailability`  
- `private Colossal.Collections.NativeAccumulator<Game.UI.InGame.DisasterInfoviewUISystem+UpdateDisasterResponseJob+Result> m_Result`  
- `private Unity.Entities.EntityQuery m_SheltersQuery`  
- `private Unity.Entities.EntityQuery m_SheltersModifiedQuery`  
- `private Game.UI.InGame.DisasterInfoviewUISystem+TypeHandle __TypeHandle`  
- `private static const System.String kGroup`  

## Properties

- `protected System.Boolean Active { protected get }`  
- `protected System.Boolean Modified { protected get }`  

## Constructors

- `public DisasterInfoviewUISystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual PerformUpdate() : System.Void`  

## Nested types

- `Game.UI.InGame.DisasterInfoviewUISystem+UpdateDisasterResponseJob`  
- `Game.UI.InGame.DisasterInfoviewUISystem+TypeHandle`  

