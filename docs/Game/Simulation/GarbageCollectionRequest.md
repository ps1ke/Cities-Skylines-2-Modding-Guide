# Game.Simulation.GarbageCollectionRequest

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct GarbageCollectionRequest : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_Target;
    public System.Int32 m_Priority;
    public Game.Simulation.GarbageCollectionRequestFlags m_Flags;
    public System.Byte m_DispatchIndex;

    public GarbageCollectionRequest(Unity.Entities.Entity target, System.Int32 priority, Game.Simulation.GarbageCollectionRequestFlags flags);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_Target`  

```csharp
public Unity.Entities.Entity m_Target;
```

- `public System.Int32 m_Priority`  

```csharp
public System.Int32 m_Priority;
```

- `public Game.Simulation.GarbageCollectionRequestFlags m_Flags`  

```csharp
public Game.Simulation.GarbageCollectionRequestFlags m_Flags;
```

- `public System.Byte m_DispatchIndex`  

```csharp
public System.Byte m_DispatchIndex;
```


## Constructors

- `public GarbageCollectionRequest(Unity.Entities.Entity target, System.Int32 priority, Game.Simulation.GarbageCollectionRequestFlags flags)`  

```csharp
public GarbageCollectionRequest(Unity.Entities.Entity target, System.Int32 priority, Game.Simulation.GarbageCollectionRequestFlags flags);
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


