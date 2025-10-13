# Game.Net.Bottleneck

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct Bottleneck : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public System.Byte m_Position;
    public System.Byte m_MinPos;
    public System.Byte m_MaxPos;
    public System.Byte m_Timer;

    public Bottleneck(System.Byte minPos, System.Byte maxPos, System.Byte timer);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Byte m_Position`  

```csharp
public System.Byte m_Position;
```

- `public System.Byte m_MinPos`  

```csharp
public System.Byte m_MinPos;
```

- `public System.Byte m_MaxPos`  

```csharp
public System.Byte m_MaxPos;
```

- `public System.Byte m_Timer`  

```csharp
public System.Byte m_Timer;
```


## Constructors

- `public Bottleneck(System.Byte minPos, System.Byte maxPos, System.Byte timer)`  

```csharp
public Bottleneck(byte minPos, byte maxPos, byte timer)
	{
		m_Position = (byte)(minPos + maxPos + 1 >> 1);
		m_MinPos = minPos;
		m_MaxPos = maxPos;
		m_Timer = timer;
	}
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


