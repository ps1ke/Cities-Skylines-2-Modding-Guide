# Game.Objects.SpawnLocation

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct SpawnLocation : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_AccessRestriction;
    public Unity.Entities.Entity m_ConnectedLane1;
    public Unity.Entities.Entity m_ConnectedLane2;
    public System.Single m_CurvePosition1;
    public System.Single m_CurvePosition2;
    public System.Int32 m_GroupIndex;
    public Game.Objects.SpawnLocationFlags m_Flags;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_AccessRestriction`  

```csharp
public Unity.Entities.Entity m_AccessRestriction;
```

- `public Unity.Entities.Entity m_ConnectedLane1`  

```csharp
public Unity.Entities.Entity m_ConnectedLane1;
```

- `public Unity.Entities.Entity m_ConnectedLane2`  

```csharp
public Unity.Entities.Entity m_ConnectedLane2;
```

- `public System.Single m_CurvePosition1`  

```csharp
public System.Single m_CurvePosition1;
```

- `public System.Single m_CurvePosition2`  

```csharp
public System.Single m_CurvePosition2;
```

- `public System.Int32 m_GroupIndex`  

```csharp
public System.Int32 m_GroupIndex;
```

- `public Game.Objects.SpawnLocationFlags m_Flags`  

```csharp
public Game.Objects.SpawnLocationFlags m_Flags;
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


