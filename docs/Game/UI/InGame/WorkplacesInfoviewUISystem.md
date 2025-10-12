# Game.UI.InGame.WorkplacesInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_WorkplaceQuery`  
- `private Unity.Entities.EntityQuery m_WorkplaceModifiedQuery`  
- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.EmploymentData> m_EmployeesData`  
- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.EmploymentData> m_WorkplacesData`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_Workplaces`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_Workers`  
- `private Unity.Collections.NativeArray<System.Int32> m_IntResults`  
- `private Unity.Collections.NativeArray<Game.UI.InGame.EmploymentData> m_EmploymentDataResults`  
- `private Game.UI.InGame.WorkplacesInfoviewUISystem+TypeHandle __TypeHandle`  
- `private static const System.String kGroup`  

## Properties

- `protected System.Boolean Active { protected get }`  
- `protected System.Boolean Modified { protected get }`  

## Constructors

- `public WorkplacesInfoviewUISystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private GetEmployeesData() : Game.UI.InGame.EmploymentData`  
- `private GetWorkers() : System.Int32`  
- `private GetWorkplaces() : System.Int32`  
- `private GetWorkplacesData() : Game.UI.InGame.EmploymentData`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual PerformUpdate() : System.Void`  
- `private ResetResults() : System.Void`  

## Nested types

- `Game.UI.InGame.WorkplacesInfoviewUISystem+Result`  
- `Game.UI.InGame.WorkplacesInfoviewUISystem+CalculateWorkplaceDataJob`  
- `Game.UI.InGame.WorkplacesInfoviewUISystem+TypeHandle`  

