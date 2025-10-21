# Game.UI.Tooltip.TempCostTooltipSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Tooltip.TooltipSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TempCostTooltipSystem : Game.UI.Tooltip.TooltipSystemBase
{
    private Game.Simulation.CitySystem m_CitySystem;
    private Unity.Entities.EntityQuery m_TempQuery;
    private Game.UI.Tooltip.IntTooltip m_Cost;
    private Game.UI.Tooltip.IntTooltip m_Refund;
    private Game.UI.Tooltip.TempCostTooltipSystem+TypeHandle __TypeHandle;

    public TempCostTooltipSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Unity.Entities.EntityQuery m_TempQuery`  

```csharp
private Unity.Entities.EntityQuery m_TempQuery;
```

- `private Game.UI.Tooltip.IntTooltip m_Cost`  

```csharp
private Game.UI.Tooltip.IntTooltip m_Cost;
```

- `private Game.UI.Tooltip.IntTooltip m_Refund`  

```csharp
private Game.UI.Tooltip.IntTooltip m_Refund;
```

- `private Game.UI.Tooltip.TempCostTooltipSystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.Tooltip.TempCostTooltipSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TempCostTooltipSystem()`  

```csharp
public TempCostTooltipSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
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


## Nested types

- `Game.UI.Tooltip.TempCostTooltipSystem+TypeHandle`  

