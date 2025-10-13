# Game.UI.Widgets.NamedWidget

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class abstract public  

**Base:** `Game.UI.Widgets.Widget`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `Game.UI.Widgets.INamed`  

## Code

```csharp
public abstract class NamedWidget : Game.UI.Widgets.Widget, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback, Game.UI.Widgets.INamed
{
    private Game.UI.Localization.LocalizedString m_displayName;
    private Game.UI.Localization.LocalizedString m_description;
    private System.Func<Game.UI.Localization.LocalizedString> <displayNameAction>k__BackingField;
    private System.Func<Game.UI.Localization.LocalizedString> <descriptionAction>k__BackingField;

    public System.Func<Game.UI.Localization.LocalizedString> displayNameAction { get; set; }
    public System.Func<Game.UI.Localization.LocalizedString> descriptionAction { get; set; }
    public Game.UI.Localization.LocalizedString displayName { get; set; }
    public Game.UI.Localization.LocalizedString description { get; set; }

    protected NamedWidget();

    protected virtual Game.UI.Widgets.WidgetChanges Update();
    public Game.UI.Widgets.WidgetChanges UpdateNameAndDescription(System.Boolean setChanged);
    protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private Game.UI.Localization.LocalizedString m_displayName`  

```csharp
private Game.UI.Localization.LocalizedString m_displayName;
```

- `private Game.UI.Localization.LocalizedString m_description`  

```csharp
private Game.UI.Localization.LocalizedString m_description;
```

- `private System.Func<Game.UI.Localization.LocalizedString> <displayNameAction>k__BackingField`  

```csharp
private System.Func<Game.UI.Localization.LocalizedString> <displayNameAction>k__BackingField;
```

- `private System.Func<Game.UI.Localization.LocalizedString> <descriptionAction>k__BackingField`  

```csharp
private System.Func<Game.UI.Localization.LocalizedString> <descriptionAction>k__BackingField;
```


## Properties

- `public System.Func<Game.UI.Localization.LocalizedString> displayNameAction { get; set }`  

```csharp
public System.Func<Game.UI.Localization.LocalizedString> displayNameAction { get; set; }
```

- `public System.Func<Game.UI.Localization.LocalizedString> descriptionAction { get; set }`  

```csharp
public System.Func<Game.UI.Localization.LocalizedString> descriptionAction { get; set; }
```

- `public Game.UI.Localization.LocalizedString displayName { get; set }`  

```csharp
public Game.UI.Localization.LocalizedString displayName { get; set; }
```

- `public Game.UI.Localization.LocalizedString description { get; set }`  

```csharp
public Game.UI.Localization.LocalizedString description { get; set; }
```


## Constructors

- `protected NamedWidget()`  

```csharp
protected NamedWidget();
```


## Methods

- `protected virtual Update() : Game.UI.Widgets.WidgetChanges`  

```csharp
protected virtual Game.UI.Widgets.WidgetChanges Update();
```

- `public UpdateNameAndDescription(System.Boolean setChanged = True) : Game.UI.Widgets.WidgetChanges`  

```csharp
public Game.UI.Widgets.WidgetChanges UpdateNameAndDescription(System.Boolean setChanged);
```

- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
```


