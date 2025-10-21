# Game.UI.InGame.PassengersSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PassengersSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private System.Int32 <passengers>k__BackingField;
    private System.Int32 <maxPassengers>k__BackingField;
    private System.Int32 <pets>k__BackingField;
    private Game.UI.InGame.VehiclePassengerLocaleKey <vehiclePassengerKey>k__BackingField;

    protected System.String group { protected get; }
    private System.Int32 passengers { private get; private set; }
    private System.Int32 maxPassengers { private get; private set; }
    private System.Int32 pets { private get; private set; }
    private Game.UI.InGame.VehiclePassengerLocaleKey vehiclePassengerKey { private get; private set; }
    protected Unity.Entities.Entity selectedEntity { protected get; }
    protected Unity.Entities.Entity selectedPrefab { protected get; }

    public PassengersSection();

    private System.Void AddPassengerCapacity(Unity.Entities.Entity prefab);
    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private System.Int32 <passengers>k__BackingField`  

```csharp
private System.Int32 <passengers>k__BackingField;
```

- `private System.Int32 <maxPassengers>k__BackingField`  

```csharp
private System.Int32 <maxPassengers>k__BackingField;
```

- `private System.Int32 <pets>k__BackingField`  

```csharp
private System.Int32 <pets>k__BackingField;
```

- `private Game.UI.InGame.VehiclePassengerLocaleKey <vehiclePassengerKey>k__BackingField`  

```csharp
private Game.UI.InGame.VehiclePassengerLocaleKey <vehiclePassengerKey>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private System.Int32 passengers { private get; private set }`  

```csharp
private System.Int32 passengers { private get; private set; }
```

- `private System.Int32 maxPassengers { private get; private set }`  

```csharp
private System.Int32 maxPassengers { private get; private set; }
```

- `private System.Int32 pets { private get; private set }`  

```csharp
private System.Int32 pets { private get; private set; }
```

- `private Game.UI.InGame.VehiclePassengerLocaleKey vehiclePassengerKey { private get; private set }`  

```csharp
private Game.UI.InGame.VehiclePassengerLocaleKey vehiclePassengerKey { private get; private set; }
```

- `protected Unity.Entities.Entity selectedEntity { protected get }`  

```csharp
protected Unity.Entities.Entity selectedEntity { protected get; }
```

- `protected Unity.Entities.Entity selectedPrefab { protected get }`  

```csharp
protected Unity.Entities.Entity selectedPrefab { protected get; }
```


## Constructors

- `public PassengersSection()`  

```csharp
public PassengersSection();
```


## Methods

- `private AddPassengerCapacity(Unity.Entities.Entity prefab) : System.Void`  

```csharp
private System.Void AddPassengerCapacity(Unity.Entities.Entity prefab);
```

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


