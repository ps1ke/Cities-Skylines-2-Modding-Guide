# Game.UI.Menu.ModdingToolchainDependency

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class public  

**Base:** `Game.UI.Widgets.ReadonlyField<Game.Modding.Toolchain.IToolchainDependency>`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `Game.UI.Widgets.INamed`, `Game.UI.Widgets.ITooltipTarget`, `Game.UI.Widgets.IUITagProvider`, `Game.UI.Widgets.IExpandable`  

## Code

```csharp
public class ModdingToolchainDependency : Game.UI.Widgets.ReadonlyField<Game.Modding.Toolchain.IToolchainDependency>, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback, Game.UI.Widgets.INamed, Game.UI.Widgets.ITooltipTarget, Game.UI.Widgets.IUITagProvider, Game.UI.Widgets.IExpandable
{
    private System.Boolean m_Expanded;
    private System.Collections.Generic.IList<Game.UI.Widgets.IWidget> m_Children;
    private Game.Reflection.ITypedValueAccessor<System.Boolean> <expandedAccessor>k__BackingField;

    public Game.Reflection.ITypedValueAccessor<System.Boolean> expandedAccessor { get; set; }
    public System.Boolean expanded { get; set; }
    public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children { get; set; }
    public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> visibleChildren { get; }

    public ModdingToolchainDependency();

    protected virtual Game.UI.Widgets.WidgetChanges Update();
    public virtual Game.UI.Widgets.WidgetChanges UpdateVisibility();
}
```


## Fields

- `private System.Boolean m_Expanded`  

```csharp
private System.Boolean m_Expanded;
```

- `private System.Collections.Generic.IList<Game.UI.Widgets.IWidget> m_Children`  

```csharp
private System.Collections.Generic.IList<Game.UI.Widgets.IWidget> m_Children;
```

- `private Game.Reflection.ITypedValueAccessor<System.Boolean> <expandedAccessor>k__BackingField`  

```csharp
private Game.Reflection.ITypedValueAccessor<System.Boolean> <expandedAccessor>k__BackingField;
```


## Properties

- `public Game.Reflection.ITypedValueAccessor<System.Boolean> expandedAccessor { get; set }`  

```csharp
public Game.Reflection.ITypedValueAccessor<System.Boolean> expandedAccessor { get; set; }
```

- `public System.Boolean expanded { get; set }`  

```csharp
public System.Boolean expanded { get; set; }
```

- `public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children { get; set }`  

```csharp
public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children { get; set; }
```

- `public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> visibleChildren { get }`  

```csharp
public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> visibleChildren { get; }
```


## Constructors

- `public ModdingToolchainDependency()`  

```csharp
public ModdingToolchainDependency();
```


## Methods

- `protected virtual Update() : Game.UI.Widgets.WidgetChanges`  

```csharp
protected virtual Game.UI.Widgets.WidgetChanges Update();
```

- `public virtual UpdateVisibility() : Game.UI.Widgets.WidgetChanges`  

```csharp
public virtual Game.UI.Widgets.WidgetChanges UpdateVisibility();
```


