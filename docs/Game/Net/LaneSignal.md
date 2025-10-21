# Game.Net.LaneSignal

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct LaneSignal : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_Petitioner;
    public Unity.Entities.Entity m_Blocker;
    public System.UInt16 m_GroupMask;
    public System.SByte m_Priority;
    public System.SByte m_Default;
    public Game.Net.LaneSignalType m_Signal;
    public Game.Net.LaneSignalFlags m_Flags;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_Petitioner`  

```csharp
public Unity.Entities.Entity m_Petitioner;
```

- `public Unity.Entities.Entity m_Blocker`  

```csharp
public Unity.Entities.Entity m_Blocker;
```

- `public System.UInt16 m_GroupMask`  

```csharp
public System.UInt16 m_GroupMask;
```

- `public System.SByte m_Priority`  

```csharp
public System.SByte m_Priority;
```

- `public System.SByte m_Default`  

```csharp
public System.SByte m_Default;
```

- `public Game.Net.LaneSignalType m_Signal`  

```csharp
public Game.Net.LaneSignalType m_Signal;
```

- `public Game.Net.LaneSignalFlags m_Flags`  

```csharp
public Game.Net.LaneSignalFlags m_Flags;
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


