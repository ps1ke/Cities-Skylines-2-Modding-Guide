# Game.UI.InGame.VehiclesSection+UIVehicle

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IComparable<Game.UI.InGame.VehiclesSection+UIVehicle>`  

**Attributes:** `IsReadOnly`  

## Code

```csharp
public sealed struct UIVehicle : System.IComparable<Game.UI.InGame.VehiclesSection+UIVehicle>
{
    private readonly Unity.Entities.Entity <entity>k__BackingField;
    private readonly Game.UI.InGame.VehicleLocaleKey <vehicleKey>k__BackingField;
    private readonly Game.UI.InGame.VehicleStateLocaleKey <stateKey>k__BackingField;

    public Unity.Entities.Entity entity { get; }
    public Game.UI.InGame.VehicleLocaleKey vehicleKey { get; }
    public Game.UI.InGame.VehicleStateLocaleKey stateKey { get; }

    public UIVehicle(Unity.Entities.Entity entity, Game.UI.InGame.VehicleLocaleKey vehicleKey, Game.UI.InGame.VehicleStateLocaleKey stateKey);

    public System.Int32 CompareTo(Game.UI.InGame.VehiclesSection+UIVehicle other);
}
```


## Fields

- `private readonly Unity.Entities.Entity <entity>k__BackingField`  

```csharp
private readonly Unity.Entities.Entity <entity>k__BackingField;
```

- `private readonly Game.UI.InGame.VehicleLocaleKey <vehicleKey>k__BackingField`  

```csharp
private readonly Game.UI.InGame.VehicleLocaleKey <vehicleKey>k__BackingField;
```

- `private readonly Game.UI.InGame.VehicleStateLocaleKey <stateKey>k__BackingField`  

```csharp
private readonly Game.UI.InGame.VehicleStateLocaleKey <stateKey>k__BackingField;
```


## Properties

- `public Unity.Entities.Entity entity { get }`  

```csharp
public Unity.Entities.Entity entity { get; }
```

- `public Game.UI.InGame.VehicleLocaleKey vehicleKey { get }`  

```csharp
public Game.UI.InGame.VehicleLocaleKey vehicleKey { get; }
```

- `public Game.UI.InGame.VehicleStateLocaleKey stateKey { get }`  

```csharp
public Game.UI.InGame.VehicleStateLocaleKey stateKey { get; }
```


## Constructors

- `public UIVehicle(Unity.Entities.Entity entity, Game.UI.InGame.VehicleLocaleKey vehicleKey, Game.UI.InGame.VehicleStateLocaleKey stateKey)`  

```csharp
public UIVehicle(Unity.Entities.Entity entity, Game.UI.InGame.VehicleLocaleKey vehicleKey, Game.UI.InGame.VehicleStateLocaleKey stateKey);
```


## Methods

- `public CompareTo(Game.UI.InGame.VehiclesSection+UIVehicle other) : System.Int32`  

```csharp
public System.Int32 CompareTo(Game.UI.InGame.VehiclesSection+UIVehicle other);
```


