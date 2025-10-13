# Game.UI.Editor.TimeOfDayWeightsChart

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Widgets.Widget`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`  

## Code

```csharp
public class TimeOfDayWeightsChart : Game.UI.Widgets.Widget, Game.UI.Widgets.IWidget, Colossal.UI.Binding.IJsonWritable, Game.UI.Widgets.IVisibleWidget, Game.UI.Widgets.IDisableCallback
{
    private Unity.Mathematics.float4 m_Value;
    private System.Single <min>k__BackingField;
    private System.Single <max>k__BackingField;
    private Game.Reflection.ITypedValueAccessor<Unity.Mathematics.float4> <accessor>k__BackingField;

    public System.Single min { get; set; }
    public System.Single max { get; set; }
    public Game.Reflection.ITypedValueAccessor<Unity.Mathematics.float4> accessor { get; set; }

    public TimeOfDayWeightsChart();

    protected virtual Game.UI.Widgets.WidgetChanges Update();
    protected virtual System.Void WriteProperties(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private Unity.Mathematics.float4 m_Value`  

```csharp
private Unity.Mathematics.float4 m_Value;
```

- `private System.Single <min>k__BackingField`  

```csharp
private System.Single <min>k__BackingField;
```

- `private System.Single <max>k__BackingField`  

```csharp
private System.Single <max>k__BackingField;
```

- `private Game.Reflection.ITypedValueAccessor<Unity.Mathematics.float4> <accessor>k__BackingField`  

```csharp
private Game.Reflection.ITypedValueAccessor<Unity.Mathematics.float4> <accessor>k__BackingField;
```


## Properties

- `public System.Single min { get; set }`  

```csharp
public System.Single min { get; set; }
```

- `public System.Single max { get; set }`  

```csharp
public System.Single max { get; set; }
```

- `public Game.Reflection.ITypedValueAccessor<Unity.Mathematics.float4> accessor { get; set }`  

```csharp
public Game.Reflection.ITypedValueAccessor<Unity.Mathematics.float4> accessor { get; set; }
```


## Constructors

- `public TimeOfDayWeightsChart()`  

```csharp
public TimeOfDayWeightsChart();
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


