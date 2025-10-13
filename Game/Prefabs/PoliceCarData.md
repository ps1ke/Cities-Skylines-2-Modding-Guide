# Game.Prefabs.PoliceCarData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct PoliceCarData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public System.Int32 m_CriminalCapacity;
    public System.Single m_CrimeReductionRate;
    public System.UInt32 m_ShiftDuration;
    public Game.Prefabs.PolicePurpose m_PurposeMask;

    public PoliceCarData(System.Int32 criminalCapacity, System.Single crimeReductionRate, System.UInt32 shiftDuration, Game.Prefabs.PolicePurpose purposeMask);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Int32 m_CriminalCapacity`  

```csharp
public System.Int32 m_CriminalCapacity;
```

- `public System.Single m_CrimeReductionRate`  

```csharp
public System.Single m_CrimeReductionRate;
```

- `public System.UInt32 m_ShiftDuration`  

```csharp
public System.UInt32 m_ShiftDuration;
```

- `public Game.Prefabs.PolicePurpose m_PurposeMask`  

```csharp
public Game.Prefabs.PolicePurpose m_PurposeMask;
```


## Constructors

- `public PoliceCarData(System.Int32 criminalCapacity, System.Single crimeReductionRate, System.UInt32 shiftDuration, Game.Prefabs.PolicePurpose purposeMask)`  

```csharp
public PoliceCarData(int criminalCapacity, float crimeReductionRate, uint shiftDuration, PolicePurpose purposeMask)
	{
		m_CriminalCapacity = criminalCapacity;
		m_CrimeReductionRate = crimeReductionRate;
		m_ShiftDuration = shiftDuration;
		m_PurposeMask = purposeMask;
	}
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


