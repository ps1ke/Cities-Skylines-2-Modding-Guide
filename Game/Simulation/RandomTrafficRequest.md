# Game.Simulation.RandomTrafficRequest

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct RandomTrafficRequest : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_Target;
    public Game.Net.RoadTypes m_RoadType;
    public Game.Net.TrackTypes m_TrackType;
    public Game.Vehicles.EnergyTypes m_EnergyTypes;
    public Game.Vehicles.SizeClass m_SizeClass;
    public Game.Simulation.RandomTrafficRequestFlags m_Flags;

    public RandomTrafficRequest(Unity.Entities.Entity target, Game.Net.RoadTypes roadType, Game.Net.TrackTypes trackType, Game.Vehicles.EnergyTypes energyTypes, Game.Vehicles.SizeClass sizeClass, Game.Simulation.RandomTrafficRequestFlags flags);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_Target`  

```csharp
public Unity.Entities.Entity m_Target;
```

- `public Game.Net.RoadTypes m_RoadType`  

```csharp
public Game.Net.RoadTypes m_RoadType;
```

- `public Game.Net.TrackTypes m_TrackType`  

```csharp
public Game.Net.TrackTypes m_TrackType;
```

- `public Game.Vehicles.EnergyTypes m_EnergyTypes`  

```csharp
public Game.Vehicles.EnergyTypes m_EnergyTypes;
```

- `public Game.Vehicles.SizeClass m_SizeClass`  

```csharp
public Game.Vehicles.SizeClass m_SizeClass;
```

- `public Game.Simulation.RandomTrafficRequestFlags m_Flags`  

```csharp
public Game.Simulation.RandomTrafficRequestFlags m_Flags;
```


## Constructors

- `public RandomTrafficRequest(Unity.Entities.Entity target, Game.Net.RoadTypes roadType, Game.Net.TrackTypes trackType, Game.Vehicles.EnergyTypes energyTypes, Game.Vehicles.SizeClass sizeClass, Game.Simulation.RandomTrafficRequestFlags flags)`  

```csharp
public RandomTrafficRequest(Unity.Entities.Entity target, Game.Net.RoadTypes roadType, Game.Net.TrackTypes trackType, Game.Vehicles.EnergyTypes energyTypes, Game.Vehicles.SizeClass sizeClass, Game.Simulation.RandomTrafficRequestFlags flags);
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


