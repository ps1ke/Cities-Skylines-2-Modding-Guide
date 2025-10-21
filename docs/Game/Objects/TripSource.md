# Game.Objects.TripSource

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct TripSource : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_Source;
    public System.Int32 m_Timer;

    public TripSource(Unity.Entities.Entity source);
    public TripSource(Unity.Entities.Entity source, System.UInt32 delay);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_Source`  

```csharp
public Unity.Entities.Entity m_Source;
```

- `public System.Int32 m_Timer`  

```csharp
public System.Int32 m_Timer;
```


## Constructors

- `public TripSource(Unity.Entities.Entity source)`  

```csharp
public TripSource(Unity.Entities.Entity source);
```

- `public TripSource(Unity.Entities.Entity source, System.UInt32 delay)`  

```csharp
public TripSource(Unity.Entities.Entity source, System.UInt32 delay);
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


