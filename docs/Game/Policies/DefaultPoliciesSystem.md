# Game.Policies.DefaultPoliciesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Policies`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Unity.Entities.EntityQuery m_CreatedQuery`  
- `private Unity.Entities.EntityQuery m_CityConfigurationQuery`  
- `private Game.Policies.DefaultPoliciesSystem+TypeHandle __TypeHandle`  

## Constructors

- `public DefaultPoliciesSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

## Nested types

- `Game.Policies.DefaultPoliciesSystem+AddDefaultPoliciesJob`  
- `Game.Policies.DefaultPoliciesSystem+TypeHandle`  

