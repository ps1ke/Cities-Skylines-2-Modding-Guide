# Game.Citizens.MailSender

**Assembly:** `Game`  
**Namespace:** `Game.Citizens`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`, `Unity.Entities.IEnableableComponent`  

## Code

```csharp
public sealed struct MailSender : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable, Unity.Entities.IEnableableComponent
{
    public System.UInt16 m_Amount;

    public MailSender(System.UInt16 amount);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.UInt16 m_Amount`  

```csharp
public System.UInt16 m_Amount;
```


## Constructors

- `public MailSender(System.UInt16 amount)`  

```csharp
public MailSender(ushort amount)
	{
		m_Amount = amount;
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


