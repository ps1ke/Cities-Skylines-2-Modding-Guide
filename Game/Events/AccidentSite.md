# Game.Events.AccidentSite

**Assembly:** `Game`  
**Namespace:** `Game.Events`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct AccidentSite : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_Event;
    public Unity.Entities.Entity m_PoliceRequest;
    public Game.Events.AccidentSiteFlags m_Flags;
    public System.UInt32 m_CreationFrame;
    public System.UInt32 m_SecuredFrame;

    public AccidentSite(Unity.Entities.Entity _event, Game.Events.AccidentSiteFlags flags, System.UInt32 currentFrame);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_Event`  

```csharp
public Unity.Entities.Entity m_Event;
```

- `public Unity.Entities.Entity m_PoliceRequest`  

```csharp
public Unity.Entities.Entity m_PoliceRequest;
```

- `public Game.Events.AccidentSiteFlags m_Flags`  

```csharp
public Game.Events.AccidentSiteFlags m_Flags;
```

- `public System.UInt32 m_CreationFrame`  

```csharp
public System.UInt32 m_CreationFrame;
```

- `public System.UInt32 m_SecuredFrame`  

```csharp
public System.UInt32 m_SecuredFrame;
```


## Constructors

- `public AccidentSite(Unity.Entities.Entity _event, Game.Events.AccidentSiteFlags flags, System.UInt32 currentFrame)`  

```csharp
public AccidentSite(Entity _event, AccidentSiteFlags flags, uint currentFrame)
	{
		m_Event = _event;
		m_PoliceRequest = Entity.Null;
		m_Flags = flags;
		m_CreationFrame = currentFrame;
		m_SecuredFrame = 0u;
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


