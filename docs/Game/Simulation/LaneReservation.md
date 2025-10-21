# Game.Simulation.WatercraftNavigationHelpers+LaneReservation

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IComparable<Game.Simulation.WatercraftNavigationHelpers+LaneReservation>`  

## Code

```csharp
public sealed struct LaneReservation : System.IComparable<Game.Simulation.WatercraftNavigationHelpers+LaneReservation>
{
    public Unity.Entities.Entity m_Lane;
    public System.Byte m_Offset;
    public System.Byte m_Priority;

    public LaneReservation(Unity.Entities.Entity lane, System.Single offset, System.Int32 priority);

    public System.Int32 CompareTo(Game.Simulation.WatercraftNavigationHelpers+LaneReservation other);
}
```


## Fields

- `public Unity.Entities.Entity m_Lane`  

```csharp
public Unity.Entities.Entity m_Lane;
```

- `public System.Byte m_Offset`  

```csharp
public System.Byte m_Offset;
```

- `public System.Byte m_Priority`  

```csharp
public System.Byte m_Priority;
```


## Constructors

- `public LaneReservation(Unity.Entities.Entity lane, System.Single offset, System.Int32 priority)`  

```csharp
public LaneReservation(Unity.Entities.Entity lane, System.Single offset, System.Int32 priority);
```


## Methods

- `public CompareTo(Game.Simulation.WatercraftNavigationHelpers+LaneReservation other) : System.Int32`  

```csharp
public System.Int32 CompareTo(Game.Simulation.WatercraftNavigationHelpers+LaneReservation other);
```


