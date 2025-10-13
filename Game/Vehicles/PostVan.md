# Game.Vehicles.PostVan

**Assembly:** `Game`  
**Namespace:** `Game.Vehicles`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct PostVan : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_TargetRequest;
    public Game.Vehicles.PostVanFlags m_State;
    public System.Int32 m_RequestCount;
    public System.Single m_PathElementTime;
    public System.Int32 m_DeliveringMail;
    public System.Int32 m_CollectedMail;
    public System.Int32 m_DeliveryEstimate;
    public System.Int32 m_CollectEstimate;

    public PostVan(Game.Vehicles.PostVanFlags flags, System.Int32 requestCount, System.Int32 deliveringMail);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_TargetRequest`  

```csharp
public Unity.Entities.Entity m_TargetRequest;
```

- `public Game.Vehicles.PostVanFlags m_State`  

```csharp
public Game.Vehicles.PostVanFlags m_State;
```

- `public System.Int32 m_RequestCount`  

```csharp
public System.Int32 m_RequestCount;
```

- `public System.Single m_PathElementTime`  

```csharp
public System.Single m_PathElementTime;
```

- `public System.Int32 m_DeliveringMail`  

```csharp
public System.Int32 m_DeliveringMail;
```

- `public System.Int32 m_CollectedMail`  

```csharp
public System.Int32 m_CollectedMail;
```

- `public System.Int32 m_DeliveryEstimate`  

```csharp
public System.Int32 m_DeliveryEstimate;
```

- `public System.Int32 m_CollectEstimate`  

```csharp
public System.Int32 m_CollectEstimate;
```


## Constructors

- `public PostVan(Game.Vehicles.PostVanFlags flags, System.Int32 requestCount, System.Int32 deliveringMail)`  

```csharp
public PostVan(PostVanFlags flags, int requestCount, int deliveringMail)
	{
		m_TargetRequest = Entity.Null;
		m_State = flags;
		m_RequestCount = requestCount;
		m_PathElementTime = 0f;
		m_DeliveringMail = deliveringMail;
		m_CollectedMail = 0;
		m_DeliveryEstimate = 0;
		m_CollectEstimate = 0;
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


