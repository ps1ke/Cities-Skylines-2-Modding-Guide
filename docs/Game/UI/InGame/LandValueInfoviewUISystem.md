# Game.UI.InGame.LandValueInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Colossal.UI.Binding.ValueBinding<System.Single> m_AverageLandValue`  
- `private Unity.Entities.EntityQuery m_LandValueQuery`  
- `private Unity.Collections.NativeArray<System.Single> m_Results`  
- `private Game.UI.InGame.LandValueInfoviewUISystem+TypeHandle __TypeHandle`  
- `private static const System.String kGroup`  

## Properties

- `protected System.Boolean Active { protected get }`  

## Constructors

- `public LandValueInfoviewUISystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual PerformUpdate() : System.Void`  
- `private UpdateLandValue() : System.Void`  

## Nested types

- `Game.UI.InGame.LandValueInfoviewUISystem+CalculateAverageLandValueJob`  
- `Game.UI.InGame.LandValueInfoviewUISystem+TypeHandle`  

