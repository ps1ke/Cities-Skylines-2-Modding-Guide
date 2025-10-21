# Game.UI.Tooltip.InputHintTooltip

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Widgets.Widget`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`  

## Code

```csharp
public class InputHintTooltip : Game.UI.Widgets.Widget, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback
{
    public Game.Input.ProxyAction m_Action;
    private Game.UI.InputHintBindings+InputHint m_Hint;
    private Game.Input.InputManager+DeviceType m_Device;
    private static const System.String kInputHint;

    public InputHintTooltip(Game.Input.ProxyAction action, Game.Input.InputManager+DeviceType device);

    public System.Void Refresh();
    protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `public Game.Input.ProxyAction m_Action`  

```csharp
public Game.Input.ProxyAction m_Action;
```

- `private Game.UI.InputHintBindings+InputHint m_Hint`  

```csharp
private Game.UI.InputHintBindings+InputHint m_Hint;
```

- `private Game.Input.InputManager+DeviceType m_Device`  

```csharp
private Game.Input.InputManager+DeviceType m_Device;
```

- `private static const System.String kInputHint`  

```csharp
private static const System.String kInputHint;
```


## Constructors

- `public InputHintTooltip(Game.Input.ProxyAction action, Game.Input.InputManager+DeviceType device)`  

```csharp
public InputHintTooltip(Game.Input.ProxyAction action, Game.Input.InputManager+DeviceType device);
```


## Methods

- `public Refresh() : System.Void`  

```csharp
public System.Void Refresh();
```

- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
```


