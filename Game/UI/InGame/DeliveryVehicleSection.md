# Game.UI.InGame.DeliveryVehicleSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.VehicleSection`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class DeliveryVehicleSection : Game.UI.InGame.VehicleSection, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Game.Economy.Resource <resource>k__BackingField;
    private Game.UI.InGame.VehicleLocaleKey <vehicleKey>k__BackingField;

    protected System.String group { protected get; }
    private Game.Economy.Resource resource { private get; private set; }
    private Game.UI.InGame.VehicleLocaleKey vehicleKey { private get; private set; }

    public DeliveryVehicleSection();

    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private Game.Economy.Resource <resource>k__BackingField`  

```csharp
private Game.Economy.Resource <resource>k__BackingField;
```

- `private Game.UI.InGame.VehicleLocaleKey <vehicleKey>k__BackingField`  

```csharp
private Game.UI.InGame.VehicleLocaleKey <vehicleKey>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private Game.Economy.Resource resource { private get; private set }`  

```csharp
private Game.Economy.Resource resource { private get; private set; }
```

- `private Game.UI.InGame.VehicleLocaleKey vehicleKey { private get; private set }`  

```csharp
private Game.UI.InGame.VehicleLocaleKey vehicleKey { private get; private set; }
```


## Constructors

- `public DeliveryVehicleSection()`  

```csharp
public DeliveryVehicleSection();
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


