# Game.Vehicles.FixParkingLocation

**Assembly:** `Game`  
**Namespace:** `Game.Vehicles`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct FixParkingLocation : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Unity.Entities.Entity m_ChangeLane;
    public Unity.Entities.Entity m_ResetLocation;

    public FixParkingLocation(Unity.Entities.Entity changeLane, Unity.Entities.Entity resetLocation);

}
```


## Fields

- `public Unity.Entities.Entity m_ChangeLane`  

```csharp
public Unity.Entities.Entity m_ChangeLane;
```

- `public Unity.Entities.Entity m_ResetLocation`  

```csharp
public Unity.Entities.Entity m_ResetLocation;
```


## Constructors

- `public FixParkingLocation(Unity.Entities.Entity changeLane, Unity.Entities.Entity resetLocation)`  

```csharp
public FixParkingLocation(Unity.Entities.Entity changeLane, Unity.Entities.Entity resetLocation);
```


