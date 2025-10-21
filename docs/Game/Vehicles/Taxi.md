# Game.Vehicles.Taxi

**Assembly:** `Game`  
**Namespace:** `Game.Vehicles`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct Taxi : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_TargetRequest;
    public Game.Vehicles.TaxiFlags m_State;
    public System.Single m_PathElementTime;
    public System.Single m_StartDistance;
    public System.Single m_MaxBoardingDistance;
    public System.Single m_MinWaitingDistance;
    public System.Int32 m_ExtraPathElementCount;
    public System.UInt16 m_NextStartingFee;
    public System.UInt16 m_CurrentFee;

    public Taxi(Game.Vehicles.TaxiFlags flags);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_TargetRequest`  

```csharp
public Unity.Entities.Entity m_TargetRequest;
```

- `public Game.Vehicles.TaxiFlags m_State`  

```csharp
public Game.Vehicles.TaxiFlags m_State;
```

- `public System.Single m_PathElementTime`  

```csharp
public System.Single m_PathElementTime;
```

- `public System.Single m_StartDistance`  

```csharp
public System.Single m_StartDistance;
```

- `public System.Single m_MaxBoardingDistance`  

```csharp
public System.Single m_MaxBoardingDistance;
```

- `public System.Single m_MinWaitingDistance`  

```csharp
public System.Single m_MinWaitingDistance;
```

- `public System.Int32 m_ExtraPathElementCount`  

```csharp
public System.Int32 m_ExtraPathElementCount;
```

- `public System.UInt16 m_NextStartingFee`  

```csharp
public System.UInt16 m_NextStartingFee;
```

- `public System.UInt16 m_CurrentFee`  

```csharp
public System.UInt16 m_CurrentFee;
```


## Constructors

- `public Taxi(Game.Vehicles.TaxiFlags flags)`  

```csharp
public Taxi(Game.Vehicles.TaxiFlags flags);
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


