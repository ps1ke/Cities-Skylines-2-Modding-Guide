# Game.Buildings.GarbageProducer

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct GarbageProducer : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_CollectionRequest;
    public System.Int32 m_Garbage;
    public Game.Buildings.GarbageProducerFlags m_Flags;
    public System.Byte m_DispatchIndex;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_CollectionRequest`  

```csharp
public Unity.Entities.Entity m_CollectionRequest;
```

- `public System.Int32 m_Garbage`  

```csharp
public System.Int32 m_Garbage;
```

- `public Game.Buildings.GarbageProducerFlags m_Flags`  

```csharp
public Game.Buildings.GarbageProducerFlags m_Flags;
```

- `public System.Byte m_DispatchIndex`  

```csharp
public System.Byte m_DispatchIndex;
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


