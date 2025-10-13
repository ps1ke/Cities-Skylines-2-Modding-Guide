# Game.UI.Widgets.Button

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `Game.UI.Widgets.NamedWidgetWithTooltip`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `Game.UI.Widgets.INamed`, `Game.UI.Widgets.ITooltipTarget`, `Game.UI.Widgets.IUITagProvider`, `Game.UI.Widgets.IInvokable`  

## Code

```csharp
public class Button : Game.UI.Widgets.NamedWidgetWithTooltip, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback, Game.UI.Widgets.INamed, Game.UI.Widgets.ITooltipTarget, Game.UI.Widgets.IUITagProvider, Game.UI.Widgets.IInvokable
{
    private System.Action <action>k__BackingField;

    public System.Action action { get; set; }

    public Button();

    public System.Void Invoke();
}
```


## Fields

- `private System.Action <action>k__BackingField`  

```csharp
private System.Action <action>k__BackingField;
```


## Properties

- `public System.Action action { get; set }`  

```csharp
public System.Action action { get; set; }
```


## Constructors

- `public Button()`  

```csharp
public Button();
```


## Methods

- `public Invoke() : System.Void`  

```csharp
public System.Void Invoke();
```


