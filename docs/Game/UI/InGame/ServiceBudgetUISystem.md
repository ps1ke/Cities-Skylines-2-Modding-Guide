# Game.UI.InGame.ServiceBudgetUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Game.Simulation.ICityServiceBudgetSystem m_CityServiceBudgetSystem`  
- `private Game.Simulation.IServiceFeeSystem m_ServiceFeeSystem`  
- `private Unity.Entities.EntityQuery m_ServiceQuery`  
- `private Game.UI.InGame.ServiceBudgetUISystem+TypeHandle __TypeHandle`  
- `private Unity.Entities.EntityQuery __query_2035132663_0`  
- `private Unity.Entities.EntityQuery __query_2035132663_1`  
- `private Unity.Entities.EntityQuery __query_2035132663_2`  
- `private Unity.Entities.EntityQuery __query_2035132663_3`  
- `private static const System.String kGroup`  

## Constructors

- `public ServiceBudgetUISystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private GetTotalBudget(Unity.Entities.Entity service, Unity.Entities.DynamicBuffer<Game.City.ServiceFee> fees) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `private ResetService(Unity.Entities.Entity service) : System.Void`  
- `private SetServiceBudget(Unity.Entities.Entity service, System.Int32 percentage) : System.Void`  
- `private SetServiceFee(Game.City.PlayerResource resource, System.Single amount) : System.Void`  
- `private WriteServiceDetails(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity serviceEntity) : System.Void`  
- `private WriteServiceFees(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity serviceEntity) : System.Void`  
- `private WriteServices(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

## Nested types

- `Game.UI.InGame.ServiceBudgetUISystem+ServiceInfo`  
- `Game.UI.InGame.ServiceBudgetUISystem+PlayerResourceReader`  
- `Game.UI.InGame.ServiceBudgetUISystem+TypeHandle`  

