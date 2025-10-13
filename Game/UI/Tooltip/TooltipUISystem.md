# Game.UI.Tooltip.TooltipUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

## Code

```csharp
public class TooltipUISystem : Game.UI.UISystemBase
{
    private Game.UpdateSystem m_UpdateSystem;
    private Game.UI.Widgets.WidgetBindings m_WidgetBindings;
    private System.Collections.Generic.List<Game.UI.Tooltip.TooltipGroup> <groups>k__BackingField;
    private Game.UI.Tooltip.TooltipGroup <mouseGroup>k__BackingField;
    private static readonly Unity.Mathematics.float2 kTooltipPointerDistance;
    private static const System.String kGroup;

    public Game.GameMode gameMode { get; }
    public System.Collections.Generic.List<Game.UI.Tooltip.TooltipGroup> groups { get; private set; }
    public Game.UI.Tooltip.TooltipGroup mouseGroup { get; private set; }

    public TooltipUISystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.UpdateSystem m_UpdateSystem`  

```csharp
private Game.UpdateSystem m_UpdateSystem;
```

- `private Game.UI.Widgets.WidgetBindings m_WidgetBindings`  

```csharp
private Game.UI.Widgets.WidgetBindings m_WidgetBindings;
```

- `private System.Collections.Generic.List<Game.UI.Tooltip.TooltipGroup> <groups>k__BackingField`  

```csharp
private System.Collections.Generic.List<Game.UI.Tooltip.TooltipGroup> <groups>k__BackingField;
```

- `private Game.UI.Tooltip.TooltipGroup <mouseGroup>k__BackingField`  

```csharp
private Game.UI.Tooltip.TooltipGroup <mouseGroup>k__BackingField;
```

- `private static readonly Unity.Mathematics.float2 kTooltipPointerDistance`  

```csharp
private static readonly Unity.Mathematics.float2 kTooltipPointerDistance;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Properties

- `public Game.GameMode gameMode { get }`  

```csharp
public Game.GameMode gameMode { get; }
```

- `public System.Collections.Generic.List<Game.UI.Tooltip.TooltipGroup> groups { get; private set }`  

```csharp
public System.Collections.Generic.List<Game.UI.Tooltip.TooltipGroup> groups { get; private set; }
```

- `public Game.UI.Tooltip.TooltipGroup mouseGroup { get; private set }`  

```csharp
public Game.UI.Tooltip.TooltipGroup mouseGroup { get; private set; }
```


## Constructors

- `public TooltipUISystem()`  

```csharp
public TooltipUISystem();
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


