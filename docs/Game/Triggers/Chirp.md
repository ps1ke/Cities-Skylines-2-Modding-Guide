# Game.Triggers.Chirp

**Assembly:** `Game`  
**Namespace:** `Game.Triggers`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct Chirp : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_Sender;
    public System.UInt32 m_CreationFrame;
    public System.UInt32 m_Likes;
    public System.UInt32 m_TargetLikes;
    public System.UInt32 m_InactiveFrame;
    public System.Int32 m_ViralFactor;
    public System.Single m_ContinuousFactor;
    public Game.Triggers.ChirpFlags m_Flags;

    public Chirp(Unity.Entities.Entity sender, System.UInt32 creationFrame);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_Sender`  

```csharp
public Unity.Entities.Entity m_Sender;
```

- `public System.UInt32 m_CreationFrame`  

```csharp
public System.UInt32 m_CreationFrame;
```

- `public System.UInt32 m_Likes`  

```csharp
public System.UInt32 m_Likes;
```

- `public System.UInt32 m_TargetLikes`  

```csharp
public System.UInt32 m_TargetLikes;
```

- `public System.UInt32 m_InactiveFrame`  

```csharp
public System.UInt32 m_InactiveFrame;
```

- `public System.Int32 m_ViralFactor`  

```csharp
public System.Int32 m_ViralFactor;
```

- `public System.Single m_ContinuousFactor`  

```csharp
public System.Single m_ContinuousFactor;
```

- `public Game.Triggers.ChirpFlags m_Flags`  

```csharp
public Game.Triggers.ChirpFlags m_Flags;
```


## Constructors

- `public Chirp(Unity.Entities.Entity sender, System.UInt32 creationFrame)`  

```csharp
public Chirp(Unity.Entities.Entity sender, System.UInt32 creationFrame);
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


