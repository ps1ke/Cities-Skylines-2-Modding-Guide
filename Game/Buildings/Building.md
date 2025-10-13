# Game.Buildings.Building

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct Building : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_RoadEdge;
    public System.Single m_CurvePosition;
    public System.UInt32 m_OptionMask;
    public Game.Buildings.BuildingFlags m_Flags;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_RoadEdge`  

```csharp
public Unity.Entities.Entity m_RoadEdge;
```

- `public System.Single m_CurvePosition`  

```csharp
public System.Single m_CurvePosition;
```

- `public System.UInt32 m_OptionMask`  

```csharp
public System.UInt32 m_OptionMask;
```

- `public Game.Buildings.BuildingFlags m_Flags`  

```csharp
public Game.Buildings.BuildingFlags m_Flags;
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


