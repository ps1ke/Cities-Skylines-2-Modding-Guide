# Game.UI.InGame.ElectricityInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ElectricityInfoviewUISystem : Game.UI.InGame.InfoviewUISystemBase, Game.Serialization.IPreDeserialize
{
    private Game.Simulation.ElectricityStatisticsSystem m_ElectricityStatisticsSystem;
    private Game.Simulation.ElectricityTradeSystem m_ElectricityTradeSystem;
    private Unity.Entities.EntityQuery m_OutsideTradeParameterGroup;
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_ElectricityProduction;
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_ElectricityConsumption;
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_ElectricityTransmitted;
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_ElectricityExport;
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_ElectricityImport;
    private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_ElectricityAvailability;
    private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_ElectricityTransmission;
    private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_ElectricityTrade;
    private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_BatteryCharge;
    private static const System.String kGroup;

    protected System.Boolean Active { protected get; }

    public ElectricityInfoviewUISystem();

    private System.Int32 <OnCreate>b__13_0();
    private System.Int32 <OnCreate>b__13_1();
    private System.Int32 <OnCreate>b__13_2();
    private System.Int32 <OnCreate>b__13_3();
    private System.Int32 <OnCreate>b__13_4();
    private Game.UI.InGame.IndicatorValue GetBatteryCharge();
    private Game.UI.InGame.IndicatorValue GetElectricityAvailability();
    private Game.UI.InGame.IndicatorValue GetElectricityTrade();
    private Game.UI.InGame.IndicatorValue GetElectricityTransmission();
    protected virtual System.Void OnCreate();
    protected virtual System.Void PerformUpdate();
}
```


## Fields

- `private Game.Simulation.ElectricityStatisticsSystem m_ElectricityStatisticsSystem`  

```csharp
private Game.Simulation.ElectricityStatisticsSystem m_ElectricityStatisticsSystem;
```

- `private Game.Simulation.ElectricityTradeSystem m_ElectricityTradeSystem`  

```csharp
private Game.Simulation.ElectricityTradeSystem m_ElectricityTradeSystem;
```

- `private Unity.Entities.EntityQuery m_OutsideTradeParameterGroup`  

```csharp
private Unity.Entities.EntityQuery m_OutsideTradeParameterGroup;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_ElectricityProduction`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_ElectricityProduction;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_ElectricityConsumption`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_ElectricityConsumption;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_ElectricityTransmitted`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_ElectricityTransmitted;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_ElectricityExport`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_ElectricityExport;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_ElectricityImport`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_ElectricityImport;
```

- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_ElectricityAvailability`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_ElectricityAvailability;
```

- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_ElectricityTransmission`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_ElectricityTransmission;
```

- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_ElectricityTrade`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_ElectricityTrade;
```

- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_BatteryCharge`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_BatteryCharge;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Properties

- `protected System.Boolean Active { protected get }`  

```csharp
protected System.Boolean Active { protected get; }
```


## Constructors

- `public ElectricityInfoviewUISystem()`  

```csharp
public ElectricityInfoviewUISystem();
```


## Methods

- `private <OnCreate>b__13_0() : System.Int32`  

```csharp
private System.Int32 <OnCreate>b__13_0();
```

- `private <OnCreate>b__13_1() : System.Int32`  

```csharp
private System.Int32 <OnCreate>b__13_1();
```

- `private <OnCreate>b__13_2() : System.Int32`  

```csharp
private System.Int32 <OnCreate>b__13_2();
```

- `private <OnCreate>b__13_3() : System.Int32`  

```csharp
private System.Int32 <OnCreate>b__13_3();
```

- `private <OnCreate>b__13_4() : System.Int32`  

```csharp
private System.Int32 <OnCreate>b__13_4();
```

- `private GetBatteryCharge() : Game.UI.InGame.IndicatorValue`  

```csharp
private Game.UI.InGame.IndicatorValue GetBatteryCharge();
```

- `private GetElectricityAvailability() : Game.UI.InGame.IndicatorValue`  

```csharp
private Game.UI.InGame.IndicatorValue GetElectricityAvailability();
```

- `private GetElectricityTrade() : Game.UI.InGame.IndicatorValue`  

```csharp
private Game.UI.InGame.IndicatorValue GetElectricityTrade();
```

- `private GetElectricityTransmission() : Game.UI.InGame.IndicatorValue`  

```csharp
private Game.UI.InGame.IndicatorValue GetElectricityTransmission();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual PerformUpdate() : System.Void`  

```csharp
protected virtual System.Void PerformUpdate();
```


