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
public WaterInfoviewUISystem();
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
private Game.UI.InGame.IndicatorValue GetSewageAvailability();
```

- `private GetWaterAvailability() : Game.UI.InGame.IndicatorValue`  

```csharp
private Game.UI.InGame.IndicatorValue GetWaterAvailability();
```

- `private GetWaterTrade() : Game.UI.InGame.IndicatorValue`  

```csharp
private Game.UI.InGame.IndicatorValue GetWaterTrade();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual PerformUpdate() : System.Void`  

```csharp
protected virtual System.Void PerformUpdate();
```


