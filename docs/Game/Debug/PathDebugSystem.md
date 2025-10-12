# Game.Debug.PathDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_PathGroup`  
- `private Colossal.GizmosSystem m_GizmosSystem`  
- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Debug.BaseDebugSystem+Option m_PersonalCarOption`  
- `private Game.Debug.BaseDebugSystem+Option m_DeliveryTruckOption`  
- `private Game.Debug.BaseDebugSystem+Option m_ServiceVehicleOption`  
- `private Game.Debug.BaseDebugSystem+Option m_ResidentOption`  
- `private Game.Debug.BaseDebugSystem+Option m_CitizenOption`  
- `private Game.Debug.BaseDebugSystem+Option m_CompanyOption`  
- `private Game.Debug.BaseDebugSystem+Option m_RouteOption`  
- `private Game.Debug.BaseDebugSystem+Option m_DeliveryRequestOption`  
- `private Game.Debug.BaseDebugSystem+Option m_ServiceRequestOption`  
- `private Game.Debug.PathDebugSystem+TypeHandle __TypeHandle`  

## Constructors

- `public PathDebugSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private DrawPathGizmos(Unity.Entities.EntityQuery group, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Debug.PathDebugSystem+PathGizmoJob`  
- `Game.Debug.PathDebugSystem+TypeHandle`  

