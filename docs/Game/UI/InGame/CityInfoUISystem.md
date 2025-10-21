# Game.UI.InGame.CityInfoUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CityInfoUISystem : Game.UI.UISystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.ResidentialDemandSystem m_ResidentialDemandSystem;
    private Game.Simulation.CommercialDemandSystem m_CommercialDemandSystem;
    private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Simulation.CitizenHappinessSystem m_CitizenHappinessSystem;
    private Colossal.UI.Binding.RawValueBinding m_ResidentialLowFactors;
    private Colossal.UI.Binding.RawValueBinding m_ResidentialMediumFactors;
    private Colossal.UI.Binding.RawValueBinding m_ResidentialHighFactors;
    private Colossal.UI.Binding.RawValueBinding m_CommercialFactors;
    private Colossal.UI.Binding.RawValueBinding m_IndustrialFactors;
    private Colossal.UI.Binding.RawValueBinding m_OfficeFactors;
    private Colossal.UI.Binding.RawValueBinding m_HappinessFactors;
    private System.Single m_ResidentialLowDemand;
    private System.Single m_ResidentialMediumDemand;
    private System.Single m_ResidentialHighDemand;
    private System.Single m_CommercialDemand;
    private System.Single m_IndustrialDemand;
    private System.Single m_OfficeDemand;
    private System.UInt32 m_LastFrameIndex;
    private System.Int32 m_AvgHappiness;
    private Game.UI.UIUpdateState m_UpdateState;
    private Game.UI.InGame.CityInfoUISystem+TypeHandle __TypeHandle;
    public static const System.String kGroup;

    private System.Single m_ResidentialLowDemandBindingValue { private get; }
    private System.Single m_ResidentialMediumDemandBindingValue { private get; }
    private System.Single m_ResidentialHighDemandBindingValue { private get; }
    private System.Single m_CommercialDemandBindingValue { private get; }
    private System.Single m_IndustrialDemandBindingValue { private get; }
    private System.Single m_OfficeDemandBindingValue { private get; }

    public CityInfoUISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Single <OnCreate>b__35_0();
    private System.Single <OnCreate>b__35_1();
    private System.Single <OnCreate>b__35_2();
    private System.Single <OnCreate>b__35_3();
    private System.Single <OnCreate>b__35_4();
    private System.Single <OnCreate>b__35_5();
    private System.Int32 <OnCreate>b__35_6();
    private static System.Single AdvanceSmoothDemand(System.Single current, System.Int32 target, System.UInt32 delta);
    public System.Void Deserialize<TReader>(TReader reader);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
    public System.Void RequestUpdate();
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
    private System.Void WriteCommercialFactors(Colossal.UI.Binding.IJsonWriter writer);
    private System.Void WriteDemandFactors(Colossal.UI.Binding.IJsonWriter writer, Unity.Collections.NativeArray<System.Int32> factors, Unity.Jobs.JobHandle deps);
    private System.Void WriteHappinessFactors(Colossal.UI.Binding.IJsonWriter writer);
    private System.Void WriteIndustrialFactors(Colossal.UI.Binding.IJsonWriter writer);
    private System.Void WriteOfficeFactors(Colossal.UI.Binding.IJsonWriter writer);
    private System.Void WriteResidentialHighFactors(Colossal.UI.Binding.IJsonWriter writer);
    private System.Void WriteResidentialLowFactors(Colossal.UI.Binding.IJsonWriter writer);
    private System.Void WriteResidentialMediumFactors(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.ResidentialDemandSystem m_ResidentialDemandSystem`  

```csharp
private Game.Simulation.ResidentialDemandSystem m_ResidentialDemandSystem;
```

- `private Game.Simulation.CommercialDemandSystem m_CommercialDemandSystem`  

```csharp
private Game.Simulation.CommercialDemandSystem m_CommercialDemandSystem;
```

- `private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem`  

```csharp
private Game.Simulation.IndustrialDemandSystem m_IndustrialDemandSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Simulation.CitizenHappinessSystem m_CitizenHappinessSystem`  

```csharp
private Game.Simulation.CitizenHappinessSystem m_CitizenHappinessSystem;
```

- `private Colossal.UI.Binding.RawValueBinding m_ResidentialLowFactors`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_ResidentialLowFactors;
```

- `private Colossal.UI.Binding.RawValueBinding m_ResidentialMediumFactors`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_ResidentialMediumFactors;
```

- `private Colossal.UI.Binding.RawValueBinding m_ResidentialHighFactors`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_ResidentialHighFactors;
```

- `private Colossal.UI.Binding.RawValueBinding m_CommercialFactors`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_CommercialFactors;
```

- `private Colossal.UI.Binding.RawValueBinding m_IndustrialFactors`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_IndustrialFactors;
```

- `private Colossal.UI.Binding.RawValueBinding m_OfficeFactors`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_OfficeFactors;
```

- `private Colossal.UI.Binding.RawValueBinding m_HappinessFactors`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_HappinessFactors;
```

- `private System.Single m_ResidentialLowDemand`  

```csharp
private System.Single m_ResidentialLowDemand;
```

- `private System.Single m_ResidentialMediumDemand`  

```csharp
private System.Single m_ResidentialMediumDemand;
```

- `private System.Single m_ResidentialHighDemand`  

```csharp
private System.Single m_ResidentialHighDemand;
```

- `private System.Single m_CommercialDemand`  

```csharp
private System.Single m_CommercialDemand;
```

- `private System.Single m_IndustrialDemand`  

```csharp
private System.Single m_IndustrialDemand;
```

- `private System.Single m_OfficeDemand`  

```csharp
private System.Single m_OfficeDemand;
```

- `private System.UInt32 m_LastFrameIndex`  

```csharp
private System.UInt32 m_LastFrameIndex;
```

- `private System.Int32 m_AvgHappiness`  

```csharp
private System.Int32 m_AvgHappiness;
```

- `private Game.UI.UIUpdateState m_UpdateState`  

```csharp
private Game.UI.UIUpdateState m_UpdateState;
```

- `private Game.UI.InGame.CityInfoUISystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.CityInfoUISystem+TypeHandle __TypeHandle;
```

- `public static const System.String kGroup`  

```csharp
public static const System.String kGroup;
```


## Properties

- `private System.Single m_ResidentialLowDemandBindingValue { private get }`  

```csharp
private System.Single m_ResidentialLowDemandBindingValue { private get; }
```

- `private System.Single m_ResidentialMediumDemandBindingValue { private get }`  

```csharp
private System.Single m_ResidentialMediumDemandBindingValue { private get; }
```

- `private System.Single m_ResidentialHighDemandBindingValue { private get }`  

```csharp
private System.Single m_ResidentialHighDemandBindingValue { private get; }
```

- `private System.Single m_CommercialDemandBindingValue { private get }`  

```csharp
private System.Single m_CommercialDemandBindingValue { private get; }
```

- `private System.Single m_IndustrialDemandBindingValue { private get }`  

```csharp
private System.Single m_IndustrialDemandBindingValue { private get; }
```

- `private System.Single m_OfficeDemandBindingValue { private get }`  

```csharp
private System.Single m_OfficeDemandBindingValue { private get; }
```


## Constructors

- `public CityInfoUISystem()`  

```csharp
public CityInfoUISystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private <OnCreate>b__35_0() : System.Single`  

```csharp
private System.Single <OnCreate>b__35_0();
```

- `private <OnCreate>b__35_1() : System.Single`  

```csharp
private System.Single <OnCreate>b__35_1();
```

- `private <OnCreate>b__35_2() : System.Single`  

```csharp
private System.Single <OnCreate>b__35_2();
```

- `private <OnCreate>b__35_3() : System.Single`  

```csharp
private System.Single <OnCreate>b__35_3();
```

- `private <OnCreate>b__35_4() : System.Single`  

```csharp
private System.Single <OnCreate>b__35_4();
```

- `private <OnCreate>b__35_5() : System.Single`  

```csharp
private System.Single <OnCreate>b__35_5();
```

- `private <OnCreate>b__35_6() : System.Int32`  

```csharp
private System.Int32 <OnCreate>b__35_6();
```

- `private static AdvanceSmoothDemand(System.Single current, System.Int32 target, System.UInt32 delta) : System.Single`  

```csharp
private static System.Single AdvanceSmoothDemand(System.Single current, System.Int32 target, System.UInt32 delta);
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public RequestUpdate() : System.Void`  

```csharp
public System.Void RequestUpdate();
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
```

- `private WriteCommercialFactors(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private System.Void WriteCommercialFactors(Colossal.UI.Binding.IJsonWriter writer);
```

- `private WriteDemandFactors(Colossal.UI.Binding.IJsonWriter writer, Unity.Collections.NativeArray<System.Int32> factors, Unity.Jobs.JobHandle deps) : System.Void`  

```csharp
private System.Void WriteDemandFactors(Colossal.UI.Binding.IJsonWriter writer, Unity.Collections.NativeArray<System.Int32> factors, Unity.Jobs.JobHandle deps);
```

- `private WriteHappinessFactors(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private System.Void WriteHappinessFactors(Colossal.UI.Binding.IJsonWriter writer);
```

- `private WriteIndustrialFactors(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private System.Void WriteIndustrialFactors(Colossal.UI.Binding.IJsonWriter writer);
```

- `private WriteOfficeFactors(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private System.Void WriteOfficeFactors(Colossal.UI.Binding.IJsonWriter writer);
```

- `private WriteResidentialHighFactors(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private System.Void WriteResidentialHighFactors(Colossal.UI.Binding.IJsonWriter writer);
```

- `private WriteResidentialLowFactors(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private System.Void WriteResidentialLowFactors(Colossal.UI.Binding.IJsonWriter writer);
```

- `private WriteResidentialMediumFactors(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private System.Void WriteResidentialMediumFactors(Colossal.UI.Binding.IJsonWriter writer);
```


## Nested types

- `Game.UI.InGame.CityInfoUISystem+TypeHandle`  

