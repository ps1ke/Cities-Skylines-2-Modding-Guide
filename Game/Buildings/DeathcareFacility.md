# Game.Buildings.DeathcareFacility

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct DeathcareFacility : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_TargetRequest;
    public Game.Buildings.DeathcareFacilityFlags m_Flags;
    public System.Single m_ProcessingState;
    public System.Int32 m_LongTermStoredCount;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_TargetRequest`  

```csharp
public Unity.Entities.Entity m_TargetRequest;
```

- `public Game.Buildings.DeathcareFacilityFlags m_Flags`  

```csharp
public Game.Buildings.DeathcareFacilityFlags m_Flags;
```

- `public System.Single m_ProcessingState`  

```csharp
public System.Single m_ProcessingState;
```

- `public System.Int32 m_LongTermStoredCount`  

```csharp
public System.Int32 m_LongTermStoredCount;
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


