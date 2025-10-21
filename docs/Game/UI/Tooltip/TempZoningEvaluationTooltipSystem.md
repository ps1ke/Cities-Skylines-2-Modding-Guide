# Game.UI.Tooltip.TempZoningEvaluationTooltipSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Tooltip.TooltipSystemBase`  

## Code

```csharp
public class TempZoningEvaluationTooltipSystem : Game.UI.Tooltip.TooltipSystemBase
{
    private Game.Tools.IZoningInfoSystem m_ZoningInfoSystem;
    private System.Int32 <maxCount>k__BackingField;
    private System.Single <scoreThreshold>k__BackingField;
    private System.Collections.Generic.List<Game.UI.Tooltip.ZoningEvaluationTooltip> m_Tooltips;

    public System.Int32 maxCount { get; set; }
    public System.Single scoreThreshold { get; set; }

    public TempZoningEvaluationTooltipSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Tools.IZoningInfoSystem m_ZoningInfoSystem`  

```csharp
private Game.Tools.IZoningInfoSystem m_ZoningInfoSystem;
```

- `private System.Int32 <maxCount>k__BackingField`  

```csharp
private System.Int32 <maxCount>k__BackingField;
```

- `private System.Single <scoreThreshold>k__BackingField`  

```csharp
private System.Single <scoreThreshold>k__BackingField;
```

- `private System.Collections.Generic.List<Game.UI.Tooltip.ZoningEvaluationTooltip> m_Tooltips`  

```csharp
private System.Collections.Generic.List<Game.UI.Tooltip.ZoningEvaluationTooltip> m_Tooltips;
```


## Properties

- `public System.Int32 maxCount { get; set }`  

```csharp
public System.Int32 maxCount { get; set; }
```

- `public System.Single scoreThreshold { get; set }`  

```csharp
public System.Single scoreThreshold { get; set; }
```


## Constructors

- `public TempZoningEvaluationTooltipSystem()`  

```csharp
public TempZoningEvaluationTooltipSystem();
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


