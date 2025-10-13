# Game.UI.Tooltip.GuideLineTooltipSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Tooltip.TooltipSystemBase`  

## Code

```csharp
public class GuideLineTooltipSystem : Game.UI.Tooltip.TooltipSystemBase
{
    private Game.Rendering.GuideLinesSystem m_GuideLinesSystem;
    private System.Collections.Generic.List<Game.UI.Tooltip.TooltipGroup> m_Groups;

    public GuideLineTooltipSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Rendering.GuideLinesSystem m_GuideLinesSystem`  

```csharp
private Game.Rendering.GuideLinesSystem m_GuideLinesSystem;
```

- `private System.Collections.Generic.List<Game.UI.Tooltip.TooltipGroup> m_Groups`  

```csharp
private System.Collections.Generic.List<Game.UI.Tooltip.TooltipGroup> m_Groups;
```


## Constructors

- `public GuideLineTooltipSystem()`  

```csharp
public GuideLineTooltipSystem();
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


