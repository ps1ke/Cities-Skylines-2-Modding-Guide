# Game.UI.InGame.MaintenanceVehicleSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.VehicleSection`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class MaintenanceVehicleSection : Game.UI.InGame.VehicleSection, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private System.Int32 <workShift>k__BackingField;

    protected System.String group { protected get; }
    private System.Int32 workShift { private get; private set; }

    public MaintenanceVehicleSection();

    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    protected System.Boolean Visible();
}
```


## Fields

- `private System.Int32 <workShift>k__BackingField`  

```csharp
private System.Int32 <workShift>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private System.Int32 workShift { private get; private set }`  

```csharp
private System.Int32 workShift { private get; private set; }
```


## Constructors

- `public MaintenanceVehicleSection()`  

```csharp
public MaintenanceVehicleSection();
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

- `protected Visible() : System.Boolean`  

```csharp
protected System.Boolean Visible();
```


