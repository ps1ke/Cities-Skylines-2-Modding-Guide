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
[Preserve]
	public ElectricityInfoviewUISystem()
	{
	}
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
private IndicatorValue GetBatteryCharge()
	{
		return new IndicatorValue(0f, m_ElectricityStatisticsSystem.batteryCapacity, m_ElectricityStatisticsSystem.batteryCharge);
	}
```

- `private GetElectricityAvailability() : Game.UI.InGame.IndicatorValue`  

```csharp
private IndicatorValue GetElectricityAvailability()
	{
		return IndicatorValue.Calculate(m_ElectricityStatisticsSystem.production, m_ElectricityStatisticsSystem.consumption);
	}
```

- `private GetElectricityTrade() : Game.UI.InGame.IndicatorValue`  

```csharp
private IndicatorValue GetElectricityTrade()
	{
		if (!m_OutsideTradeParameterGroup.IsEmptyIgnoreFilter)
		{
			OutsideTradeParameterData singleton = m_OutsideTradeParameterGroup.GetSingleton<OutsideTradeParameterData>();
			float num = (float)m_ElectricityTradeSystem.export * singleton.m_ElectricityExportPrice - (float)m_ElectricityTradeSystem.import * singleton.m_ElectricityImportPrice;
			float num2 = math.max(0.01f, (float)m_ElectricityStatisticsSystem.consumption * singleton.m_ElectricityExportPrice);
			return new IndicatorValue(-1f, 1f, math.clamp(num / num2, -1f, 1f));
		}
		return new IndicatorValue(-1f, 1f, 0f);
	}
```

- `private GetElectricityTransmission() : Game.UI.InGame.IndicatorValue`  

```csharp
private IndicatorValue GetElectricityTransmission()
	{
		float max = m_ElectricityStatisticsSystem.consumption;
		float current = m_ElectricityStatisticsSystem.fulfilledConsumption;
		return new IndicatorValue(0f, max, current);
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ElectricityStatisticsSystem = base.World.GetOrCreateSystemManaged<ElectricityStatisticsSystem>();
		m_ElectricityTradeSystem = base.World.GetOrCreateSystemManaged<ElectricityTradeSystem>();
		m_OutsideTradeParameterGroup = GetEntityQuery(ComponentType.ReadOnly<OutsideTradeParameterData>());
		AddBinding(m_ElectricityProduction = new GetterValueBinding<int>("electricityInfo", "electricityProduction", () => m_ElectricityStatisticsSystem.production));
		AddBinding(m_ElectricityConsumption = new GetterValueBinding<int>("electricityInfo", "electricityConsumption", () => m_ElectricityStatisticsSystem.consumption));
		AddBinding(m_ElectricityTransmitted = new GetterValueBinding<int>("electricityInfo", "electricityTransmitted", () => m_ElectricityStatisticsSystem.fulfilledConsumption));
		AddBinding(m_ElectricityExport = new GetterValueBinding<int>("electricityInfo", "electricityExport", () => m_ElectricityTradeSystem.export));
		AddBinding(m_ElectricityImport = new GetterValueBinding<int>("electricityInfo", "electricityImport", () => m_ElectricityTradeSystem.import));
		AddBinding(m_ElectricityAvailability = new GetterValueBinding<IndicatorValue>("electricityInfo", "electricityAvailability", GetElectricityAvailability, new ValueWriter<IndicatorValue>()));
		AddBinding(m_ElectricityTransmission = new GetterValueBinding<IndicatorValue>("electricityInfo", "electricityTransmission", GetElectricityTransmission, new ValueWriter<IndicatorValue>()));
		AddBinding(m_ElectricityTrade = new GetterValueBinding<IndicatorValue>("electricityInfo", "electricityTrade", GetElectricityTrade, new ValueWriter<IndicatorValue>()));
		AddBinding(m_BatteryCharge = new GetterValueBinding<IndicatorValue>("electricityInfo", "batteryCharge", GetBatteryCharge, new ValueWriter<IndicatorValue>()));
	}
```

- `protected virtual PerformUpdate() : System.Void`  

```csharp
protected override void PerformUpdate()
	{
		m_ElectricityProduction.Update();
		m_ElectricityConsumption.Update();
		m_ElectricityTransmitted.Update();
		m_ElectricityExport.Update();
		m_ElectricityImport.Update();
		m_ElectricityAvailability.Update();
		m_ElectricityTransmission.Update();
		m_ElectricityTrade.Update();
		m_BatteryCharge.Update();
	}
```


