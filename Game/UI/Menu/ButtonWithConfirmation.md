# Game.UI.Menu.ButtonWithConfirmation

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class public  

**Base:** `Game.UI.Widgets.Button`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `Game.UI.Widgets.INamed`, `Game.UI.Widgets.ITooltipTarget`, `Game.UI.Widgets.IUITagProvider`, `Game.UI.Widgets.IInvokable`  

## Code

```csharp
public class ButtonWithConfirmation : Game.UI.Widgets.Button, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback, Game.UI.Widgets.INamed, Game.UI.Widgets.ITooltipTarget, Game.UI.Widgets.IUITagProvider, Game.UI.Widgets.IInvokable
{
    private System.Nullable<Game.UI.Localization.LocalizedString> m_ConfirmationMessage;

    public System.Nullable<Game.UI.Localization.LocalizedString> confirmationMessage { get; set; }

    public ButtonWithConfirmation();

    protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private System.Nullable<Game.UI.Localization.LocalizedString> m_ConfirmationMessage`  

```csharp
private System.Nullable<Game.UI.Localization.LocalizedString> m_ConfirmationMessage;
```


## Properties

- `public System.Nullable<Game.UI.Localization.LocalizedString> confirmationMessage { get; set }`  

```csharp
public System.Nullable<Game.UI.Localization.LocalizedString> confirmationMessage { get; set; }
```


## Constructors

- `public ButtonWithConfirmation()`  

```csharp
public ButtonWithConfirmation();
```


## Methods

- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
```


