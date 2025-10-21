# Game.UI.InGame.BatterySection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class BatterySection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private System.Int32 <batteryCharge>k__BackingField;
    private System.Int32 <batteryCapacity>k__BackingField;
    private System.Int32 <flow>k__BackingField;
    private System.Single <remainingTime>k__BackingField;

    protected System.String group { protected get; }
    private System.Int32 batteryCharge { private get; private set; }
    private System.Int32 batteryCapacity { private get; private set; }
    private System.Int32 flow { private get; private set; }
    private System.Single remainingTime { private get; private set; }

    public BatterySection();

    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private System.Int32 <batteryCharge>k__BackingField`  

```csharp
private System.Int32 <batteryCharge>k__BackingField;
```

- `private System.Int32 <batteryCapacity>k__BackingField`  

```csharp
private System.Int32 <batteryCapacity>k__BackingField;
```

- `private System.Int32 <flow>k__BackingField`  

```csharp
private System.Int32 <flow>k__BackingField;
```

- `private System.Single <remainingTime>k__BackingField`  

```csharp
private System.Single <remainingTime>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private System.Int32 batteryCharge { private get; private set }`  

```csharp
private System.Int32 batteryCharge { private get; private set; }
```

- `private System.Int32 batteryCapacity { private get; private set }`  

```csharp
private System.Int32 batteryCapacity { private get; private set; }
```

- `private System.Int32 flow { private get; private set }`  

```csharp
private System.Int32 flow { private get; private set; }
```

- `private System.Single remainingTime { private get; private set }`  

```csharp
private System.Single remainingTime { private get; private set; }
```


## Constructors

- `public BatterySection()`  

```csharp
public BatterySection();
```


## Methods

- `protected virtual OnProcess() : System.Void`  

```csharp
protected virtual System.Void OnProcess();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
```

- `protected virtual Reset() : System.Void`  

```csharp
protected virtual System.Void Reset();
```

- `private Visible() : System.Boolean`  

```csharp
private System.Boolean Visible();
```


