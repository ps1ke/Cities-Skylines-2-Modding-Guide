# Game.UI.Widgets.EnumField

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `Game.UI.Widgets.Field<System.UInt64>`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `Game.UI.Widgets.INamed`, `Game.UI.Widgets.ITooltipTarget`, `Game.UI.Widgets.IUITagProvider`, `Game.UI.Widgets.ISettable`, `Game.UI.Widgets.IWarning`  

## Code

```csharp
public class EnumField : Game.UI.Widgets.Field<System.UInt64>, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback, Game.UI.Widgets.INamed, Game.UI.Widgets.ITooltipTarget, Game.UI.Widgets.IUITagProvider, Game.UI.Widgets.ISettable, Game.UI.Widgets.IWarning
{
    private System.Int32 m_ItemsVersion;
    private System.Boolean m_Warning;
    private System.Func<System.Boolean> <warningAction>k__BackingField;
    private Game.UI.Widgets.EnumMember[] <enumMembers>k__BackingField;
    private System.Func<System.Int32> <itemsVersion>k__BackingField;
    private Game.Reflection.ITypedValueAccessor<Game.UI.Widgets.EnumMember[]> <itemsAccessor>k__BackingField;

    public System.Func<System.Boolean> warningAction { get; set; }
    public Game.UI.Widgets.EnumMember[] enumMembers { get; set; }
    public System.Func<System.Int32> itemsVersion { get; set; }
    public Game.Reflection.ITypedValueAccessor<Game.UI.Widgets.EnumMember[]> itemsAccessor { get; set; }
    public System.Boolean warning { get; set; }

    public EnumField();

    protected virtual Game.UI.Widgets.WidgetChanges Update();
    protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private System.Int32 m_ItemsVersion`  

```csharp
private System.Int32 m_ItemsVersion;
```

- `private System.Boolean m_Warning`  

```csharp
private System.Boolean m_Warning;
```

- `private System.Func<System.Boolean> <warningAction>k__BackingField`  

```csharp
private System.Func<System.Boolean> <warningAction>k__BackingField;
```

- `private Game.UI.Widgets.EnumMember[] <enumMembers>k__BackingField`  

```csharp
private Game.UI.Widgets.EnumMember[] <enumMembers>k__BackingField;
```

- `private System.Func<System.Int32> <itemsVersion>k__BackingField`  

```csharp
private System.Func<System.Int32> <itemsVersion>k__BackingField;
```

- `private Game.Reflection.ITypedValueAccessor<Game.UI.Widgets.EnumMember[]> <itemsAccessor>k__BackingField`  

```csharp
private Game.Reflection.ITypedValueAccessor<Game.UI.Widgets.EnumMember[]> <itemsAccessor>k__BackingField;
```


## Properties

- `public System.Func<System.Boolean> warningAction { get; set }`  

```csharp
public System.Func<System.Boolean> warningAction { get; set; }
```

- `public Game.UI.Widgets.EnumMember[] enumMembers { get; set }`  

```csharp
public Game.UI.Widgets.EnumMember[] enumMembers { get; set; }
```

- `public System.Func<System.Int32> itemsVersion { get; set }`  

```csharp
public System.Func<System.Int32> itemsVersion { get; set; }
```

- `public Game.Reflection.ITypedValueAccessor<Game.UI.Widgets.EnumMember[]> itemsAccessor { get; set }`  

```csharp
public Game.Reflection.ITypedValueAccessor<Game.UI.Widgets.EnumMember[]> itemsAccessor { get; set; }
```

- `public System.Boolean warning { get; set }`  

```csharp
public System.Boolean warning { get; set; }
```


## Constructors

- `public EnumField()`  

```csharp
public EnumField();
```


## Methods

- `protected virtual Update() : Game.UI.Widgets.WidgetChanges`  

```csharp
protected virtual Game.UI.Widgets.WidgetChanges Update();
```

- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
```


