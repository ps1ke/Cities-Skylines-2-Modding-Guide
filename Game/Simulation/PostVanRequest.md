# Game.Simulation.PostVanRequest

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct PostVanRequest : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_Target;
    public Game.Simulation.PostVanRequestFlags m_Flags;
    public System.Byte m_DispatchIndex;
    public System.UInt16 m_Priority;

    public PostVanRequest(Unity.Entities.Entity target, Game.Simulation.PostVanRequestFlags flags, System.UInt16 priority);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_Target`  

```csharp
public Unity.Entities.Entity m_Target;
```

- `public Game.Simulation.PostVanRequestFlags m_Flags`  

```csharp
public Game.Simulation.PostVanRequestFlags m_Flags;
```

- `public System.Byte m_DispatchIndex`  

```csharp
public System.Byte m_DispatchIndex;
```

- `public System.UInt16 m_Priority`  

```csharp
public System.UInt16 m_Priority;
```


## Constructors

- `public PostVanRequest(Unity.Entities.Entity target, Game.Simulation.PostVanRequestFlags flags, System.UInt16 priority)`  

```csharp
public PostVanRequest(Entity target, PostVanRequestFlags flags, ushort priority)
	{
		m_Target = target;
		m_Flags = flags;
		m_Priority = priority;
		m_DispatchIndex = 0;
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


