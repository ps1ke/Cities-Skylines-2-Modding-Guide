# Game.Policies.Policy

**Assembly:** `Game`  
**Namespace:** `Game.Policies`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct Policy : Unity.Entities.IBufferElementData, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_Policy;
    public Game.Policies.PolicyFlags m_Flags;
    public System.Single m_Adjustment;

    public Policy(Unity.Entities.Entity policy, Game.Policies.PolicyFlags flags, System.Single adjustment);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_Policy`  

```csharp
public Unity.Entities.Entity m_Policy;
```

- `public Game.Policies.PolicyFlags m_Flags`  

```csharp
public Game.Policies.PolicyFlags m_Flags;
```

- `public System.Single m_Adjustment`  

```csharp
public System.Single m_Adjustment;
```


## Constructors

- `public Policy(Unity.Entities.Entity policy, Game.Policies.PolicyFlags flags, System.Single adjustment)`  

```csharp
public Policy(Entity policy, PolicyFlags flags, float adjustment)
	{
		m_Policy = policy;
		m_Flags = flags;
		m_Adjustment = adjustment;
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


