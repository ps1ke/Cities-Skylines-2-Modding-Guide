# Game.City.ServiceFee

**Assembly:** `Game`  
**Namespace:** `Game.City`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct ServiceFee : Unity.Entities.IBufferElementData, Colossal.Serialization.Entities.ISerializable
{
    public Game.City.PlayerResource m_Resource;
    public System.Single m_Fee;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Single GetDefaultFee(Game.City.PlayerResource resource);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.City.PlayerResource m_Resource`  

```csharp
public Game.City.PlayerResource m_Resource;
```

- `public System.Single m_Fee`  

```csharp
public System.Single m_Fee;
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public GetDefaultFee(Game.City.PlayerResource resource) : System.Single`  

```csharp
public float GetDefaultFee(PlayerResource resource)
	{
		return resource switch
		{
			PlayerResource.BasicEducation => 100f, 
			PlayerResource.SecondaryEducation => 200f, 
			PlayerResource.HigherEducation => 300f, 
			PlayerResource.Healthcare => 100f, 
			PlayerResource.Garbage => 0.1f, 
			PlayerResource.Electricity => 0.2f, 
			PlayerResource.Water => 0.1f, 
			_ => 0f, 
		};
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


