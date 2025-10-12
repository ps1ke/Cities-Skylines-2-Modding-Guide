# Game.UI.InGame.ProfitabilitySection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.TaxSystem m_TaxSystem`  
- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  
- `private Unity.Entities.EntityQuery m_DistrictBuildingQuery`  
- `private Unity.Entities.EntityQuery m_ProcessQuery`  
- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  
- `public Unity.Collections.NativeArray<System.Int32> m_Results`  
- `private Game.UI.InGame.CompanyProfitability <profitability>k__BackingField`  
- `private Unity.Collections.NativeArray<Unity.Mathematics.int2> m_Factors`  
- `private Unity.Collections.NativeList<Game.UI.InGame.FactorInfo> <profitabilityFactors>k__BackingField`  
- `private Game.UI.InGame.ProfitabilitySection+TypeHandle __TypeHandle`  

## Properties

- `protected System.String group { protected get }`  
- `private Game.UI.InGame.CompanyProfitability profitability { private get; private set }`  
- `private Unity.Collections.NativeList<Game.UI.InGame.FactorInfo> profitabilityFactors { private get; private set }`  

## Constructors

- `public ProfitabilitySection()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnProcess() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `protected virtual Reset() : System.Void`  

## Nested types

- `Game.UI.InGame.ProfitabilitySection+Result`  
- `Game.UI.InGame.ProfitabilitySection+ProfitabilityJob`  
- `Game.UI.InGame.ProfitabilitySection+DistrictProfitabilityJob`  
- `Game.UI.InGame.ProfitabilitySection+TypeHandle`  

