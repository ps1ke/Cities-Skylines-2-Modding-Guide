# Game.UI.Editor.DLCInfoField

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Widgets.Widget`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`  

## Code

```csharp
public class DLCInfoField : Game.UI.Widgets.Widget, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback
{
    private Game.UI.Localization.LocalizedString m_DisplayName;
    private Game.UI.Localization.LocalizedString m_Type;
    private System.String m_Image;

    public Game.UI.Localization.LocalizedString displayName { get; set; }
    public Game.UI.Localization.LocalizedString type { get; set; }
    public System.String image { get; set; }

    public DLCInfoField();

    protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private Game.UI.Localization.LocalizedString m_DisplayName`  

```csharp
private Game.UI.Localization.LocalizedString m_DisplayName;
```

- `private Game.UI.Localization.LocalizedString m_Type`  

```csharp
private Game.UI.Localization.LocalizedString m_Type;
```

- `private System.String m_Image`  

```csharp
private System.String m_Image;
```


## Properties

- `public Game.UI.Localization.LocalizedString displayName { get; set }`  

```csharp
public Game.UI.Localization.LocalizedString displayName { get; set; }
```

- `public Game.UI.Localization.LocalizedString type { get; set }`  

```csharp
public Game.UI.Localization.LocalizedString type { get; set; }
```

- `public System.String image { get; set }`  

```csharp
public System.String image { get; set; }
```


## Constructors

- `public DLCInfoField()`  

```csharp
public DLCInfoField();
```


## Methods

- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
```


