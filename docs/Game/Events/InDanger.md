# Game.Events.InDanger

**Assembly:** `Game`  
**Namespace:** `Game.Events`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct InDanger : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_Event;
    public Unity.Entities.Entity m_EvacuationRequest;
    public Game.Events.DangerFlags m_Flags;
    public System.UInt32 m_EndFrame;

    public InDanger(Unity.Entities.Entity _event, Unity.Entities.Entity evacuationRequest, Game.Events.DangerFlags flags, System.UInt32 endFrame);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_Event`  

```csharp
public Unity.Entities.Entity m_Event;
```

- `public Unity.Entities.Entity m_EvacuationRequest`  

```csharp
public Unity.Entities.Entity m_EvacuationRequest;
```

- `public Game.Events.DangerFlags m_Flags`  

```csharp
public Game.Events.DangerFlags m_Flags;
```

- `public System.UInt32 m_EndFrame`  

```csharp
public System.UInt32 m_EndFrame;
```


## Constructors

- `public InDanger(Unity.Entities.Entity _event, Unity.Entities.Entity evacuationRequest, Game.Events.DangerFlags flags, System.UInt32 endFrame)`  

```csharp
public InDanger(Unity.Entities.Entity _event, Unity.Entities.Entity evacuationRequest, Game.Events.DangerFlags flags, System.UInt32 endFrame);
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


