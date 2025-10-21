# Game.Net.SlaveLane

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct SlaveLane : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Game.Net.SlaveLaneFlags m_Flags;
    public System.UInt32 m_Group;
    public System.UInt16 m_MinIndex;
    public System.UInt16 m_MaxIndex;
    public System.UInt16 m_SubIndex;
    public System.UInt16 m_MasterIndex;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.Net.SlaveLaneFlags m_Flags`  

```csharp
public Game.Net.SlaveLaneFlags m_Flags;
```

- `public System.UInt32 m_Group`  

```csharp
public System.UInt32 m_Group;
```

- `public System.UInt16 m_MinIndex`  

```csharp
public System.UInt16 m_MinIndex;
```

- `public System.UInt16 m_MaxIndex`  

```csharp
public System.UInt16 m_MaxIndex;
```

- `public System.UInt16 m_SubIndex`  

```csharp
public System.UInt16 m_SubIndex;
```

- `public System.UInt16 m_MasterIndex`  

```csharp
public System.UInt16 m_MasterIndex;
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


