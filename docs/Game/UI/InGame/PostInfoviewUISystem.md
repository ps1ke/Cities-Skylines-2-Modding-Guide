# Game.UI.InGame.PostInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  
- `private Unity.Entities.EntityQuery m_PostFacilityModifiedQuery`  
- `private Unity.Entities.EntityQuery m_MailProducerQuery`  
- `private Unity.Entities.EntityQuery m_MailProducerModifiedQuery`  
- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_CollectedMail`  
- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_DeliveredMail`  
- `private Colossal.UI.Binding.ValueBinding<System.Single> m_MailProductionRate`  
- `private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_PostServiceAvailability`  
- `private Unity.Collections.NativeArray<Unity.Mathematics.float2> m_Result`  
- `private Game.UI.InGame.PostInfoviewUISystem+TypeHandle __TypeHandle`  
- `private static const System.String kGroup`  
- `private static const System.Single kAccumulationFactor`  

## Properties

- `protected System.Boolean Active { protected get }`  
- `protected System.Boolean Modified { protected get }`  

## Constructors

- `public PostInfoviewUISystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual PerformUpdate() : System.Void`  
- `private ResetResults() : System.Void`  
- `private UpdateAvailability() : System.Void`  
- `private UpdateMailRate() : System.Void`  
- `private UpdateProcessingRate() : System.Void`  

## Nested types

- `Game.UI.InGame.PostInfoviewUISystem+UpdateMailRateJob`  
- `Game.UI.InGame.PostInfoviewUISystem+TypeHandle`  

