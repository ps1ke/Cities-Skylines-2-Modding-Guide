# Game.UI.InGame.CityInfoUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Simulation.ResidentialDemandSystem m_ResidentialDemandSystem`  
- `private Game.Simulation.CommercialDemandSystem m_CommercialDemandSystem`  
- `private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Game.Simulation.CitizenHappinessSystem m_CitizenHappinessSystem`  
- `private Colossal.UI.Binding.RawValueBinding m_ResidentialLowFactors`  
- `private Colossal.UI.Binding.RawValueBinding m_ResidentialMediumFactors`  
- `private Colossal.UI.Binding.RawValueBinding m_ResidentialHighFactors`  
- `private Colossal.UI.Binding.RawValueBinding m_CommercialFactors`  
- `private Colossal.UI.Binding.RawValueBinding m_IndustrialFactors`  
- `private Colossal.UI.Binding.RawValueBinding m_OfficeFactors`  
- `private Colossal.UI.Binding.RawValueBinding m_HappinessFactors`  
- `private System.Single m_ResidentialLowDemand`  
- `private System.Single m_ResidentialMediumDemand`  
- `private System.Single m_ResidentialHighDemand`  
- `private System.Single m_CommercialDemand`  
- `private System.Single m_IndustrialDemand`  
- `private System.Single m_OfficeDemand`  
- `private System.UInt32 m_LastFrameIndex`  
- `private System.Int32 m_AvgHappiness`  
- `private Game.UI.UIUpdateState m_UpdateState`  
- `private Game.UI.InGame.CityInfoUISystem+TypeHandle __TypeHandle`  
- `public static const System.String kGroup`  

## Properties

- `private System.Single m_ResidentialLowDemandBindingValue { private get }`  
- `private System.Single m_ResidentialMediumDemandBindingValue { private get }`  
- `private System.Single m_ResidentialHighDemandBindingValue { private get }`  
- `private System.Single m_CommercialDemandBindingValue { private get }`  
- `private System.Single m_IndustrialDemandBindingValue { private get }`  
- `private System.Single m_OfficeDemandBindingValue { private get }`  

## Constructors

- `public CityInfoUISystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private <OnCreate>b__35_0() : System.Single`  
- `private <OnCreate>b__35_1() : System.Single`  
- `private <OnCreate>b__35_2() : System.Single`  
- `private <OnCreate>b__35_3() : System.Single`  
- `private <OnCreate>b__35_4() : System.Single`  
- `private <OnCreate>b__35_5() : System.Single`  
- `private <OnCreate>b__35_6() : System.Int32`  
- `private static AdvanceSmoothDemand(System.Single current, System.Int32 target, System.UInt32 delta) : System.Single`  
- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public RequestUpdate() : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  
- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  
- `private WriteCommercialFactors(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `private WriteDemandFactors(Colossal.UI.Binding.IJsonWriter writer, Unity.Collections.NativeArray<System.Int32> factors, Unity.Jobs.JobHandle deps) : System.Void`  
- `private WriteHappinessFactors(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `private WriteIndustrialFactors(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `private WriteOfficeFactors(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `private WriteResidentialHighFactors(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `private WriteResidentialLowFactors(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `private WriteResidentialMediumFactors(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

## Nested types

- `Game.UI.InGame.CityInfoUISystem+TypeHandle`  

