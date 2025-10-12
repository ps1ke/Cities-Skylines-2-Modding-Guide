# Game.UI.InGame.TrafficInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_AggregateQuery`  
- `private Colossal.UI.Binding.RawValueBinding m_TrafficFlow`  
- `private Unity.Collections.NativeArray<System.Single> m_Results`  
- `private System.Single[] m_Flow`  
- `private Game.UI.InGame.TrafficInfoviewUISystem+TypeHandle __TypeHandle`  
- `private static const System.String kGroup`  

## Properties

- `protected System.Boolean Active { protected get }`  

## Constructors

- `public TrafficInfoviewUISystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual PerformUpdate() : System.Void`  
- `private Reset() : System.Void`  
- `private UpdateTrafficFlowBinding(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

## Nested types

- `Game.UI.InGame.TrafficInfoviewUISystem+UpdateFlowJob`  
- `Game.UI.InGame.TrafficInfoviewUISystem+TypeHandle`  

