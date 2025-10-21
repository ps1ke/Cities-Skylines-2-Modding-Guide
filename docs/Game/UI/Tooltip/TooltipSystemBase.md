# Game.UI.Tooltip.TooltipSystemBase

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class abstract public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public abstract class TooltipSystemBase : Game.GameSystemBase
{
    private Game.UI.Tooltip.TooltipUISystem m_TooltipUISystem;

    protected TooltipSystemBase();

    protected System.Void AddGroup(Game.UI.Tooltip.TooltipGroup group);
    protected System.Void AddMouseTooltip(Game.UI.Widgets.IWidget tooltip);
    protected virtual System.Void OnCreate();
    protected static Unity.Mathematics.float2 WorldToTooltipPos(UnityEngine.Vector3 worldPos, System.Boolean& onScreen);
}
```


## Fields

- `private Game.UI.Tooltip.TooltipUISystem m_TooltipUISystem`  

```csharp
private Game.UI.Tooltip.TooltipUISystem m_TooltipUISystem;
```


## Constructors

- `protected TooltipSystemBase()`  

```csharp
protected TooltipSystemBase();
```


## Methods

- `protected AddGroup(Game.UI.Tooltip.TooltipGroup group) : System.Void`  

```csharp
protected System.Void AddGroup(Game.UI.Tooltip.TooltipGroup group);
```

- `protected AddMouseTooltip(Game.UI.Widgets.IWidget tooltip) : System.Void`  

```csharp
protected System.Void AddMouseTooltip(Game.UI.Widgets.IWidget tooltip);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected static WorldToTooltipPos(UnityEngine.Vector3 worldPos, System.Boolean& onScreen) : Unity.Mathematics.float2`  

```csharp
protected static Unity.Mathematics.float2 WorldToTooltipPos(UnityEngine.Vector3 worldPos, System.Boolean& onScreen);
```


## Nested types

- `Game.UI.Tooltip.TooltipSystemBase+<>c__DisplayClass2_0`  
- `Game.UI.Tooltip.TooltipSystemBase+<>c__DisplayClass3_0`  

