# Game.Citizens.Criminal

**Assembly:** `Game`  
**Namespace:** `Game.Citizens`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct Criminal : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_Event;
    public System.UInt16 m_JailTime;
    public Game.Citizens.CriminalFlags m_Flags;

    public Criminal(Unity.Entities.Entity _event, Game.Citizens.CriminalFlags flags);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_Event`  

```csharp
public Unity.Entities.Entity m_Event;
```

- `public System.UInt16 m_JailTime`  

```csharp
public System.UInt16 m_JailTime;
```

- `public Game.Citizens.CriminalFlags m_Flags`  

```csharp
public Game.Citizens.CriminalFlags m_Flags;
```


## Constructors

- `public Criminal(Unity.Entities.Entity _event, Game.Citizens.CriminalFlags flags)`  

```csharp
public Criminal(Entity _event, CriminalFlags flags)
	{
		m_Event = _event;
		m_JailTime = 0;
		m_Flags = flags;
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


