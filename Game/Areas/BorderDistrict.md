# Game.Areas.BorderDistrict

**Assembly:** `Game`  
**Namespace:** `Game.Areas`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct BorderDistrict : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_Left;
    public Unity.Entities.Entity m_Right;

    public BorderDistrict(Unity.Entities.Entity left, Unity.Entities.Entity right);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_Left`  

```csharp
public Unity.Entities.Entity m_Left;
```

- `public Unity.Entities.Entity m_Right`  

```csharp
public Unity.Entities.Entity m_Right;
```


## Constructors

- `public BorderDistrict(Unity.Entities.Entity left, Unity.Entities.Entity right)`  

```csharp
public BorderDistrict(Entity left, Entity right)
	{
		m_Left = left;
		m_Right = right;
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


