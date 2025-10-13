# Game.UI.InGame.ToolbarBottomUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ToolbarBottomUISystem : Game.UI.UISystemBase
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Simulation.ICityStatisticsSystem m_CityStatisticsSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Simulation.ICityServiceBudgetSystem m_CityServiceBudgetSystem;
    private Colossal.UI.Binding.GetterValueBinding<System.String> m_CityNameBinding;
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_MoneyBinding;
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_MoneyDeltaBinding;
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_PopulationBinding;
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_PopulationDeltaBinding;
    private Colossal.UI.Binding.GetterValueBinding<System.Boolean> m_UnlimitedMoneyBinding;
    private Game.Prefabs.UIToolbarBottomConfigurationPrefab m_ToolbarBottomConfigurationPrefab;
    private Unity.Entities.EntityQuery m_ToolbarBottomConfigurationQuery;
    private Game.UI.InGame.ToolbarBottomUISystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_2118611066_0;
    private static const System.String kGroup;

    public ToolbarBottomUISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.String <OnCreate>b__14_0();
    private System.Int32 <OnCreate>b__14_1();
    private System.Boolean <OnCreate>b__14_2();
    private Unity.Mathematics.float2 <OnCreate>b__14_3();
    private Unity.Mathematics.float2 <OnCreate>b__14_4();
    private System.Int32 GetPopulation();
    private System.Int32 GetPopulationDelta();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    private System.Void SetCityName(System.String name);
}
```


## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Simulation.ICityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.ICityStatisticsSystem m_CityStatisticsSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Simulation.ICityServiceBudgetSystem m_CityServiceBudgetSystem`  

```csharp
private Game.Simulation.ICityServiceBudgetSystem m_CityServiceBudgetSystem;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.String> m_CityNameBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.String> m_CityNameBinding;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_MoneyBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_MoneyBinding;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_MoneyDeltaBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_MoneyDeltaBinding;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_PopulationBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_PopulationBinding;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_PopulationDeltaBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_PopulationDeltaBinding;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Boolean> m_UnlimitedMoneyBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Boolean> m_UnlimitedMoneyBinding;
```

- `private Game.Prefabs.UIToolbarBottomConfigurationPrefab m_ToolbarBottomConfigurationPrefab`  

```csharp
private Game.Prefabs.UIToolbarBottomConfigurationPrefab m_ToolbarBottomConfigurationPrefab;
```

- `private Unity.Entities.EntityQuery m_ToolbarBottomConfigurationQuery`  

```csharp
private Unity.Entities.EntityQuery m_ToolbarBottomConfigurationQuery;
```

- `private Game.UI.InGame.ToolbarBottomUISystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.ToolbarBottomUISystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_2118611066_0`  

```csharp
private Unity.Entities.EntityQuery __query_2118611066_0;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Constructors

- `public ToolbarBottomUISystem()`  

```csharp
public ToolbarBottomUISystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private <OnCreate>b__14_0() : System.String`  

```csharp
private System.String <OnCreate>b__14_0();
```

- `private <OnCreate>b__14_1() : System.Int32`  

```csharp
private System.Int32 <OnCreate>b__14_1();
```

- `private <OnCreate>b__14_2() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__14_2();
```

- `private <OnCreate>b__14_3() : Unity.Mathematics.float2`  

```csharp
private Unity.Mathematics.float2 <OnCreate>b__14_3();
```

- `private <OnCreate>b__14_4() : Unity.Mathematics.float2`  

```csharp
private Unity.Mathematics.float2 <OnCreate>b__14_4();
```

- `private GetPopulation() : System.Int32`  

```csharp
private System.Int32 GetPopulation();
```

- `private GetPopulationDelta() : System.Int32`  

```csharp
private System.Int32 GetPopulationDelta();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private SetCityName(System.String name) : System.Void`  

```csharp
private System.Void SetCityName(System.String name);
```


## Nested types

- `Game.UI.InGame.ToolbarBottomUISystem+TypeHandle`  

