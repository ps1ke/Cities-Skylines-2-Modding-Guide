# Game.UI.InGame.WaterInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WaterInfoviewUISystem : Game.UI.InGame.InfoviewUISystemBase, Game.Serialization.IPreDeserialize
{
    private Game.Simulation.WaterStatisticsSystem m_WaterStatisticsSystem;
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_WaterCapacity;
    private Game.Simulation.WaterTradeSystem m_WaterTradeSystem;
    private Unity.Entities.EntityQuery m_OutsideTradeParameterGroup;
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_WaterConsumption;
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_SewageCapacity;
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_SewageConsumption;
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_WaterExport;
    private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_WaterAvailability;
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_WaterImport;
    private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_SewageAvailability;
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_SewageExport;
    private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_WaterTrade;
    private static const System.String kGroup;

    protected System.Boolean Active { protected get; }

    public WaterInfoviewUISystem();

    private System.Int32 <OnCreate>b__14_0();
    private System.Int32 <OnCreate>b__14_1();
    private System.Int32 <OnCreate>b__14_2();
    private System.Int32 <OnCreate>b__14_3();
    private System.Int32 <OnCreate>b__14_4();
    private System.Int32 <OnCreate>b__14_5();
    private System.Int32 <OnCreate>b__14_6();
    private Game.UI.InGame.IndicatorValue GetSewageAvailability();
    private Game.UI.InGame.IndicatorValue GetWaterAvailability();
    private Game.UI.InGame.IndicatorValue GetWaterTrade();
    protected virtual System.Void OnCreate();
    protected virtual System.Void PerformUpdate();
}
```


## Fields

- `private Game.Simulation.WaterStatisticsSystem m_WaterStatisticsSystem`  

```csharp
private Game.Simulation.WaterStatisticsSystem m_WaterStatisticsSystem;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_WaterCapacity`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_WaterCapacity;
```

- `private Game.Simulation.WaterTradeSystem m_WaterTradeSystem`  

```csharp
private Game.Simulation.WaterTradeSystem m_WaterTradeSystem;
```

- `private Unity.Entities.EntityQuery m_OutsideTradeParameterGroup`  

```csharp
private Unity.Entities.EntityQuery m_OutsideTradeParameterGroup;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_WaterConsumption`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_WaterConsumption;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_SewageCapacity`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_SewageCapacity;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_SewageConsumption`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_SewageConsumption;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_WaterExport`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_WaterExport;
```

- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_WaterAvailability`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_WaterAvailability;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_WaterImport`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_WaterImport;
```

- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_SewageAvailability`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_SewageAvailability;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_SewageExport`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_SewageExport;
```

- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_WaterTrade`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_WaterTrade;
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

- `public WaterInfoviewUISystem()`  

```csharp
[Preserve]
	public WaterInfoviewUISystem()
	{
	}
```


## Methods

- `private <OnCreate>b__14_0() : System.Int32`  

```csharp
private System.Int32 <OnCreate>b__14_0();
```

- `private <OnCreate>b__14_1() : System.Int32`  

```csharp
private System.Int32 <OnCreate>b__14_1();
```

- `private <OnCreate>b__14_2() : System.Int32`  

```csharp
private System.Int32 <OnCreate>b__14_2();
```

- `private <OnCreate>b__14_3() : System.Int32`  

```csharp
private System.Int32 <OnCreate>b__14_3();
```

- `private <OnCreate>b__14_4() : System.Int32`  

```csharp
private System.Int32 <OnCreate>b__14_4();
```

- `private <OnCreate>b__14_5() : System.Int32`  

```csharp
private System.Int32 <OnCreate>b__14_5();
```

- `private <OnCreate>b__14_6() : System.Int32`  

```csharp
private System.Int32 <OnCreate>b__14_6();
```

- `private GetSewageAvailability() : Game.UI.InGame.IndicatorValue`  

```csharp
private IndicatorValue GetSewageAvailability()
	{
		return IndicatorValue.Calculate(m_WaterStatisticsSystem.sewageCapacity, m_WaterStatisticsSystem.sewageConsumption);
	}
```

- `private GetWaterAvailability() : Game.UI.InGame.IndicatorValue`  

```csharp
private IndicatorValue GetWaterAvailability()
	{
		return IndicatorValue.Calculate(m_WaterStatisticsSystem.freshCapacity, m_WaterStatisticsSystem.freshConsumption);
	}
```

- `private GetWaterTrade() : Game.UI.InGame.IndicatorValue`  

```csharp
private IndicatorValue GetWaterTrade()
	{
		if (!m_OutsideTradeParameterGroup.IsEmptyIgnoreFilter)
		{
			OutsideTradeParameterData singleton = m_OutsideTradeParameterGroup.GetSingleton<OutsideTradeParameterData>();
			float num = (float)m_WaterTradeSystem.freshExport * singleton.m_WaterExportPrice - (float)m_WaterTradeSystem.freshImport * singleton.m_WaterImportPrice;
			float num2 = math.max(0.01f, (float)m_WaterStatisticsSystem.freshConsumption * singleton.m_WaterExportPrice);
			return new IndicatorValue(-1f, 1f, math.clamp(num / num2, -1f, 1f));
		}
		return new IndicatorValue(-1f, 1f, 0f);
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_WaterStatisticsSystem = base.World.GetOrCreateSystemManaged<WaterStatisticsSystem>();
		m_WaterTradeSystem = base.World.GetOrCreateSystemManaged<WaterTradeSystem>();
		m_OutsideTradeParameterGroup = GetEntityQuery(ComponentType.ReadOnly<OutsideTradeParameterData>());
		AddBinding(m_WaterCapacity = new GetterValueBinding<int>("waterInfo", "waterCapacity", () => m_WaterStatisticsSystem.freshCapacity));
		AddBinding(m_WaterConsumption = new GetterValueBinding<int>("waterInfo", "waterConsumption", () => m_WaterStatisticsSystem.freshConsumption));
		AddBinding(m_SewageCapacity = new GetterValueBinding<int>("waterInfo", "sewageCapacity", () => m_WaterStatisticsSystem.sewageCapacity));
		AddBinding(m_SewageConsumption = new GetterValueBinding<int>("waterInfo", "sewageConsumption", () => m_WaterStatisticsSystem.sewageConsumption));
		AddBinding(m_WaterExport = new GetterValueBinding<int>("waterInfo", "waterExport", () => m_WaterTradeSystem.freshExport));
		AddBinding(m_WaterImport = new GetterValueBinding<int>("waterInfo", "waterImport", () => m_WaterTradeSystem.freshImport));
		AddBinding(m_SewageExport = new GetterValueBinding<int>("waterInfo", "sewageExport", () => m_WaterTradeSystem.sewageExport));
		AddBinding(m_WaterAvailability = new GetterValueBinding<IndicatorValue>("waterInfo", "waterAvailability", GetWaterAvailability, new ValueWriter<IndicatorValue>()));
		AddBinding(m_SewageAvailability = new GetterValueBinding<IndicatorValue>("waterInfo", "sewageAvailability", GetSewageAvailability, new ValueWriter<IndicatorValue>()));
		AddBinding(m_WaterTrade = new GetterValueBinding<IndicatorValue>("waterInfo", "waterTrade", GetWaterTrade, new ValueWriter<IndicatorValue>()));
	}
```

- `protected virtual PerformUpdate() : System.Void`  

```csharp
protected override void PerformUpdate()
	{
		m_WaterCapacity.Update();
		m_WaterConsumption.Update();
		m_SewageCapacity.Update();
		m_SewageConsumption.Update();
		m_WaterExport.Update();
		m_WaterImport.Update();
		m_SewageExport.Update();
		m_WaterAvailability.Update();
		m_SewageAvailability.Update();
		m_WaterTrade.Update();
	}
```


