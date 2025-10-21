# Game.UI.InGame.PublicTransportVehicleSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.VehicleWithLineSection`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PublicTransportVehicleSection : Game.UI.InGame.VehicleWithLineSection, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Game.UI.InGame.VehicleLocaleKey <vehicleKey>k__BackingField;

    protected System.String group { protected get; }
    private Game.UI.InGame.VehicleLocaleKey vehicleKey { private get; private set; }

    public PublicTransportVehicleSection();

    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    private System.Boolean Visible();
}
```


## Fields

- `private Game.UI.InGame.VehicleLocaleKey <vehicleKey>k__BackingField`  

```csharp
private Game.UI.InGame.VehicleLocaleKey <vehicleKey>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private Game.UI.InGame.VehicleLocaleKey vehicleKey { private get; private set }`  

```csharp
private Game.UI.InGame.VehicleLocaleKey vehicleKey { private get; private set; }
```


## Constructors

- `public PublicTransportVehicleSection()`  

```csharp
public PublicTransportVehicleSection();
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

- `private Visible() : System.Boolean`  

```csharp
private System.Boolean Visible();
```


